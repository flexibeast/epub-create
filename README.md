## NOTE: This repository is now read-only - official repository now at https://git.sr.ht/~flexibeast/epub-create
EPUB-CREATE(1) - General Commands Manual

# NAME

**epub-create** - simple shell script for creating EPUB documents

# SYNOPSIS

**epub-create**
*dir*

# DESCRIPTION

**epub-create**
is a simple POSIX shell script for creating an EPUB document from a
directory containing non-binary files.

When run,
**epub-create**
will ask for the document title, authors, language and publication ID.
Pressing ENTER at any prompt will result in a default value being
used; the defaults are
"A Document",
"\[unknown]",
"en"
and
"\[unknown]",
respectively.
**epub-create**
will then start
`EDITOR`
with a list of the files found in
*dir*.
This is the EPUB
'spine',
via which one specifies the order in which the reader of the EPUB
should read the files.

Upon save and exit,
**epub-create**
will open each file in the reading order specified, allowing one to
finalise the contents of the XHTML version of each file.
At a minimum, this should involve changing the contents of the
&lt;title&gt;
element, but this is not required.

Once all the files have been processed,
**epub-create**
will open the
*nav.xhtml*
file containing the table of contents, for finalising.
Upon save and exit, a file named
'*&zwnj;*&zwnj;*dir*.epub'
will be created in the current directory.

## Dependencies

This script is intended to be runnable via a POSIX-compliant shell,
requiring only the presence of
cat(1p),
date(1p)
and
zip(1).

# ENVIRONMENT

`EDITOR`

> The editor to use for editing.

# SEE ALSO

EPUB 3 Overview

> [https://www.w3.org/publishing/epub32/epub-overview.html](https://www.w3.org/publishing/epub32/epub-overview.html)

EPUB Open Container Format (OCF) 3.2

> [https://www.w3.org/publishing/epub/epub-ocf.html](https://www.w3.org/publishing/epub/epub-ocf.html)

EPUB Packages 3.2

> [https://www.w3.org/publishing/epub32/epub-packages.html](https://www.w3.org/publishing/epub32/epub-packages.html)

EPUBCheck

> [https://www.w3.org/publishing/epubcheck/](https://www.w3.org/publishing/epubcheck/)

# AUTHORS

Alexis [flexibeast@gmail.com](mailto:flexibeast@gmail.com)

# CAVEATS

**epub-create**
is not intended to be anything other than a portable, low-dependency
script for creating a minimal EPUB from a small collection of files.
There are no plans for it to develop further capabilities and become a
serious tool for working with EPUBs.

One cross-platform option for serious EPUB work is Sigil, based on
QtWebEngine:

[https://sigil-ebook.com/](https://sigil-ebook.com/)

For simply creating an EPUB from an existing document in formats such
PDF or OOXML, consider Pandoc:

[https://pandoc.org](https://pandoc.org)

---
*README generated from `epub-create.1` mdoc(7) source with mandoc(1).*
