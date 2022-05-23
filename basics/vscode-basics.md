We support VSCode as one of our IDE for most development work. 

Here are some basics and recommendation that can add some help to your development, or save you a few clicks.
You might already know these, or in case not, it is a good time to catch up, please walk-through them one by one if you have not.

This is written in a cheat-sheet like format without detailed description for quick look-up

- [Why VSCode](#why-vscode)
  - [Hotkeys](#hotkeys)
    - [Editing](#editing)
    - [Terminal](#terminal)
  - [Configs](#configs)
  - [Extensions](#extensions)
    - [General](#general)
    - [Language Specific](#language-specific)

# Why VSCode

VSCode has GUI and has a low learning curve to start with, it can be used on Linux, MacOS and Windows.

If you have not chosen a supported IDE (either VSCode or vim), we recommend VSCode for beginners. 

# Configs



# Extensions

__Note__: In order to use extension in remote machine, some extensions must be installed _both at local and remote_. If you find some extension missing in remote machine, visit the extension tab and `Install in SSH: ....`

![image](https://user-images.githubusercontent.com/20808792/169727390-b16d6d77-ea6f-4c71-8d67-33bb13633307.png)

__General__

`ms-vscode-remote.remote-ssh`: Use VSCode on remote directory just like local

`aaron-bond.better-comments`: Highlight comments by categories

`eamodio.gitlens`: Integrate GUI git diff and history, among other features, into VSCode 

__Language Specific__

`ms-python.vscode-pylance`: `python3` syntax highlighter and linter support

`yzhang.markdown-all-in-one`: `markdown` syntax highlighter and formatter

`esbenp.prettier-vscode`: `javascript` formatter

`graphql.vscode-graphql`: `graphql` syntax highlighter


# Hotkeys

__Advanced features and configs__

`ctrl+shift+P`: search for config of VSCode or plugin, most function can be started from this hot-key, then do a search

`ctrl + -`: Decrease text size

`ctrl + =`: Increase text size

__Editing__

`ctrl+f`: find, you can also do highlight then `ctrl+f` (or other find / replace hotkey), VSCode generate the required Regex for you.

`ctrl+shift+F`: find globally

`ctrl+h`: replace

`ctrl+shift+H`: replace globally

`ctrl+g`: go to line (enter a line number)

`ctrl+shift+arrow`: multi-line text cursor

`ctrl+/`: comment / uncomment

`ctrl+w`: close file

`ctrl+shift+I`: format file

__Terminal__

`` ctrl+` ``: open / close terminal, focus to terminal

`ctrl+shift+5`: split terminal into 2

`` ctrl+shift+` ``: new terminal

`ctrl+d`: terminate current terminal

# Contribution

If you find something useful and want to add it here, please do.
