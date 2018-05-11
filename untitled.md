---
description: Bottom-Up Parser
---

# Chapter 8

* Bottom-up
* shift reduce
* LR\(k\)
  * parsing engine
  * technique for engine table

## shift-reduce parser

needles for parsing

* stack 
* input buffer

![shift-reduce](.gitbook/assets/image.png)

### shift-reduce parsing technique

* parse-table
* TOS\(\)
* peek\(\)

## LR\(k\) Parsers

### LR\(0\) table construction

#### item & bookmark

* item = production + bookmark
* bookmark - progress bar
  * bookmark symbol ''."
* e.g. item for A -&gt; XYZ
  * .XYZ    // fresh item
  * X.YZ
  * XY.Z
  * XYZ.     // reducible item

#### closure

* closure\(items\)

```text
function Closure(State) return Set
    ans = state
    repeat
        prev = ans
        foreach (A->'alpha'‧B'gamma' in ans) do
            foreach p in ProductionFor(B) do
                ans = ans + {B->RHS(p)}
    until ans = prev
    retrun(ans)
endfu
```

