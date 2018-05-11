# Chapter 6

LL\(1\) prediction conflict

* common prefixes
  * productions 的 前置詞一樣

```text
procedure Factor()
    for A in N do
        alpha = longestCommonPrefix(ProductionFor(A))
        while( abs(alpha) > 0 ) do
            V = new NonTerminal()
            Production = Production + {A-> 'alpha'V}
            foreach p in ProductionFor(A) or RHS(p) = 'beta'_p
                Production = Production - {p}
                Production = Production + {V->'beta'_p}
            alpha = longestCommonPrefix(ProductionFor(A)
end
    
```

* left recursion

```text
procedure EliminateLeftRecursion()
    for A in N do
        if r.all is ProductionFor(A) or RHS(r)=A'alpha'
            X = new NonTerminal()
            Y = new NonTerminal()
            for p in ProductionFor(A) do
                if p==r
                then Production = Production + {A -> XY}
                else Production = Production + {X -> RHS(p)}
            Production = Production + {Y -> 'alpha'Y , Y -> 'lambda'}
end
```



