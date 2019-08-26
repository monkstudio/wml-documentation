# `<timestamp>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > Timestamp

This is the default implementation of the [time](../parsers/time.md) parser.

This element will convert and export the node's inner text into a timestamp.

Optionally, if the 'format' attribute is set, then the returned timestamp will be formatted as a date string.

## Attributes

**parser** : 'time'

**format**

See documentation on PHP's [date()](https://www.php.net/manual/en/function.date.php) function for a list of supported formatting characters.

## Examples

## Basic Usage:

```
<timestamp>24th August 2019</timestamp>
```