# Px to Tailwind Converter

[![Version](https://img.shields.io/visual-studio-marketplace/v/azzam.px-to-tailwind-converter)](https://marketplace.visualstudio.com/items?itemName=azzam.px-to-tailwind-converter)
[![Downloads](https://img.shields.io/visual-studio-marketplace/d/azzam.px-to-tailwind-converter)](https://marketplace.visualstudio.com/items?itemName=azzam.px-to-tailwind-converter)
[![Rating](https://img.shields.io/visual-studio-marketplace/r/azzam.px-to-tailwind-converter)](https://marketplace.visualstudio.com/items?itemName=azzam.px-to-tailwind-converter)

A powerful VS Code extension that automatically converts pixel values to Tailwind CSS utility classes as you type, making Tailwind development faster and more intuitive.

## ✨ Features

### 🚀 **Automatic Real-time Conversion**
Type familiar pixel values and watch them transform into Tailwind classes instantly:
```html
<!-- Type this -->
<div class="p-16px m-8px w-200px">

<!-- Get this automatically -->
<div class="p-4 m-2 w-[200px]">
```

### 🎯 **Smart Mapping**
- **Standard Values**: Converts to Tailwind's spacing scale (`16px` → `p-4`)
- **Custom Values**: Creates arbitrary values for non-standard pixels (`17px` → `p-[17px]`)
- **Fractional Support**: Handles sub-pixel values (`2.5px` → `p-[2.5px]`)
- **Intelligent Detection**: Only processes valid Tailwind properties

### 🔧 **Comprehensive Property Support**
- **Padding**: `p-`, `px-`, `py-`, `pt-`, `pr-`, `pb-`, `pl-`
- **Margin**: `m-`, `mx-`, `my-`, `mt-`, `mr-`, `mb-`, `ml-`
- **Sizing**: `w-`, `h-`
- **Flexbox**: `gap-`, `gap-x-`, `gap-y-`
- **Positioning**: `top-`, `right-`, `bottom-`, `left-`, `inset-`
- **Typography**: `text-` (font size), `font-`/`font-weight-` (font weight)

### 🎨 **Visual Feedback**
- **Conversion Highlighting**: See exactly what changed with subtle highlighting
- **Different Indicators**: Standard conversions get checkmarks ✓, custom values get [px] indicators
- **Hover Tooltips**: Rich information about Tailwind classes and their pixel equivalents

### ⚙️ **Custom Configuration Support**
- **Tailwind Config Integration**: Automatically reads your `tailwind.config.js`
- **Custom Spacing Scales**: Supports project-specific spacing values
- **File Type Filtering**: Configure which file types to process

### 🌐 **Multi-Framework Support**
Works seamlessly with:
- **HTML** (`class` attributes)
- **React/JSX** (`className` attributes)
- **Vue.js** (`class` attributes)
- **Svelte** (`class` attributes)
- **TypeScript** variants of all above

## 🚀 Getting Started

1. **Install** the extension from the VS Code marketplace
2. **Open** any HTML, JSX, Vue, or Svelte file
3. **Type** pixel-based classes like `p-16px`
4. **Watch** them convert automatically to `p-4`

## 📖 Usage Examples

### Basic Spacing
```html
<!-- Input -->
<div class="p-16px m-8px">Content</div>

<!-- Output -->
<div class="p-4 m-2">Content</div>
```

### Complex Layouts
```jsx
// Input
<div className="w-320px h-240px px-24px py-12px gap-x-16px">
  <span className="top-8px right-4px">Positioned</span>
</div>

// Output
<div className="w-80 h-60 px-6 py-3 gap-x-4">
  <span className="top-2 right-1">Positioned</span>
</div>
```

### Custom Values
```html
<!-- Input -->
<div class="p-17px m-25px w-350px">Custom spacing</div>

<!-- Output -->
<div class="p-[17px] m-[25px] w-[350px]">Custom spacing</div>
```

## ⚙️ Configuration

### Extension Settings

Access through VS Code Settings (`Ctrl/Cmd + ,`) and search for "Px to Tailwind":

| Setting | Default | Description |
|---------|---------|-------------|
| `pxToTailwind.enabled` | `true` | Enable/disable the extension |
| `pxToTailwind.supportedFileTypes` | `["html", "javascript", "typescript", ...]` | File types where conversion is active |
| `pxToTailwind.showVisualFeedback` | `true` | Show highlighting when conversions occur |
| `pxToTailwind.showHoverTooltips` | `true` | Show pixel values in hover tooltips |
| `pxToTailwind.customSpacingScale` | `undefined` | Custom spacing scale override |

### Tailwind Config Integration

The extension automatically reads your `tailwind.config.js` file and uses custom spacing scales:

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    spacing: {
      'xs': '2px',
      'sm': '6px',
      'md': '10px',
      'lg': '14px'
    }
  }
}
```

With this config, `p-2px` becomes `p-xs` instead of `p-[2px]`.

## 🎯 Commands

Access these commands through the Command Palette (`Ctrl/Cmd + Shift + P`):

- **Px to Tailwind: Toggle** - Enable/disable the extension
- **Px to Tailwind: Show Configuration** - View current settings
- **Px to Tailwind: Reset Configuration** - Reset to defaults
- **Px to Tailwind: Show Logs** - View extension logs for debugging

## 💡 Tips & Best Practices

### For New Tailwind Users
- Start with familiar pixel values and learn Tailwind's scale naturally
- Use hover tooltips to understand the relationship between pixels and scale values
- Pay attention to visual feedback to see standard vs. custom conversions

### For Experienced Developers
- Leverage custom spacing scales for design system consistency
- Use the extension for rapid prototyping with pixel values
- Configure file types to match your project structure

### For Teams
- Share Tailwind config files to ensure consistent conversions across team members
- Use the extension during code reviews to identify inconsistent spacing
- Standardize on common pixel values that map to Tailwind's scale

## 🔧 Troubleshooting

### Extension Not Working?
1. Check that the file type is supported in settings
2. Ensure the extension is enabled (`pxToTailwind.enabled: true`)
3. Verify you're typing valid pixel classes (e.g., `p-16px`, not `padding-16px`)

### Performance Issues?
1. The extension includes intelligent caching and debouncing
2. Large files are processed efficiently with optimized algorithms
3. Check the output panel for performance metrics if needed

### Custom Config Not Loading?
1. Ensure your `tailwind.config.js` is in the workspace root
2. Check the file syntax is valid JavaScript
3. Restart VS Code after making config changes

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Setup
```bash
git clone https://github.com/Azzam/px-to-tailwind-converter.git
cd px-to-tailwind-converter
npm install
npm run compile
```

### Running Tests
```bash
npm test
```

## 📝 Changelog

See [CHANGELOG.md](CHANGELOG.md) for a detailed history of changes.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Tailwind CSS team for creating an amazing utility-first framework
- VS Code team for excellent extension APIs
- The open-source community for inspiration and feedback

---

**Enjoy faster Tailwind development!** 🚀

If you find this extension helpful, please consider:
- ⭐ Starring the repository
- 📝 Leaving a review on the marketplace
- 🐛 Reporting issues or suggesting features
- 💝 Sharing with your team and community
