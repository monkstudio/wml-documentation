# `<splice>`

> [Node](./node.md) > [Internal](./internal.md) > [Construct](./construct.md) > Splice

This element is a special Construct element that will replace itself with elements exported by its parser.

This element is not intended to be used directly, but rather should be extended by Elements with parsers that export a list of elements to 'splice' into the target node's index.

Note that elements extending Splice should export the hash ids of the elements to insert.

See documentation on built-in Splice elements [Loop](./loop.md), [Import](./import.md) and [Mixin](./mixin.md) for examples on how this element works.