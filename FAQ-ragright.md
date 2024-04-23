---
title: Setting text ragged right
category: formatting
permalink: /FAQ-ragright
---

The trick with typesetting ragged right is to be sure you've told the
TeX engine "make this paragraph ragged, but never _too_
ragged".  The LaTeX `\raggedright` command (and the
corresponding `flushleft` environment) has a tendency to
miss the "never" part, and will often create ridiculously short
lines, for some minor benefit later in the paragraph.  The
Plain TeX version of the command doesn't suffer this failing, but
is rather conservative: it is loathe to create too large a gap at the
end of the line, but in some circumstances&nbsp;&mdash; such as where
[hyphenation is suppressed](FAQ-hyphoff)&nbsp;&mdash; painfully large gaps
may sometimes be required.

Martin Schröder's [`ragged2e`](https://ctan.org/pkg/ragged2e) package offers the best of both
worlds: it provides raggedness which is built on the Plain TeX
model, but which is easily configurable.  It defines easily-remembered
command (e.g., `\RaggedRight`) and environment (e.g.,
`FlushLeft`) names that are simply capitalised
transformations of the LaTeX kernel originals.  The documentation
discusses the issues and explains the significance of the various
parameters of [`ragged2e`](https://ctan.org/pkg/ragged2e)'s operation.

