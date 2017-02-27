# HTML & CSS/SCSS Guidelines


### HTML - Syntax

1. Use soft tabs with two (2) spaces.
2. Always use double quotes for attributes.
3. Never omit optional closing tags (eg. `</li>`, `</body>`, etc.)


### HTML - Rules

1. Always start with <!DOCTYPE html>
2. Include language attribute into your html tag.
3. Use IE compatibility mode, like
   `<meta http-equiv=“X-UA-Compatible” content=“IE=Edge”>`
4. Always assign charset into your meta, like
   `<meta charset=“UTF-8”>`
5. CSS & JS includes doesn’t need `text/css` or `text/javascript` because they are respective defaults.
6. Attribute Ordering should be:
   * `id, name`,
   * `class`, `data-*`,
   * `src`, `for`, `type`, `href`, `value`,
   * `title`, `alt`,
   * `role`, `aria-*`
7. Always use classes instead of `id`s whereas possible, other than modal-triggering, etc.
8. Boolean Attributes - Do not add values to boolean attributes such as `checked`, `disabled`, etc. (not its value) as its presence of boolean attribute represents its true value & the absence represents its false value.
9. Reduce markup wherever possible.
10. Use javascript markups as low as possible.


### CSS/SASS - Syntax

1. Use soft tabs with two (2) spaces.
2. When grouping selectors keep individual selectors to a single line.
3. Include one space before the opening brace `{` of the declaration block.
4. Place closing braces `}` of declaration blocks in new line.
5. Use one space after each colon `:` declaration.
6. Each declaration should appear in its own line.
7. End all declarations with a semi-colon `;`, whether its the last declaration. Same follows for inline HTML styling as well)
8. Comma-separated property values should include space (` `) after each comma `,`. Foe ex: `color: rgba(0, 0, 0, 0.2)`;
9. Use either **all-caps** or **all-smalls** hex values inside a project.
10. Use shorthand hex values wherever possible. For ex: color: `#fff`;
11. Use quotes in values of quote attributes, such as use `input[type=“text”]` instead of `input[type=text]`
12. Avoid specifying units in for zero (0) values, such as use `margin: 0;` instead of `margin: 0px;`


### CSS/SASS - Rules

1. Declaration Order: Positioning, Box Model, Typography, Visual, Misc.
2. Try not use @import wherever possible. Instead use multiple `<link>` elements. (Can be ignored in SASS/SCSS)
3. Place media queries as close as their relevant rule-sets in case of CSS. In SASS use media queries inside the selector (just by inheriting it)
4. Prefixed properties should follow a pattern.
5. For single declarations use a single line. For ex: `.icon { background-position: 0 0; }`
6. Use shorthand notations whenever you need it. For example if you need to assign margins for more than 2 directions use shorthand.
7. Avoid unnecessary nesting in SASS/SCSS. Try not to nest your SASS/SCSS more than 3 levels (keep it as low as possible).
8. Keep your class names small & use dashes (no underscores or camelCase).
9. Use descriptive class names. Try to keep them small wherever possible.
10. Prefix classes based on the closest parent.
11. Use `.js-*` class names to denote the behaviour, but do not use them inside your CSS/SASS.
12. These all applies to SASS/SCSS variable names as well.


### CSS/SASS - Comments

1. Use descriptive comments rather to just defining the class name itself. For example,
    * Instead of using `/* Modal Header */`
    * Use `/* Wrapping element for modal-title & modal-close */`
2. Use consistent commenting hierarchy.
3. Do not use more than 80 columns per line.
4. Always assign master comments for a big components/pages in different style and normal comments in different style.


### SASS/SCSS Specific - Rules

1. Use Prepros as our SASS/SCSS compiler to maintain consistency. Enable Autoprefixing & Sourcemapping by default.
2. Define a proper structure of your SASS structure to start with. Have a look at “SASS Structuring - Rules”.
3. Don’t use more than 3 levels (keep it as low as possible) of nesting in your SASS/SCSS.
4. Use ‘&’ wherever possible, such as `:hover`, `:after`, `:before`, and many others.
5. Use SASS/SCSS functions such as `mix`, `darken`, `lighten` for blending colors while hovering, selecting etc.
6. Use empty lines whenever required.
7. Use `!default` & `!global` wherever possible in variables.
