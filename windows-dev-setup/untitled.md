# Basics

## Software and tools

### Windows Terminal

Go to Microsoft Store and install Windows Terminal.

### Windows Package Manager - Chocolatey

* Go to [https://chocolatey.org/install](https://chocolatey.org/install)
* Open Windows Terminal as admin:

{% tabs %}
{% tab title="Run" %}
```csharp
Set-ExecutionPolicy AllSigned
Get-ExecutionPolicy
```
{% endtab %}

{% tab title="Output" %}
```

AllSigned
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Run" %}
```csharp
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
{% endtab %}

{% tab title="Output" %}
```
Getting latest version of the Chocolatey package for download.
Getting Chocolatey from https://chocolatey.org/api/v2/package/chocolatey/0.10.15.
Downloading 7-Zip commandline tool prior to extraction.
Extracting C:\Users\Laptop\AppData\Local\Temp\chocolatey\chocInstall\chocolatey.zip to C:\Users\Laptop\AppData\Local\Temp\chocolatey\chocInstall...
Installing chocolatey on this machine
  Setting ChocolateyInstall to 'C:\ProgramData\chocolatey'
WARNING: It's very likely you will need to close and reopen your shell
  before you can use choco.
Restricting write permissions to Administrators
We are setting up the Chocolatey package repository.
The packages themselves go to 'C:\ProgramData\chocolatey\lib'
  (i.e. C:\ProgramData\chocolatey\lib\yourPackageName).
A shim file for the command line goes to 'C:\ProgramData\chocolatey\bin'
  and points to an executable in 'C:\ProgramData\chocolatey\lib\yourPackageName'.

Creating Chocolatey folders if they do not already exist.

WARNING: You can safely ignore errors related to missing log files when
  upgrading from a version of Chocolatey less than 0.9.9.
  'Batch file could not be found' is also safe to ignore.
  'The system cannot find the file specified' - also safe.
chocolatey.nupkg file not installed in lib.
 Attempting to locate it from bootstrapper.
PATH environment variable does not have C:\ProgramData\chocolatey\bin in it. Adding...
WARNING: Not setting tab completion: Profile file does not exist at
'C:\Users\Laptop\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1'.
Chocolatey (choco.exe) is now ready.
You can call choco from anywhere, command line or powershell by typing choco.
Run choco /? for a list of functions.
You may need to shut down and restart powershell and/or consoles
 first prior to using choco.
Ensuring chocolatey commands are on the path
Ensuring chocolatey.nupkg is in the lib folder
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Run" %}
```csharp
choco
```
{% endtab %}

{% tab title="Output" %}
```
Chocolatey v0.10.15
Please run 'choco -?' or 'choco <command> -?' for help menu.
```
{% endtab %}
{% endtabs %}

### Browsers

* Chrome
* Firefox
* Firefox Dev

### Tools

* [notepadplusplus](../cool-stuff/notepad++-customization.md) 🚀
* greenshot

{% tabs %}
{% tab title="Run" %}
```csharp
choco install googlechrome firefox notepadplusplus
```
{% endtab %}
{% endtabs %}

{% embed url="https://www.mozilla.org/en-US/firefox/developer/" %}



## Make Backup of installed choco packages for re-use

{% tabs %}
{% tab title="Run" %}
```text
choco install choco-package-list-backup
```
{% endtab %}
{% endtabs %}

This will create a folder under _`C:\Users\<username>\Documents\ChocolateyPackageListBackup`_ with 3 files: 

* **AllProgramsList** - a list of all installed Windows programs \(by Chocolatey or not\)
* **choco-package-list-backup.config** - to customize your backups
* **packages.config** - a list of all installed Windows programs _**by Chocolatey**_

### _**To re-install your Chocolatey packages:**_

1. _Open **Windows Terminal** as admin_
2. _Navigate to ****C:\Users\**&lt;username&gt;**\Documents\ChocolateyPackageListBackup_
3. _Run:_ ****`CHOCO INSTALL PACKAGES.CONFIG -Y`

{% hint style="info" %}
_The list of packages I installed  you can download from   &lt;link&gt;_
{% endhint %}

## WSL2 and Ubuntu

To be able to run Ubuntu under Windows, first we need to enable [_**Windows Subsystem for Linux**_ _\(WSL2\)_](../cool-stuff/untitled.md)_:_

![](../.gitbook/assets/image%20%2814%29.png)

![](../.gitbook/assets/image%20%2813%29.png)

After System reboot, go to Microsoft Store and get Ubuntu 20.04 LTS.

Launch Ubuntu and

* Enter new UNIX username _\(**hint:** to avoid warning regarding regular expression use only lowercase letters\)_
* Enter new password

## Windows Terminal, ZSH and Ubuntu

Open Windows Terminal and in tabs, from the drop-down menu, choose Ubuntu 20.04.

_**First, let's update Ubuntu:**_ 

```text
sudo apt-get update
sudo apt-get upgrade
```

Now, let's install _**Z-shell \(ZSH\):**_

```text
sudo apt-get install zsh
```

To help manage ZSH, let's install [_**Oh My Zsh**_](https://github.com/ohmyzsh/ohmyzsh) _****_by using _**curl command:**_

```text
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

![](../.gitbook/assets/image%20%2815%29.png)

How about customizing our zsh-terminal?

We are going to install [Powerlevel10k](https://github.com/romkatv/powerlevel10k), but first [_Meslo Nerd Font patched for Powerlevel10k_](https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k) _._

When done, under Windows Terminal drop-down menu navigate to Settings and add `"fontFace": "MesloLGS NF"` to your profile**s** like: 

![Adding font style to Windows Terminal config](../.gitbook/assets/image%20%2818%29.png)

_Next,_ we need to install Powerlevel10k itself with these commands:

```text
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>! ~/.zshrc
```

When done, reopen Windows Terminal and you should be presented with Configuration wizard as on the image below

![](../.gitbook/assets/image%20%2817%29.png)

In Ubuntu Terminal type `nano ~/.zshrc` to open zsh config

![Zsh config](../.gitbook/assets/image%20%2816%29.png)

