# `<user>`

> [Node](./node.md) > User

This is the default implementation of the [../parsers/user.md] role.

Use this element to create users in the target WordPress context.

Note that by default the frontend admin bar will be hidden for each inserted user. This can be overridden by embedded child elements. For example:

```
<show_admin_bar_front>true</show_admin_bar_front>
```

## Supported Child Elements:

By default, embedded child elements will be passed to [wp_insert_user()](https://codex.wordpress.org/Function_Reference/wp_insert_user)'s $userdata parameter. 

`<field>` : @todo

`<term>` : @todo

## Attributes

pass

@todo

name

@todo

email

@todo

role

@todo

## Valueless Attributes

'@' : @todo

'+' : @todo

''  : @todo

## Attribute-less Value

## Examples