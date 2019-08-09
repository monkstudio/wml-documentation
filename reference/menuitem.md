# `<menuitem>`

> [Node](./node.md) > Menuitem

This is the default implementation of the [menuitem](../parsers/menuitem.md) parser.

Use this element to create menu items. If embedded in `<menu>` then the exported menu item will be assigned to that menu.

Note if the 'link' attribute is set then the parser will attempt to auto-configure the menu item based on the kind of node that the element is linked to.

For example: linking to `<post>` elements will set the link as a post permalink, while linking to `<term>`'s will set a link to that term's archive page.

## Supported Child Elements

By default embedded elements not listed below will be passed as $menu_item_data to the [wp_update_nav_menu_item()](https://developer.wordpress.org/reference/functions/wp_update_nav_menu_item/) function.

`<menuitem>` : Adds a nested sub-menu item.

`<field>` : Will be saved as metadata for the exported menu item. See [Field](./field.md) for more documentation.

`<description>` : Alias for `<menu-item-description>`.

## Attributes

**parser** : 'menuitem'

**url** : '#'

The custom menu item's URL. This defaults to '#' when omitted which should be handy if you just want a menu item to act as a parent for a sub-menu.

**object** : null

Set with the taxonomy for term menu items, and the post_type for menu items linking to posts and post archives.

**type** : null

Accepts 'post_type', 'taxonomy', 'post_type_archive' or 'custom'.

**title** : null

The link title

**target** : null

Sets the 'target' attribute when constructing the menu item anchor tag.

**class** : null

CSS classes to add to the menu item anchor tag.

**rel** : null

From MDN: Specifies the relationship of the target object to the link object. The value is a space-separated list of [link types](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types).

## Valueless Attributes

**archive**

Shorthand for setting 'post_type_archive' as the type value.

For example, writing `<menuitem object='post' archive />` is the same as writing `<menuitem object='post' type='post_type_archive' />`.

## Attribute-less Values

If provided, this value will be used as shorthand for the menu item title.

## Examples

### Basic Usage:

```
<menu location='primary' >

    <!-- Custom link that should open in a new tab -->
    <menuitem url="http://monk.com.au" target='_blank' >Custom Link</menuitem>

    <!-- Link to home page with a custom class -->
    <menuitem link='frontpage' class='home-page-link' />

    <!-- Link to a category archive page -->
    <menuitem &example_category />

    <!-- Link to the 'post' archive page with a custom title -->
    <menuitem object=post archive 'Latest Posts' />

</menu>
```

### Creating nested menu items:

```
<menu primary >

    <!-- Note this menu item will be saved as a custom link with the url '#' -->
    <menuitem>

        About Us

        <menuitem link=contact 'Contact' />
        <menuitem link=staff 'staff' />
        <menuitem link=history 'History' />

    </menuitem>

</menu>
```