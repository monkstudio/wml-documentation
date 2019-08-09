# `<import>`

> [Node](./node.md) > [Internal](./internal.md) > [Construct](./construct.md) > [Splice](./splice.md) > Import

The default implementation of the [import](../parsers/import.md) parser.

Loads and parses an external WPML resource and imports it into the main node tree.

Similar to `@import` used in CSS preprocessors, this element can be used to organise your data structure into multiple WPML files.

Note that since this element uses the 'src' attribute for linking external resources, WPML will automatically rebuild every time a source file is modified.

## Attributes

**parser** : 'import'

**walk** : false

## Examples

### Organising all pages into an external WPML resource:

```
/* ./content/pages.wpml */

<page>

    <title>About Me</title>

</page>

<page "Contact" />

/* ./main.wpml */

<import src=./content/pages.wpml />

```

### Dynamically importing external WPML resources:

```
<loop each={['page-a', 'page-b']} as=page >

    <import src='./pages/{ $page }.wpml' />

</loop>
```