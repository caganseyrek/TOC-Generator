# TOC-Generator

A simple script that uses the headings in the content of the page and automatically generates a table of contents with styling.

You can see an example image of a generated TOC in [this example image](https://github.com/caganseyrek/TOC-Generator/blob/main/example.png).

***

## Setup and Usage

First, install the `toc-generator.js` file.

Then edit the parts shown below:

```javascript
// "page-contents" is where the generator will get the header elements.
var pageContents = document.getElementById("page-contents");

// "toc" is where the generator will put the table of contents.
document.getElementById("toc").appendChild(toclist);
```

By default, the generator uses `h2`, `h3`, and `h4` elements while generating the TOC and reserves `h1` element for the page title. But if you want to include `h1` elements, just edit this variable in the `toc-generator.js` file to be `true`.

```javascript
var includeh1 = false;
```

Finally, you can add this line right before the `</body>` tag in your HTML file.

```html
<script src="/path/to/toc-generator.js"></script>
```

***

## Styling

If you don't want to deal with the styling, you can just install the `toc-style.css` file and import it into your main css file.

```css
@import url("/path/to/toc-style.css");
```

Or you can add it directly to your HTML file without importing it into your main css file by putting this line between `<head>` tags.

```html
<link rel="stylesheet" href="/path/to/toc-style.css" />
```

***

## Custom Styling

You can change main list's appearance by adding styling to the container where the script put the list (`#toc` as default). Container and sublists have these classes as default:
```css
#toc { /* your styling */ }
#toc ul { /* your styling */ }
#toc ul li { /* your styling */ }
#toc ul li a{ /* your styling */ }

.toc-sublist { /* for h2 */ }
.toc-doublesublist { /* for h3 */ }
.toc-triplesublist { /* for h4 */ }
```

When you exclude `h1` tags, all the sublists go up one heading level.
```css
.toc-sublist { /* for h3 */ }
.toc-doublesublist { /* for h4 */ }
.toc-triplesublist { /* this class is not used when h1 is not included  */ }
```
   
If you change these classes, don't forget to also update those classes' name in the `toc-generator.js` file.
