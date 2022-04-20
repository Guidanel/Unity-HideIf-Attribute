# 🙈 Unity HideIf Attribute 
## A small Unity Extension that Hide Fields in Editor 
This little code will help you use scripts in Unity faster, more efficiently and more comfortably.

## Attribute Features

### ● **Hide If Bool Value**
```
[HideIf("hideColliderSettings", true)]
public Vector3 size;
```

### ● **Hide If Field is (not) Null**
```
[HideIfNull("target")]
float distanceToTarget;
```
```
[HideIfNotNull("target")]
public string error = "Please, set enemy's target";
```
### ● **Hide If Enum Instance Value Equal/NotEqual to Enum Value**
```
public enum Type : int
   {
       archer,
       warrior,
       mage
   }
    
public Type EnemyType;

[HideIfEnumValue("EnemyType",HideIf.NotEqual, (int) Type.warrior)]
public float swordDamage;

[HideIfEnumValue("EnemyType",HideIf.NotEqual, (int) Type.archer)]
public float arrowDamage;

[HideIfEnumValue("EnemyType",HideIf.NotEqual, (int) Type.mage)]
public float orbDamage;
```
### ● **Will do with other Unity Field Attributes**
```
[HideIfNotNull("textFieldUI")]
[TextArea(1,2)] public string textArea;
```
### ● **And even will do with another HideIf Attribute**
```
[HideIfNull("playerColliders")]
[HideIfEnumValueAttribute("colliderType", HideIf.Equal, (int) Type.Box)]
public float radius;
```
### ● **HideIf Attribute also will affect on Field with {get;set}-property**
```
[HideIfEnumValue("EnemyType",HideIf.Equal, (int) Type.warrior)]
public float projectileSpeed {get; private set;}
```
## Installation
You can just download repository and **move file to Unity Assets folder**. Installation is finished.
## Example
I made a simple [HideIfExample.cs](https://github.com/Stulk3/Unity-HideIf-Attribute/blob/main/HideIfExample.cs) with a demonstration of all attribute features that will be not included in the final build, so it's not necessary to delete.
