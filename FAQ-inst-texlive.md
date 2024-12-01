---
title: Installation using TeX&nbsp;Live manager
category: installing
permalink: /FAQ-inst-texlive
---

TeX&nbsp;Live manager (`tlmgr`) is, by default, a shell (or
Windows terminal window) command.  There is voluminous documentation
about it from the command
  `tldoc tlmgr`
but basic operation is pretty straightforward.  The manager needs to
know where to download stuff from; the canonical setup is
```
tlmgr option repository http://mirror.ctan.org/systems/texlive/tlnet
```
which passes the decision to the mirror selector.  You can (of course)
specify a particular archive or mirror that you "trust", or even a
local disc copy that you keep up-to-date (disc space and bandwidth are
so cheap nowadays, that a "home mirror" of CTAN is a feasible
proposition).

To install a single package, use:
```
tlmgr install <package>
```

To update a single package that has previously been installed, use:
```
tlmgr update <package>
```

To update everything you already have in your installation, use:
```
tlmgr update --all
```

