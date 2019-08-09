# `<layout>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > [Group](./group.md) > Layout

Alias of [`<group>`](./group.md) intended to be a more semantic method of writing flexible layouts.

## Attributes

See [Group](./group.md) for documentation on supported attributes.

## Examples

### Basic example with `<layouts>`:

```
<layouts>

    <layout layout='greeting' >

        <node name='greeting' >Hello, World!</node>

    </layout>

    <layout 'heading' >

        <heading 'bar' />

    </layout>

</layouts>
```