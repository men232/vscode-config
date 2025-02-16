# 🚀 Minimalistic VS Code Config

<img width="1743" alt="Preview" src="Preview.png">

# 📌 Description

This is my VS Code configuration for a clean and minimalistic interface. While it should work with other themes, full compatibility is not guaranteed.

# 🔧 Requirements

Ensure you have the following installed:

- [Custom UI Style+](https://marketplace.visualstudio.com/items?itemName=subframe7536.custom-ui-style) – for UI customization
- [Symbols Icons](https://marketplace.visualstudio.com/items?itemName=miguelsolorio.symbols) – for better file icons
- [PurpleSchool Theme](https://marketplace.visualstudio.com/items?itemName=PurpleSchool.purpleschool-theme) – my preferred theme
- [Maple Mono](https://github.com/subframe7536/maple-font) – recommended font

# 📥 Installation

1. Copy the contents of [vscode-settings.json](vscode-settings.json) into your VS Code user settings..
2. Save [vscode-styles.css](vscode-styles.css) to `{userHome}/Documents/vscode-styles.css` (or any other location).
3. Make sure to update the `custom-ui-style.external.imports` path in your settings accordingly.

# 🎨 Customization

You can tweak various UI elements using the following CSS variables:

```
/* Global transparency amount */
--al-transparency-percent: 25%;

/* Editor split line color */
--al-pane-split-color: rgb(255, 255, 255);
--al-pane-split-transparent: 2.5%;

/* Label name */
--al-label-name-shadow: 0px 2px 4px rgba(0, 0, 0, 0.15);

/* Tabs adjustments (Highly requested feature! 😆) */
--al-tab-height: 38px;
--al-tab-y-offset: 7px;

--al-tab-activeBackground: white;
--al-tab-activeColor: black;
--al-tab-fontSize: 14px;
--al-tab-borderRadius: 4px;

/* Custom project icon (Explorer) */
--al-project-icon: '🤯'; /* Default: 🚀 */
```

# ⚠️ Known Issues

- Horizontal scrolling extends beyond the container, making it appear smaller than its actual size.
- Window dragging issue – the window becomes unmovable using the mouse.

Let me know if you want to add possible workarounds or solutions! 🚀
