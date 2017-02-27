# HTML & CSS/SCSS Guidelines
General HTML, CSS & SASS Guidelines.

### Table of Contents:
   * [**HTML**](https://github.com/saurav12/HTML-CSS-SASS-Guidelines#html)
      * [HTML - Syntax](https://github.com/saurav12/HTML-CSS-SASS-Guidelines#html---syntax)
      * [HTML - Rules](https://github.com/saurav12/HTML-CSS-SASS-Guidelines#html---rules)
      * [HTML - Example](https://github.com/saurav12/HTML-CSS-SASS-Guidelines#html---example)
      
   * [**CSS/SASS**](https://github.com/saurav12/HTML-CSS-SASS-Guidelines#csssass)
      * [CSS/SASS - Syntax](https://github.com/saurav12/HTML-CSS-SASS-Guidelines#csssass---syntax)
      * [CSS/SASS - Example](https://github.com/saurav12/HTML-CSS-SASS-Guidelines#csssass---example)
      * [CSS/SASS - Rules](https://github.com/saurav12/HTML-CSS-SASS-Guidelines#csssass---rules)
      * [CSS/SASS - Comments](https://github.com/saurav12/HTML-CSS-SASS-Guidelines#csssass---comments)
      
   * [**SASS/SCSS Structuring**](https://github.com/saurav12/HTML-CSS-SASS-Guidelines#sassscss-structuring)

HTML
-----

### HTML - Syntax

1. Use soft tabs with two (2) spaces.
2. Always use double quotes for attributes.
3. Never omit optional closing tags (eg. `</li>`, `</body>`, etc.)


### HTML - Rules

1. Always start with **`<!DOCTYPE html>`**
2. Include language attribute into your html tag, like:
   ```html
   <html lang="en-us">
      <!-- ... -->
   </html>
   ```
3. Use IE compatibility mode, like:
   ```html
   <meta http-equiv=“X-UA-Compatible” content=“IE=Edge”>
   ```
   
4. Always assign charset into your meta, like:
   ```html
   <meta charset=“UTF-8”>
   ```
   
5. Use viewport meta information for supporting responsiveness to your template, eg:
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1.0, minimum-scale=1.0, user-scalable=no">
   ```
   
6. CSS & JS includes doesn’t need **`text/css`** or **`text/javascript`** because they are respective defaults.
7. Attribute Ordering - should be in a particular order for ease of reading of code:
   * `id`, `name`,
   * `class`, `data-*`,
   * `src`, `for`, `type`, `href`, `value`,
   * `title`, `alt`,
   * `role`, `aria-*`
8. Use **`id`'s** in camelCase & **classes** in dash format. Like:
   ```html
   <div id="myId" class="my-class"></div>
   ```
   
9. Always use **classes** instead of **`id`'s** wherever possible, other than modal-triggering, etc.
10. Boolean Attributes - Do not add values to boolean attributes such as **`checked`**, **`disabled`**, etc. (not its value) as its presence of boolean attribute represents its true value & the absence represents its false value.
11. Reduce markup wherever possible.
12. Use javascript markups as low as possible.


### HTML - Example
General structure of your HTML should look like:

```html
<!DOCTYPE html>
<html lang="en-us">
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1.0, minimum-scale=1.0, user-scalable=no">
    <meta http-equiv=“X-UA-Compatible” content=“IE=Edge”>
    <meta charset=“UTF-8”>
    <title>Page title</title>
  </head>
  <body>
    <img id="companyLogo" src="images/company-logo.png" alt="Company">
    <h1 class="hello-world">Hello, world!</h1>
  </body>
</html>
```

CSS/SASS
-----

### CSS/SASS - Syntax

1. Use soft tabs with two (2) spaces.
2. When grouping selectors keep individual selectors to a single line, like:
3. Include one space before the opening brace **`{`** of the declaration block, Like:
4. Place closing braces **`}`** of declaration blocks in new line.
5. Use one space after each colon **`:`** for each declaration.
6. Each declaration should appear in its own line.
7. End all declarations with a semi-colon **`;`**, whether its the last declaration. Same follows for inline HTML styling as well.
8. Comma-separated property values should include space (` `) after each comma **`,`**. For ex: **`color: rgba(0, 0, 0, 0.2)`;**
9. Use either **all-caps** or **all-smalls** hex values all over the project.
10. Use shorthand hex values wherever possible. For ex: color: **`#fff`**;
11. Use quotes in values of quote attributes, such as use **`input[type=“text”]`** instead of **`input[type=text]`**.
12. Avoid specifying units in for zero (0) values, such as use **`margin: 0;`** instead of **`margin: 0px;`**

### CSS/SASS - Example
This covers all the above points.

```css
.selector,
.selector-secondary,
.selector[type="text"] {
   padding: 15px;
   margin-bottom: 15px;
   background-color: rgba(0, 0, 0, 0.5);
   box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```


### CSS/SASS - Rules

1. Declaration Order: **Positioning**, **Box Model**, **Typography**, **Visual**, **Misc**. Example:
   ```css
   .declaration-order {
     /* Positioning */
     position: absolute;
     top: 0;
     right: 0;
     bottom: 0;
     left: 0;
     z-index: 100;

     /* Box-model */
     display: block;
     float: right;
     width: 100px;
     height: 100px;

     /* Typography */
     font: normal 13px "Helvetica Neue", sans-serif;
     line-height: 1.5;
     color: #333;
     text-align: center;

     /* Visual */
     background-color: #f5f5f5;
     border: 1px solid #e5e5e5;
     border-radius: 3px;

     /* Misc */
     opacity: 1;
   }
   ```

2. Try not use **`@import`** wherever possible. Instead use multiple **`<link>`** elements. (Can be ignored in SASS/SCSS)
3. Place media queries as close as their relevant rule-sets in case of CSS. In SASS use media queries inside the selector (just by inheriting it)
4. Prefixed properties should follow a pattern.
5. For single declarations use a single line. For ex:
   ```css
   .icon { background-position: 0 0; }.
   ```
   
6. Use shorthand notations whenever you need it. For example if you need to assign margins for more than 2 directions use shorthand. For ex:
   ```css
   .selector {
      margin: 0 10px 10px 0; // margin for top, right, bootm & left respectively
   }
   ```
   
7. Avoid unnecessary nesting in SASS/SCSS. Try not to nest your SASS/SCSS more than 3 levels (keep it as low as possible). Example:
   ```css
   .parent-selector {
   
      .child-one {  
         .child-one-one { ... } // do not inherit more than 3 levels
      }
      
      .child-two { ... }
   }
   ```
   
8. Keep your class names small & use dashes (no underscores or camelCase). Also discussed in HTML.
9. Use descriptive class names. Try to keep them small wherever possible.
10. Prefix classes based on the closest parent. Ex:
   ```css
   modal--header-title { ... }
   modal--header-subtitle { ... }
   ```
   
11. Use **`.js-*`** class names to denote the behaviour, but do not use them inside your CSS/SASS.
12. These all applies to SASS/SCSS variable names as well.

### CSS/SASS - Comments

1. Use descriptive comments rather to just defining the class name itself. For example,
    * Instead of using `/* Modal Header */`
    * Use `/* Wrapping element for modal-title & modal-close */`
2. Use consistent commenting hierarchy.
3. Do not use more than 80 columns per line.
4. Always assign master comments for a big components/pages in different style and normal comments in different style. You can use **`//`** comments in SASS, like:
   ```sass
   // ######################################## //
   // ## MODALS.SCSS ## //
   // ######################################## //
   ```

### SASS/SCSS Specific - Rules

1. Use **Prepros** for SASS/SCSS compilation to maintain consistency. Enable **Autoprefixing** & **Sourcemapping** by default.
2. Define a proper structure of your SASS structure to start with. Have a look at [SASS/SCSS Structuring](https://github.com/saurav12/HTML-CSS-SASS-Guidelines#sassscss-structuring).
3. Don’t use more than 3 levels (keep it as low as possible) of nesting in your SASS/SCSS.
4. Use ‘&’ wherever possible, such as **`:hover`**, **`:after`**, **`:before`**, and many others.
5. Use SASS/SCSS functions such as **`mix`**, **`darken`**, **`lighten`** for blending colors while hovering, selecting etc.
6. Use empty lines whenever required.
7. Use **`!default`** & **`!global`** wherever possible in variables.


SASS/SCSS Structuring
-----
```
sass/ 
| 
|– base/ 
|   |– _reset.scss       # Reset/normalize 
|   |– _typography.scss  # Typography rules 
|   ...                  # Etc… 
| 
|– helpers/ 
|   |– _variables.scss   # Sass Variables 
|   |– _functions.scss   # Sass Functions 
|   |– _mixins.scss      # Sass Mixins 
|   |– _helpers.scss     # Class & placeholders helpers 
|   ...                  # Etc… 
|
|– components/ 
|   |– _buttons.scss     # Buttons 
|   |– _carousel.scss    # Carousel 
|   |– _cover.scss       # Cover 
|   |– _dropdown.scss    # Dropdown 
|   |– _navigation.scss  # Navigation 
|   ...                  # Etc… 
| 
|– layout/ 
|   |– _grid.scss        # Grid system 
|   |– _header.scss      # Header 
|   |– _footer.scss      # Footer 
|   |– _sidebar.scss     # Sidebar 
|   |– _forms.scss       # Forms 
|   ...                  # Etc… 
| 
|– pages/ 
|   |– _home.scss        # Home specific styles 
|   |– _contact.scss     # Contact specific styles 
|   ...                  # Etc… 
| 
|– themes/ 
|   |– _theme.scss       # Default theme 
|   |– _admin.scss       # Admin theme 
|   ...                  # Etc… 
| 
|– vendors/ 
|   |– _bootstrap.scss   # Bootstrap 
|   |– _jquery-ui.scss   # jQuery UI 
|   ...                  # Etc… 
| 
| 
`– main.scss             # primary Sass file
```

### References
* [Github Styleguide](http://primercss.io/scaffolding/)
* [Code Guide by @mdo](http://codeguide.co/)
* [CSS Guidelines](http://cssguidelin.es/)
* [SASS Guidelines](https://sass-guidelin.es/)
