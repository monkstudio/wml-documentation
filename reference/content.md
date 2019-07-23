# `<content>`

> [Node](./node.md) > Content

This element can be embedded in `<post>` elements for holding content to be saved as the post's 'post_content'

## Attributes

**parser** : 'markdown'

**name** : 'post_content'

**walk** : false

## Examples

### Basic Usage:

```
<post>

    <title>Hello, World</title>

    <!-- 
    Markdown can also be written directly in the <post>'s body and 
    it will save to post_content
    -->
    <content>

        ## WPML is...

        - A programmatic approach to managing content in Wordpress
        - A faster workflow
        - Fun!

    </content>

</post>
```

### Importing an external markdown file as the node's src:

```
<post>

    <title>External Content Example</title>

    <!-- Updating the src file will cause this node to re-export -->
    <content src='./example.md' />

</post>
```