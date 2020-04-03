# Variables and Conditionals

_**Constant**_ is a value that _**cannot be changed.**_ We use constants when we need to ensure that a value does not change.

A variable is a name that represents data stored in memory during program execution. We use variables to store _**temporary values**_ in memory.

| Variable name | Description |
| :--- | :--- |
| **Local variable** | Holds temporary data within the scope of a method. Not a member of a type. |
| **Field** | Holds data associated with a type or an instance of a type. **Member of a type.** |
| **Parameter** | A temporary variable used to pass data from one method to another method. Not a member of a type. |
| **Array element** | One member of a sequenced collection of \(usually\) homogeneous data items. Can be **either local or a member of a type.** |

## **Variable D**eclarations

{% hint style="warning" %}
A variable must be declared before it can be used. 
{% endhint %}

The variable declaration defines the variable and accomplishes two things. • It gives the variable a name and associates a type with it. • It allows the compiler to allocate memory for it. 

A simple variable declaration requires at least a type and a name:

```csharp
int number;     // variable named "number", of value-type integer
```

.. where "number" is _**THE IDENTIFIER**_ for our variable. 

Just declared \(but not initialized\) variable contains **undefined value** until program assigns them a value.

## Variable Initializers

A variable initializer consists of an **equal sign `=`** followed by the **initializing value** so we can use the declaration to initialize its memory to a specific value:

```csharp
int number = 5;    // "= 5" is initializer
```

**Local** variables without initializers have an **undefined value and cannot be used** **until** they have been assigned a value. Attempting to use an undefined local variable causes the compiler to produce an error message.

**Class fields** and **Struct fields**, as variable types, are **automatically initialized** with default value.





















C\# operators tell the computer _**what programmer want to do**_. In other words, operators are _**VERBS**_ and not descriptors. 

The equals symbol **`=`** is called the _**assignment operator** and it takes the value on its **RIGHT** and **stores it i**n the variable on the **LEFT.**_

