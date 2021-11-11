---
description: >-
  The KeyValues format is used in the Source engine to store meta data for
  resources, scripts, materials, VGUI elements, and more.
---

# KeyValues

## File Format

The KeyValues format is used in the Source engine to store meta data for resources, scripts, materials, VGUI elements, and more. The KeyValues.h header in the Source SDK code defines the file format in the following manner

### About KeyValues Text File Format:

* It has 3 control characters **{**, **}** and **"**. Names and values may be quoted or not. The quote **"** character must not be used within name or values, only for quoting whole tokens. You may use escape sequences while parsing and add within a quoted token a **\\"** to add quotes within your name or token.
* When using Escape Sequences, the parser must know that by setting **KeyValues::UsesEscapeSequences( true )**, which is off by default.
* Non-quoted tokens ends with a whitespace, **{**, **}** and **"**. So you may use **{** and **}** within quoted tokens, but not for non-quoted tokens.
* An open bracket **{** after a key name indicates a list of subkeys which is finished with a closing bracket **}**. Subkeys use the same definitions recursively.
* Whitespaces are space, return, newline and tabulator. Allowed Escape sequences are **\n**, **\t**, **\\\\**, and **\\"**.
* The number character **#** is used for macro purposes (eg #include), don't use it as first character in key names.

\
Please note that the above is only an informal description of the format. It is not a definitive guide for how the format should be interpreted by parsers. It has not been tested whether the KeyValues parser in the Source SDK Code parses exactly as according to the above. The KeyValues parser might not handle very long keyvalues correctly.

It appears from the source code that:

*   You can use include statements in keyvalues scripts to include other text files.

    ```
    #include "file path"
    ```

    You can also use the base statement that appears to do the exact same thing.

    ```
    #base "file path"
    ```

{% hint style="warning" %}
&#x20;**Bug:** It appears that the #include statement does not work. The #base statement does work, and actually acts as you would expect from a typical include command: it reads the file and creates the controls as children of the panel that called the include statement.
{% endhint %}

**Example:** Say you want to include **panelBase.res** in your resource file called **specificPanel.res**. You would then write the following:

```
"#base" "panelBase.res"

"Resource/specificPanel.res"
{
	// Specify panel-specific controls here
}
```

* The file format specification allows for C++ style comments. However, the implementation of this in Valve's Key-Value code is poor, and assumes anything following a single forward slash is a comment.

```
// This is a comment until the line ends
/ This is also a comment until the line ends
```

* &#x20;EDIT : This does not appear to be the case (Refer [this](https://github.com/ValveSoftware/source-sdk-2013/blob/master/sp/src/tier1/utlbuffer.cpp#L406) or codeblock bellow).

```
bool CUtlBuffer::EatCPPComment()
{
	if ( IsText() && IsValid() )
	{
		// If we don't have a a c++ style comment next, we're done
		const char *pPeek = (const char *)PeekGet( 2 * sizeof(char), 0 );
		if ( !pPeek || ( pPeek[0] != '/' ) || ( pPeek[1] != '/' ) )
			return false;

		// Deal with c++ style comments
		m_Get += 2;

		// read complete line
		for ( char c = GetChar(); IsValid(); c = GetChar() )
		{
			if ( c == '\n' )
				break;
		}
		return true;
	}
	return false;
}
```

*   There is no support for block comments, and if contained in a single line, they will eliminate everything after them (due to being treated as a single-line comment).

    ```
    /* This is an inline comment, which will not work in this file format. */ "this_pair_is_ignored" "true"
    ```
* You can use conditional statements that will be ignored if non true, this will work on any key value and its children. If you prepend a key value statement with a `[$X360]` token or a `[$WIN32]` token it will be ignored depending on the platform in use. Since we have the source code for the keyvalues parser, you might be able to create your own conditional statements.
* Each token can be up to 1024 characters long (including null-termination, and double quotes, that will leave room for 1021 actual characters). Note that some functions in the KeyValues class will not handle strings with over 256 characters correctly. Searching for a key name over 256 characters containing a '/' causes a buffer overrun on the stack in the `KeyValues::FindKey` function.

## Definition

**The KeyValues class** handles data buffer input, file input, and file output.

A KeyValue is defined recursively as a named key either with a value or children. All keys have names set to them and a search can be performed by the names. If a KeyValue is a parent key, it contains other KeyValues.

### Value Types

{% hint style="info" %}
&#x20;**Note:**The KeyValue type gets set automatically when a set value function (i.e. `SetFloat`) is called.
{% endhint %}

* `TYPE_NONE`
* `TYPE_STRING`
* `TYPE_INT`
* `TYPE_FLOAT`
* `TYPE_PTR`
* `TYPE_WSTRING`
* `TYPE_COLOR`

### Example

```
"ParentKey1"
{
	"ValueKey1"	"1"
	"ParentKey2"
	{
		...
	}
}
```

## Important Notes

* It is important to note that you must include filesystem.h. Not doing this will result in the inability to reliably call LoadFromFile and SaveToFile. Symptoms are crashes in datastore.dll or a fail-state.
* SaveToFile will not save any keyvalues whose value string is empty, although these can be loaded without any problems.
* In `tier1/KeyValues.cpp`, uncomment this line to hit the \~CLeakTrack assert to see what's looking like it's leaking

```
// #define LEAKTRACK
```

* When you have completed using a KeyValues object, if you are unsure, check if is NULL and if not, call the object's `deleteThis` function.
* If you, or any code utilizing the KeyValues object, fail to delete your KeyValues objects, you will end up with memory leaks.
* Many instances of the usage of the KeyValues in the SDK do not call their `deleteThis` function, therefore making memory leaks.

### CLeakTrack

This class is in `tier1/KeyValues.cpp`.

Replacing the deconstructor for the CLeakTrack class can help you stomp out KeyValues leaks when the engine shuts down.

```
	~CLeakTrack()
	{
		AssertMsg ( keys.Count() == 0, VarArgs("keys.Count() is %i",keys.Count()) );

		for(int x=0;x<keys.Count();x++)
		{
			keys[x].kv->deleteThis();
			keys.Remove(x);
		}
	}
```

When you do this in debug build, you should get told how many leaks you get when you shutdown the game. This number may vary for the amount of activity done within the game.

Although this modification can remove all leaked memory, it should not be relied on to take care of them. Some memory leaks are caused by the engine, so this is a last resort for those kinds of leaks.

### Example

```
ComboBox *pCombo = new ComboBox(...);
pCombo->AddItem("Text", new KeyValues("UserData", "Key", "Value"));
```

It's important to note that if you were to follow what is called by the AddItem function, you would see that the UserData KeyValues are copied, rather than used directly. Copying KeyValues is a common source of confusion of how your KeyValues objects are used, so make sure to follow where they go. If you are unsure, you could try calling the `deleteThis` function and see if the same functionality as before still exists.

### Fix

```
ComboBox *pCombo = new ComboBox(...);
KeyValues *kv = new KeyValues("UserData", "Key", "Value");
pCombo->AddItem("Text", kv);
kv->deleteThis();
```

## What not to do

```
ComboBox *pCombo = new ComboBox(...);
pCombo->AddItem("Text", new KeyValues("UserData", "Key", "Value"));
```

```
Button *pButton = new Button(...);
KeyValues *kv = new KeyValues("ButtonCommand");
pButton->SetCommand(kv);
kv->deleteThis();
```

## Useful Traverses

The following loops are contained in the following function: `void Traverse(KeyValues *pKV);`

### All Subkeys

```
for ( KeyValues *sub = pKV->GetFirstSubKey(); sub; sub = sub->GetNextKey() )
```

This loop steps through all subkeys contained in pKV.To handle subkeys with their own subkeys in pKV, you may want use a recursive loop. To check if a subkey has subkeys, do the following:

```
if(sub->GetFirstSubKey())
{
	Traverse(sub);
}
```

### All Values

```
for ( KeyValues *sub = pKV->GetFirstValue(); sub; sub = sub->GetNextValue() )
```

This loop steps through all subkeys contained in a pKV that have values.It is also valid to use the KeyValues member function `GetDataType` in the loop to do a type specific traverse.

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/KeyValues](https://developer.valvesoftware.com/wiki/KeyValues)
{% endhint %}







