# `<term>`

> [Node](./node.md) > Term

The default implementation of the [term](../parsers/term.md) parser.

Use this element to insert terms into the target WordPress context.

The term's name can be set by either the node's inner text or as an attribute-less value. 

If embedded in a `<post>` tag, the exported post will be assigned to the exported terms.

## Supported Child Elements

By default embedded elements will be passed to to the $args parameter when calling [wp_insert_term](https://codex.wordpress.org/Function_Reference/wp_insert_term).

`<term>` : Embedded term tags will be exported as children of the parent term for hierarchical taxonomies.

`<field>` : Field elements will be exported as the term's metadata.

## Attributes

**parser** : 'term'

**taxonomy**

The taxonomy to save the term as.

**description**

The term's description

## Attribute-less Values

If set, this value will be assigned as the term's title.

## Examples

### Basic Usage:

Note that categories can be inserted by the term alias tag `<category>`.

```
<term taxonomy=category description='This is an example category.' >Example</term>
```

### Creating child terms:

```
<term taxonomy=category >

    Child Categories Example

    <description>This category contains the following children:</description>

    <term taxonomy=category 'Child A' />
    <term taxonomy=category 'Child B' />
    <term taxonomy=category 'Child C' />

</term>
```

### Assigning a post to its embedded terms:

```
<post 'Embedded Tags Example' >

    This post will be embedded with the following tags:

    <term taxonomy=post_tag 'Tag A' />
    <term taxonomy=post_tag 'Tag B' />
    <term taxonomy=post_tag 'Tag C' />

</post>
```