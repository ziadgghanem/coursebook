---
layout: post
title: 'Algebraic Topology'
---

### paths and homotopy

A path in a space $X$ is a continuous map $f:I \rightarrow X$ two paths are said to be homotopic if one can be continuously deforrmed to the other with endpoints fixed.

We define a homotopy of paths as the family of maps $f_t:I \rightarrow X$ such that
1. $f_t(0) = x_0$ and $f_t(1) = x_1$ for all $t \in I$
2. The map $F: I \times I \rightarrow X$ defined by $F(t,x) := f_t(x)$ is continuous

In these terms, the paths $f_1, f_2$ with coincident endpoints $x_0,x_1$ are homotopic if there exists a homotopy $f_t$ connecting them.

<div class="example">
  ***Example: Path Homotopy in Convex Spaces***  
  \Large
  In any convex space $X$ two paths $f,g:I \rightarrow X$ having the same endpoints are homotopoic via the homotopy $h_t(x) = (1-t)f(x) + tg(x)$
</div>
