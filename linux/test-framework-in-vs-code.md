---
description: 'using C#, SpecFlow, NUnit and Selenium WebDriver'
---

# Test framework in VS Code

## Setup

{% hint style="warning" %}
Prerequisites: 

* [x] [VS Code installed](untitled.md)
* [x] [.NET Core SDK installed](untitled.md)
{% endhint %}

## Creating an Automation Test Project in VS Code

#### Step 1: Open terminal in suitable location for the project

#### Step 2: Create a new directory for the project and navigate to it

```bash
mkdir NUnitBDDFramework
```

```bash
cd NUnitBDDFramework
```

#### Step 3: Launch VS Code in the current directory

```bash
code .
```

#### Step 4: In VS Code open integrated _bash_ terminal

#### Step 5: Create a new project with name NUnitBDDProject

```bash
dotnet new nunit --name NUnitBDDProject
```

#### Step 6: Create Solution file with name ProjectSolution 

{% tabs %}
{% tab title="Command" %}
```bash
dotnet new sln --name ProjectSolution
```
{% endtab %}

{% tab title="Output" %}
```

```
{% endtab %}
{% endtabs %}

#### Step 7: Add NUnitBDDProject to ProjectSolution 

{% tabs %}
{% tab title="Command" %}
```bash
dotnet sln add NUnitBDDProject
```
{% endtab %}

{% tab title="Output" %}
    Project `NUnitBDDProject/NUnitBDDProject.csproj` added to the solution.
{% endtab %}
{% endtabs %}

![Until now this is how the framework should look like](../.gitbook/assets/image%20%289%29.png)



