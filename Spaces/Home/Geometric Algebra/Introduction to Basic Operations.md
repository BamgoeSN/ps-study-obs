이 문서는 다음 영상에 기반을 두고 있다.

<https://youtu.be/2AKt6adG_OI>
# Multivectors
- $k$-vector는 $k$-dimensional subspace를 의미한다.
- $k = 0,\ 1,\ 2,\ 3$ 각각에 대해 scalar, vector, bivector, trivector라 부른다.
- Multivector는 여러 개의 $k$-vector의 합을 의미한다. 즉, Multivector = Scalar + Vector + Bivector + ... 이다.
# Grade Projection Operator
- Multivector $A$에 대해 ${\left< A \right>}_k$는  $A$의 $k$-vector 부분만을 남긴다.
	- $k = 0$일 땐 subscript를 보통 생략한다.
	- ${\left< a + be_1 + ce_2 + de_1e_2 \right>} = a$
	- ${\left< a + be_1 + ce_2 + de_1e_2 \right>}_1 = be_1+ce_2$
	- ${\left< a + be_1 + ce_2 + de_1e_2 \right>}_2 = de_1e_2$
- 어떤 multivector $A$가 ${\left< A \right>}_k = A$를 만족할 때, $A$ has a grade of $k$라고 한다.
# Geometric Product
## The Meaning of Geometric Product
여러 가지 picture에서 바라볼 수 있다. 여기서의 설명은 exhaustive하지 않다.
### Geometric Picture
Vanilla geometric algebra(VGA)에서의 관점에서 보자.
- 두 평행한 벡터 $\vec{u}$, $\vec{v}$의 geometric product $\vec{u}\vec{v}$는 둘의 길이이다.
- 두 벡터가 반대 방향을 보고 있으면 둘의 길이에 부호가 반대이다.
- 두 벡터가 수직이면 $\vec{u}\vec{v}$는 두 벡터로 span되는 bivector이다.
- 두 벡터가 수직하지도 평행하지도 않으면, 한 벡터를 다른 벡터에 평행한 성분과 수직인 성분으로 나눈 후 분배법칙을 적용한다.
즉, geometric product는 "평행한 성분은 서로 상쇄하고" "수직인 성분은 서로 합쳐지는" 곱셈이라고 생각할 수 있다.
### Algebraic Picture
VGA 외의 GA에서는 어떻게 생각해야 할까?
- Orthonormal basis가 $e_1$ ~ $e_n$으로 주어진다고 하자.
- $i \ne j$면 $e_i e_j$는 bivector이다.
- $i \ne j$면 $e_ie_j = -e_je_i$이다.
- $e_i e_i$는 scalar이지만, 이 값은 $1$, $-1$, $0$ 중 하나이다.
	- VGA에선 $e_i^2 = 1$이다.
	- Euclidean PGA에선 $e_0^2 = 0$이고 나머지에 대해선 $e_i^2 = 1$이다.
	- CGA에선 $e_+^2 = 1$, $e_-^2=-1$이다.
- 제곱이 $1$인 basis가 $p$개, $-1$인 게 $q$개, $0$인 게 $r$개 있는 GA를 $\mathbb{G}(p, q, r)$ 또는 $\mathrm{Cl}(p, r ,q)$이라 한다. 여기서 $\mathrm{Cl}$은 GA의 개념을 처음 세운 Clifford의 이름을 따온 것이다.
	- 예시로 $\mathbb{G}(1, 1, 1)$에서의 geometric product를 보자.
	- 이 GA는 $e_1^2 = 1$, $e_2^2=-1$, $e_0^2=0$인 세 basis를 갖는다.

$$ \begin{aligned}
(e_1 - e_0e_2)(2+e_1e_2-e_0e_1) &=
2e_1 + e_1e_1e_2 - e_1e_0e_1 - 2e_0e_2 - e_0e_2e_1e_2 + e_0e_2e_0e_1 \\ &=
2e_1 + e_1e_1e_2 + e_0e_1e_1 - 2e_0e_2 + e_0e_1e_2e_2 - e_0e_0e_2e_1 \\ &=
2e_1 + e_2 + e_0 - 2e_0e_2 + e_0e_1e_2e_2 - e_0e_0e_2e_1 \\ &=
2e_1 + e_2 + e_0 - 2e_0e_2 - e_0e_1 - e_0e_0e_2e_1 \\ &=
2e_1 + e_2 + e_0 - 2e_0e_2 - e_0e_1
\end{aligned} $$
- 여기부터 여러 basis의 geometric product를 $e$를 생략하여 index만을 연달아 쓴다. 즉, $e_{ij} := e_i e_j$, $e_{ijk} := e_ie_je_k$와 같은 식이다.
$$ (e_1 - e_0e_2)(2+e_1e_2-e_0e_1) = 2e_1 + e_2 + e_0 - 2e_{02} - e_{01} $$
### Transformation Picture
Geometric product는 변환과 관련지어서 생각할 수 있다.
- 2D VGA에서의 회전
	- 두 unit vectors $\hat{u}$, $\hat{v}$에 대해, 벡터 $\vec{a}$를 $\hat{u} \rightarrow \hat{v}$의 각도만큼 회전시킨 벡터는 $\vec{a} \hat{u} \hat{v}$이다.
	- $\hat{v} \hat{u} \vec{a}$는 같은 결과를 낸다.
	- 이는 2차원에서의 GA에서만 유효하다.
- 2D VGA에서의 대칭
	- 어떤 unit vector $\hat{v}$에 대해 $\vec{a}$를 대칭시킨 벡터는 $\hat{v} \vec{a} \hat{v}$이다.
	- 이는 임의의 차원의 VGA에서 유효하다.
- VGA에서의 임의의 orthogonal transformation
	- 대칭을 두 번 적용한 $\hat{u}\hat{v}\vec{a}\hat{v}\hat{u}$는 회전 변환을 두 번 적용한 것과 동치이다.
	- 임의의 orthogonal transformation은 $\cdots \hat{w} \hat{v} \hat{u} \vec{a} \hat{u} \hat{v} \hat{w} \cdots$처럼 대칭을 조합한 것으로 생각할 수 있다.
	- 대칭은 차원에 구애받지 않으므로 이 성질 역시 차원과 무관하다.
## Reverse Operation
- ${(\vec{u}\vec{v}\vec{w})}^\dagger := \vec{w}\vec{v}\vec{w}$
- ${(\alpha A + \beta B)}^\dagger = \alpha A^\dagger + \beta B^\dagger$
- Reverse는 $k=0,1,4,5,8,9, \cdots$에 대해 $k$-vector의 부호를 유지하며, $k=2,3,6,7,10,11,\cdots$에 대해 $k$-vector의 부호를 뒤집는다.
## Grade Involution
- Reverse에 비해 부호의 반전이 다른데, $k$가 홀수면 부호를 뒤집고 짝수면 유지한다.
- ${(A+B)}^* = A^* + B^*$
- $(\alpha A)^* = \alpha A^*$
- $(AB)^* = A^*B^*$
## Magnitude of Multivectors
- $|A|^2 := \left< A^\dagger A \right>$
- 일반적인 GA에선 magnetude의 제곱에만 관심을 둔다.
# Other Products
## Outer Product
- $j$-vector $A_j$와 $k$-vector $B_k$에 대해 $A_j \wedge B_k = {\left< A_j B_k \right>}_{j+k}$이다.
	- Factor를 공유하는 두 multivector의 outer product는 $0$이다.
	- Factor를 공유하지 않는 multivector의 outer product는 geometric product와 같다.

$$\begin{aligned}
(e_{01} + e_{56}) \wedge (e_{1234} + e_{3456}) &=
e_{01} \wedge e_{1234} + e_{01} \wedge e_{3456} + e_{56} \wedge e_{1234} + e_{56} \wedge e_{3456} \\ &=
e_{01} \wedge e_{3456} + e_{56} \wedge e_{1234} \\ &=
e_{013456} + e_{561234} = e_{013456}+ e_{123456}
\end{aligned}$$
## Duals
- Orthogonal complement of an object
- Hodge star를 사용해 $\star A$로 표기한다.
- 정의는 다음과 같이 주어진다.
	- Basis multivector 중 $k$가 가장 큰 것을 pseudoscalar $i$로 정의한다.
		- 예시로 basis vector가 $\{e_1, e_2, e_3\}$으로 주어지면 basis multivector는 $\{1, e_1, e_2, e_3, e_{12}, e_{23}, e_{13}, e_{123}\}$이며, $i = e_{123}$이다.
	- 모든 basis multivector $E$의 dual을 $E\ \star E = i$인 $\star E$로 정의한다. 여기서 쓰이는 곱셈은 geometric product이다.
	- 모든 multivector의 dual은 이로부터 선형성을 활용하여 계산한다.
## Regressive Product
- 대강 두 multivector가 의미하는 subspace의 교집합 정도로 보면 된다.
$$ A \vee B := \star^{-1} (\star A \wedge \star B) $$
- 같은 multivector의 regressive product는 $0$이다.
## Inner Product
- $j$-vector $A$와 $k$-vector $B$가 있다고 할 때, 둘의 내적 $A \cdot B$의 정의는 $j$, $k$의 대소관계에 따라 갈린다.
	- WLOG $j \le k$일 때, $A$의 $B$에 대한 projection을 $A_\parallel$이라 하자.
	- $A \cdot B := A_\parallel B$이고, $B \cdot A := BA_\parallel$이다.
- 실제 계산에선...
	- 우선 분배법칙으로 분해한다.
	- 한 vector가 다른 vector에 완전히 포함되면 geometric product로 변환한다.
		- $e_{56} \cdot e_{3456} = e_{56} e_{3456} = e_{345566}$
	- 그렇지 않은 경우엔 전부 $0$이다.
		- $e_{12} \cdot e_{134} = 0$
## Outer / Inner Product and Geometric Product
-  $A_j \wedge B_k = {\left< A_j B_k \right>}_{j+k}$
- $A_j \cdot B_k = {\left< A_j B_k \right>}_{|j-k|}$
- $j$, $k$의 대소관계에 구애받지 않는 inner product의 변형판은 left/right contraction으로 정의할 수 있다.
	- Left contraction $A_j \lrcorner B_k := {\left< A_j B_k \right>}_{k-j}$는 $A_j$를 $B_k$에 projection한 것이다.
	- Right contraction $A_j \llcorner B_k := {\left< A_j B_k \right>}_{j-k}$는 $B_k$를 $A_j$에 projection한 것이다.
	- Grade가 음수인 grade projection은 항상 결과가 $0$인 것으로 간주한다.
	- Inner product는 left/right contraction 중 nonzero인 것으로 정의하는 셈이다.
	- 적용에는 inner product가 쓰이고, 이론 전개에는 left/right contraction이 쓰인다.