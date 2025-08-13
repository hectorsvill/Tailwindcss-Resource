# Tailwindcss-Resource

Tailwindcss Resource and Snippets

## 📚 Resources

Here are some great resources for learning and working with Tailwind CSS:

  * **Official Documentation**: [Tailwind CSS Docs](https://tailwindcss.com/docs) - The primary source for all utilities and concepts.
  * **Playground**: [Tailwind Play](https://play.tailwindcss.com/) - An online environment to experiment with Tailwind CSS in real-time.
  * **Video Course**: [Tailwind CSS v4 Full Course 2025](https://youtu.be/6biMWgD6_JY?si=YJCYCRIWjjyK0XSY) - A comprehensive video tutorial to master Tailwind.
  * **Flexbox Game**: [Flexbox Froggy](https://flexboxfroggy.com/) - A fun, interactive game to learn the fundamentals of Flexbox.
  * **Grid Game**: [CSS Grid Garden](https://cssgridgarden.com/) - A game that teaches you the ins and outs of CSS Grid.
  
  * **Set of designed components**: [shadcn](https://ui.shadcn.com/)

-----

## ↔️ Margin and Padding

**Margin** adds space *outside* an element's border, while **padding** adds space *inside* it.

The syntax is `propertyDirection-{size}`.

  * **Property**: `m` for `margin`, `p` for `padding`.
  * **Direction (Optional)**:
      * `t` - top
      * `b` - bottom
      * `l` - left
      * `r` - right
      * `x` - left and right (`-inline`)
      * `y` - top and bottom (`-block`)
  * **Size**: A number from the [spacing scale](https://tailwindcss.com/docs/customizing-spacing) (e.g., `4` which is `1rem` or `16px` by default). You can also use arbitrary values like `m-[10px]`.

<!-- end list -->

```html
<div class="m-8 p-4">Content</div>

<div class="mx-4 py-2">Content</div>

<div class="ml-4">I have a left margin.</div>
<div class="-mt-2 ml-4">I am pulled up with a negative top margin.</div>
```

-----

## 💪 Flexbox

Flexbox is a layout model for arranging items in a single dimension (a row or a column). To make an element a flex container, you use the `flex` utility.

**Key Flexbox Utilities:**

  * **`flex-direction`**: Controls the direction of the main axis.
      * `flex-row` (default): Items are laid out horizontally.
      * `flex-row-reverse`: Items are laid out horizontally, in reverse order.
      * `flex-col`: Items are laid out vertically.
      * `flex-col-reverse`: Items are laid out vertically, in reverse order.
  * **`justify-content`**: Aligns items along the main axis.
      * `justify-start`, `justify-end`, `justify-center`, `justify-between`, `justify-around`, `justify-evenly`.
  * **`align-items`**: Aligns items along the cross axis.
      * `items-start`, `items-end`, `items-center`, `items-baseline`, `items-stretch`.
  * **`gap`**: Adds space between flex items.
      * `gap-4`, `gap-x-4`, `gap-y-2`.
  * **`flex-wrap`**: Controls how items wrap.
      * `flex-wrap`, `flex-nowrap`, `flex-wrap-reverse`.

<!-- end list -->

```html
<div class="flex h-48 items-center justify-around rounded-lg bg-slate-200">
  <div class="h-16 w-16 rounded-lg bg-sky-500"></div>
  <div class="h-16 w-16 rounded-lg bg-sky-500"></div>
  <div class="h-16 w-16 rounded-lg bg-sky-500"></div>
</div>
```

-----

## 🏁 Grid

CSS Grid is a powerful two-dimensional layout system, allowing you to control both columns and rows.

**Key Grid Utilities:**

  * **`grid`**: Establishes a grid container.
  * **`grid-cols-{number}`**: Defines the number of columns. e.g., `grid-cols-3`.
  * **`grid-rows-{number}`**: Defines the number of rows. e.g., `grid-rows-2`.
  * **`gap-{size}`**: Defines the space between grid items. `gap-x-{size}` and `gap-y-{size}` control horizontal and vertical gaps respectively.
  * **`col-span-{number}`**: Makes an item span across multiple columns.
  * **`row-span-{number}`**: Makes an item span across multiple rows.

<!-- end list -->

```html
<div class="grid grid-cols-4 gap-4">
  <div class="col-span-2 h-16 rounded-lg bg-blue-500"></div>
  <div class="h-16 rounded-lg bg-blue-500"></div>
  <div class="h-16 rounded-lg bg-blue-500"></div>
  <div class="h-16 rounded-lg bg-blue-500"></div>
  <div class="col-span-3 h-16 rounded-lg bg-blue-500"></div>
  <div class="h-16 rounded-lg bg-blue-500"></div>
</div>
```

-----

## 📱 Responsive Design (Mobile-First)

Tailwind uses a **mobile-first** breakpoint system. This means unprefixed utilities (like `uppercase`) apply to all screen sizes, while prefixed utilities (like `md:uppercase`) only apply at the specified breakpoint *and above*.

**Default Breakpoints:**

  * **`sm`**: 640px
  * **`md`**: 768px
  * **`lg`**: 1024px
  * **`xl`**: 1280px
  * **`2xl`**: 1536px

You can target a specific range by combining a `min-width` breakpoint with a `max-width` modifier. For example, `md:max-lg:bg-green-500` will only apply on "medium" screens.

```html
<div class="grid grid-cols-1 gap-4 md:grid-cols-2 lg:grid-cols-4">
  <div class="h-24 rounded-lg bg-violet-500"></div>
  <div class="h-24 rounded-lg bg-violet-500"></div>
  <div class="h-24 rounded-lg bg-violet-500"></div>
  <div class="h-24 rounded-lg bg-violet-500"></div>
</div>

<div class="hidden md:block">
 <p>I only appear on screens 768px and wider!</p>
</div>
```

For more details, see the [Responsive Design documentation](https://tailwindcss.com/docs/responsive-design).

-----

## 🌙 Dark Mode

Tailwind includes a `dark` variant that lets you style your site differently when dark mode is enabled. You can base it on the user's system preference or toggle it manually with a class.

To enable dark mode, add `darkMode: 'selector'` to your `tailwind.config.js` file.

```js
// tailwind.config.js
module.exports = {
  darkMode: 'selector',
  // ...
}
```

Then, you can apply the `dark` variant to any utility class. It will be applied when an ancestor element has the `.dark` class.

```html
<html>
<body class="bg-white dark:bg-slate-900">

  <div class="bg-slate-200 text-black dark:bg-slate-800 dark:text-white">
    <h1 class="text-xl font-bold">This is a title</h1>
    <p>This component will have a light background in light mode and a dark background in dark mode.</p>
  </div>

</body>
</html>
```

See the [Dark Mode documentation](https://tailwindcss.com/docs/dark-mode) for more information.

-----

## ✨ Shadows

Tailwind provides utilities for both `box-shadow` and `drop-shadow`.

  * **Box Shadow (`shadow-`**): Applies a shadow to the element's box itself. Perfect for cards and UI elements.

      * Utilities: `shadow-sm`, `shadow`, `shadow-md`, `shadow-lg`, `shadow-xl`, `shadow-2xl`, `shadow-inner`.

  * **Drop Shadow (`drop-shadow-`**): Applies a shadow that conforms to the shape of the content within the element, ignoring the bounding box. This is great for text or transparent images.

      * Utilities: `drop-shadow-sm`, `drop-shadow`, `drop-shadow-md`, `drop-shadow-lg`, `drop-shadow-xl`, `drop-shadow-2xl`.

<!-- end list -->

```html
<div class="m-4 rounded-lg bg-white p-6 shadow-xl">
  I have a box-shadow.
</div>

<div class="m-4 text-5xl font-bold text-white drop-shadow-lg">
  I have a drop-shadow!
</div>
```

For more advanced examples, visit the documentation for [Box Shadow](https://tailwindcss.com/docs/box-shadow) and [Drop Shadow](https://tailwindcss.com/docs/drop-shadow).
