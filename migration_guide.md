# Migration Guide

This guide will help you upgrade from previous versions of Tailwind CSS to the latest version. We'll cover breaking changes, new features, and best practices for updating your existing projects.

## Breaking Changes

### 1. PostCSS Plugin Package Change

The PostCSS plugin for Tailwind CSS has been moved to a separate package. If you're using Tailwind CSS directly as a PostCSS plugin, you'll need to update your configuration.

Old configuration:
```js
module.exports = {
  plugins: [
    require('tailwindcss'),
    // ...other plugins
  ]
}
```

New configuration:
```js
module.exports = {
  plugins: [
    require('@tailwindcss/postcss'),
    // ...other plugins
  ]
}
```

Make sure to install the new package:

```bash
npm install @tailwindcss/postcss
```

### 2. Theme Configuration Changes

Some theme configuration options have been updated or removed. Review your `tailwind.config.js` file and update the following:

- The `theme.extend` object is now the preferred way to add or override theme values.
- Some color names have been updated for consistency. Check the latest color palette documentation.

### 3. Variant Syntax Changes

The syntax for custom variants has been updated. If you're using custom variants, you'll need to update your configuration:

Old syntax:
```js
module.exports = {
  variants: {
    extend: {
      backgroundColor: ['active'],
    }
  }
}
```

New syntax:
```js
module.exports = {
  theme: {
    extend: {
      backgroundColor: {
        active: 'var(--tw-bg-opacity)',
      }
    }
  }
}
```

## New Features

### 1. Improved Theme Function

The `theme()` function now supports dot notation for accessing nested theme values:

```css
.example {
  color: theme('colors.blue.500');
}
```

### 2. Custom Variants

You can now define custom variants using the `@custom-variant` at-rule in your CSS:

```css
@custom-variant hocus {
  &:hover, &:focus {
    @slot;
  }
}
```

### 3. Source Control

The new `@source` at-rule allows you to specify which utility classes should be generated:

```css
@source 'components/**/*.{js,ts,jsx,tsx}';
```

## Updating Your Project

1. Update your dependencies:
   ```bash
   npm update tailwindcss @tailwindcss/postcss
   ```

2. Review and update your `tailwind.config.js` file:
   - Check for deprecated options and update them according to the latest documentation.
   - Consider using `theme.extend` for custom theme values.

3. Update your build process:
   - If you're using Tailwind CSS as a PostCSS plugin, update to `@tailwindcss/postcss`.
   - Ensure your build tool is compatible with the latest version of Tailwind CSS.

4. Review your custom CSS:
   - Update any custom variants to use the new `@custom-variant` syntax.
   - Consider using the new `@source` at-rule to optimize your build.

5. Test thoroughly:
   - Run your build process and check for any errors or warnings.
   - Review your application's styling to ensure everything looks as expected.
   - Pay special attention to custom components and utilities.

## Best Practices

- Use the new `@custom-variant` and `@source` at-rules to improve your workflow and optimize your builds.
- Leverage the improved `theme()` function for more flexible theme value access.
- Keep your `tailwind.config.js` file organized and use `theme.extend` for custom values.
- Regularly check the Tailwind CSS documentation for updates and new features.

By following this migration guide, you should be able to smoothly upgrade your project to the latest version of Tailwind CSS. If you encounter any issues, refer to the official documentation or seek help from the Tailwind CSS community.