# `<Date>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > [Timestamp](./timestamp.md) > Date

An alias of `<timestamp>` with the 'format' attribute preset to 'Ymd', which formats the exported value so that it is compatible with ACF's 'Date' Field.

See [`<timestamp>`](./timestamp.md) for documentation on supported input for this element, as well as documentation on the [timestamp](../parsers/timestamp.md) parser.

## Attributes

**format** : 'Ymd'

## Examples

### Any valid date format supported by PHP can be used:

```
<date>July 1st</date>
<!-- Exports : '20190701' -->
```

### Export today's date:

```
<date>today</date>
```