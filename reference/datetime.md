# `<datetime>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > [Timestamp](./timestamp.md) > Datetime

Takes a valid date and time and exports it in a format that is compatible with ACF's DateTime field as well as MYSQL's  DATETIME type.

See documentation on [`<timestamp>`](./timestamp.md) and on the [timestamp]() parser for more information on supported attributes and valid inputs.

## Attributes

**format** : 'Y-m-d H:i:s'

## Examples

### Export today's datetime at 2pm:
```
<datetime>today 2pm</datetime>
<!-- Exports: '2019-07-24 14:00:00' -->
```