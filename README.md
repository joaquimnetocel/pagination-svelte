# pagination-svelte

![GITHUB VERSION](https://img.shields.io/github/package-json/v/joaquimnetocel/pagination-svelte?label=github%20version&logo=github&color=lightgray) ![NPM VERSION](https://img.shields.io/npm/v/pagination-svelte?color=red&logo=npm&label=npm%20version) ![NPM Downloads](https://img.shields.io/npm/dw/pagination-svelte?color=red&label=npm%20downloads&logo=npm) ![NPM License](https://img.shields.io/npm/l/pagination-svelte?color) [![Twitter](https://img.shields.io/twitter/follow/:twitterHandle.svg?style=social&label=@joaquimnetocel)](https://twitter.com/joaquimnetocel)

Pagination is an excellent method for organizing website content into separate pages so users can find the desired page/content. It is a feature we can use on a blog page, a product page, or any other page with a lot of content that we want to distribute across multiple pages.

**pagination-svelte** is a light weight svelte component that enables the user to select a specific page from a range of pages.

![PAGINATION](./image.png)

## VERSIONS

- VERSION 1.0.0 OR ABOVE WORKS WITH SVELTE 5 ONLY (NEWER AND RECOMMENDED VERSIONS WITH IMPROVEMENTS!)
- PREVIOUS VERSIONS WORKS WITH SVELTE 3, 4 AND 5.

## FEATURES

- NON-OPINIONATED STYLING.
- NON-OPINIONATED POSITIONING.
- TYPESCRIPT SUPPORT.

## INSTALLATION

```bash
npm install pagination-svelte
```

## DEMO

- [REPL: BASIC EXAMPLE](https://svelte.dev/repl/1cb3d1d2e60546569c80258abb5834e5)
- [REPL: BOOTSTRAP EXAMPLE](https://svelte.dev/repl/00a67cfddc074cbbb22823f46fc5cc76)
- [REPL: SHORT MODE EXAMPLE](https://svelte.dev/repl/6208d3cbba394a14bb5a7529f78748b6)

## EXAMPLES AND DEVELOPING

To run the examples from `/src/routes`:

```bash
git clone https://github.com/joaquimnetocel/pagination-svelte.git
cd pagination-svelte
npm install
npm run dev
```

## COMPONENT STRUCTURE

- PaginationItems: A svelte component for pagination.

## PROPS

| PROP                        | DESCRIPTION                                                                                                              | TYPE                                         | REQUIRED | DEFAULT |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------- | -------- | ------- |
| `propActivePage` (bindable) | ACTIVE PAGE.                                                                                                             | `number`                                     | NO       | 1       |
| `propNumberOfRows`          | TOTAL NUMBER OF ROWS.                                                                                                    | `number`                                     | NO       | -       |
| `propNumberOfRowsPerPage`   | TOTAL NUMBER OF ROWS PER PAGE.                                                                                           | `number`                                     | NO       | -       |
| `propNumberOfPages`         | TOTAL NUMBER OF PAGES. IF `propNumberOfRows` AND `propNumberOfRowsPerPage` ARE INFORMED, THIS PROPERTY WILL NOT BE USED. | `number`                                     | NO       | 1       |
| `propTag`                   | HTML TAG OF THE PAGINATION ITEM.                                                                                         | `'span' OR 'div' OR 'li' OR 'button' OR 'a'` | YES      | -       |
| `propInnerTag`              | HTML TAG INSIDE THE PAGINATION ITEM.                                                                                     | `'span' OR 'div' OR 'li' OR 'button' OR 'a'` | NO       | `span`  |
| `propPrevious`              | PREVIOUS BUTTON TEXT.                                                                                                    | `string`                                     | NO       | -       |
| `propNext`                  | NEXT BUTTON TEXT.                                                                                                        | `string`                                     | NO       | -       |
| `propShortMode`             | IF IN SHORT MODE, PAGINATION WILL SHOW ONLY FORWARD AND BACKWARD BUTTONS.                                                | `boolean`                                    | NO       | `false` |
| `propShortModeLimit`        | IF THE NUMBER OF PAGES IS GREATER THAN `propShortModeLimit` THE SHORT MODE IS ACTIVATED.                                 | `number`                                     | NO       | `1000`  |
| `style`                     | CSS STYLES FOR PAGINATION ITEMS.                                                                                         | `string`                                     | NO       | -       |
| `class`                     | CSS CLASSES FOR PAGINATION ITEMS.                                                                                        | `string`                                     | NO       | -       |
| `propDisabledStyle`         | CSS STYLES FOR DISABLED PAGINATION ITEMS.                                                                                | `string`                                     | NO       | -       |
| `propDisabledClass`         | CSS CLASSES FOR DISABLED PAGINATION ITEMS.                                                                               | `string`                                     | NO       | -       |
| `propActiveStyle`           | CSS STYLES FOR ACTIVE PAGINATION ITEMS.                                                                                  | `string`                                     | NO       | -       |
| `propActiveClass`           | CSS CLASSES FOR ACTIVE PAGINATION ITEMS.                                                                                 | `string`                                     | NO       | -       |
| `propInnerClass`            | CSS CLASSES FOR THE TAG INSIDE PAGINATION ITEMS.                                                                         | `string`                                     | NO       | -       |
| `propInnerStyle`            | CSS CLASSES FOR THE TAG INSIDE PAGINATION ITEMS.                                                                         | `string`                                     | NO       | -       |
