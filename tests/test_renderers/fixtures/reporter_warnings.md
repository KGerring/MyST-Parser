Duplicate Reference definitions:
.
[a]: b
[a]: c
.
source/path:2: (WARNING/2) Duplicate reference definition: A
.

Missing Reference:
.
[a](b)
.
source/path:1: (WARNING/2) Reference not found: b
.

Unknown role:
.
abc

{xyz}`a`
.
source/path:3: (ERROR/3) Unknown interpreted text role "xyz".
.

Unknown directive:
.

```{xyz}
```
.
source/path:2: (ERROR/3) Unknown directive type "xyz".
.

Bad Front Matter:
.
---
a: {
---
.
source/path:1: (ERROR/3) Front matter block:
while parsing a flow node
expected the node content, but found '<stream end>'
  in "<unicode string>", line 1, column 5:
    a: {
        ^
.

Directive parsing error:
.

```{class}
```
.
source/path:2: (ERROR/3) Directive 'class': 1 argument(s) required, 0 supplied
.

Directive run error:
.

```{date}
x
```
.
source/path:2: (ERROR/3) Invalid context: the "date" directive can only be used within a substitution definition.
.

Non-consecutive headings:
.
# title 1
### title 3
.
source/path:2: (WARNING/2) Non-consecutive header level increase; 1 to 3
.
