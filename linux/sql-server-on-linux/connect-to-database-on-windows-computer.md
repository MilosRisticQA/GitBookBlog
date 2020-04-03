---
description: by using VS Code
---

# Connect to Database installed on Windows computer

{% hint style="warning" %}
_**Prerequisites:**_ 

1. _Remote connection between Linux and Windows machine has to be established_
2. _VS Code has to be installed on Linux machine with:_
   1. \_\_[_SQL Server \(mssql\) extension_](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql)\_\_
   2. \_\_[_SQLTools - Database tools extension_](https://marketplace.visualstudio.com/items?itemName=mtxr.sqltools) __
{% endhint %}

## Steps:

### 1. Setting Database engine for a remote connection

#### 1. On Windows machine:

* Open SSMS and _**connect**_ to Database engine
* Under Object Explorer right click on the Database engine name &gt; _**Properties**_
* Under _**Security page**_ make sure for Server authentication that _**"SQL Server and Windows Authentication mode" is checked**_

![](../../.gitbook/assets/image%20%283%29.png)

* Under Connections page **check** _"Allow remote connection to this server"_ **checkbox** and click **OK**

![](../../.gitbook/assets/image%20%284%29.png)

* Under Object Explorer navigate to _**Security &gt; Logins**_
  * right click on targeted _**Login &gt; Properties**_
* Under _**User mapping page**_:
  * for _Users mapped to this login_ section, check _**desired Database**_
  * for _Database role membership for: master_ section, check:
    * _db\_datareader_
    * _db\_datawriter_
    * _**db\_owner**_

![](../../.gitbook/assets/image%20%281%29.png)

* Click OK.

### 2. Setting up Windows for a remote connection

### 3. Connect by using VS Code



