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

- [REPL: BASIC EXAMPLE](https://svelte-5-preview.vercel.app/#H4sIAAAAAAAACm1Q0UrDQBD8lWMRqlApCoJckkLQIn3RoOKL58Ml2cSjl7vjbtNSQv5drkErpY87MzszuwM0SmMA_jmAkR0Ch9w5mAPtXRzCFjUhzCHY3lcRSUPllSOmpWkzARQELIURpDpnPbGBFbJVRpKyZk3YBTayxtuOzdwffj25zpK4p5FYIEmYV6S2WMgWWcYuDtDlzVUiTLqYImOMSU_so4Xz1r3L2KbsiawR8Is-qiBLjfUb7TVGXlab1tve1JzV0m9aj_vkKJ8qnBOXusekstp6vvtWhP-WnvuuRP_SvNpdyIbb-_EcUaCPl2XD3YEulan5MXGiTr4wCrNYCpO6w3vzh_f1x4oV-dOKszPSdBF1MIfO1qpRWAMn3-P4Nf4AL9AyN-MBAAA=)
- [REPL: BOOTSTRAP EXAMPLE](https://svelte-5-preview.vercel.app/#H4sIAAAAAAAACnVS70_bMBD9VyxrEptEa0phYiFBqwpDnRCUUSFN8z64yTUx8y_Zl7BS9X-fkjRtV22f4rv37l3u3q3oQioINPqxokZooBEdOUePKS5dHYQKFAI9psGWPq0zcUi9dEiUMHnCKQZOr7jhKLWzHsmKTEUujUBpzQRBB7ImC281OXLbfK9VPbrkpq5UgCSgQBilKCuYihxIQt41qfeDD5fcxKxtWjcycVsdFSCypnOspPlVPzgWHhYJpwWiCxFjaWb6LyEDJSvfN4DMOM3m1mJAL9zn8_5J_5RlMiBLQ9gBfS1NPw2B01bVg0o4DbhUEAoA7PLSIORe4rJGCzG8OOvdPD_NHu-HTLw5fzsYGT18vM7d17uJ_nQv7Mn3t8Ebpo-z1y_BZcPl9cfzZ1sUrizHD_pu9PQy7qRTb0OwXubSJJwKY81S23LzR-yqWcnfazBxJiuSKhFCwqnunW18iY2oiPBS9JSYN4M0CzaiknnjBoHfQjsFGz7HuFRbnZ1pW5hjfGBxl-fovHUzUd-Fkt0ozTg7OehJBL0P1kUTY8CP91mNqQesaxnEXEHWEbNNfMhrD6ljiSY65NyXeg7-YfHNvoZkdXqx_j88BV_vLFmd75Hm0mTRrllLODjjLZ11q2Wlal1hRlTtK5PVBh2NZ5PnGzId3d5E5J9aMWvZ3ZceU20zuZCQ0Qh9Ceuf6z9ey0tY0wMAAA==)
- [REPL: SHORT MODE EXAMPLE](https://svelte-5-preview.vercel.app/#H4sIAAAAAAAACm1QW0vDMBT-K-EgTGFSfdCHXgZFhwy8DDZ8MT6k7WkXliYhOZ2M0v8uWZmTscfz3Tk91FKhh_irBy1ahBhya2EKtLfh8DtUhDAFbzpXBiT1pZOWmBK6yTiQ5zDjmpNsrXHEerYUjdSCpNELwtazgdXOtGxi__DbMXWSBJ9CYp4EYV6S3OFSNMgydnWAru9vEq7TaKwMNTo9iw8R1hm7FmFN0REZzeGIPksvCoXVivYKAy_KbeNMp6uYVcJtG4f75CQfJ1wSF6rDpDTKuPhnIwn_md67tkD3UYflPusf74Yjs9oYR2-mwlfZSsr6h5EqpK7iU13wZf3ZCwauoxnXqT38Nn9aLz7nbJm_zGN2QZpGQQdTaE0la4kVxOQ6HL6HXx-trV3gAQAA)

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
