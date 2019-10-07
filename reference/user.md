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

`<field>` : Embedded Field elements will be exported as the parent `<user>` metadata.

`<term>` : Parent User will be assigned to each of the embedded Term elements.

## Attributes

**parser** : 'user'

**pass**

The user password. Note that this is required when creating users in WordPress.

**name**

This attribute is utilised for setting the user's login name. Also required.

**email**

The user's email address.

**role**

This attribute can either receive a string as a single role, or an array of multiple roles to assign to the exported user.

## Valueless Attributes

By default, valueless attributes without a modifier will be set as the inserted user's role.

### Valueless Attribute Modifiers

'+' : Each valueless attribute added with this modifier will be appended to the user's role array.

## Attribute-less Value

Attribute-less values can be used as shorthand for assigned the user's password.

## Examples

### Basic Usage:

Insert a user with the default role (usually Subscriber).

```
<user name=johndoe pass='password1234' />
```

### Using shorthand

Create a user with the role of editor

```
<user @eddy "my password" editor />
```

### Assigning multiple roles

```
<user @jane 'password' +editor +author >

    <first_name 'Jane' />
    <last_name>Doe</last_name>
    <display_name>Jane Doe</display_name>

</user>
```