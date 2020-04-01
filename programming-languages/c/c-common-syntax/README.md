---
description: Introduction
---

# C\#: Common Syntax

> _C\# program is a related set of **type declarations**._

## Types

Type is a **template** for creating _**data structures.**_  To create new types, C\# programs use _**type declarations.**_  A type declaration specifies following elements:

* a _**Name**_
* a **Data structure**, to contain its _**data members**_
* _**Behaviors**_ and _**constrains**_

_**Instantiating the type**_ is creating an actual object from the type's template:

* The object created by instantiating a type is called either an _**Object** of the type_ or an _**Instance** of the type._
* _Every data item_ is an **instance of some type** provided by: the language; the BCL \(Base Class Library\) or another library; or defined by the programmer.

Types can store:

* **single** data item: _**Simple**_ types
* **multiple** data items of _the same type_ - individual data items are called _**Elements**_ referenced by _number called **an index**_
* **multiple** data items of _many different types_ - individual data items are called _**Members**_ referenced by _names:_
  * _**Data members** - **store data** that is relevant to the object of the class or to the class as a whole_
  * _**Function members - execute code** and define how the type can act_

```csharp
class XYZ 
{
    // data members
    DataMember1
    DataMember2
    
    
    // function members
    Function1()
    {
        ExecutableCode
    }
    
    Function2()
    {
        ExecutableCode
    }
}
```

## Main [categories ](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/types-and-variables)of C\# types

### [_Value types_](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/value-types)\_\_

_Variables_ of value types directly contain **data** of _value types._

### [_Reference types_](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/reference-types)\_\_

_Variables_ of reference types store **references to data** of ****_reference types_ \(known as objects\).

|  | Predefined types | User-defined types |
| :--- | :--- | :--- |
| _**VALUE TYPES**_ | sbyte / byte | struct |
|  | short / ushort | enum |
|  | int / uint |  |
|  | long / ulong |  |
|  | bool |  |

