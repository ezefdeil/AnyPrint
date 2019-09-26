#  Welcome to AnyPrint.js

This is a Javascript library that allows you to print a part of your HTML website

### Prerequisites

Nothing! ;)

### Installing

Put the reference to AnyPrint.js in your HTML

```html
<script src="~/js/AnyPrint.js"></script>
```
## Usage

Optional: You can add options using **AnyPrint.config(options)**

You have two options to print

### Using id:

1) Put any **id** in your HTML code
	```html
	<div id="printableDiv">...</div>
	```
2) Print this HTML element using **AnyPrint.Print('printableDiv')**

### Using attribute
1) Put **anyPrint attribute** on each element that you need print
	```html
	<div anyPrint>...</div>
	...
	...
	<div anyPrint>...</div>
	```
2) Simple use **AnyPrint.Print()**

**Note:** in XHTML you need use **anyPrint="anyPrint"**

### Hide or force to show elements
The attribute **showOnPrint** can toogle visibility on print window

```html
showOnPrint="hidden"  <!--Hidden on print-->
showOnPrint="visible" <!--Visible on print although element have class="hidden" or display:none;-->
```

### Options example:
```javascript
var options = {
	title: "My Custom Title",
	appendDate: true,
	removeHeaderAndFooter: true
}
AnyPrint.config(options);
AnyPrint.Print('printableDiv');
```

## Usage Example using id

```html
<h2>
	This block **will printed**
</h2>
<div id="printableDiv">
    <h2>
        Here start the printable HTML
    </h2>
    <p showOnPrint="hidden">This text is HIDDEN on print</p>
	<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
    <p style="display:none;" showOnPrint="visible">This text is VISIBLE only on print</p>    
</div>

<button type="button" onclick="AnyPrint.Print('printableDiv')">Print!</button>
```

## Usage Example using attribute

```html
<h2>
	This title is out of printable HTML
</h2>
<div anyPrint>
    <h2>
        Here start the printable HTML
    </h2>
    <p showOnPrint="hidden">This text is HIDDEN on print</p>
    <p style="display:none;" showOnPrint="visible">This text is VISIBLE only on print</p>    
</div>

<h2>
	This block **will not printed** because haven't the **anyPrint attribute**
</h2>
<div>
    <h2>
        Here start the printable HTML
    </h2>
    <p showOnPrint="hidden">This text is HIDDEN on print</p>
    <p style="display:none;" showOnPrint="visible">This text is VISIBLE only on print</p>    
</div>

<h2>
	This block **will printed** also.
</h2>
<div anyPrint>
    <h2>
        Here start the printable HTML
    </h2>
    <p showOnPrint="hidden">This text is HIDDEN on print</p>
	<p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
    <p style="display:none;" showOnPrint="visible">This text is VISIBLE only on print</p>    
</div>

<button type="button" onclick="AnyPrint.Print()">Print!</button>
```


## License

This project is licensed under the MIT License - see the [LICENSE.MD](LICENSE.MD) file for details

## Acknowledgments
This project has been inspirated in many answers of StackOverflow

* (https://stackoverflow.com/questions/19829743/how-to-dynamically-print-iframe)
* (https://stackoverflow.com/questions/2255291/print-the-contents-of-a-div)
* (https://stackoverflow.com/questions/217776/how-to-apply-css-to-iframe)
