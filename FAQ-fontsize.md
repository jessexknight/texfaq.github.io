---
title: Fonts at arbitrary sizes
category: programming
tags:
  - latex
  - macros
permalink: /FAQ-fontsize
---

Almost all fonts, nowadays, are provided with LaTeX control
(`fd`) files, so the temptation to risk the
[problems of `\newfont`](FAQ-newfontstar) is usually easy to
resist.

However, one temptation remains, arising from the way that LaTeX
restricts the sizes of fonts.  In fact, the restriction only
significantly applies to the default (Computer Modern) and the
Cork-encoded (T1) EC fonts, but it is widely considered to be
anomalous, nowadays.  In recognition of this problem, there is a
package [`fix-cm`](https://ctan.org/pkg/fix-cm) which will allow you to use the fonts, within
LaTeX, at any size you choose.  If you're not using scalable
versions of the fonts, most modern distributions will just generate an
appropriate bitmap for you.

So, suppose you want to produce a heading in Computer Modern Roman at
30 points, you might be tempted to write:
```latex
\newfont{\bigfont}{cmr10 at 30pt}
\begin{center}
  \bigfont Huge text
\end{center}
```
which will indeed work, but will actually produce a worse result than
```latex
\usepackage{fix-cm}
...
\begin{center}
  \fontsize{30}{36}\selectfont
  Huge text
\end{center}
```


[`Fix-cm`](https://ctan.org/pkg/fix-cm) has one or two omissions&nbsp;&mdash; fonts the LaTeX
team did not consider useful, including the CM dunhill fonts (as
CM, but with stretched ascenders) and the CM fibonacci font (which is only
available in 8-point design size).  If
[`fix-cm`](https://ctan.org/pkg/fix-cm) doesn't do the job, try the one of the 
[`type1cm`](https://ctan.org/pkg/type1cm) (for CM fonts),
[`type1ec`](https://ctan.org/pkg/type1ec) (for EC fonts) or
[`anyfontsize`](https://ctan.org/pkg/anyfontsize) packages.

A further alternative might be to switch to the
[_Latin Modern_ fonts](FAQ-uselmfonts) (which
provide a close simulacrum of the _Computer Modern_ set);
these fonts were scalable from their first
distribution, and don't therefore need any such trick as the above.
