
# `<Blog>`

> [Node](./node.md) > [Post]() > [Page]() > Blog

Shorthand for creating Post pages. Note that this node is automatically assigned the id 'blog' for easy referencing when creating 'linked' nodes like [`<menuitem>`](). See [`<page>`]() for more information on supported attributes.

```
<blog></blog>
```

is the same as writing:

```
<post type='page' option='page_for_posts' ></post>
```

## Attributes

**option** : 'page_for_posts'

**id** : 'blog'

## Examples

### Basic example for creating a Posts page:

```
<blog>

    <title>My Blog</title>

</blog>
```