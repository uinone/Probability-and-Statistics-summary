# 2주차 확률과 통계 내용 정리

## 목차

- Finite Sample Space
- Counting Methods
- Conditional Probability
- Independent Events

## Finite Sample Space

Finite Sample Space는 말 그대로 공간이 유한하므로 다음과 같이 나타낼 수 있다.

$$
|S| = n, S = \{ s_1, \cdots s_n \}
$$

따라서 Simple Sample Space S란

1. S의 크기가 유한하며
2. $P(s_1 occurs) = P(s_2 occurs) = \cdots = P(s_n occurs) = {1 \over n}$

따라서 만약 A라는 event가 m개의 결과를 포함하는 event라면 $P(A) = {m \over n}$ 임을 알 수 있다.

## Counting Methods

### Multiplication Rule

예를들어 k개의 단계로 이루어진 experiment가 있다고 생각하자.

이때 $n_i$ 가 $i$번째 단계에서 나올 수 있는 결과의 수라고 한다면, $|S| = n_1 \cdot n_2 \cdots n_k$ 와 같다.

### Permutation

n개의 요소로 구성된 집합이 존재한다고 하자.

`중복을 허락하지 않으면서 순서가 존재하도록` 집합에서 k개의 요소를 고르는 모든 경우를 구하는 것이 n으로부터 k개의 permutation이라고 할 수 있다.

이때 k개의 요소를 구할 때 순서가 존재하도록 뽑아야하므로 이는 k개의 단계로 이루어진 experiment라고 할 수 있다.

따라서 n개의 원소에 대한 k개의 permutation은 다음과 같이 나타낸다.

$$
n \cdot (n-1) \cdots (n-k+1) = {n! \over (n-k)!}
$$

### Combinations

n개의 요소로 구성된 집합이 존재한다고 하자.

이때 S에서 크기가 k인 부분집합을 모두 구하는 경우의 수를 n개의 원소에 대한 k개의 Combination이라고 한다.

이때 부분집합이기 때문에 당연히 `중복이 없으며 부분집합을 구성하는 원소만 같다면 서로 같은 부분집합으로 본다`는 것을 알아두자.

이때 permutation한 결과에서 크기 k에 대해 고려된 순서를 다시 고려하지 않도록 만들기 위해서는 k!만큼을 한가지 경우로 만들어야한다. 따라서 permutation한 결과에 k!을 곱해주면 combination의 일반화라고 할 수 있다.

이를 수식으로 나타내면 다음과 같다.

$$
{n \choose k} = {n! \over (n-k)!} \cdot {1 \over k!}
$$

## Conditional Probability

두 event A, B에 대해 event B가 발생했을 때, A가 발생할 확률을 conditional probablity라고 한다. 이는 다음과 같이 표기한다.

$$
P(A|B) = {P(A \cap B) \over P(B)}, if P(B) > 0
$$

### Multiplication rule for conditinal probability

event A, B에 대해 다음 두가지가 성립한다.

1. 만약 $P(B) > 0$ 라면, $P(A \cap B) = P(A | B) \cdot P(B)$
2. 만약 $P(A) > 0$ 라면, $P(A \cap B) = P(B | A) \cdot P(A)$

### Generalization form

$A_1 \cdots A_n$ events에 대해 $\forall i$, $P(A_i) > 0$ 라면
$$P(\displaystyle\bigcap^{n}_{i=1}A_i) = P(A_1) \cdot P(A_2 | A_1) \cdot P(A_3 | A_1 \cap A_2) \cdots P(A_n | A_1 \cap A_2 \cdots A_{n-1})$$

#### 증명

우변의 조건부 확률을 풀어서 전부 곱해보면 결국 좌변이 남게된다.

$$\cancel{P(A_1)} \cdot {\cancel{P(A_1 \cap A_2)} \over \cancel{P(A_1)}} \cdot {\cancel{P(A_1 \cap A_2 \cap A_3)} \over \cancel{P(A_1 \cap A_2)}} \cdots { P(A_1 \cap A_2 \cdots \cap A_n) \over \cancel{P(A_1 \cap A_2 \cdots \cap A_{n-1})}}$$

### Conditional probability and partitions

#### Low of total probability

event $B_1 \cdots B_k$ 가 S의 `k개의 partitions`라고 하고 각각의 확률은 0보다 크다고 하자.

이때 $A \subset S$ 인 A에 대해 다음이 성립한다.

$$
P(A) = \displaystyle\sum^k_{i=1} P(B_i) \cdot P(A | B_i)
$$

##### 증명

집합 S에 대해 partition $B_1 \cdots B_k$에 대해
$$A = (B_1 \cap A) \cup (B_2 \cap A) \cdots \cup (B_k \cap A)$$

이때 각각의 intersection들은 mutually disjoint하므로 axiom 3에 의해 $P(B_i) > 0$ 일때 $P(A) = \displaystyle\sum^k_{i=1} P(B_i \cap A)$ 이다.

따라서 $\forall i$에 대해 $P(A) = \displaystyle\sum^k_{i=1} P(B_i) \cdot P(A | B_i)$ 이다.

##### ex) Game

조건은 다음과 같다.

1. 1~50 사이의 수중 하나를 골라 이를 X라 하자.
2. X이상인 수 Y가 나올때까지 수를 계속 뽑는다.(`중복이 허용된다.`)

event $A_i$를 $X = i$ 라 하고, B를 Y가 50인 event라고 하자.

특정 X를 뽑았을 때, 50이 뽑혀 게임이 종료되려면, X 이상 50 이하인 수 중 50이 뽑힐 확률을 구해야한다.

이는 $1 \over 50-X+1$ 임을 알 수 있다. 저 범위($X \leq 50$) 내에서 50이 나오는 사건(B)은 단 하나이기 때문이다.

따라서 이를 일반화 하면 다음과 같다.

$$P(B | A_i) = {1 \over 50-i+1}$$

또한 $A_1 \cdots A_{50}$ 은 `중복이 가능하게 뽑으므로` 서로 mutually disjoint함을 알 수 있다.

결과적으로 50개의 partitions($A_1 \cdots A_{50}$)를 가진 집합 S에서 $B \subset S$ 인 event B의 확률은 Low of total probability에 의해 다음과 같다.

$$
P(B) = \displaystyle\sum^{Y}_{i=1} P(A_i) \cdot P(B | A_i)
$$

이때 $P(A_i) = {1 \over 50}$ 이며 $P(B | A_i) = {1 \over 50-i+1}$ 그리고 $Y = 50$ 이므로

$$
P(B) = \displaystyle\sum^{50}_{i=1} {1 \over 50} \cdot {1 \over 50-i+1}
$$

가 성립함을 알 수 있다.

## Independent Events⭐

두 event A, B가 서로 independent라는 것은 서로가 서로에게 영향을 주지 않는 다는 것을 말한다. 따라서 conditional probability를 구하더라도 event 각각이 일어날 확률과 같다.

이는 $P(A | B) = P(A)$ 이며 ${P(A \cap B) \over P(B)} = P(A)$ 와 동치이다.

또한 $P(A \cap B) = P(A) \cdot P(B)$ 와 동치이다.

independent인 두 event A, B에 대해 $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ 라고 할 수 있다. 이때 왜 $A \cap B$ 의 확률까지 빼줘야하는 지 의아할 수 있다.

아무리 두 event가 독립이어도 동시에 일어날 수 있기 때문이다.

따라서 $P(A \cup B)$ 를 구할때 두 event가 독립이더라도 $P(A \cap B)$ 도 같이 빼주어야한다.

### Independence of complements

만약 event A, B가 서로 independent이라면 A와 $B^c$ 또한 independent이다.

#### 증명

$P(A \cap B^c) = P(A) - P(A \cap B)$

$P(A) - P(A \cap B) = P(A) - P(A) \cdot P(B)$ (A 와 B는 independent이기 때문에)

$P(A) - P(A) \cdot P(B) = P(A)(1 - P(B))$

$P(A)(1 - P(B)) = P(A) \cdot P(B^c)$

### Mutually Independent Events

k개의 events $A_1 \cdots A_k$ 가 mutually independent라고 하는 것은 다음과 동치이다.

$\forall subset$ $\{A_{i_1}, \cdots , A_{i_j}\}$ for $2 \leq j \leq k$ 에 대해 다음이 성립한다.

$$
P(A_{i_1} \cap A_{i_2} \cap \cdots \cap A_{i_j}) = P(A_{i_1}) \cdot P(A_{i_2}) \cdots P(A_{i_j})
$$

이때 $\forall subset$ $\{A_{i_1}, \cdots , A_{i_j}\}$ 에서 각 $A_{i_j}$ 는 k개의 events $A_1 \cdots A_k$ 에서 j개의 event를 골랐다는 것을 의미한다.

따라서 k개의 event들에서 고른 $A_{i_j}$ 들은 서로 mutually independent이므로 위 식이 성립한다.

#### ex) 기계

1. 기계는 6개의 물건을 생산한다.
2. 각각의 물건은 결함이거나 결함이 아닐 수 있으며, 각각의 물건들은 mutually independent하게 생산된다.

따라서 결함일 확률을 $T$, $i$ 번째 물건이 결함일때 $D_i$ 라고 하면

$P(D_1) = P(D_2) = \cdots = P(D_6) = T$ 이다.

만약 2개의 물건이 결함일 확률을 구한다고 하자.

그럼 나머지 4개의 물건은 결함이 아니기 때문에 다음과 같이 나타낼 수 있다.

예를들어 1, 2번이 결함이라면

$$
P(D_1 \cap D_2 \cap D^c_3 \cap D^c_4 \cap D^c_5 \cap D^c_6) = T \cdot T \cdot (1-T) \cdot (1-T) \cdot (1-T) \cdot (1-T)
$$

하나의 경우에 대해 확률을 구하면 $T^2 \cdot (1-T)^4$ 임을 알 수 있다.

이제 6개중 무작위로 2개를 골랐을 때, 그 2개의 물건이 결함일 확률을 구하자면 다음과 같다.

$$
{6 \choose 2} \cdot T^2 \cdot (1-T)^4
$$
