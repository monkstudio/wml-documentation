# `<gallery>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > [Select](./select.md) > Gallery

Alias of `<select>`.

The element has no special meaning other than a more verbose means of exporting a collection of images.

## Attributes

See [Select](./select.md) for documentation on supported attributes.

## Examples

### Saving a gallery for a post:

Note that `<gallery>` will be saved as with the meta key 'gallery' since the name attribute is omitted.

```
<post>

    <title>My Favourite Penguins</title>

    <gallery>
        <img src="./images/penguins1.jpg" alt="Penguins 1"/>
        <img src="./images/penguins2.jpg" alt="Penguins 2"/>
        <img src="./images/penguins3.jpg" alt="Penguins 3"/>
    </gallery>

</post>
```