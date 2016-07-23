# Exercises
1. Write all programs in the slides and feed them into the CafeOBJ system. Moreover, write some more test code and do some more testing for the programs.
2. Revise the simulator (including the revised one) so that it can deal with the case in which there are four threads.

# レポート

#### E‐strategy

NAT-TRIPLE-IMLMの `strat: (1 0)` は評価の順番を指定している。
このケースではまず1つめのタームから評価し、最後に全体がredexかどうかを評価してone-step-rewriteを行う。

NAT-TRIPLE-OMLMの `strat: (0 1 0)` の場合は、まず全体がredexかどうか評価してone-step-rewriteを行い、
次に取り出された最初の要素を評価する。

CafeObjはユーザーが指定せずとも最適な評価戦略を用いる。
例えば `if_then{_}else{_}` は (1 0 2 3) と評価する。
これは第1引数がtrueかfalseであることを評価したあとone-step-rewriteを行い、第2、第3引数の式を評価する。

#### Infinite Lists

任意の有限な長さのリストを生成する式を表現できる。
INF-LIST は汎用的な要素をとる無限リストである。
NAT-INF-LIST はその要素が NAT である。

#### Sieve of Eratosthenes

ERATOSTHENES-SIEVE は無限リストを用いてエラトステネスのふるいを定義している。
末端がnilであるケースを考えなくてよいのでシンプルになっている。

#### Hamming’s Problem

HAMMING は無限リストを用いてハミング問題を定義している。
末端のnilのケースが省略でき、マージ処理がシンプルになっている。

#### Simulator of a Mutex Protocol

下記のような t1 & t2のマルチスレッドシステムを考える。

```
Loop: “Remainder Section”
  rs: while test&set(locked) = true {}
  ms: locked := true;
    “Critical Section”
  cs: locked := false;
```

* Remainder Section: 共有資源をもちいない
* Critical Sction: 共有資源をもちいる

1. 最初 t は rs へ入り `locked` が false であるか確認する
  - Y: ms へ入り `locked` を true に変更し Critical Section の操作を行う
  - N: rs にとどまり続ける
2. t が cs まで達したとき `locked` を false に変更し Remainder Section へ戻る
