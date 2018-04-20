# Top-Down Parser

overview

* 理論上，Top-down parser 不比 bottom-up parser 有效力
* 實際上，TD parser 比 BU parser 更被廣泛的應用
  * 效率、簡潔、除錯易

-

Forms

* Recursive-descent parser
* Table-driven LL parser

* Derivation vs Parsing

* 兩者是反向的

  * Derivation 是由 grammar 長出樹
  * Parsing 是由 input 找出符合 grammar 的樹

parsing technique

* top down
* predictive
* LL\(k\)
  * k : number of symbols of lookahead
* recursive descent

---

#### Recursive descent

* parsing next k

* predict set

#### LL\(k\)

Predict set for LL\(1\)

* empty set
* more than one production
* exactly one production

---

#### predict set的計算方式

* 由 first, follow 組成
* ![](/assets/compute-predict-set.png)
  * First\(A\)若為空，找Follow\(A\)

---

#### 檢查是否為LL\(1\)的方法

假設 A-&gt;a\|b 為 grammar G的一個production

1. First\(a\) 不可以含有任何First\(b\)之terminal
   1. predict set 中的元素不可有交集
2. a,b至少有一可以生出λ
3. * 如果 b-&gt;\*λ ，First\(a\)不可包含任何First\(A\)之terminal
   * 如果 a-&gt;\*λ ，First\(b\)不可包含任何First\(B\)之terminal

* ![](/assets/isLL1.png)![](/assets/predict_set.png)



