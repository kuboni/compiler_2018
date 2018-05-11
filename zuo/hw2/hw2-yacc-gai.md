---
description: Yacc parser
---

# HW2 - Yacc 概覽

## Yacc - Yet Another Compiler Compiler

### Yacc 程式架構

{% code-tabs %}
{% code-tabs-item title="yacc architecutre" %}
```c
%{
    C declarations
%}
    yacc declarations
%%
    Grammar rules
%%    
    Additional C code
```
{% endcode-tabs-item %}
{% endcode-tabs %}

* Declarations

```text
%{
    #include <stdio.h>
    #include <stdlib.h>
%}
%token ID NUM
%start expr
```

| **Yacc declaration** | **說明** |
| --- | --- | --- | --- | --- | --- | --- | --- |
| %start | 指定grammar的 start symbol |
| %union | 宣告semantic values可能會有的資料型態集合 |
| %token | 宣告terminal symbol |
| %type | 使用%union宣告的名字，宣告 nonterminal symbol的semantic values |
| %right | 宣告 right-associative 的 terminal symbol |
| %left | 宣告 left-associative 的 terminal symbol |
| %nonassoc | 宣告一個無相關性的\(nonassociative\)的terminal symbol |

### Lex & Yacc 執行檔案

![](../../.gitbook/assets/image%20%281%29.png)

#### 編譯指令

```text
yacc -d bas.y    # create y.tab.h y.tab.c
lex bas.l        # create lex.yy.c
cc lex.yy.c y.tab.c -o bas.exe    # compile/link
```

