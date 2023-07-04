---
title: "Setup Guide"
subtitle: ""
date: 2023-06-23T12:13:57+09:00
draft: false
author: Yu Long
categories: ["setup"]
tags: ["git", "vscode", "iterm", "python", "mysql", "java", "ruby", "node", "go"]
featuredImage: "/images/setup_guide/advanced.gif"
featuredImagePreview: "/images/setup_guide/Windows-Python-Coding-Setup_Watermarked.webp"
hiddenFromHomePage: false
hiddenFromSearch: false
---

Setting up the coding environing is always a obstacle for beginners to start to learn. Hope this post will help you step into the coding world and enjoy it!
<!--more-->


## 1 Homebrew {#homebrew}

Homebew is called the missing package manager for OS X, 

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Search any package you want to install on your local on [Homebrew](https://brew.sh/), check its avaliablity and follow the instrcution to install.


## 2 zsh {#zsh}

[zsh](https://www.zsh.org/)(Z shell) is built on the top of `bash`, but has more advanced features.

```bash
brew install zsh
```

Change the configurations by modifying its config file, 
```bash
vim ~/.zshrc
```

### iTerm2 {#iterm2}
[iTerm2](https://iterm2.com/) is a replacement for terminal.
```bash
brew install --cask iterm2
```

### oh-my-zsh {#oh-my-zsh}
[Oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh) is used as a framework to manage zsh configurations, including themes, plugins...
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
Oh-my-zsh has a lots of themes you can choose, here I use [angnoster](https://github.com/agnoster/agnoster-zsh-theme), which you need to install the [powerline font](https://github.com/powerline/fonts) as a dependency.
Import the following json to setup the iTerm2 profile, 
```json
{
  "Ansi 6 Color" : {
    "Red Component" : 0.16470588235294117,
    "Color Space" : "sRGB",
    "Blue Component" : 0.59607843137254901,
    "Green Component" : 0.63137254901960782
  },
  "Tags" : [

  ],
  "Ansi 12 Color" : {
    "Red Component" : 0.51372549019607838,
    "Color Space" : "sRGB",
    "Blue Component" : 0.58823529411764708,
    "Green Component" : 0.58039215686274515
  },
  "Ansi 7 Color" : {
    "Red Component" : 0.93333333333333335,
    "Color Space" : "sRGB",
    "Blue Component" : 0.83529411764705885,
    "Green Component" : 0.90980392156862744
  },
  "Ansi 8 Color" : {
    "Red Component" : 0.3407056094147265,
    "Color Space" : "sRGB",
    "Blue Component" : 0.352935791015625,
    "Alpha Component" : 1,
    "Green Component" : 0.35044445790185969
  },
  "Bold Color" : {
    "Red Component" : 0.57647058823529407,
    "Color Space" : "sRGB",
    "Blue Component" : 0.63137254901960782,
    "Green Component" : 0.63137254901960782
  },
  "Ansi 9 Color" : {
    "Red Component" : 0.79607843137254897,
    "Color Space" : "sRGB",
    "Blue Component" : 0.086274509803921581,
    "Green Component" : 0.29411764705882354
  },
  "Custom Directory" : "No",
  "Ansi 5 Color" : {
    "Red Component" : 0.82745098039215681,
    "Color Space" : "sRGB",
    "Blue Component" : 0.50980392156862742,
    "Green Component" : 0.21176470588235294
  },
  "Rows" : 25,
  "Default Bookmark" : "No",
  "Cursor Guide Color" : {
    "Red Component" : 0.70213186740875244,
    "Color Space" : "sRGB",
    "Blue Component" : 1,
    "Alpha Component" : 0.25,
    "Green Component" : 0.9268307089805603
  },
  "Non-ASCII Anti Aliased" : true,
  "Use Bright Bold" : true,
  "Ansi 10 Color" : {
    "Red Component" : 0.34509803921568627,
    "Color Space" : "sRGB",
    "Blue Component" : 0.45882352941176469,
    "Green Component" : 0.43137254901960786
  },
  "Ambiguous Double Width" : false,
  "Jobs to Ignore" : [
    "rlogin",
    "ssh",
    "slogin",
    "telnet"
  ],
  "Ansi 15 Color" : {
    "Red Component" : 0.99215686274509807,
    "Color Space" : "sRGB",
    "Blue Component" : 0.8901960784313725,
    "Green Component" : 0.96470588235294119
  },
  "Foreground Color" : {
    "Red Component" : 0.51372549019607838,
    "Color Space" : "sRGB",
    "Blue Component" : 0.58823529411764708,
    "Green Component" : 0.58039215686274515
  },
  "Bound Hosts" : [

  ],
  "Working Directory" : "\/Users\/yu.long",
  "Blinking Cursor" : false,
  "Disable Window Resizing" : true,
  "Sync Title" : false,
  "Prompt Before Closing 2" : false,
  "BM Growl" : true,
  "Command" : "",
  "Description" : "Default",
  "Mouse Reporting" : true,
  "Screen" : -1,
  "Selection Color" : {
    "Red Component" : 0.027450980392156866,
    "Color Space" : "sRGB",
    "Blue Component" : 0.25882352941176473,
    "Green Component" : 0.21176470588235294
  },
  "Columns" : 80,
  "Idle Code" : 0,
  "Ansi 13 Color" : {
    "Red Component" : 0.42352941176470588,
    "Color Space" : "sRGB",
    "Blue Component" : 0.7686274509803922,
    "Green Component" : 0.44313725490196076
  },
  "Custom Command" : "No",
  "ASCII Anti Aliased" : true,
  "Non Ascii Font" : "Monaco 12",
  "Vertical Spacing" : 1,
  "Use Bold Font" : true,
  "Option Key Sends" : 0,
  "Selected Text Color" : {
    "Red Component" : 0.57647058823529407,
    "Color Space" : "sRGB",
    "Blue Component" : 0.63137254901960782,
    "Green Component" : 0.63137254901960782
  },
  "Background Color" : {
    "Red Component" : 0,
    "Color Space" : "sRGB",
    "Blue Component" : 0.21176470588235294,
    "Green Component" : 0.16862745098039217
  },
  "Character Encoding" : 4,
  "Ansi 11 Color" : {
    "Red Component" : 0.396078431372549,
    "Color Space" : "sRGB",
    "Blue Component" : 0.51372549019607838,
    "Green Component" : 0.4823529411764706
  },
  "Use Italic Font" : true,
  "Unlimited Scrollback" : false,
  "Keyboard Map" : {
    "0xf700-0x260000" : {
      "Text" : "[1;6A",
      "Action" : 10
    },
    "0x37-0x40000" : {
      "Text" : "0x1f",
      "Action" : 11
    },
    "0x32-0x40000" : {
      "Text" : "0x00",
      "Action" : 11
    },
    "0xf709-0x20000" : {
      "Text" : "[17;2~",
      "Action" : 10
    },
    "0xf70c-0x20000" : {
      "Text" : "[20;2~",
      "Action" : 10
    },
    "0xf729-0x20000" : {
      "Text" : "[1;2H",
      "Action" : 10
    },
    "0xf72b-0x40000" : {
      "Text" : "[1;5F",
      "Action" : 10
    },
    "0xf705-0x20000" : {
      "Text" : "[1;2Q",
      "Action" : 10
    },
    "0xf703-0x260000" : {
      "Text" : "[1;6C",
      "Action" : 10
    },
    "0xf700-0x220000" : {
      "Text" : "[1;2A",
      "Action" : 10
    },
    "0xf701-0x280000" : {
      "Text" : "0x1b 0x1b 0x5b 0x42",
      "Action" : 11
    },
    "0x38-0x40000" : {
      "Text" : "0x7f",
      "Action" : 11
    },
    "0x33-0x40000" : {
      "Text" : "0x1b",
      "Action" : 11
    },
    "0xf703-0x220000" : {
      "Text" : "[1;2C",
      "Action" : 10
    },
    "0xf701-0x240000" : {
      "Text" : "[1;5B",
      "Action" : 10
    },
    "0xf70d-0x20000" : {
      "Text" : "[21;2~",
      "Action" : 10
    },
    "0xf702-0x260000" : {
      "Text" : "[1;6D",
      "Action" : 10
    },
    "0xf729-0x40000" : {
      "Text" : "[1;5H",
      "Action" : 10
    },
    "0xf706-0x20000" : {
      "Text" : "[1;2R",
      "Action" : 10
    },
    "0x34-0x40000" : {
      "Text" : "0x1c",
      "Action" : 11
    },
    "0xf700-0x280000" : {
      "Text" : "0x1b 0x1b 0x5b 0x41",
      "Action" : 11
    },
    "0x2d-0x40000" : {
      "Text" : "0x1f",
      "Action" : 11
    },
    "0xf70e-0x20000" : {
      "Text" : "[23;2~",
      "Action" : 10
    },
    "0xf702-0x220000" : {
      "Text" : "[1;2D",
      "Action" : 10
    },
    "0xf703-0x280000" : {
      "Text" : "0x1b 0x1b 0x5b 0x43",
      "Action" : 11
    },
    "0xf700-0x240000" : {
      "Text" : "[1;5A",
      "Action" : 10
    },
    "0xf707-0x20000" : {
      "Text" : "[1;2S",
      "Action" : 10
    },
    "0xf70a-0x20000" : {
      "Text" : "[18;2~",
      "Action" : 10
    },
    "0x35-0x40000" : {
      "Text" : "0x1d",
      "Action" : 11
    },
    "0xf70f-0x20000" : {
      "Text" : "[24;2~",
      "Action" : 10
    },
    "0xf703-0x240000" : {
      "Text" : "[1;5C",
      "Action" : 10
    },
    "0xf701-0x260000" : {
      "Text" : "[1;6B",
      "Action" : 10
    },
    "0xf702-0x280000" : {
      "Text" : "0x1b 0x1b 0x5b 0x44",
      "Action" : 11
    },
    "0xf72b-0x20000" : {
      "Text" : "[1;2F",
      "Action" : 10
    },
    "0x36-0x40000" : {
      "Text" : "0x1e",
      "Action" : 11
    },
    "0xf708-0x20000" : {
      "Text" : "[15;2~",
      "Action" : 10
    },
    "0xf701-0x220000" : {
      "Text" : "[1;2B",
      "Action" : 10
    },
    "0xf70b-0x20000" : {
      "Text" : "[19;2~",
      "Action" : 10
    },
    "0xf702-0x240000" : {
      "Text" : "[1;5D",
      "Action" : 10
    },
    "0xf704-0x20000" : {
      "Text" : "[1;2P",
      "Action" : 10
    }
  },
  "Window Type" : 0,
  "Background Image Location" : "",
  "Blur" : false,
  "Badge Color" : {
    "Red Component" : 1,
    "Color Space" : "sRGB",
    "Blue Component" : 0,
    "Alpha Component" : 0.5,
    "Green Component" : 0.1491314172744751
  },
  "Scrollback Lines" : 1000,
  "Send Code When Idle" : false,
  "Close Sessions On End" : true,
  "Terminal Type" : "xterm-256color",
  "Visual Bell" : true,
  "Flashing Bell" : false,
  "Silence Bell" : false,
  "Ansi 14 Color" : {
    "Red Component" : 0.57647058823529407,
    "Color Space" : "sRGB",
    "Blue Component" : 0.63137254901960782,
    "Green Component" : 0.63137254901960782
  },
  "Name" : "Solarized%2520Dark",
  "Cursor Text Color" : {
    "Red Component" : 0.027450980392156866,
    "Color Space" : "sRGB",
    "Blue Component" : 0.25882352941176473,
    "Green Component" : 0.21176470588235294
  },
  "Shortcut" : "",
  "Cursor Color" : {
    "Red Component" : 0.51372549019607838,
    "Color Space" : "sRGB",
    "Blue Component" : 0.58823529411764708,
    "Green Component" : 0.58039215686274515
  },
  "Ansi 0 Color" : {
    "Red Component" : 0.027450980392156866,
    "Color Space" : "sRGB",
    "Blue Component" : 0.25882352941176473,
    "Green Component" : 0.21176470588235294
  },
  "Ansi 1 Color" : {
    "Red Component" : 0.86274509803921573,
    "Color Space" : "sRGB",
    "Blue Component" : 0.18431372549019609,
    "Green Component" : 0.19607843137254902
  },
  "Horizontal Spacing" : 1,
  "Ansi 3 Color" : {
    "Red Component" : 0.70980392156862748,
    "Color Space" : "sRGB",
    "Blue Component" : 0,
    "Green Component" : 0.53725490196078429
  },
  "Transparency" : 0,
  "Guid" : "1AAB9A7B-51CA-4A0B-A19E-6E952867DFF3",
  "Use Non-ASCII Font" : false,
  "Ansi 2 Color" : {
    "Red Component" : 0.52156862745098043,
    "Color Space" : "sRGB",
    "Blue Component" : 0,
    "Green Component" : 0.59999999999999998
  },
  "Normal Font" : "MesloLGSDZForPowerline-Regular 12",
  "Link Color" : {
    "Red Component" : 0,
    "Color Space" : "sRGB",
    "Blue Component" : 0.73423302173614502,
    "Alpha Component" : 1,
    "Green Component" : 0.35916060209274292
  },
  "Ansi 4 Color" : {
    "Red Component" : 0.14901960784313725,
    "Color Space" : "sRGB",
    "Blue Component" : 0.82352941176470584,
    "Green Component" : 0.54509803921568623
  },
  "Right Option Key Sends" : 0
}

```

By inserting the follwing lines to the `~/.zshrc` configs to make zsh settings work, 
```bash
# oh-my-zsh
export ZSH="$HOME/.oh-my-zsh"
ZSH_THEME="agnoster"
plugins=(
  git
  zsh-autosuggestions
  zsh-syntax-highlighting
)
source $ZSH/oh-my-zsh.sh
```
[zsh-autosuggestion](https://github.com/zsh-users/zsh-autosuggestions) and [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) are two useful plugins, the former one will auto complete your command base on the history, and the later one helps you highlight the command keyword. 


## 3 Git {#git}
[Git](https://git-scm.com/) is a version control system which thinks of data as a series of snapshots of a miniature filesystem. On mac it will be installed together with Xcode. 
```bash
brew install git
```
Configurations which values specific personally to the user and affects all of the repositories.
```bash
git --global user.name "<yourName>"
git --global user.email yourEmail@xxx.com
```
By following the instructions of SSH, you also need to put your public key to the remote sever, such GitHub, BitBucket, GitLab...
```bash 
ssh-keygen -t rsa -C "yourEmail@xxx.com"
pbcopy < ~/.ssh/id_rsa.pub
```

### ignore files
Create the file `~/.gitignore` as shown below,
```bash
# Folder view configuration files
.DS_Store
Desktop.ini

# Thumbnail cache files
._*
Thumbs.db

# Files that might appear on external disks
.Spotlight-V100
.Trashes

# Compiled Python files
*.pyc

# Compiled C++ files
*.out

# Application specific files
venv
node_modules
.sass-cache
```
and set the default ignore files for git by running following command,
```bash
git config --global core.excludesfile ~/.gitignore
```


### multi account
If you want to set multiple git account on local, `~/.ssh/config` is what you want to update,
```bash
Host work.github.com
  HostName github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/github-work
  IdentitiesOnly yes

Host personal.github.com
  HostName github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/github-personal
  IdentitiesOnly yes
```
And change the repository config file `.git/config` to use correct remote url,
```bash
[remote "origin"]
    url = git@personal.github.com:designcise/my-repo.git
```
or use the command line to set, 
```bash
git remote set-url origin git@personal.github.com:designcise/my-repo.git
```


## 4 Visual Studio Code {#vscode}
[Visual Studio Code](https://code.visualstudio.com/) is lightweight code editor with powerful plugins, 
```bash
brew install --cask visual-studio-code
```

Since we downloaded powerline font to use for terminal, need to set it for vscode terminal as well, 
`[Command] + [Shift] + P` and add the following line into "user settings", 
```JSON
{
  "terminal.integrated.fontFamily": "Meslo LG M DZ for Powerline"
}
```

## 5 Python {#python}
[Python](https://www.python.org/) is an interpreted language, interactively, and object-oriented. 

Here, we use `Pyenv` to manage multiple version in one machine, 
```bash
brew install pyenv
```
Also insert following lines into `~/.zshrc` to enable shims and autocompletion
```bash
# pyenv
eval "$(pyenv init -)"
```
Then you install any version of Python and use it via `pyenv` commands.


## 6 Java {#java}
[Java](https://www.java.com/) is a popular programming language which aims to "Write once, Run everywhere". 

Here, we use `Jenv` to manage multiple version in one machine, 
```bash
brew install jenv
```
And also config the settings of zsh in `~/.zshrc`,
```bash
# jenv
eval "$(jenv init -)"
```
As for JDK, Java Development Kit, we need to download from [HomePage](http://www.oracle.com/technetwork/java/javase/downloads/) for specific version. 
Then you can add it by `jenv` as below,
```bash
jenv add /Library/Java/JavaVirtualMachines/<version>/Contents/Home
```

### Maven
[Maven](http://maven.apache.org/) is used to manage Java project and auto build the application. 
```bash
brew install maven
```
JDK need to be configured when using `mvn`, here we force it to use the version that `jenv` is using,
```bash
jenv enable-plugin maven
```


## 7 Ruby {#ruby}
[Ruby](https://www.ruby-lang.org/en/) is server side script language, fully object-oriented. 
```bash
brew install rbenv ruby-build rbenv-default-gems rbenv-gemset
```
`rbenv` and `ruby-build` are used to manage and install Ruby versions for development environment, set the condifgurations in `~/.zshrc` as following,
```bash
# rbenv
eval "$(rbenv init -)"
```



## 8 Node.js {#node-js}
[NodeJs](https://nodejs.org/en) is the JavaScript which is running on the server side, also known as a JavaScript runtime built on Chrome's V8 JavaScript engine. 

Here, we use `nvm` to manage different version of node, 
```bash
brew install nvm
```
`~/.zshrc` needs to be configured for it, 
```bash
# nvm
export NVM_DIR="$HOME/.nvm"
  [ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"    # This loads nvm
  [ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/         homebrew/opt/nvm/etc/bash_completion.d/nvm"  # This loads nvm bash_completion
```


## 9 Go {#go}
[Go](https://go.dev/) is an open source programming language, which is designed for web server, storage cluster or centralized server. 
```bash
brew install go
```


## 10 MySQL {#mysql}
[MySQL](https://www.mysql.com/) is a widely used database software, and SQL stands for Structured Query Language. 
```bash
brew install mysql
```
To have lanuchd start MySQL as a background service,
```bash
brew services start mysql
```


## Reference {#reference} 
[macOS Setup Guide](https://sourabhbajaj.com/mac-setup/)