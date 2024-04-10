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

JTF includes predefined classifications of cuneiform artefact types. This section introduces the keywords used in JTF to describe the different types of cuneiform artifacts.
These types are consistent with types used in major cuneiform artifact repositories such as the [Cuneiform Digital Library Initiative (CDLI)](https://cdli.mpiwg-berlin.mpg.de) and [ORACC](https://oracc.museum.upenn.edu) 

#### Cuneiform artifact types

Tablet
: An artifact in the shape of a tablet with one or many impressions

Envelope
: An artifact in the shape of an envelope that may encompass another cuneiform artifact, e.g., a tablet

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

Width
: Width of the cuneiform artifact

Height
: Height of the cuneiform artifact

Depth
: Depth of the cuneiform artifact

## Text Content

JTF-LD is able to express textual contents present on surfaces of cuneiform tablets.
A text content always belongs to a 
To express textual contents, the following definitions apply:

Line
: A line in a text block on a surface of a cuneiform tablet
A line usually occurs within a given surface. Hence, a surface may contain an arbitrary amount of lines.
Lines are ordered by their occurrence on the surface, usually from top to bottom.

Word
: A word consists of a list of characters which have been identified as a semantic entity
A line consists of several words in the order of their writing, usually from left to right.

Character
: A character forms the basic means of writing cuneiform texts

CharacterPaleography
: The paleographic description of a cuneiform character used on a cuneiform artifact

## Annotations


## JTF as linked data: JTF-LD









### Automatic Links

Spec Markdown does not yet automatically link urls.
