---
layout: compact
title: Useful Phrases in One Page
---

Regex, AV Code: `\(Av[0-9]+,P[0-9]+\)`

Regex, SRT to Texts: `\n\n[0-9]+\n[0-9]+:[0-9]+:[0-9]+,[0-9]+ --> [0-9]+:[0-9]+:[0-9]+,[0-9]+\n`

Regex, Any Strings until: `^[\u0000-\uFFFF]* \- (?=\d)`

^[\u0000-\uFFFF]* \- (?=\d)|\(Av[0-9]+,P[0-9]+\)

^[\u0000-\uFFFF]* \- (?=\d)([0-9]{1,3})\.([0-9p]{1,3})|\(Av[0-9]+,P[0-9]+\)
$1