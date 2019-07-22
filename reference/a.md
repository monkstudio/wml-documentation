# `<A>`

> Node > Field > A

## Overview

This tag can be used to save metadata that is compatible with ACF Link fields. See documentation on the 'link' parser for more information on supported attributes and how this element is exported.

### Attributes

**parser** : 'link'

**href** : '#'

**target** : null

## Examples

### Setting an external link to open on a new tab:

```
<a href="http://monk.com.au" target="_blank" dump >Monk Media</a>
/*
Exports as:
array (
    'title'     => 'Monk Media',
    'url'       => 'http://monk.com.au',
    'target'    => '_blank',
)
*/
```

### Linking to a page in WordPress, using the page's title as the link title

```
<page id='about' >

    <title>About Me</title>

</page>

<a href="about" dump />

/*
Exports as:
array (
    'title'     5=> 'About Me',
    'url'       => 'http://dev.d/about-me/',
    'target'    => NULL,
)
*/
```