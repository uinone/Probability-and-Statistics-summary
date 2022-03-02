# 1주차 확률과 통계 내용 정리

## 목차

- [Introduction to Probablity](#Introduction-to-Probablity)
- [Set Theory (operations & relations)](#Set-Theory-(operations-&-relations))
- [The definition of probability](#The-definition-of-probability)

## Introduction to Probablity

### 목차

- [Experiment](#Experiment)
- [Sample Space](#Sample-Space)
- [Event](#Event)

### Experiment

Experiment는 가능한 식별 가능한 모든 결과를 말한다. 모든 경우의 수를 다 세는 것을 설명하신듯.

### Sample Space

> $S$ 로 표기한다.

한 experiment에 대해 가능한 모든 결과들의 집합을 말한다.

주사위를 한 번 던질 때의 Sample Space는 다음과 같이 나타낸다.

$$
S = \{1, 2, 3, 4, 5, 6\}
$$

### Event

> $E$ 로 표기한다.

조건이 `잘 정의되었을 때`, 한 experiment에 대한 모든 가능한 결과들의 집합을 의미한다.

조건이 있기 때문에 모든 결과들을 의미하는 것이 아닌 부분집합(Subset)을 의미한다는 것을 잘 기억하자.

주사위에서 짝수만 나오는 사건들의 집합은 다음과 같이 나타낼 수 있다.

$$
E = \{ 2, 4, 6 \}
$$

`심지어 sample space 또한 하나의 event임을 생각하자.`

## Set Theory (operations & relations)

### 목차

- [Subset($\subset$)](<#Subset($\subset$)>)
- [Empty Set($\varnothing$)](<#Empty-Set($\varnothing$)>)
- [Complement($A^c$)](<#Complement($A^c$)>)
- [Union](#Union)
- [Intersection](#Intersection)
- [De Morgan's law](#De-Morgan's-law)
- [Distributive Property](#Distributive-Property)
- [Partitioning a set⭐](#Partitioning-a-set⭐)

### Subset($\subset$)

$A \subset B$ 라는 것은 다음 세 가지를 의미한다.

- A는 B의 부분집합이다.
- B는 A를 포함한다.
- $\forall a \in A, a \in B$

Sample Space의 부분집합인 A, B, C에 대해

- 만약 $A \subset B, B \subset C$ 라면 $A \subset C$ 이다.
- $A \subset B, B \subset A$ 라면 $A = B$ 이다.

### Empty Set($\varnothing$)

어떤 Event가 empty set이라는 것은 해당 event가 절대 일어나지 않는 다는 것을 의미한다.

예를 들어 주사위를 굴리는데 7 이상이 나오는 event는 존재하지 않으므로 empty set이라고 할 수 있다.

### Complement($A^c$)

특정 event A에 대해 complement(여집합)를 구하라는 것은 A가 일어나지 않는 event를 구하라는 것을 의미한다.

주사위를 굴림에 있어 짝수인 수가 나오는 event를 A라고 하면, A의 complement인 $A^c$는 $\{ 1, 3, 5 \}$ 라는 것을 알 수 있다.

따라서 다음 세 가지가 성립한다.

- $(A^c)^c = A$
- $\varnothing^c = S$
- $S^c = \varnothing$

### Union

두 event A, B를 union한다는 것을 기호로 표현하면 $A \cup B$ 으로 표현한다. 이는 A, B 그리고 A와 B가 동시에 일어나는 모든 사건들이 일어나는 event를 말한다.

이때 두 개 이상의 집합들을 union 시키고 싶다면 다음과 같이 표기한다.

$$
\displaystyle\bigcup_{i=1}^nA_i
$$

이때 n이 무한대로 갈 시 n만 $\infin$ 으로 바꿔주면 된다.

두 event A, B에 대해 다음이 성립한다.

- $A \cup B = B \cup A$
- $A \cup A = A$
- $A \cup A^c = S$
- $A \cup \varnothing = A$
- $A \cup S = S$
- 만약 $A \subset B$ 라면 $A \cup B = B$

따라서 다음과 같은 associative property(결합 법칙)이 성립한다.

$$
A \cup B \cup C = (A \cup B) \cup C = A \cup (B \cup C)
$$

### Intersection

두 event A, B에 대해 intersection한다는 것은 $A \cap B$ 로 표기한다. 이는 A와 B가 동시에 일어나는 event를 말한다.

두 개 이상의 집합들을 intersection 시키고 싶다면 다음과 같이 표기한다.

$$
\displaystyle\bigcap_{i=1}^nA_i
$$

n이 무한대로 갈 시 n만 $\infin$ 으로 바꿔주면 된다.

두 event A, B에 대해 다음이 성립한다.

- $A \cap B = B \cap A$
- $A \cap A = A$
- $A \cap A^c = \varnothing$
- $A \cap \varnothing = \varnothing$
- $A \cap S = A$

이때 $A \cap B = \varnothing$ 이라면 두 집합 A, B가 disjoint하다고 표현한다.

$A_i, \cdots , A_n$ 이 서로 disjoint하다는 것을 다음과 같이 나타낼 수 있다.

$$
A_i \cap A_j = \varnothing, (\forall i,j)
$$

### De Morgan's law

드 모르간 법칙은 다음 두 가지가 성립함을 보인다.

- $(A \cap B)^c = A^c \cup B^c$
- $(A \cup B)^c = A^c \cap B^c$

### Distributive Property

집합에서의 distributive property(분배 법칙)은 다음과 같이 나타낸다.

- $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$
- $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$

### Partitioning a set⭐

특정 집합 U에 대해 partitioning(쪼개기)을 한다는 것은 다음 조건이 성립한다는 것이다.

쪼개진 하나의 event를 $p_i$ 라고 하자.

1. $\displaystyle\bigcup_{i=1}^np_i = U$
2. $p_i \cap p_j = \varnothing (\forall i, j)$

밴다이어그램에서 서로 교집합이 있는 event A, B가 있다고 하자.

이때 A를 partitioning 한다면 A를 다음 두 개로 만들 수 있다.

$$
A = (A \cap B) \cup (A \cap B^c)
$$

즉 $A \cap B$ 와 $A \cap B^c$ 두개로 partitioning 했음을 알 수 있다.

또한 $A \cup B$ 는 $B$ 와 $A \cap B^c$ 의 합집합으로 나타낼 수 있으므로 이 또한 partitioning이다.

## The definition of probability

### 목차

- [Probablity](#Probablity)
- [Boole's inequality](#Boole's-inequality)
- [Probablity가 0인 Event는 일어날 수 없는 불가능한 event인가?](#Probablity가-0인-Event는-일어날-수-없는-불가능한-event인가?)

### Probablity

> 특정 event(E)에 대한 probablity는 $P(E)$ 로 표기한다.

$P(E)$ 는 하나의 값으로 나타내어지며 무조건 다음의 axioms를 만족시켜야한다.

1. $\forall A \subset S$ 라면 $0 \leq P(A)$ 이다.
2. $P(S) = 1$
3. $P(\displaystyle\bigcup_{i=1}^\infin A_i) = \displaystyle\sum_{i=1}^\infin P(A_i)$

이 axioms을 Kolmogorov axioms라 부른다.

차례대로 이해해보자.

#### 1. $\forall A \subset S$ 라면 $0 \leq P(A)$ 이다.

$P(A)$ 를 구하려면 S라는 event들 중 A라는 event가 얼마나 일어날 수 있는지를 알아야한다.

즉 이미 A가 S의 subset임을 명시했기 때문에 A라는 event가 일어나는 경우를 세어보면, 무조건 0 이상이다. 따라서 $P(A)$ 는 0 이상일 수밖에 없다.

#### 2. $P(S) = 1$

S라는 event들 중에서 S가 일어날 확률은 100% 즉 1과 같다.

#### 3. $P(\displaystyle\bigcup_{i=1}^\infin A_i) = \displaystyle\sum_{i=1}^\infin P(A_i)$

사실 이 axiom은 조건을 빼고 결과만 적었기 때문에 조건과 같이 설명하겠다.

1. 셀 수 있는 무한개(`혹은 유한개`)의 집합이 있으며
2. 집합들($A_1, A_2, \cdots$)이 서로 disjoint하다면

$$
P(\displaystyle\bigcup_{i=1}^\infin A_i) = \displaystyle\sum_{i=1}^\infin P(A_i), P(\displaystyle\bigcup_{i=1}^n A_i) = \displaystyle\sum_{i=1}^n P(A_i)
$$

서로 disjoint한 event A와 B가 있다고 하면, $A \cap B = \varnothing$ 이기 때문에 단순히 A가 일어날 경우와 B가 일어날 경우를 더한 값이 $A \cup B$ 가 일어날 경우의 수와 같다.

따라서 $A \cup B$ 가 일어날 확률도 마찬가지로 단순히 $P(A)$ 와 $P(B)$ 의 합과 같아진다. 즉 다음 식이 성립한다.

$$
P(A \cup B) = P(A) + P(B)
$$

따라서 셀 수 있는 무한개의 서로 disjoint한 집합들을 union시킨 후 확률을 구하는 것과 각각의 집합의 확률을 구한 다음 더하는 것은 같다는 것을 알 수 있다.

### $P(\varnothing) = 0$ 의 증명

셀 수 있는 무한개의 공집합($A_1, A_2, \cdots$, $A_i = \varnothing$)이 있다고 가정하자.

그렇다면 아무 $i, j$ 에 대해 $A_i \cap A_j$ 는 $\varnothing$ 즉 공집합임을 알 수 있고, 이는 서로 disjoint하다.

따라서 3번째 axiom에 의해 다음이 성립한다.

$$
P(\varnothing) = P(\displaystyle\bigcup_{i=1}^\infin A_i) = \displaystyle\sum_{i=1}^\infin P(A_i) = \displaystyle\sum_{i=1}^\infin P(\varnothing)
$$

위 식의 맨 첫번째와 마지막만을 보고 생각을 해보자.

$P(\varnothing)$ 과 $\displaystyle\sum_{i=1}^\infin P(\varnothing)$ 를 같게 만드는 유일한 값은 0임을 알 수 있다.

### $P(A \cap B^c) = P(A)-P(A \cap B)$ 의 증명

서로 disjoint하지 않은 집합 A, B가 있다고 가정하자. 이때 A를 $A \cap B$ 와 $A \cap B^c$ 로 partitioning했다고 하자.

두 집합의 intersection은 empty set이므로 서로 disjoint 하다고 할 수 있다.

집합의 수가 유한하며, mutually disjoint 하므로 3번째 axiom을 이용하면 다음과 같은 식이 성립한다.

$$
P(A) = P(A \cap B^c) + P(A \cap B)
$$

이때 $P(A \cap B)$를 좌변으로 넘기면 증명이 끝난다.

### Boole's inequality

이 부등식은 event들 간에 mutually disjoint하다는 조건이 없다.

이 부분이 3번째 axiom과 다른 점이며, 식에 차이를 준다.

각 event($A_1, A_2, \cdots $)에 대해 다음 부등식이 성립한다.

$$
P(\displaystyle\bigcup_{i=1}^\infin A_i) \leq \displaystyle\sum_{i=1}^\infin P(A_i)
$$

#### 증명

Event B는 다음과 같다고 하자.

$$
B_1 = A_1, B_2 = A_2 \cap A_1^c, B_3 = A_3 \cap (A_1 \cup A_2)^c, \cdots, B_i = A_i \cap (\displaystyle\bigcup_{j=1}^{i-1} A_i)^c
$$

$B_i$ 는 기존 $A_i$ 에서 다른 집합들과 겹치는 부분을 뺀 형태이다. 만약 겹치는 부분이 없다면 $A_i$ 와 같을 것이기 때문에 이는 $B_i \subseteq A_i$ 임을 알 수 있다.

$B_i$ 들을 모두 union 시키면 $A_i$ 와 같다. 겹치는 부분을 뺐지만 그 부분을 $B_{i-1}$ 이 채워서 합쳐지기 때문이다.

$A \cup B = (A \cap B^c) \cup (A \cap B)$ 를 떠올리면 되겠다.

따라서 $\displaystyle\bigcup_{i=1}^\infin A_i = \displaystyle\bigcup_{i=1}^\infin B_i$ 이며, $B_1, B_2, \cdots$ 들은 mutually disjoint 이므로 3번째 axiom을 만족한다. 따라서 다음 식이 성립하게 된다.

$$
P(\displaystyle\bigcup_{i=1}^\infin A_i) = P(\displaystyle\bigcup_{i=1}^\infin B_i) = \displaystyle\sum_{i=1}^\infin P(B_i)
$$

이제 원래 부등식을 조금 변형시키면 다음과 같아진다.

$$
\displaystyle\sum_{i=1}^\infin P(B_i) \leq \displaystyle\sum_{i=1}^\infin P(A_i)
$$

이때 $B_i \subseteq A_i$ 이기 때문에 $P(B_i) \leq P(A_i)$ 이다. 따라서 원래의 Boole의 부등식이 증명됨을 알 수 있다.

### Probablity가 0인 Event는 일어날 수 없는 불가능한 event인가?

이는 empty set과 헷갈릴 수 있는 개념이다.\
empty set은 애초에 일어날 일이 없는 불가능한 event임을 명시했기 때문에 확률이 0임을 알 수 있다.

하지만 확률이 0인 event이라고 해서 불가능한 event인것은 아니다.

실수로 이루어진 수평선이 있고, 0이상 1미만의 범위에서 균등하게 한 점을 뽑는다고 생각해보자. 이때 실수로 이루어진 수평선이기 때문에 분모가 한 없이 커져서 한 점을 뽑을 확률은 0이 된다.

그렇다고 한 점이 뽑힐 수 없는 불가능한 event인가? 라고 생각해보면 아님을 알 수 있다.

즉, 확률이 0이라고 해서 불가능한 event는 아니다.
