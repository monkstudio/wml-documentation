# `<layouts>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > [Select](./select.md) > Layouts

This element is an alias of [Select](./select.md), which can be used as a more verbose means of defining ACF flexible layouts.

## Attributes

**name** : 'page_layouts'

## Examples

### Basic Usage:

```
<frontpage>

    <title>Welcome</title>

    <layouts>

        <layout 'my_flexible_content' >
        
            <title>My layout</title>
        
            <content md >
            
                ## Header

                Lorem Ipsum
            
            </content>

        </layout>

    </layouts>

</frontpage>
```