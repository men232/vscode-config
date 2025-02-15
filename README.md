# Preview

<img width="1743" alt="Preview" src="Preview.png">

# Description

This is my vscode config to make interface looks minimalistic. It should work fine with other themes but not guaranteed.

# Requirements

- [Custom UI Style+](https://marketplace.visualstudio.com/items?itemName=subframe7536.custom-ui-style)
- [Symbols Icons](https://marketplace.visualstudio.com/items?itemName=miguelsolorio.symbols)
- [PurpleSchool Theme](https://marketplace.visualstudio.com/items?itemName=PurpleSchool.purpleschool-theme)
- [Maple Mono](https://github.com/subframe7536/maple-font)

# Installation

1. Copy-paste content from [vscode-settings.json](vscode-settings.json) into user settings.
2. Save [vscode-styles.css](vscode-styles.css) into {userHome}/Documents/vscode-styles.css or whatever you want, but do not forget to adjust a `custom-ui-style.external.imports` path.

# Configurations

You can adjust few things via css variables:

```
// Global transparency amount
--al-transparency-percent: 25%;

// Editor split line color
--al-pane-split-color: rgb(255, 255, 255);
--al-pane-split-transparent: 2.5%;

// Label name
--al-label-name-shadow: 0px 2px 4px rgba(0, 0, 0, 0.15);

// Tabs adjustments (Most wanted feature) 🤣
--al-tab-height: 38px;
--al-tab-y-offset: 7px;

--al-tab-activeBackground: white;
--al-tab-activeColor: black;
--al-tab-fontSize: 14px;
--al-tab-borderRadius: 4px;

// Custom project icon (Explorer)
--al-project-icon: '🤯'; // by default 🚀
```
