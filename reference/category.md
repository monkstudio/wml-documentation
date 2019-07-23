# `<Category>`

> [Node](./node.md) > [Term](./term.md) > Category

Alias of [`<term>`](./term.md) for creating terms for the 'category' taxonomy.

Writing:

```
<category>Example Category</category>
```

Is the same as writing:

```
<term taxonomy='category' >Example Category</term>
```

## Attributes

**taxonomy** : 'category'

## Examples

### Assigning categories to a post:

```
<post>

    <title>Hello, World!</title>

    This is my first post!

    <category>Category A</category>
    <category>Category B</category>

</post>
```

