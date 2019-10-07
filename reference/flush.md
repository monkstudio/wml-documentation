# `<flush>`

> [Node](./node.md) > [Internal](./internal.md) > [Construct](./construct.md) > [Ignore](./internal.md) > Flush

This element is the default implementation of the [flush](../parsers/flush.md) parser, which flushes all cached nodes from the point it is located within the node tree.

Flush can serve as a utility tag when, for unknown reasons, adding or removing markup has seemingly no effect on the target WordPress context.

When used, restored cache nodes will ignored while a delete action will be applied to the remaining cached nodes. This means the proceeding nodes will be re-inserted into the target WordPress context.

## Attributes

**parser** : 'flush'

## Examples

### Basic Usage

The first page element will not be re-inserted while it remains unmodified, and all posts after `<flush>` will always be deleted and re-created within the current WordPress target.

```
<page 'Page One' />

<flush />

<page 'Page Two' />

<page 'Page Three' />
```