# `<loop>`

> [Node](./node.md) > [Internal](./internal.md) > [Construct](./construct.md) > [Splice](./splice.md) > Loop

The default implementation of the [`loop`](../parsers/loop.md) parser.

The element will loop through its embedded markup for each item in its 'each' attribute, using the value of 'as' as the variable name to assign the current loop item value to.

## Attributes

**as** : 'item'

A string to set the variable name for the current loop item value. The value set for this attribute can then be accessed as a variable in any expression parsed within the loop. For example, if this attribute is omitted, and the default value of 'item' is used, then the current loop item can be read as `{ $item }`.

**each** : []

If a string is provided then it will be split into an array by the ',' delimiter. So for example 'foo, bar, baz' will be converted to `array('foo', 'bar', 'baz')`.

If the value is numeric then it will be converted into an array containing a range of numbers starting at `0`.

If an expression is set for this attribute then it should return a iterable value like an array.

**key** : null

If this attribute is set, then the current loop's index key will be available within its context. If a string value is provided for this attribute then it will be used as the variable name for the current index, otherwise `$key` will be used by default.

**walk** : false

**parser** : 'loop'

## Examples

### Basic Usage:

```
<loop each='foo, bar, baz' >

    <node>{ $item }</node>

</loop>
/* 
Exports:
<0/0/node> 'foo'
<0/1/node> 'bar'
<0/2/node> 'baz'
*/
```

### Using numeric values:

```
<loop each=-3 as=number >

    <node>{ $number }</node>

</loop>
/*
Exports:
<0/0/node> '0'
<0/1/node> '-1'
<0/2/node> '-2'
*/
```

### Using index keys:

```
<loop each={['foo', 'bar', 'baz']} key >

    <node>{ $key }: { $item }</node>

</loop>
/*
Exports:
<0/0/node> '0: foo'
<0/1/node> '1: bar'
<0/2/node> '2: baz'
*/
```