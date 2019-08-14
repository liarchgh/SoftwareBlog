# Visual Studio Code

## settings.json

- Mac OS
    ```
    {
        "editor.fontFamily": "'Source Code Pro', Menlo, Monaco, 'Courier New', monospace",
        "workbench.colorTheme": "Monokai Dimmed",
        "vim.leader": ",",
        // vim shortcut
        "vim.normalModeKeyBindingsNonRecursive": [
            {
                "before": [
                "Z",
                "Z"
                ],
                "after": [],
                "commands": [
                {
                    "command": "workbench.action.files.save",
                    "args": []
                },
                {
                    "command": "workbench.action.closeActiveEditor",
                    "args": []
                }
                ]
            },
            {
                "before": [
                "leader",
                "w"
                ],
                "after": [],
                "commands": [
                {
                    "command": "workbench.action.files.save",
                    "args": []
                }
                ]
            },
            {
                "before": [
                "leader",
                "q"
                ],
                "after": [],
                "commands": [
                {
                    "command": "workbench.action.closeActiveEditor",
                    "args": []
                }
                ]
            }
        ],
        "gitlens.blame.format": "${author}|${agoOrDate|14-}|${message|40?}",
        "explorer.confirmDelete": false
    }
    ```