##Install package control

https://packagecontrol.io/installation

Follow the instructions in that page.

##Install packages into sublime:

Open package control with Ctrl+shift+P
Put the name of the package
Install the plugin

Interesting packages:

* Markdown preview
* Markdown editing


###Configure markdown editing theme: 
Go to Preferences -> Package Settings -> Markdown Editing -> Markdown GFM Settings and put the following line:
```
{
    "color_scheme": "Packages/MarkdownEditing/MarkdownEditor-Dark.tmTheme"
}
```

###Configure markdown viewer keybinding:
Go to Preferences -> Key Bindings [User] and add the following bind:
```
[
    { "keys": ["alt+m"], "command": "markdown_preview", "args": {"target": "browser", "parser":"markdown"} }
]
``` 

##Sublime tips

* add a directory to your opened project from power shell
```subl <directory_name> -add```



