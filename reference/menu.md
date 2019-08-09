# `<menu>`

> [Node](./node.md) > Menu

The default implementation of the [menu](../parsers/menu.md) parser.

Insert menus into the target WordPress' context.

## Supported Child Elements

`<menuitem>` : A menu item to assign to this menu. See [Menuitem](./menuitem.md) for more documentation.

`<menu-name>` :  The title of the menu to create. If omitted then one will be automatically generated as "Menu %d", where %d is the menu instance number.

`<title>` : Alias of 'menu-name'.

`<description>` : The menu description

`<parent>` : The parent Menu

`<field>` : Will be saved as metadata for the exported menu. See [Field](./field.md) for more documentation.

## Attributes

**parser** : 'menu'

**location** : 'primary'

## Valueless Attributes

Valueless attributes will be assigned as the menu's location. Use the '+' mod to define additional locations to assign the menu to.

## Attribute-less values

If an attribute-less value is provided, then it will be used as a shorthand for the menu's title.

## Examples

### Basic Usage:

```
<menu>

    <title>Main Menu</title>

    <menuitem url="https://monk.com.au/">Monk Media</menuitem>

</menu>
/*
This menu will be added to location 'primary' by default since the 'location' parameter is omitted.
*/
```

### Assigning a menu to multiple locations.

```
<menu +primary +secondary >

    <menuitem url="http://monk.com.au">Monk Media</menuitem>

</menu>
```