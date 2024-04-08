# JTF-LD Format specification

JTF-LD is a linked data-compatible JSON-based format for storing and processing textual cuneiform tablet data and metadata about cuneiform artifacts.
This specification document describes the structure and usage of the JTF format and its relations to other formats describing cuneiform tablet contents.

## Introduction

JTF-LD is a format for encoding various features on cuneiform artifacts and linking elements found on said cuneiform tablets to existing data in the linked open data cloud.
In doing so, JTF-LD defines a vocabulary for describing elements of a cuneiform tablet and can act as an exchange format between different databases providing cuneiform artifact data.
This specification builds on work by Ilya Khait, who defined the format JTF as an alternative format to the format ATF, which is commonly used to describe transliterations of cuneiform tablets.

### Requirements Language
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC2119]

### Conventions Used in This Document

The ordering of the members of any JSON object defined in this document MUST be considered irrelevant, as specified by [RFC7159].

Some examples use the combination of a JavaScript single-line comment
(//) followed by an ellipsis (...) as placeholder notation for
content deemed irrelevant by the authors.  These placeholders must of
course be deleted or otherwise replaced before attempting to
validate the corresponding JSON code example.

Whitespace is used in the examples inside this document to help
illustrate the data structures, but it is not required.  Unquoted
whitespace is not significant in JSON.

### Definitions
* JavaScript Object Notation (JSON), and the terms object, member, name, value, array, number, true, false, and null, are to be interpreted as defined in [RFC7159].
* 


## Format structure

This section describes the structure of a JTF-LD document. JTF-LD is a hierarchical representation of the contents of a cuneiform artifact.
The contents JTF-LD can describe are introduced in the following sections.

### Medium

JTF includes predefined classifications of cuneiform artefact types. This section introduces the keywords used in JTF to describe the different types of cuneiform artefacts.
These types are consistent with types used in major cuneiform artifact repositories such as the [Cuneiform Digital Library Initiative (CDLI)](https://cdli.mpiwg-berlin.mpg.de) and [ORACC](https://oracc.museum.upenn.edu) 

#### Cuneiform artefact types
* Cuneiform tablet: *tablet*
* 

### Layout

A cuneiform tablet may include 

* A set of surfaces (typically obverse, reverse, left, right, top, bottom)
* A set of cuneiform sign inscriptions on each of the aforementioned surfaces

#### Surfaces

Surfaces of cuneiform artifacts commonly contain textual information, seal impressions, or other areas of interest that may need further detailed examination and description by scholars.
This specification assumes that an agreement to classify surfaces on the cuneiform artifact has been reached before encoding in JTF-LD is attempted.
In particular, this involves researchers' agreement concerning the orientation of the cuneiform tablet and, hence, the identification of its different surfaces.
Therefore, the following definitions of surfaces are the results of scholarly work and may be applied to areas on the cuneiform tablet:

Top
: One or many surfaces located at the top of a cuneiform artifact as defined by one or many scholars interpreting the contents of the artifact

Bottom
: One or many surfaces located at the bottom of a cuneiform artifact as defined by one or many scholars interpreting the contents of the artifact

Left
: One or many surfaces located on the left side of a cuneiform artifact as defined by one or many scholars interpreting the contents of the artifact

Right
: One or many surfaces located on the right side of a cuneiform artifact as defined by one or many scholars interpreting the contents of the artifact

Obverse
: One or many surfaces located on the obverse or front side of a cuneiform artifact as defined by one or many scholars interpreting the contents of the artifact

Reverse
: One or many surfaces located on the obverse or back side of a cuneiform artifact as defined by one or many scholars interpreting the contents of the artifact


## Metadata
Metadata associated with cuneiform artifacts may include:

* Width of the cuneiform tablet
* Height of the cuneiform tablet
* Depth of the cuneiform tablet


## JTF as linked data: JTF-LD

Spec Markdown is first and foremost [Markdown](http://daringfireball.net/projects/markdown/syntax).
More specifically, it's based on [Github-flavored Markdown](https://help.github.com/articles/github-flavored-markdown/).

This section explains the syntax and capabilities of Markdown that Spec Markdown
supports and augments.


## Character Encoding

Markdown allows you to write text which uses &, <, and >. The output HTML will
automatically use the `&amp;`, `&lt;`, and `&gt;` entities.

Well formed HTML entities can be written inline directly. If you write `&copy;`,
it will appear in the HTML output as &copy;.


### Escape sequence

Markdown makes use of certain characters to format text, in order to render one
explicitly, place a backslash before it.

You can type \*literal asterisks\* instead of emphasis by typing
`\*literal asterisks\*`.

Escaping does not apply within code.

Spec Markdown allows backslash escapes for any ASCII punctuation character.

```
\!\"\#\$\%\&\'\(\)\*\+\,\-\.\/\:\;\<\=\>\?\@\[\\\]\^\_\`\{\|\}\~
```

Produces the following:

\!\"\#\$\%\&\'\(\)\*\+\,\-\.\/\:\;\<\=\>\?\@\[\\\]\^\_\`\{\|\}\~

## Inline formatting

Markdown allows for inline stylistic and structual formatting. Inline
formatting is allowed in paragraphs, list items, and table cells.


### Inline HTML

Markdown is not a replacement for HTML and instead leverages HTML by allowing
its use inline within paragraphs, links, etc.

This code has <blink>blinking</blink> and <em>emphasized</em> formatting.

Markdown syntax can continue to be <u>used *within* inline HTML</u>.


### Links

Use `[ ]` square brackets to indicate linked text followed immediately by `( )`
parenthesis to describe the URL the text will link to.

The linked text can contain any other inline formatting.

```
This is an [-->*example*<--](https://www.facebook.com) of a link.
```

Produces the following:

This is an [-->*example*<--](https://www.facebook.com) of a link.


Todo: Links do not yet support a reference style short-form.


### Emphasis

Wrapping asterisks *(\*)* indicate emphasis.

```
Example of **bold** and *italic* and ***bold italic***.
```

Produces the following:

Example of **bold** and *italic* and ***bold italic***.

Alternatively, use underscore *(\_)* for italic emphasis.

```
Example of _italic_ and **_bold italic_** or _**bold italic**_.
```

Produces the following:

Example of _italic_ and **_bold italic_** or _**bold italic**_.


### Inline Code

Wrapping back-ticks *(\`)* indicate inline code, text inside back-ticks is not
formatted, allowing for special characters to be used in inline code without
escapes.

```
This is an `example` of some inline code.
```

Produces

This is an `example` of some inline code.


Inline code can also use double- or triple-backticks. Wrapping spaces are removed.

``` `` ` `` ``` Produces `` ` ``


### Images

```
![Specs](http://i.imgur.com/aV8o3rE.png)
```

Produces the following:

![Specs](http://i.imgur.com/aV8o3rE.png)


## Blocks

Markdown allows for block-level structual formatting. Every block is seperated
by at least two new lines. Spec Markdown makes use of Markdown's blocks to
produce more specific structural formatting.


### Block HTML

Markdown is not a replacement for HTML and instead leverages HTML by allowing
its use as complete blocks when separated from surrounding content by blank
lines.

Note: Markdown formatting syntax is not processed within block-level HTML tags.

For example, to add an HTML table to a Markdown article:

```
Unrelated previous paragraph followed by a blank line

<table>
<tr>
<td>Table cell</td>
<td>

<table>
<tr>
<td>*Tables in tables*</td>
</tr>
</table>

</td>
</tr>
</table>
```

Produces the following:

Unrelated previous paragraph followed by a blank line

<table>
<tr>
<td>Table cell</td>
<td>

<table>
<tr>
  <td>*Tables in tables*</td>
</tr>
</table>

</td>
</tr>
</table>

And using `<pre>` produces a simple code block:

```
<pre>
Buffalo Bill ’s
defunct
       who used to
       ride a watersmooth-silver
                                stallion
and break onetwothreefourfive pigeonsjustlikethat
                                                 Jesus
he was a handsome man
                     and what i want to know is
how do you like your blueeyed boy
Mister Death
</pre>
```

Produces the following:

<pre>
Buffalo Bill ’s
defunct
       who used to
       ride a watersmooth-silver
                                stallion
and break onetwothreefourfive pigeonsjustlikethat
                                                 Jesus
he was a handsome man
                     and what i want to know is
how do you like your blueeyed boy
Mister Death
</pre>


### Section Headers

Regular Markdown supports two styles of headers, Setext and atx, however Spec
Markdown generally only supports atx style headers.

```example
# Header
```

Setext headers are not supported by Spec Markdown.

```counter-example
Header
------
```

The number of `#` characters refers to the depth of the section. To produce an,
`<h3>`, type `###`. Optionally, a header may be "closed" by any number of `#`
characters.

Note: Spec Markdown requires that documents start with a header.


### Paragraphs

Paragraphs are the most simple Markdown blocks. Lines are appended together to
form a single \<p> tag. Any inline syntax is allowed within a paragraph.


### Lists

Markdown lists are lines which each start with either a ordered bullet `1.` or
unordered bullet, `*`, `-`, or `+`. Lists are optionally indented by two spaces.

Lists can be nested within other lists by indenting by at least two spaces.

```example
  1. this
  2. is
  3. a
    - nested
  4. list
```

Produces the following:

  1. this
  2. is
  3. a
    - nested
  4. list

#### Task Lists

Spec Markdown also supports task lists. Start a list item with `[ ]` or `[x]` to
render a checkbox. This can be useful for keeping your tasks inline with
in-progress draft specifications.

```example
  1. this
  2. [ ] is
  3. [x] a
    - [X] nested
  4. todo list
```

Produces the following:

  1. this
  2. [ ] is
  3. [x] a
    - [X] nested
  4. todo list


### Code Block

A block of code is formed by either indenting by 4 spaces, or wrapping with
<code>\`\`\`</code> on their own lines.

    ```
    const code = sample();
    ```

Produces the following:

```
const code = sample();
```


### Block Quotes

Spec markdown does not yet support Markdown's `>` style block quotes.


### Horizontal Rules

Spec Markdown does not yet support Markdown's `---` style \<hr>.


### Automatic Links

Spec Markdown does not yet automatically link urls.
