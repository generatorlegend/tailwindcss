# Utility Reference

This page provides a comprehensive reference guide for all utility classes available in Tailwind CSS, organized by category. Each section includes usage examples and configurable options where applicable.

## Layout

### Container

The `container` class sets the `max-width` of an element to match the `min-width` of the current breakpoint.

```html
<div class="container">
  <!-- Content here -->
</div>
```

By default, this class only centers the content. You can combine it with breakpoint classes to make it responsive:

```html
<div class="container md:px-20 lg:px-40">
  <!-- Content here -->
</div>
```

### Display

Control the display box type of an element.

- `block`
- `inline-block`
- `inline`
- `flex`
- `inline-flex`
- `table`
- `grid`
- `hidden`

Example:
```html
<div class="block"><!-- Block-level element --></div>
<span class="inline-block"><!-- Inline-block element --></span>
```

### Flexbox

Utilities for controlling flex containers and items.

#### Flex Container

- `flex`: Creates a block-level flex container
- `inline-flex`: Creates an inline-level flex container

#### Flex Direction

- `flex-row`
- `flex-row-reverse`
- `flex-col`
- `flex-col-reverse`

#### Flex Wrap

- `flex-wrap`
- `flex-wrap-reverse`
- `flex-nowrap`

#### Flex Grow / Shrink

- `flex-grow`
- `flex-grow-0`
- `flex-shrink`
- `flex-shrink-0`

Example:
```html
<div class="flex flex-row flex-wrap">
  <div class="flex-grow">Flex item</div>
  <div class="flex-shrink-0">Fixed width item</div>
</div>
```

### Grid

Utilities for creating grid layouts.

- `grid`: Creates a grid container
- `grid-cols-{n}`: Sets the number of columns in the grid
- `col-span-{n}`: Spans an item across n columns
- `col-start-{n}`: Starts an item at column n
- `col-end-{n}`: Ends an item at column n

Example:
```html
<div class="grid grid-cols-3 gap-4">
  <div class="col-span-2">Wide column</div>
  <div>Normal column</div>
  <div>Normal column</div>
</div>
```

## Spacing

### Padding

Add padding to elements using classes prefixed with `p-`, `px-`, `py-`, `pt-`, `pr-`, `pb-`, or `pl-`.

```html
<div class="p-4">All around padding</div>
<div class="px-4 py-2">Horizontal and vertical padding</div>
```

### Margin

Add margin to elements using classes prefixed with `m-`, `mx-`, `my-`, `mt-`, `mr-`, `mb-`, or `ml-`.

```html
<div class="m-4">All around margin</div>
<div class="mx-auto">Horizontally centered with auto margins</div>
```

## Typography

### Font Family

- `font-sans`
- `font-serif`
- `font-mono`

### Font Size

- `text-xs`
- `text-sm`
- `text-base`
- `text-lg`
- `text-xl`
- `text-2xl` (and up to `text-9xl`)

### Font Weight

- `font-thin`
- `font-extralight`
- `font-light`
- `font-normal`
- `font-medium`
- `font-semibold`
- `font-bold`
- `font-extrabold`
- `font-black`

### Text Color

Use `text-{color}` classes to set the text color.

```html
<p class="text-blue-500">Blue text</p>
<p class="text-red-700">Dark red text</p>
```

### Text Alignment

- `text-left`
- `text-center`
- `text-right`
- `text-justify`

### Text Decoration

- `underline`
- `overline`
- `line-through`
- `no-underline`

## Backgrounds

### Background Color

Use `bg-{color}` classes to set the background color.

```html
<div class="bg-gray-200">Gray background</div>
<div class="bg-blue-500">Blue background</div>
```

### Background Size

- `bg-auto`
- `bg-cover`
- `bg-contain`

### Background Position

- `bg-bottom`
- `bg-center`
- `bg-left`
- `bg-left-bottom`
- `bg-left-top`
- `bg-right`
- `bg-right-bottom`
- `bg-right-top`
- `bg-top`

## Borders

### Border Width

- `border`
- `border-0`
- `border-2`
- `border-4`
- `border-8`

You can also target specific sides: `border-{side}` where side can be `t`, `r`, `b`, or `l`.

### Border Color

Use `border-{color}` classes to set the border color.

```html
<div class="border-2 border-blue-500">Blue border</div>
```

### Border Radius

- `rounded-none`
- `rounded-sm`
- `rounded`
- `rounded-md`
- `rounded-lg`
- `rounded-full`

## Effects

### Opacity

- `opacity-0`
- `opacity-25`
- `opacity-50`
- `opacity-75`
- `opacity-100`

### Box Shadow

- `shadow-sm`
- `shadow`
- `shadow-md`
- `shadow-lg`
- `shadow-xl`
- `shadow-2xl`
- `shadow-inner`
- `shadow-none`

## Interactivity

### Cursor

- `cursor-auto`
- `cursor-default`
- `cursor-pointer`
- `cursor-wait`
- `cursor-text`
- `cursor-move`
- `cursor-not-allowed`

### User Select

- `select-none`
- `select-text`
- `select-all`
- `select-auto`

## Sizing

### Width

- `w-{number}` or `w-{fraction}`
- `w-full`
- `w-screen`
- `w-min`
- `w-max`
- `w-auto`

### Height

- `h-{number}` or `h-{fraction}`
- `h-full`
- `h-screen`
- `h-min`
- `h-max`
- `h-auto`

## Flexbox and Grid

### Flex

- `flex-1`
- `flex-auto`
- `flex-initial`
- `flex-none`

### Grid Template Columns

- `grid-cols-{n}` where n is 1-12
- `grid-cols-none`

### Gap

- `gap-{size}`
- `gap-x-{size}`
- `gap-y-{size}`

## Customization

Tailwind CSS is highly customizable. You can extend or override the default configuration in your `tailwind.config.js` file. Here's an example of how you might customize the color palette:

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        'custom-blue': '#1da1f2',
        'custom-green': '#17bf63',
      },
    },
  },
  variants: {},
  plugins: [],
}
```

After adding these custom colors, you can use them like any other color utility:

```html
<div class="bg-custom-blue text-custom-green">
  Custom colored element
</div>
```

Remember to refer to the official Tailwind CSS documentation for the most up-to-date and detailed information on utility classes and customization options.