# `<map>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > Map

The default implementation of the [map](../parsers/map.md) parser.

Use the element for exporting an array of coordinates that is compatible with ACF's 'Google Map' field.

## Attributes

**key** : null

Set your Google Maps JavaScript API key here. If omitted, and ACF is installed on the target WordPress' context, then the 'map' parser will attempt to set this attribute with ACF's `google_api_key` setting.

**parser** : 'map'

## Attribute-less Value

If an attribute-less value is set and is not empty, then it will be used as a shorthand for the node's inner content.

## Examples

### Basic Usage:

```
<map "8/10 Eastbrook Terrace, East Perth, WA" />
/*
Exports:
array (
    'address'   => '8/10 Eastbrook Terrace, Perth WA 6004, Australia',
    'lat'       => -31.952786,
    'lng'       => 115.8766209,
)
*/
```