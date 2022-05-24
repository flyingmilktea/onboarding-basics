We support VSCode as one of our IDE for most development work. 

Here are some basics and recommendation that can add some help to your development, or save you a few clicks.
You might already know these, or in case not, it is a good time to catch up, please walk-through them one by one if you have not.

This is written in a cheat-sheet like format without detailed description for quick look-up.

- [Why VSCode](#why-vscode)
- [Tabs](#tabs)
- [Configs](#configs)
- [Extensions](#extensions)
- [Hotkeys](#hotkeys)
- [Contribution](#contribution)

# Why VSCode

VSCode has GUI and has a low learning curve to start with, it can be used on Linux, MacOS and Windows.

If you have not chosen a supported IDE (either VSCode or vim), we recommend VSCode for beginners. 

# Tabs

In general, we recommend you to open one VSCode window per repository

```bash
git clone git@github.com:flyingmilktea/onboarding-basics.git

code onboarding-basics
```

__Explorer__

Here you will find all files in this repository, and click to edit each one

![image](https://user-images.githubusercontent.com/20808792/169729246-8f08c032-925e-45cf-9e1f-ab8bc314331d.png)

__Search__

To search for keywords in the whole repository, and click to edit the location

![image](https://user-images.githubusercontent.com/20808792/169729338-bf7b0128-edf0-4215-b20a-a59df17d1fc1.png)

__Source Control__

To track your staged / local changes, allows you to open a file to pick specific lines to stage

![image](https://user-images.githubusercontent.com/20808792/169729617-c3368dbf-51bf-4753-bac6-35cab20becda.png)

Another feature is from git-lens plugin that show commit history

![image](https://user-images.githubusercontent.com/20808792/169729721-1931bb3a-95a6-4685-b72d-ba058d7ae5e9.png)

__Terminal__

To run commands during development, command-line tools are necessary for development, e.g. from `npm`, `pip`, `git` or other tools

![Screenshot from 2022-05-23 09-55-05](https://user-images.githubusercontent.com/20808792/169729863-3866256a-818f-40dd-b4ce-da798357045c.png)


# Configs

These configs can be set using UI or JSON

`ctrl+shift+P` > `Preferences: Open Settings (UI)`

__Recommended__

`"terminal.integrated.scrollback": 100000`: increase your scrollback buffer large enough to see some error message, default of 1000 is grossly not enough.

`"editor.formatOnSave": true`: format your code on save, saves typing a few spaces and ensures formatting is correct. This feature calls the formatter of your choice, you have to install and config the formatter properly for this feature to work.

`"diffEditor.ignoreTrimWhitespace": false`: python formatting is based on whitespace, presence or not make a difference.

`"terminal.integrated.allowChords": false`: if you will use `nano` editor on terminal sometimes. 

Disable `ctrl+w` to close VSCode completely if it does: different version of VSCode seem to have different behavior, see [microsoft/vscode#54492](https://github.com/microsoft/vscode/issues/54492).
Especially you are doing at remote, closing VSCode means also disconnect from the terminal and lose all remote apps that you have open, and environment variables you have set, just re-opening VSCode doesn't get you back those states at remote.

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
