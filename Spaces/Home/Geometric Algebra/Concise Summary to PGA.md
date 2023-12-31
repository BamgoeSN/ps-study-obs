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
		- 