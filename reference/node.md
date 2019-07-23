# `<Node>`

> Node

This is the base node upon which every tag in WPML extends. Any none-special tag written in WPML will be resolved as a `<node>` tag with the tagname set as the node's name attribute if it's not already defined.

For example, a tag written as:

```
<hello />
```

Is the same as writing

```
<node name="hello" />
```

All special tags extend the Node tag as well. Which means you can consider every attribute defined for this tag as global and can have an effect on all WPML tags.

## Attributes

**name** : `<tagname>`

This value can be any arbitrary string and is typically treated as the key value associated with the node's exported value. By default, WPML will use the tagname as the 'name' attribute value if it's not explicitly defined in the markup.

```
<node parser='group' >
    <hello>World</hello>
    <node name="foo">Bar</node>
</node>

/*
Exports as:
array (
    'hello' => 'World',
    'foo'   => 'Bar',
)
*/
```

**id** : None

A unique identifier for a node. While not required, setting a node's ID can be useful if you want to reference the node's exported value when parsing another node. More significantly, if the node's ID matches an ID in the cache, then that cached state will be restored to that node; regardless if the node's markup has changed or if it changed position within the node tree. This attribute must always be unique, assigning multiple node's with the same ID can lead to unintentional behaviour.

```
<node id='example' />
```

**src** : None

A link to an external resource relative to the current WPML document. If the src file is a readable text file, then it's contents will be imported and set as the node's inner text. How 'src' elements are handled depends on what node's parser. For example, the `<img>` and `<file>` tags would save the src file as in attachment in the current WordPress context. Typically however, if the resource was readable, the imported contents will be treated as regular text inside the tag's body and how it's exported depends on the parser used.

```
// example.md
# Hello World

// example.wpml
<node src='example.md' parser='markdown' />

/*
Exports as:
'<h1>Hello World!</h1>'
*/

```

**option** : None

If set then this attribute will enable the node's exported value to be saved to the current WordPress' options; where the exported value is the option_value and the option attribute value is the option_name. If option is set, but without a value, then the node's name attribute will be used as the option_name instead.

```
// example.wpml
<node option='hello'>World</node>
<foo option >Bar</foo>

// Your WordPress app
echo get_option('hello'); //prints 'World'
echo get_option('foo'); // prints 'Bar'
```

**dump** : None

Prints the exported value of the node to the console. Useful for debugging the parsing of a node, or inspecting what kind of value may be passed to other nodes. Like all log types in WPML, the printed information is prefixed with the name and location of the node that is dumping the exported value.

```
<node dump >Hello World</node> // <0/0/node> 'Hello World'
```

**link** : None

This attribute takes the ID of another node. When defined, this node's cache is invalidated when the 'linked' node's cache is expired. This will force the node to re-export is value when the 'linked' node does as well. This attribute can be handy if a node is dependant on the state of another node. For example: Some special tags like `<mixin />`  requires this node to be defined with the ID of the template it's importing so that it will always re-export its contents every time the template's markup is updated.

```
<node id='test' >Linked nodes will always re-export when this node is updated</node>

<node link='test' >This node will always re-export when the 'linked' node is updated</node>

```

**parser** : 'to_string'

Set the parser to export the node's value with. Parser's are the heart of WPML and each node, including special tags, always has a parser defined.

```
<node parser='group' >
    <first>Foo</first>
    <second>Bar</second>
</node>

/* 
Uses the 'group' parser to export the node's child elements as:
array (
  'first'   => 'Foo',
  'second'  => 'Bar',
)
*/

```

**cache** : true

Controls whether to cache the node. If set to false the node's parser will re-export its value on each run instead of returning the cached value, even if the node's state was not changed.

**walk** : true

Controls whether to walk and export the node's children. If set to false then child nodes will be ignored and thus will not be exported. Handy if you want to export a node's contents as raw html and therefore don't want its inner tags to be handled as WPML elements.

**context** : empty Array

Set variables that are accessible within the scope of the node. Note that variables can not be used in attributes set on the same node; Only the inner content and child nodes will be affected by the node's context. Variables can be defined as a url-like query string or as an expression. All descendants of a parent will extend it's own context when defining variables within their own scope, including overriding variables with it's own.

```
<node parser='to_array' context={['name' => 'Foo', 'greeting' => 'Hello World!']} >

    <node context='name=Bar' >

        { $greeting }, my name is { $name }!

    </node>

</node>
/*
The above export:
'Hello World!, my name is Bar!'
*/
```

## Valueless Attributes
Don't forget that valueless attributes defined for `<node>` are applicable to all special tags.

**raw** : An alias for setting the 'raw' parser, as well as the cache attribute to false. So writing `<node raw >` is shorthand instead of `<node parser='raw' walk={false} >`. 

**md** : Alias for attribute: `parser='markdown'`.

**yml** : Alias for attribute: `parser='yaml'`.

**lorem** : Alias for attribute: `parser='lorem'`.

## Attribute-less Values

None

## Examples

@todo