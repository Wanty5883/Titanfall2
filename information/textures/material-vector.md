---
description: >-
  A material vector is a collection of values used with some material commands.
  They most often represent a RGB color.
---

# 矢量材质

A **material vector** is a collection of values used with some [material](valve-material-type-vmt.md) commands. They most often represent a [RGB](colors/#rgb) color.

## 语法

```text
$scale "[1 1]"
$color "[1 1 1]"
$color "{255 255 255}"
$envmaptint "{100 0 58}"
$vec4 "[1 2 3 4]"
```

* Quotes are always required, because there are spaces in the value.
* Values inside `[`square brackets`]` are used as-is, often for [floats](https://developer.valvesoftware.com/wiki/Float) or [normals](https://developer.valvesoftware.com/wiki/Normal). They are [normals](https://developer.valvesoftware.com/wiki/Normal) for colors.
* Values inside `{`curly brackets`}` are divided by 255, so that standard RGB integer 0-255 values can be used.
* Between two to four values can be used, depending on the requirements of the parameter. Listed below:

### **vector2**

A vector with two values.

### **vector3**

A vector with three values.

### **vector4**

A vector with four values.

### 访问

Access an individual component of a material vector like this:

```text
$my_vector[0]
$my_vector[1]
// etc.
```

## 来源和参考

{% hint style="info" %}
Source: [https://developer.valvesoftware.com/wiki/Material\_vector](https://developer.valvesoftware.com/wiki/Material_vector)
{% endhint %}

