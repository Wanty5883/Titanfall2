# NUT & GNUT-Squirrel游戏语言

## 关于Squirrel

Squirrel is a programming language similar to Lua, but uses a C like syntax. In Source Squirrel is used as one of the scripting languages in the VScript scripting system.

{% hint style="warning" %}
This explains a version of Squirrel suspected to be modified by Respawn. To learn about Squirrel for other, non-Respawn games, check [Squirrel - Valve Developer Community](https://developer.valvesoftware.com/wiki/Squirrel).
{% endhint %}

### 变量

A Varaible can be declared by specifying it's type, then it's name, an equals sign, then it's value, like so:

```csharp
int x = 5;
```

Then, it can be used by typing it's name.

```csharp
printt(x);
```

### 数据类型

There are multiple base data types for Squirrel, and some data types from source.

| 数据类型 | 解释 |
| :--- | :--- |
| bool | A boolean value, true or false. |
| int |  |
| float |  |
| vector | An element with x, y, and z components. |
| array&lt;T&gt; | An array of dynamic value, of type T. |
| struct | A class alternative without functions, explained below. |
| var | Can contain anything, but cannot be used as input to functions with input types that are not 'var'. |
| entity | Is used for anything in the game world, except UI, which should use var, as their type is unknown. |

### 函数和Globalization

Functions are the primary way to execute code. All code that is not a variable deceleration must be inside a function.

Declaration example:

```csharp
// Function syntax is <return type> function functionName(type p1, type p2)
// Function that gives back an int
// This example does NOT work in MP and will return an error.
int function CoolFunction(int x, int y) {
    return x * y + x * x;
}
// function that doesn't return back anything
void function Mod_SetMaxHealth(int newMaxHealth) {
    entity player = GetPlayerArray()[0];
    if (newMaxHealth <= 0) return;
    player.SetMaxHealth(newMaxHealth);
}
```

### 结构体

Structs are used either as a class alternative or for grouping variables in a singleton method.

Declaring example:

{% tabs %}
{% tab title="Declaring a regular struct" %}
```csharp
struct SimpleStruct {
    int x = 5;
    float y = 2.5;
    array<int> z = [7, 8, 9, 10]
}
// Creating a struct is done like declaring a variable;
// First the struct's name, then the variable's name.
// --- EXAMPLE ---
SimpleStruct example;
// Accessing struct properties can be done using a dot after the name of the instance.
// --- EXAMPLE ---
example.x = 6; 
example.y = 3.5;
example.z[0] = 6;
```
{% endtab %}

{% tab title="Declaring a Singleton struct" %}
```csharp
struct {
    int x = 5;
    float y = 2.5;
    array<int> z = [1, 2, 3,
} singletonStruct
// A singleton struct just makes one instance of itself using the name-
// -after it's contents. Unlike a regular struct, the name is inserted-
// -**AFTER** the declaration of the struct's properties.
// Accessing struct properties can be done using a dot after the name of the struct.
// --- EXAMPLE ---
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Sources:

* [https://developer.valvesoftware.com/wiki/Squirrel](https://developer.valvesoftware.com/wiki/Squirrel)
{% endhint %}

