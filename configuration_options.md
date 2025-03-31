---
title: Tailwind CSS Configuration Options
description: A comprehensive guide to all available configuration options in Tailwind CSS, including theme customization, plugin addition, and advanced settings.
---

# Tailwind CSS Configuration Options

Tailwind CSS provides a powerful and flexible configuration system that allows you to customize every aspect of your design system. This guide covers all available configuration options, including theme customization, plugin addition, and advanced settings.

## Table of Contents

1. [Basic Configuration Structure](#basic-configuration-structure)
2. [Theme Customization](#theme-customization)
3. [Plugins](#plugins)
4. [Content Configuration](#content-configuration)
5. [Dark Mode](#dark-mode)
6. [Prefix](#prefix)
7. [Important](#important)
8. [Separator](#separator)
9. [Presets](#presets)
10. [Future](#future)

## Basic Configuration Structure

A typical Tailwind CSS configuration file (`tailwind.config.js`) has the following structure:

```javascript
module.exports = {
  content: [],
  theme: {},
  plugins: [],
  // Other options...
}
```

## Theme Customization

The `theme` section is where you define your design system's colors, typography, spacing, and more. You can either extend the default theme or completely override it.

```javascript
module.exports = {
  theme: {
    colors: {
      // Override the default color palette
      blue: '#1fb6ff',
      purple: '#7e5bef',
      // ...
    },
    extend: {
      // Extend the default theme
      spacing: {
        '128': '32rem',
        '144': '36rem',
      },
    },
  },
}
```

### Accessing Theme Values

In your CSS, you can access theme values using the `theme()` function:

```css
.example {
  color: theme('colors.blue');
  padding: theme('spacing.4');
}
```

## Plugins

Plugins allow you to add new styles, utilities, or components to your Tailwind CSS project. You can add plugins in the `plugins` array:

```javascript
const plugin = require('tailwindcss/plugin')

module.exports = {
  plugins: [
    require('@tailwindcss/forms'),
    plugin(function({ addUtilities, theme }) {
      const newUtilities = {
        '.custom-class': {
          padding: theme('spacing.2'),
          backgroundColor: theme('colors.gray.200'),
        },
      }
      addUtilities(newUtilities)
    }),
  ],
}
```

## Content Configuration

The `content` option specifies which files Tailwind should scan to find class names that need to be included in your CSS:

```javascript
module.exports = {
  content: [
    './src/**/*.{html,js,jsx,ts,tsx}',
    './public/index.html',
  ],
}
```

## Dark Mode

Tailwind CSS supports different strategies for implementing dark mode:

```javascript
module.exports = {
  darkMode: 'media', // or 'class' or 'selector' or ['class', '.custom-dark-class']
}
```

- `'media'`: Uses the `prefers-color-scheme` media query
- `'class'`: Requires adding a `.dark` class to the `html` element
- `'selector'`: Similar to `'class'` but uses `:where()` for more predictable behavior
- `['class', '.custom-dark-class']`: Uses a custom class instead of `.dark`

## Prefix

You can add a custom prefix to all of Tailwind's generated utility classes:

```javascript
module.exports = {
  prefix: 'tw-',
}
```

This would change classes like `bg-red-500` to `tw-bg-red-500`.

## Important

You can make all of Tailwind's utilities `!important` by setting the `important` option to `true`:

```javascript
module.exports = {
  important: true,
}
```

Alternatively, you can use a custom selector:

```javascript
module.exports = {
  important: '#app',
}
```

## Separator

You can customize the separator character used for responsive breakpoints, hover states, and other modifiers:

```javascript
module.exports = {
  separator: '_',
}
```

This would change classes like `md:text-lg` to `md_text-lg`.

## Presets

Presets allow you to share common configuration between projects:

```javascript
module.exports = {
  presets: [
    require('./custom-preset.js'),
  ],
}
```

## Future

The `future` option allows you to opt-in to future breaking changes:

```javascript
module.exports = {
  future: {
    removeDeprecatedGapUtilities: true,
    purgeLayersByDefault: true,
  },
}
```

You can also use `'all'` to opt-in to all future features:

```javascript
module.exports = {
  future: 'all',
}
```

By leveraging these configuration options, you can fully customize Tailwind CSS to fit your project's needs. Remember to refer to the official Tailwind CSS documentation for the most up-to-date information on configuration options and best practices.