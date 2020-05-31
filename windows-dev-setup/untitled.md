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

1. _Open **Windows Terminal - PowerShell** as admin_
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

## Node.js

First we'll install Node Version Manager \(nvm\) under Ubuntu:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```

Open zshconfig and, if not already added, do add these lines at the end of Settings.json file:

```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" #This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion" #This loads nvm bash_completion
```

Or, we can install the nvm [for Zsh](https://github.com/lukechilds/zsh-nvm#manually) plugin, run:

```csharp
git clone https://github.com/lukechilds/zsh-nvm.git ~/.zsh-nvm
source ~/.zsh-nvm/zsh-nvm.plugin.zsh
```

Open **zshconfig** and add **nvm** to plugin list. Save changes, reopen terminal.

To check if installed properly:

{% tabs %}
{% tab title="Run" %}
```csharp
nvm
```
{% endtab %}

{% tab title="Output" %}
```text
Node Version Manager (v0.35.3)

Note: <version> refers to any version-like string nvm understands. This includes:
  - full or partial version numbers, starting with an optional "v" (0.10, v0.1.2, v1)
  - default (built-in) aliases: node, stable, unstable, iojs, system
  - custom aliases you define with `nvm alias foo`

 Any options that produce colorized output should respect the `--no-colors` option.

Usage:
  nvm --help                                Show this message
  nvm --version                             Print out the installed version of nvm
  nvm install [-s] <version>                Download and install a <version>, [-s] from source. Uses .nvmrc if available
    --reinstall-packages-from=<version>     When installing, reinstall packages installed in <node|iojs|node version number>
    --lts                                   When installing, only select from LTS (long-term support) versions
    --lts=<LTS name>                        When installing, only select from versions for a specific LTS line
    --skip-default-packages                 When installing, skip the default-packages file if it exists
    --latest-npm                            After installing, attempt to upgrade to the latest working npm on the given node version
    --no-progress                           Disable the progress bar on any downloads
  nvm uninstall <version>                   Uninstall a version
  nvm uninstall --lts                       Uninstall using automatic LTS (long-term support) alias `lts/*`, if available.
  nvm uninstall --lts=<LTS name>            Uninstall using automatic alias for provided LTS line, if available.
  nvm use [--silent] <version>              Modify PATH to use <version>. Uses .nvmrc if available
    --lts                                   Uses automatic LTS (long-term support) alias `lts/*`, if available.
    --lts=<LTS name>                        Uses automatic alias for provided LTS line, if available.
  nvm exec [--silent] <version> [<command>] Run <command> on <version>. Uses .nvmrc if available
    --lts                                   Uses automatic LTS (long-term support) alias `lts/*`, if available.
    --lts=<LTS name>                        Uses automatic alias for provided LTS line, if available.
  nvm run [--silent] <version> [<args>]     Run `node` on <version> with <args> as arguments. Uses .nvmrc if available
    --lts                                   Uses automatic LTS (long-term support) alias `lts/*`, if available.
    --lts=<LTS name>                        Uses automatic alias for provided LTS line, if available.
  nvm current                               Display currently activated version of Node
  nvm ls [<version>]                        List installed versions, matching a given <version> if provided
    --no-colors                             Suppress colored output
    --no-alias                              Suppress `nvm alias` output
  nvm ls-remote [<version>]                 List remote versions available for install, matching a given <version> if provided
    --lts                                   When listing, only show LTS (long-term support) versions
    --lts=<LTS name>                        When listing, only show versions for a specific LTS line
    --no-colors                             Suppress colored output
  nvm version <version>                     Resolve the given description to a single local version
  nvm version-remote <version>              Resolve the given description to a single remote version
    --lts                                   When listing, only select from LTS (long-term support) versions
    --lts=<LTS name>                        When listing, only select from versions for a specific LTS line
  nvm deactivate                            Undo effects of `nvm` on current shell
  nvm alias [<pattern>]                     Show all aliases beginning with <pattern>
    --no-colors                             Suppress colored output
  nvm alias <name> <version>                Set an alias named <name> pointing to <version>
  nvm unalias <name>                        Deletes the alias named <name>
  nvm install-latest-npm                    Attempt to upgrade to the latest working `npm` on the current node version
  nvm reinstall-packages <version>          Reinstall global `npm` packages contained in <version> to current version
  nvm unload                                Unload `nvm` from shell
  nvm which [current | <version>]           Display path to installed node version. Uses .nvmrc if available
  nvm cache dir                             Display path to the cache directory for nvm
  nvm cache clear                           Empty cache directory for nvm

Example:
  nvm install 8.0.0                     Install a specific version number
  nvm use 8.0                           Use the latest available 8.0.x release
  nvm run 6.10.3 app.js                 Run app.js using node 6.10.3
  nvm exec 4.8.3 node app.js            Run `node app.js` with the PATH pointing to node 4.8.3
  nvm alias default 8.1.0               Set default node version on a shell
  nvm alias default node                Always default to the latest available node version on a shell

Note:
  to remove, delete, or uninstall nvm - just remove the `$NVM_DIR` folder (usually `~/.nvm`)
```
{% endtab %}
{% endtabs %}

