Congratz to get past the first tutorial.

We support VSCode as one of our IDE for most development work. 

Here are some basics and recommendation that can add some help to your development, or save you a few clicks.
You might already know these, or in case not, it is a good time to catch up. This is written in a cheat-sheet like format without detailed description for quick look-up

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

## Hotkeys

### Editing
`ctrl+f`: find
`ctrl+shift+F`: find globally
`ctrl+h`: replace
`ctrl+shift+H`: replace globally
`ctrl+g`: go to line (enter a line number)
`ctrl+shift+arrow`: multi-line text cursor
`ctrl+/`: comment / uncomment
`ctrl+w`: close file
`ctrl+shift+I`: format file

### Terminal
`` ctrl+` ``: open / close terminal, focus to terminal
`ctrl+shift+5`: split terminal into 2
`` `ctrl+shift+` ``: new terminal
`ctrl+d`: terminate current terminal


`ctrl+shift+P`: search for config of VSCode or plugin, most function can be started from this hot-key, then do a search

## Configs



## Extensions

Note: In order to use extension in remote machine, some extensions must be installed both at local and remote. If you find some extension missing in remote machine, visit the extension tab and `Install in SSH: ....`

### General

`ms-vscode-remote.remote-ssh`: Use VSCode on remote directory just like local
`aaron-bond.better-comments`: Highlight comments by categories
`eamodio.gitlens`: Integrate GUI git diff and history, among other features, into VSCode 

### Language Specific

`ms-python.vscode-pylance`: `python3` syntax highlighter and linter support
`yzhang.markdown-all-in-one`: `markdown` syntax highlighter and formatter
`esbenp.prettier-vscode`: `javascript` formatter
`graphql.vscode-graphql`: `graphql` syntax highlighter