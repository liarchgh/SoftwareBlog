# VSCode

## settings.json

```text
{
    "gitlens.blame.format": "${author}|${agoOrDate|14-}|${message|40?}",
    "explorer.confirmDelete": false,
    "editor.suggestSelection": "first",
    "editor.fontSize": 16,
    // 关闭预览模式
    "workbench.editor.enablePreview": false,
    // 关闭预览模式
    "workbench.editor.enablePreviewFromQuickOpen": false,
    // 回车不选中提示
    "editor.acceptSuggestionOnEnter": "off",
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
}
```

