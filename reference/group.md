# `<group>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > Group

This element is the default implementation of the `group` parser. Embedded tags will be exported as an associative array where the child element's name is the child tag's array key.

## Attributes

**parser** : 'group'

**layout** : none

This attribute makes that element compatible with ACF's Flexible Layouts. The set value will be used as the row's layout name.

Note: If an attribute-less value is set, it will be assigned to this attribute as a shorthand. For example, writing `<group "two_column" >` is the same as `<group layout="two_column" >`

## Examples

### Basic Usage:

```
<group>

    <option name='first'>A</option>
    <second>B</second>
    <third 'C' />

</group>

/*
Exports:
array (
  'first'   => 'A',
  'second'  => 'B',
  'third'   => 'C',
)
/*
```

### Working with Flexible Layouts:

```
<select name='page_layouts'>

    <group "full-width" >

        <node name=content parser=markdown >
            ### Hello World

            Lorem ipsum, dolor sit amet consectetur adipisicing elit. 
            Sunt maiores corrupti veniam saepe autem!
        </node>

    </group>

</select>
/*
Exports:
array (
    0 => array (
        'content'       => '<h3>Hello World</h3>
                            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                            Sunt maiores corrupti veniam saepe autem!</p>',
        'acf_fc_layout' => 'full-width',
    ),
)
*/
```