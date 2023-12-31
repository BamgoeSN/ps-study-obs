# Geometric Algebra
- 벡터나 쿼터니온 등과 같은 기하 연산을 극단적으로 추상화한 물건
- Clifford algebra라고도 부르며, GA라고 줄여서 부름
- 스칼라, 벡터 등을 multivector로 추상화하여 다룬다.
## Multivectors
- $n$차원 GA에서 $k$-vector는 $k$차원 subspace를 의미한다.
- $k=0, 1, 2, 3$ 각각에 대해 scalar, vector, bivector, trivector라 부른다.
- Multivector는 여러 개의 $k$-vector 합을 의미한다.
- 두 개의 multivector를 곱하는 가장 기본적인 연산을 geometric product라 하며, 두 multivector $u$, $v$의 geometric product는 $uv$로 표기한다. 그 의미와 성질은 후술한다.
## Basis Multivectors
- GA는 multivector로 이뤄진 basis 체계를 갖는다.
- $2$차원 GA를 예시로 들어보자.
	- Scalar basis는 $1$로 유일하다.
	- Vector basis는 $e_0$, $e_1$ 두 개가 있다.
		- Index는 0-based여도 되고 1-based여도 된다.
	- Bivector basis는 vector basis 2개의 모든 geometric product이다. 여기선 $e_0e_1$로 유일하다.
		- 둘 이상의 vector basis의 geometric product는 편의상 index를 이어서 쓰는 것으로 표기한다. 예를 들어 $e_{01} := e_0 e_1$이다.
- $n$차원 GA에서 unit pseudoscalar는 $e_{0 1 2 \cdots (n-1)}$로 정의된다.
## Grade Projection Operator
- Multivector $A$의 $k$차 grade projection ${\left< A \right>}_k$는 $A$의 $k$-vector 성분만을 의미한다.
	- $k = 0$일 땐 subscript를 보통 생략한다.
	- ${\left< a + be_1 + ce_2 + de_{12} \right>} = a$
	- ${\left< a + be_1 + ce_2 + de_{12} \right>}_1 = be_1+ce_2$
	- ${\left< a + be_1 + ce_2 + de_{12} \right>}_2 = de_{12}$
- ${\left< A \right>}_k = A$일 때를 $A$ has a grade of $k$라고 한다.
## Geometric Product
- 두 개의 multivector를 곱하는 가장 일반적인 형태이다.
### Geometric Interpretation
- 가장 단순한 2차원에서의 평면벡터 연산을 고려한다.
- $e_0$, $e_1$은 일반적으로 생각하는 $x$, $y$ 방향의 단위벡터이다.
- 방향이 같은 두 평행한 vector $u$, $v$의 geometric product $uv$는 둘의 길이 곱이다.
- 방향이 반대인 두 평행한 vector $u$, $v$의 geometric product $uv$는 둘의 길이 곱에 $-$ 부호를 붙인다.
- 수직인 두 벡터의 geometric product는 bivector이다. 두 벡터로 만들어지는 직사각형에 대응된다.
- 일반적인 두 벡터의 geometric product는, 한 벡터를 다른 벡터에 평행/수직인 성분으로 나누어 분배법칙을 적용하여 계산한다. 그러면 scalar + bivector 형태의 multivector가 나온다.
### Algebraic Properties
- Orthonormal basis $e_1$ ~ $e_n$이 주어진다고 하자.
- $i \ne j$면 $e_{ij}$는 bivector이며, $e_{ij} = -e_{ji}$이다.
- $e_{ii} =: e_i^2$은 scalar이다.
	- $e_i^2$의 값은 GA의 정의에 따라 다르며, $1$, $-1$, $0$ 중 하나이다.
	- 제곱이 $1$인 basis가 $p$개, $-1$인 게 $q$개, $0$인 게 $r$개 있는 GA를 $\mathbb{G}(p, q, r)$ 또는 $\mathrm{Cl}(p, q, r)$이라고 한다.
		- 예시로 $e_1^2 = 1$, $e_2^2 = -1$, $e_0^2=0$인 GA를 보자. 이 GA는 $\mathbb{G}(1, 1, 1)$이다.
		- 여기서 $(e_1 - e_0e_2)(2+e_1e_2-e_0e_1)$를 계산해보자.
		- 분배법칙을 적용하면 $2e_1 + e_{112} - e_{101} - 2e_{02} - e_{0212} + e_{0201}$이다.
		- $e_{ij} = -e_{ji}$임을 적용하면 $2e_1 + e_{112} + e_{011} - 2e_{02} + e_{0122} - e_{0021}$이다.
		- 같은 basis의 제곱에 대한 식을 적용하면 $2e_1 + e_2 + e_0 - 2e_{02} - e_{01}$이다.
		- 따라서 $(e_1 - e_0e_2)(2+e_1e_2-e_0e_1) = 2e_1 + e_2 + e_0 - 2e_{02} - e_{01}$이다.
### Relation with Transformations
- 2차원 평면벡터를 다루는 GA에서의 회전
	- 두 unit vectors $\hat{u}$, $\hat{v}$에 대해, 벡터 $\vec{a}$를 $\hat{u} \rightarrow \hat{v}$를 따라 회전시킨 벡터는 $\vec{a}\hat{u}\hat{v} = \hat{v}\hat{u}\vec{a}$이다.
	- Unit vector는 그 magnitude가 $1$인 vector이다.
- $n$차원 벡터를 다루는 GA에서의 대칭
	- 어떤 unit vector $\hat{v}$에 대해 $\vec{a}$를 대칭시킨 벡터는 $\hat{v}\vec{a}\hat{v}$이다.
	- 더 나아가, 임의의 orthogonal transformation은 대칭의 연속으로 표현할 수 있다. 즉, $\cdots \hat{w} \hat{v} \hat{u} \vec{a} \hat{u} \hat{v} \hat{w} \cdots$의 형태로 기술할 수 있다.
## Operations Related with Geometric Product
### Reverse
- ${(\vec{u}\vec{v}\vec{w})}^\dagger := \vec{w}\vec{v}\vec{w}$
- ${(\alpha A + \beta B)}^\dagger = \alpha A^\dagger + \beta B^\dagger$
- Reverse는 $k=0,1,4,5,8,9, \cdots$에 대해 $k$-vector의 부호를 유지하며, $k=2,3,6,7,10,11,\cdots$에 대해 $k$-vector의 부호를 뒤집는다.
### Grade Involution
- Reverse와 동일하나 부호의 반전에 대한 성질이 다른데, $k$가 홀수면 부호가 뒤집히고 짝수면 안 뒤집힌다.
- $(\alpha A + \beta B)^* = \alpha A^* + \beta B^*$
- $(AB)^* = A^* B^*$
### Magnitude of Multivectors
- $|A|^2 := \left< A^\dagger A \right>$
- Magnitude가 음수일 때도 있기 때문에 일반적으로는 magnitude의 제곱만 다룬다.
## Other Products
### Outer Product
- $j$-vector $A_j$와 $k$-vector $B_k$에 대해 $A_j \wedge B_k := {\left< A_jB_k \right>}_{j+k}$이다.
- $A \wedge B = - B \wedge A$이다.
- 대강 두 multivector가 의미하는 subspace가 span하는 subspace에 해당한다.
- Basis의 선형결합으로 이뤄진 vector에 대한 outer product의 계산은 다음과 같이 진행한다.
	- $(e_{01} + e_{56}) \wedge (e_{1234} + e_{3456})$를 계산해보자.
	- 분배법칙을 적용하면 $e_{01} \wedge e_{1234} + e_{01} \wedge e_{3456} + e_{56} \wedge e_{1234} + e_{56} \wedge e_{3456}$이 된다.
	- Index가 겹치는 게 있는 basis multivector의 outer product는 $0$이다. 정의에 의해 scalar 항은 사라지기 때문이다. 이를 적용하면 $e_{01} \wedge e_{3456} + e_{56} \wedge e_{1234}$가 된다.
	- Index가 겹치는 게 없는 basis multivector의 outer product는 geometric product이다. 이를 적용하면 $e_{013456} + e_{561234} = e_{013456} + e_{123456}$을 얻는다.
### Duals
- Multivector $A$가 의미하는 object에 수직인 object를 의미한다.
- Hodge star를 사용하여 $\star A$라 표기한다.
- 정의는 다음과 같다.
	- Basis multivector 중 $k$가 가장 큰 것을 pseudoscalar $i$라 한다.
		- 엄밀한 정의는 이와 다른 것 같으나 orthonormal basis가 주어졌다면 괜찮다.
		- 예시로 3차원 GA에서 $i = e_{012}$이다.
	- 모든 basis multivector $E$의 dual $\star E$는 $EF = i$인 $F$로 정의한다.
	- Basis가 아닌 multivector의 dual은 이로부터 선형성을 활용하여 적절히 정의한다.
		- 이 예시는 후에 2D projective geometric algebra 중간에 설명한다.
### Regressive Product
- $j$-vector $A_j$와 $k$-vector $B_k$에 대해 $A_j \vee B_k := \star^{-1} (\star A_j \wedge \star B_k)$이다.
- $A \vee B = -B \vee A$이고, $A \vee A = 0$이다.
- 대강 두 multivector가 의미하는 subspace의 교집합 정도에 해당한다.
### Inner Product
- $j$-vector $A_j$와 $k$-vector $B_k$에 대해 $A_j \cdot B_k := {\left< A_jB_k \right>}_{|j-k|}$이다.
- $B$에 평행한 $A$의 성분을 $A_\parallel$라 할 때 $A \cdot B = A_\parallel B$이고 $B \cdot A = B A_\parallel$이다.
- Basis의 선형결합으로 이뤄진 vector에 대한 inner product의 계산은 다음과 같다.
	- 전반적으로 outer product와 유사하다.
	- 다만, 한 basis multivector가 다른 basis multivector에 "완전히" 포함되는 경우가 아니면 모든 항은 $0$이 되며, 그러한 경우라면 inner product는 geometric product가 된다.
		- $e_{12} \cdot e_{134} = 0$
		- $e_{12} \cdot e_{124} = e_{12124} = -e_{11224}$
### Left / Right Contraction
- Contraction은 한쪽의 차원을 상쇄시킨다는 의미의 contraction이다.
- Left contraction $A_j \lrcorner B_k := {\left< A_j B_k \right>}_{k-j}$는 $A_j$를 $B_k$에 projection한 것이다.
- Right contraction $A_j \llcorner B_k := {\left< A_j B_k \right>}_{j-k}$는 $B_k$를 $A_j$에 projection한 것이다.
- Grade가 음수인 grade projection은 항상 결과가 $0$인 것으로 간주한다.
- Inner product는 left/right contraction 중 nonzero인 것으로 정의하는 것과 같다.
- 실용적인 연산은 아니지만, inner product와 관련된 성질을 전개할 때에 필요하다.
# 2D Projective Geometric Algebra
## Definition of Vectors in 2D PGA
- 2D projective geometric algebra(PGA)는 $\mathbb{G}(2, 0, 1)$이다. $e_0^2 = 0$, $e_1^2 = e_2^2 = 1$이다.
- 2D PGA에선 직선 $ax + by + c = 0$을 vector $ae_1 + be_2 + ce_0$으로 나타낸다.
- 직선에 $e_0$을 더하는 것은 직선을 평행이동하는 것에 해당한다.
### Inner Product of Vectors
$$ (a_1e_1 + a_2e_2 + a_0e_0) \cdot (b_1e_1 + b_2e_2 + b_0e_0) = a_1b_1 + a_2b_2$$
- 두 방향벡터의 내적이다.
### Infinity Lines
- $e_0$ 항만 있는 직선은 무한히 멀리 있는 영역에 대응된다.
- $e_0^2 = 0$이므로, 이를 inner product에 적용해보면 모든 직선과 평행하면서 수직이다.
## Definition of Bivectors in 2D PGA
- 2D PGA에서 bivector는 점을 의미한다.
- 두 직선 $\vec{u}$, $\vec{v}$의 outer product $\vec{u} \wedge \vec{v}$는 직선의 교점에 대응된다.
	- 두 vector의 선형결합은 두 직선의 교점을 지나는 임의의 직선에 대응된다.
	- Outer product는 두 subspace가 span하는 subspace에 대응된다.
	- 두 직선이 span하는 것은 두 직선의 선형결합으로, 그 교점을 지나는 임의의 직선이다.
	- PGA에서 이 subspace는 이를 그 교점 자체라고 생각한다.
- 이와 같이 두 object가 만나는 것을 구하는 걸 PGA에선 두 object의 "meet"라고 한다.
- 직선과 마찬가지로 scaling은 bivector가 지칭하는 점을 바꾸지 않는다.
- Bivector $e_{12} + xe_{20} + ye_{01}$은 점 $(x, y)$에 대응된다.
### Infinity Points
- $e_{12}$ 항의 계수가 $0$인 bivector는 방향만 정의되어 있고 무한히 멀리 있는 점이다.
- 평행한 두 직선의 교점을 계산하면 infinity point가 나오며, 그 방향은 두 직선의 방향이다.
## Projection
- 2D PGA에서 multivector $A$를 multivector $B$에 projection한 것은 $(A \cdot B) B$이다.
	- 이에 대한 설명이 필요하면 [이 영상](https://youtu.be/0i3ocLhbxJ4?t=1104)을 참고하는 것을 추천한다.
- 점 $P$를 직선 $\vec{u}$를 projection한 점은 $(P \cdot \vec{u}) \vec{u}$이다.
- 점 $P$를 지나고 직선 $\vec{u}$에 평행한 직선은 $(\vec{u} \cdot P)P$이다.
	- 이 사실들의 유도에는 다음 성질이 사용된다.
		- Vector $\vec{u}$와 bivector $P$에 대해 $\vec{u}P = \vec{u}\cdot P + \vec{u} \wedge P$이다.
		- 점 $P$를 지나고 직선 $\vec{u}$에 수직인 직선은 $\vec{u} \cdot P$이다.
		- 점 $P$가 직선 $\vec{u}$ 위에 있다면 $\vec{u} \cdot P = \vec{u}P$이다.
		- Vector, bivector는 scaling 하더라도 그들이 지칭하는 object는 변하지 않는다.
## Rigid Transformations
### Reflection
- 두 직선 $\vec{a}$, $\vec{u}$에 대해 $\vec{u}$로 $\vec{a}$를 대칭시킨 직선은 $\vec{u}\vec{a}\vec{u}$이다.
	- 이 식의 유도가 필요하면 [이 영상](https://youtu.be/0i3ocLhbxJ4?t=1366)을 참고하는 것을 추천한다.
### Rotation
- 두 직선 $\vec{u}$, $\vec{v}$의 교점을 중심으로 직선 $\vec{a}$를 $\vec{u} \rightarrow \vec{v}$의 방향으로 그 각도의 두 배만큼 회전시킨 직선은 $\vec{v}\vec{u}\vec{a}\vec{u}\vec{v}$이다.
	-  $\vec{u}$에 대해 대칭시킨 후 $\vec{v}$에 대해 대칭시킨 것에 해당한다.
### Translation
- 평행한 두 직선 $\vec{u}$, $\vec{v}$에 대해 직선 $\vec{a}$를 $\vec{u} \rightarrow \vec{v}$ 방향으로 그 거리의 두 배만큼 평행이동시킨 직선은 $\vec{v}\vec{u}\vec{a}\vec{u}\vec{v}$이다.
	- Rotation과 같은 식이다.
### Generalized Rigid Transformation
- 그동한 PGA에서는 object가 scaling에 영향을 받지 않아 normalization이 필요 없었지만, transformation에 대해서는 multivector의 magnitude가 중요해진다.
- Bivector의 exponential form은 Taylor series로 정의된다.
	- 서로 수직인 두 unit vector $\hat{u}$, $\hat{v}$에 대해 $e^{\hat{u} \hat{v} \theta} := \cos\theta + \hat{u}\hat{v}\sin\theta$이다.
		- $\hat{u}$는 unit vector이므로 $\hat{u}^2 = 1$이다. 이로부터 $e^{\hat{u}\hat{v}\theta} = \hat{u}(\hat{u}\cos\theta + \hat{v}\sin\theta)$라고도 쓴다.
	- Unit vector $\hat{u}$에 대해 $e^{\hat{u} e_0 x} = 1 + \hat{u}e_0x - \hat{u}(\hat{u}+e_0x)$이다.
- Unit bivector로 표현되는 점 $\hat{P}$에 대해 object $A$를 $P$를 중심으로 $2\theta$ 회전시킨 object는 $e^{-\hat{P}\theta} A e^{\hat{P}\theta}$이다.
- Unit vector로 표현되는 직선 $\hat{u}$에 대해 object $A$를 $\hat{u}$에 수직인 방향으로 $2x$ 평행이동시킨 object는 $e^{-\hat{u} e_0 x} A e^{\hat{u} e_0 x}$이다.
# 