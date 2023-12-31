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
- $2$차원 GA를 예시로 들어보자.
	- Scalar basis는 $1$로 유일하다.
	- Vector basis는 $e_0$, $e_1$ 두 개가 있다.
	- Bivector basis는 vector basis 2개의 모든 geometric product이다. 여기선 $e_