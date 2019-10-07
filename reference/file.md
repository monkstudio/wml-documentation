# `<File>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > File

The default wrapper for the [file](../parsers/file.md) parser.

File paths set in the 'src' attribute will be side-loaded to the current WordPress context as attachments.

Since `<file>` extends Field, the exported value (the attachment ID if the default parser is used) can be saved as metadata when embedded in other special tags.

Note that since the global 'src' attribute is used to set the file path, WPML will rebuild automatically every time the source file is modified; updating the attachment currently saved to WordPress with the modified version.

## Attributes

**parser** : 'file'

**alt** : none

Set's the attachment's title for the source file being saved to WordPress. This attribute is more intended for the `<file>` alias `<img>` as a more semantic means of setting the value of the 'alt' attribute when rendering the image html.

## Examples

### Basic example:

```
<file src=./files/text.txt />
```

### Saving a file as metadata:

```
<page>

    <title>Hello, World</title>

    <file name='header_video' src='./files/video.mp4' />

</page>
```