# stabilo.js
A javascript highlighter from search field.

## Description
This filter highlights all the  matching text provided in a search field. This matches
any string with an insensitive case and ignores accents. You can customize the selectors
for the filter search and display non-matching blocks.

## How to use

### Filter method

The javascript method to use to apply filter is the following:
```js
applyFilter(elmt, elmSelector, parentSelector, underlineClass, hideOnFilter, counterId)
```


var DEFAULT_ELEMENT_SELECTOR = ".element";
var DEFAULT_PARENT_SELECTOR = ".elements-container";
var DEFAULT_UNDERLINE_CLASS = "underline";
var DEFAULT_COUNTER_ID = "filter-counter";
var DEFAULT_FILTER_HIDE = false;

With parameters:

| Parameter        | Type      | Required | Default value         | Description                                                     |
|:-----------------|:----------|:---------|:----------------------|:----------------------------------------------------------------|
| `elmt`           | "object"  | YES      | N/A                   | The search field input                                          |
| `elmSelector`    | "string"  | NO       | ".element"            | The elements in wich to search (jQuery)                         |
| `parentSelector` | "string"  | NO       | ".elements-container" | The parent element containing search elements (jQuery)          |
| `underlineClass` | "string"  | NO       | "underline"           | The class to apply for highligting                              |
| `hideOnFilter`   | "boolean" | NO       | `false`               | Define if non-containing filter content elements must be hidden |
| `counterId`      | "string"  | NO       | "filter-counter"      | The counter element id to display results                       |

### Default configuration

```html
	<input type="search"
		   onkeyup="applyFilter(this);"
		   onsearch="this.onkeyup();"
		   placeholder="Search...">
	<span id="filter-counter" class="filter-counter"> </span>
	<div class="elements-container">
		<div class="element" style="display: block;">
			<span>Probably a title</span>
			<p>Some random text that no one read</p>
			<span>what about a date 2017-07-17</span>
		</div>
		...
	</div>
```

### Custom configuration

```html
	<input type="search"
		   onkeyup="applyFilter(this, '.elem', '.cont', 'green', true, 'counter');"
		   onsearch="this.onkeyup()"
		   placeholder="Search">
	<span id="counter" class="filter-counter"> </span>
	<div class="cont">
		<div class="elem" style="display: block;">
			<span>Probably a title</span>
			<p>Some random text that no one read</p>
			<span>what about a date 2017-07-17</span>
		</div>
		...
	</div>
```

## Demo

Demo is available on: https://dangeffroy.github.io/stabilo.js
