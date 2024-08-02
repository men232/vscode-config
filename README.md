# Preview

<img width="1743" alt="Preview" src="Preview.png">

# Description

This is my vscode config to make interface looks minimalistic. It should work fine with other themes but not guaranteed.

# Requirements

- [Apc Cusmoize UI++](https://marketplace.visualstudio.com/items?itemName=drcika.apc-extension)
- [VSCode Animations](https://marketplace.visualstudio.com/items?itemName=BrandonKirbyson.vscode-animations)
- [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)
- [PurpleSchool Theme](https://marketplace.visualstudio.com/items?itemName=PurpleSchool.purpleschool-theme)

# Installation

1. Copy-paste content from [vscode-settings.json](vscode-settings.json) into user settings.
2. Save [vscode-styles.css](vscode-styles.css) into {userHome}/Documents/vscode-styles.css or whatever you want, but do not forget to adjust a `apc.imports` path.

# Configurations

You can adjust few things via css variables:

```
// Window transparency amount
--al-transparency-percent: 25%;

// Split line color
--al-pane-split-color: rgba(255,255,255,0.025);

// Most wanted feature 🤣
--al-tab-height: 38px;
--al-tab-y-offset: 7px;

--al-tab-activeBackground: white;
--al-tab-activeColor: black;
--al-tab-fontSize: 14px;
```
