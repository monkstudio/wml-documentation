# `<exec>`

> [Node](./node.md) > Exec

The element is a wrapper for the [exec](../parsers/exec.md) parser. Inner text will be passed to PHP's eval() function and the returning result will be exported by the node. See documentation on the [exec](../parsers.exec.md) parser for more information on accepted attributes.

Note that expressions will be parsed first before the inner text is executed.

## Attributes

**parser** : 'exec'

**walk** : false

## Examples

### Basic usage using arithmetic:

```
<exec>

    return 1 + 1;

</exec>
```

### Get the site name from the current WordPress context:

```
<exec>

    return get_bloginfo('name');

</exec>
```

### Using `<exec>` with context variables:

```
<exec context=base=4&exp=2 >

    return pow({ $base }, { $exp });

</exec>
```