# `<time>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > [Timestamp](./timestamp.md) > Time

Alias of [Timestamp](./timestamp.md) for exporting metadata compatible with ACF's time field.

See [Timestamp](./timestamp.md) for more information.

## Attributes

**format** : 'H:i:s'

## Examples

### Basic Usage:

```
<time>3:00pm</time>
<!-- Exports: <0/0/time> '15:00:00' -->
```

### Get the current time:

```
<time>now</time>
```
