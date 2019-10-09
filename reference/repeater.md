# `<repeater>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > [Select](./select.md) > Repeater

This element is an alias of [Select](./select.md), which can be used as a more verbose way of defining ACF Repeater rows.

## Examples

### Basic Usage:

Example with [Row](./row.md).

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