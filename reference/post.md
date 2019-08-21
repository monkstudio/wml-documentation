# `<post>`

> [Node](./node.md) > Post

Perhaps the heart of WML, this element is the default implementation of the [post](../parsers/post.md) parser.

Use this element to insert post entries into the target WordPress context.

Note that the order in which `<post>` tags are inserted can determine their menu_order value.

Embedded text will be parsed as markdown and saved as the 'post_content'. If you would like to use a different parser for the 'post_content' parameter then use `<post_content>` or `<content>` child elements.

## Supported Child Elements

By default child elements embedded inside `<post>`s will be passed to the [wp_insert_post()](https://developer.wordpress.org/reference/functions/wp_insert_post/) as the argument array.

`<title>` : Alias for `<post_title>`

`<excerpt>` : Alias for `<post_excerpt>`

`<content>` : Alias for `<post_content>`

`<term>` : The exported post will be assigned to embedded [Term](./term.md)s and all elements that extend it.

`<field>` : [Field](./field.md) elements will be exported as the post's metadata.

`<post>` : Embedded Post elements will be saved as child posts. Typically used with hierarchical post_types like `<page>`.

## Attributes

**type** : 'post'

The value sets the 'post_type' of the exported post object.

**status** : 'public'

This value will be used as the `post_status' parameter.

Note you can still also set the post_status as a child element. For example:

```
/* Setting the post's status to private */
<post>
    <post_status>private</post_status>
</post>
```

**template** : The page template to render this post with. The provided value should be a path to the active theme's template file relative to the theme's root. For example:

```
/* Setting a page's template */
<page template='templates/contact.php' >
    <title>Contact Me</title>
</page>
```

**parser** : 'post'

## Attribute-less Values

If an attribute-less value is set, then it will be passed as the 'post_tile' parameter. Note this still can be overridden by embedded elements.

## Examples

### Basic Usage:

```
<post>

    <title>Hello, World</title>

    This is my first blog post!

</post>
```

### Writing raw html as the post_content

```
<post>

    <title>Post Format: Quote</title>

    <content raw >

        <blockquote>
            Only one thing is impossible for God: To find any sense in any copyright law on the planet.
            <cite><a href="http://www.brainyquote.com/quotes/quotes/m/marktwain163473.html">Mark Twain</a></cite>
        </blockquote>

    </content>

</post>
```

### Posts with tags and categories

```
<post>

    <title>Animals I like</title>

    The following is a growing catelogue of my favourite animals.

    <category>Dogs</category>
    <category>Platypus</category>

    <tag>Animals</tag>
    <tag>Interests</tag>
    <tag>Life</tag>

</post>
```

### Adding a featured img

```
<page>

    <title>Hello, World</title>

    <img src='path/to/image.jpg' featured />

</page>
```

### Adding a gallery of images to a post as metadata:

```
<post 'My Holiday' >

    <gallery>
        <img src='./image_1.jpg' alt='At the Beach' />
        <img src='./image_2.jpg' alt='With the tour group' />
        <img src='./image_3.jpg' alt='In da club' />
        <img src='./image_4.jpg' alt='On the plane' />
    </gallery>

</post>
```