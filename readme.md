# angular-blocks

Block style template inheritance for [AngularJS](http://angularjs.org) inspired by [Jade](http://jade-lang.com) and [Handlebars](http://handlebarsjs.com).

## Usage

Given the template below:

```html
<script type="text/ng-template" id="/layout.html">
    <header data-block="header">
        <p>:header</p>
    </header>
    <div data-block="content">
        <p>:content</p>
    </div>
    <footer data-block="footer">
        <p>:footer</p>
    </footer>
</script>
```

### Block Replace: `data-block`

```html
<div data-extend-template="/layout.html">
   <div data-block="content">
       <p>Foo</p>
   </div>
</div>
```

Becomes:

```html
<div data-extend-template="/layout.html">
    <header data-block="header">
        <p>:header</p>
    </header>
    <div data-block="content">
        <p>Foo</p>
    </div>
    <footer data-block="footer">
        <p>:footer</p>
    </footer>
</div>
```

### Block Prepend: `data-block-prepend`

```html
<div data-extend-template="/layout.html">
   <div data-block-prepend="content">
       <p>Foo</p>
   </div>
</div>
```

Becomes:

```html
<div data-extend-template="/layout.html">
    <header data-block="header">
        <p>:header</p>
    </header>
    <div data-block="content">
       <div data-block-prepend="content">
           <p>Foo</p>
       </div>
       <p>:content</p>
    </div>
    <footer data-block="footer">
        <p>:footer</p>
    </footer>
</div>
```

### Block Append: `data-block-append`

```html
<div data-extend-template="/layout.html">
   <div data-block-append="content">
       <p>Foo</p>
   </div>
</div>
```

Becomes:

```html
<div data-extend-template="/layout.html">
    <header data-block="header">
        <p>:header</p>
    </header>
    <div data-block="content">
       <p>:content</p>
       <div data-block-append="content">
           <p>Foo</p>
       </div>
    </div>
    <footer data-block="footer">
        <p>:footer</p>
    </footer>
</div>
```

### Block Before: `data-block-before`

```html
<div data-extend-template="/layout.html">
   <div data-block-before="content">
       <p>Foo</p>
   </div>
</div>
```

Becomes:

```html
<div data-extend-template="/layout.html">
    <header data-block="header">
        <p>:header</p>
    </header>
   <div data-block-before="content">
       <p>Foo</p>
   </div>
    <div data-block="content">
       <p>:content</p>
    </div>
    <footer data-block="footer">
        <p>:footer</p>
    </footer>
</div>
```

### Block After: `data-block-after`

```html
<div data-extend-template="/layout.html">
   <div data-block-after="content">
       <p>Foo</p>
   </div>
</div>
```

Becomes:

```html
<div data-extend-template="/layout.html">
    <header data-block="header">
        <p>:header</p>
    </header>
    <div data-block="content">
       <p>:content</p>
    </div>
   <div data-block-after="content">
       <p>Foo</p>
   </div>
    <footer data-block="footer">
        <p>:footer</p>
    </footer>
</div>
```

## Installation

Load `angular-blocks.min.js` then add the `angular-blocks` module to your Angular app.


```javascript
angular.module('app', ['angular-blocks']);
```


## Licsense

Copyright (c) 2013 William L. Bunselmeyer. https://github.com/wmluke/angular-blocks

Licensed under the MIT License