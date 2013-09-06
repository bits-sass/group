# Bits.sass group

Group component for creating a visual connection between UI components that
belong together.

Read more about [Bits.sass toolkit](https://github.com/bits-sass/bits.sass).

## Installation

* __Bower:__ `bower install --save bits-sass-group`
* __Download:__ [zip](https://github.com/bits-sass/group/zipball/master), [tar.gz](https://github.com/bits-sass/group/tarball/master)
* __Git:__ `git clone https://github.com/bits-sass/group.git`

## Demo

See [demo](https://rawgithub.com/bits-sass/group/master/demo/index.html).

## Available SASS variables

* `bits-components-ns` - components namespace, defaults to 'bits-'
* `bits-group-border-width` - size of `Button` and `FormControl` border width
* `bits-group-supported-selectors` - list of supported (ie. accounted for)
  components inside a group

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

The button group items may contain other components, e.g., [Bits.sass button]
(https://github.com/bits-sass/button), buttons with dropdown menus or
[Bits.sass form control](https://github.com/bits-sass/form-control).

```html
<div class="Group">
  <div class="Group-item">
    <a class="Button" href="#">Dashboard</a>
  </div>
  <div class="Group-item">
    <a class="Button" href="#">Settings</a>
  </div>
  <div class="Group-item with-Dropdown">
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

Be default, the group works with `Button` and `FormControl` components.

```html
<div class="Group">
  <div class="Group-item">
    <input class="FormControl" type="text">
  </div>
  <div class="Group-item">
    <a class="Button" href="#">Send</a>
  </div>
</div>
```

This component intelligently removes certain `border-radius` values from
your application-level button and form control theme.

## Customising

Your application-level CSS can build upon this component.

If your app's button theme uses a border width other than `1px`, you can adjust
the `bits-group-border-width` variable. For example, if your buttons and form
controls used 3px borders, you would modify the variable:

```scss
$bits-group-border-width: 3px;
```

If you need to adjust the space between buttons, or buttons and groups,
or multiple groups, you might want to add a rule like this to your
application-level CSS:

```scss
/**
 * Add some space between adjacent .Button and .Group components
 */

.Button + .Button,
.Button + .Group,
.Group + .Button,
.Group + .Group {
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