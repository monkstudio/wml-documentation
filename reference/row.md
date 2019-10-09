# `<row>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > [Group](./group.md) > Row

This element is an alias of [Group](./group.md), which can be used as a more verbose way of defining rows within an ACF repeater field.

## Examples

### Basic Usage:

Example with [Repeater](./repeater.md).

```
<page>

    <title>Hello, World!</title>

    <repeater name=my_list >

        <row>
        
            <title>First Row</title>
        
            <content>
            
                Lorem Ipsum
            
            </content>

        </row>

    </repeater>

</page>
```