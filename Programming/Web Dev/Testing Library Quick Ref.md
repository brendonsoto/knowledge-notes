---
aliases: 
created: 2022-08-23, 5:05:17 pm (Tuesday, August 23rd)
updated: 2022-08-23, 5:07:25 pm (Tuesday, August 23rd)
---
A collection of articles for quick reference.

[Asserting elements are not present](https://testing-library.com/docs/guide-disappearance/#asserting-elements-are-not-present)

[Cheatsheet](https://testing-library.com/docs/react-testing-library/cheatsheet/)
The [queries](https://testing-library.com/docs/react-testing-library/cheatsheet/#queries) section is useful for comparing the different `{get|find|query}*By` functions

[ESLint rules](https://github.com/testing-library/eslint-plugin-testing-library#supported-rules)

[Full Example](https://testing-library.com/docs/react-testing-library/example-intro)

[How to match by text](https://testing-library.com/docs/queries/about#textmatch)

Links:
Use `screen.getByRole('link')` to grab links
For types, `screen.getAllByRole('link') as HTMLAnchorElement[];`
Then for checking href, you can just use the `.href` property of the anchor elements.

[Jest DOM](https://testing-library.com/docs/ecosystem-jest-dom/)
[Matchers](https://github.com/testing-library/jest-dom#custom-matchers) (e.g. `.toBeInTheDocument()`, `toBeDisabled()`)

[Jest expect API](https://jestjs.io/docs/expect)