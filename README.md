# pagination-svelte

![GITHUB VERSION](https://img.shields.io/github/package-json/v/joaquimnetocel/pagination-svelte?label=github%20version&logo=github&color=lightgray) ![NPM VERSION](https://img.shields.io/npm/v/pagination-svelte?color=red&logo=npm&label=npm%20version) ![NPM Downloads](https://img.shields.io/npm/dw/pagination-svelte?color=red&label=npm%20downloads&logo=npm) ![NPM License](https://img.shields.io/npm/l/pagination-svelte?color) [![Twitter](https://img.shields.io/twitter/follow/:twitterHandle.svg?style=social&label=@joaquimnetocel)](https://twitter.com/joaquimnetocel)

Pagination is an excellent method for organizing website content into separate pages so users can find the desired page/content. It is a feature we can use on a blog page, a product page, or any other page with a lot of content that we want to distribute across multiple pages.

**pagination-svelte** is a light weight svelte component that enables the user to select a specific page from a range of pages. The component's formatting was inspired by bootstrap. Really just an inspiration, since the component doesn't rely on bootstrap to work.

![PAGINATION](./image.png)

## DEMO

[REPL: BASIC EXAMPLE](https://svelte.dev/repl/1cb3d1d2e60546569c80258abb5834e5)

## INSTALLATION

```bash
npm install pagination-svelte
```

## HOW TO USE IT

```svelte
<script>
    import Pagination from 'pagination-svelte';
    let page = 1;
</script>

<p>THE SELECTED PAGE IS: {page}</p>

<Pagination
    propNumberOfPages={7}
    bind:propActivePage={page}
    on:eventChange={(parEvent) => console.log(parEvent.detail.numberActivePage)}
/>
```

## PROPS

* BEHAVIOR PROPS:

| PROP                      | TYPE                           | DEFAULT         | DESCRIPTION                                             |
| ------------------------- | ------------------------------ | --------------- | ------------------------------------------------------- |
| `propActivePage`          | `number`                       | `1`             | The selected/active page (bind to this prop)            |
| `propNumberOfPages`       | `number`                       | `5`             | The total number of pages. If `propNumberOfRows` is different from `undefined`, this property will not be used. |
| `propPrevious`            | `string`                       | `PREVIOUS`      | Text of the previous button.                            |
| `propNext`                | `string`                       | `NEXT`          | Text of the next button.                                |
| `propSize`                | `normal` OR `small` OR `large` | `normal`        | Size of the component.                                  |

* FORMATING PROPS

| PROP                       | TYPE                                     | DEFAULT          | DESCRIPTION                                 |
| -------------------------- | ---------------------------------------- | ---------------- | ------------------------------------------- |
| `cssActiveBackgroundColor` | `string` (RGB, RGBA, HEX OR COLOR NAME)  | `#0d6efd` (blue) | Background color of the active page.        |
| `cssBackgroundColor`       | `string` (RGB, RGBA, HEX OR COLOR NAME)  | `#fff` (white)   | Background color of the inactive pages.     |
| `cssHoverBackgroundColor`  | `string` (RGB, RGBA, HEX OR COLOR NAME)  | `#f8f9fa`        | Background color (when hover).              |
| `cssActiveFontColor`       | `string` (RGB, RGBA, HEX OR COLOR NAME)  | `white`          | Font color of the active page.              |
| `cssFontColor`             | `string` (RGB, RGBA, HEX OR COLOR NAME)  | `#f8f9fa`        | Font color of the inactive pages.           |
| `cssHoverFontColor`        | `string` (RGB, RGBA, HEX OR COLOR NAME)  | `#0a58ca`        | Font color of the inactive pages (when hover). |
| `cssActiveBorderColor`     | `string` (RGB, RGBA, HEX OR COLOR NAME)  | `#0d6efd` (blue) | Border color of the active page.            |
| `cssDisabledColor`         | `string` (RGB, RGBA, HEX OR COLOR NAME)  | `rgba(33, 37, 41, 0.75)` | Font color of disabled buttons.     |
| `cssBorderColor`           | `string` (RGB, RGBA, HEX OR COLOR NAME)  | `#dee2e6`        | Border color.                               |
| `cssBorderWidth`           | `string` (rem OR px)                     | `1px`            | Border width.                               |

## EVENTS

* **on:eventChange**

## DEVELOPING

Once you've created a project and installed dependencies with `npm install`, start a development server:

```bash
npm run dev
```
