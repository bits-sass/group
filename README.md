# Bits.sass group

Group component for creating a visual connection between UI components that
belong together.

Read more about [Bits.sass toolkit](https://github.com/bits-sass/bits.sass).

## Installation

* __Bower:__ `bower install --save bits-sass-group`
* __Download:__ [zip](https://github.com/bits-sass/group/zipball/master), [tar.gz](https://github.com/bits-sass/group/tarball/master)
* __Git:__ `git clone https://github.com/bits-sass/group.git`

## Available SASS variables

* `bits-components-ns` - components namespace, defaults to 'bits-'
* `bits-group-border-width` - size of `Button` and `FormControl` border width

## Available classes

* `Group` - wrapper component around a group of `Group-item` objects
* `Group-item` - `Group` descendant used to contain other elements

## Supported components

* `Button` - [component repo](https://github.com/bits-sass/button)
* `FormControl` - [component repo](https://github.com/bits-sass/form-control)

## Usage

An element with the `Group` class must be used to wrap a collection of elements
with the `Group-item` class. The `Group` component *must* only contain
`Group-item` components as children.

The button group items may contain other components, e.g., [Bits.sass button](https://github.com/bits-sass/button)
or buttons with dropdown menus.

```html
<div class="ButtonGroup">
  <div class="ButtonGroup-item">
    <a class="Button" href="#">Dashboard</a>
  </div>
  <div class="ButtonGroup-item">
    <a class="Button" href="#">Settings</a>
  </div>
  <div class="ButtonGroup-item with-Dropdown">
    <a class="Button js-dropdownToggle" href="#">
      Account
      <i class="Icon Icon--caret"></i>
    </a>
    <div class="Dropdown">
      ...
    </div>
  </div>
</div>
```

This component intelligently removes certain `border-radius` values from
your application-level button theme.

## Customising

Your application-level CSS can build upon this component.

If your app's button theme uses a border width other than `1px`, you can adjust the
button group component to accommodate this. For example, if your buttons used
3px borders, you would add this rule to your application-level CSS:

```scss
.ButtonGroup-item {
  margin-left: -3px;
}
```

If you need to adjust the space between buttons, or buttons and button groups,
or multiple button groups, you might want to add a rule like this to your
application-level CSS:

```scss
/**
 * Add some space between adjacent .btn and .btn-group components
 */

.Button + .Button,
.Button + .ButtonGroup,
.ButtonGroup + .Button,
.ButtonGroup + .ButtonGroup {
  margin-left: 5px;
}
```

## Requirements

* Sass 3.2+

## Browser support

* Google Chrome (latest)
* Opera (latest)
* Firefox 4+
* Safari 5+
* Internet Explorer 8+