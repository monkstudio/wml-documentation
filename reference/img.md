# `<img>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > [File](./file.md) > Img

Alias of `<file>` as a more semantic means of saving images to WordPress.

## Attributes

See [File](./file.md) for documentation on supported attributes.

## Valueless Attributes

**featured** : Automatically sets the node name with the value '_thumbnail_id'. This provides a shorthand for saving images as the 'featured image' of a post.

## Examples

### Basic Usage:

```
<img src="./images/penguin.jpg" alt="Penguin!" />
```

### Setting a featured image for a post

```
<post>

    <title>Just another post about penguins</title>

    <img src="./images/penguin.jpg" alt="Penguin" featured />

</post>
```