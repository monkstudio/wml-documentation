# `<field>`

> [Node](./node.md) > [Meta](./meta.md) > Field

The exported value from `<field>` nodes will typically be saved as metadata when embedded in the markup of WPML tags that support it.

Field nodes have no preconfigured attributes and can potentially use any parser to export its value. All tags that extend `<field>` can also be saved as metadata.

Note that WPML will always attempt to use update_field() when saving metadata if Advanced Custom Fields is installed and activated within the current WordPress context. This will allow metadata to be formatted by their respective ACF fields on update. WPML will fallback to WordPress' native functions for updating metadata if ACF is not available.

## Examples

### Inserting metadata into a post:

```
<post "Hello, World!" >

    <field name='test' >1</field>

</post>
```

### Inserting metadata into a user:

```
<user @tester "password" >

    <field name=hello "World!" />

</user>
```

### Inserting metadata into a term with a special tag that extends Field:

```
<category "This category is assigned to posts about fruit!" >

    Fruit

    <select name="fruit_type_filter" >

        <node name='option_1'>Apples</node>
        <option_2>Bananas</option_2>
        <option_3 'Oranges' />

    </select>

</category>
```