# `<options>`

> [Node](./node.md) > Options

This is the default implementation of the [options](../parser/options.md) parser.

All child elements will be saved to the options table in the target WordPress' context.

Similar to setting the 'option' attribute directly on an element, except `<options>` offers a macro way of setting options where the exported child's 'name' is the `option_name`, and its exported value the `option_value`. Also unlike the 'option' attribute, removed children will also be deleted from the options table as well.

## Attributes

**parser** : 'options'

## Examples

