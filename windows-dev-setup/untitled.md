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
* git
* vscode

{% tabs %}
{% tab title="Run" %}
```csharp
choco install googlechrome firefox notepadplusplus greenshot git vscode
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

### _**Z-shell \(ZSH\):**_

How about customizing our terminal to look like

![](../.gitbook/assets/image%20%2820%29.png)

```text
sudo apt-get install zsh
```

To help manage ZSH, let's install [_**Oh My Zsh**_](https://github.com/ohmyzsh/ohmyzsh) _****_by using _**curl command:**_

```text
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

![](../.gitbook/assets/image%20%2815%29.png)

### Powerlevel10k

We are going to install [Powerlevel10k](https://github.com/romkatv/powerlevel10k), but first download and install [_Fira Code Regular Nerd Font Complete Mono Windows Compatible_](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraCode/Regular/complete) __so we can also have nice [ligatures](https://github.com/tonsky/FiraCode/#whats-in-the-box).

When done, under Windows Terminal drop-down menu navigate to Settings and add `"fontFace": "FiraCode NF"` to Settings.json as default setting for all profiles like: 

![](../.gitbook/assets/image%20%2824%29.png)

_Next,_ we need to install **Powerlevel10k** itself with these commands:

```text
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>! ~/.zshrc
```

When done, reopen Windows Terminal and you should be presented with Configuration wizard as on the image below

![](../.gitbook/assets/image%20%2818%29.png)

To make it look just like mine, choose:

* Prompt Style: 3
* Character Set: 1
* Show current time?: 2
* Prompt Separators: 1
* Prompt Heads: 1
* Prompt Tails: 2
* Prompt Height: 1 
* Prompt Spacing: 1
* Icons: 2
* Prompt Flow: 1
* Enable Transient Prompt?: n
* Instant Prompt Mode: 3

### Theme

Of course, we will change the color scheme of out terminal, so do as follows:

* Go to [terminalsplash ](https://terminalsplash.com/)website and choose  _**VSCode Theme for Windows Terminalby:**_ [_adstep_](https://github.com/adstep) __
* Copy _the code_ and paste it into Windows Terminal .json settings file by adding it into _**`// Add custom color schemes to this array.`**_ section, with `"name" : "VSCode",` so you can use it as colorScheme for your profiles, as shown:

![](../.gitbook/assets/image%20%2821%29.png)

And, one final touch should be adding Ubuntu logo gif in the bottom right corner of out terminal.

Download this one and save it with name _**ubuntuLogo.gif**_  to _**C:\Users\Desktop\Pictures\Icons**_ 

![](../.gitbook/assets/ubuntulogo.gif)

Now, simple add these lines to Settings.json file

```text
"backgroundImage" : "C:/Users/Laptop/Pictures/Icons/ubuntuLogo.gif",
"backgroundImageStretchMode" : "none",
"backgroundImageAlignment" : "bottomRight",
"backgroundImageOpacity": 0.7
```

_Note that we've changed backslashes with **forward slashes** for our image location!_

![](../.gitbook/assets/image%20%2825%29.png)

### Plugins

Also, we will need some Oh-My-Zsh plugins, so inside Ubuntu terminal, run these commands:

```text
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

To access .zshrc config from now on we will use _**VSCode**_ as editor so let's install it:

* Open Windows _**PowerShell tab**_ and enter `choco install vscode` 
* Now, back to _**Ubuntu tab**_, type `code ~/.zshrc` 
  * Note: Since this is the first time we're running VSCode, accept _**Remote - WSL extension**_ to be installed.
* add plugins:
  * git
  * zsh-syntax-highlighting
  * zsh-autosuggestions
  * extract  - _extracts file from the archive type of file_
  * colored-man-pages
  * sudo _- adding sudo at the beginning of the line if typed **Esc two times** after the command_
  * history - _shortcut_ **`h`** _will execute history command_
  * npm
* uncomment alias \(by removing \# in front of that line\) and change it to `zshconfig="code ~/.zshrc"`

![](../.gitbook/assets/image%20%2823%29.png)

* Save changes by hitting Ctrl+S.

{% hint style="info" %}
_Notice bottom-left corner of VS Code indicating we're inside Ubuntu over WSL._
{% endhint %}

So, from now on if we want to access to zsh config, we'll just type alias: `zshconfig`

### Colorls

Finally, let make our folders and files listing more cool:

* `sudo apt install ruby-full`

  * ruby dev dependencies:

  ```text
  sudo apt-get install -y build-essential git libreadline-dev
  sudo apt-get install -y libssl-dev zlib1g-dev autoconf libicu-dev
  sudo apt-get install -y git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3
  sudo apt-get install -y libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev
  ```

* restart terminal
* `sudo gem install colorls`
* restart terminal
* `zshconfig` and add lines:
  * at the end of the config file: 
    * source $\(dirname $\(gem which colorls\)\)/tab\_complete.sh
  * under aliases: 
    * alias ls="colorls --gs --tree --group-directories-first"
    * alias ld="colorls --dirs"

![](../.gitbook/assets/image%20%2822%29.png)

{% hint style="info" %}
For other customization related to **colorls** visit [github page](https://github.com/athityakumar/colorls)
{% endhint %}



