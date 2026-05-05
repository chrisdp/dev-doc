---
title: Table lint demo
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---

This file is a deliberate test fixture for the Table lint workflow. It contains
several broken tables, one per rule. Annotations should appear inline in the PR.

## pipe-no-blank-above (error)
| Col1 | Col2 |
| ---- | ---- |
| a    | b    |

## escaped-html-in-cell (error)

| Tag    | Renders as       |
| ------ | ---------------- |
| \<ul>  | literal text     |
| \<br/> | literal text     |

## pipe-split (error)

| A | B |
| - | - |
| 1 | 2 |

| A | B |
| - | - |
| 3 | 4 |

## html-blank-row (warning)

<table>
  <thead>
    <tr><th>X</th></tr>
  </thead>
  <tbody>
    <tr><td>1</td></tr>

    <tr><td>2</td></tr>

    <tr><td>3</td></tr>
  </tbody>
</table>
