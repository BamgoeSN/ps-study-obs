이 문서는 다음 영상에 기반을 두고 있다.

<https://youtu.be/0i3ocLhbxJ4>
# Fundamental Components
## Vectors in 2D PGA
- 우선 2D만을 생각하자.
- 2D PGA가 다루는 공간은 2D이지만, 2D PGA 자체는 3D이다.
- 직선 $ax + by + c = 0$을 하나의 vector $ae_1 + be_2 + ce_0$으로 간주한다.
	- $e_1$, $e_2$의 계수를 조절하는 것은 기울기를 조절하는 것이다.
	- $e_0$의 계수를 조절하는 것은 직선을 평행이동 시키는 것이다.
	- Scaling은 직선을 바꾸지 않는다.
- 이러한 2D PGA는 $\mathrm{Cl}(2, 0, 1)$이다.
	- $e_1^2 = e_2^2 = 1$, $e_0^2 = 0$
- $ae_1 + be_2 + ce_0$의 방향벡터는 $(b, -a)$이다.
### Inner Product of Vectors
$$ (a_1e_1 + a_2e_2 + a_0e_0) \cdot (b_1e_1 + b_2e_2 + b_0e_0) = a_1b_1 + a_2b_2$$
- 두 방향벡터의 내적이다.
- 두 직선이 평행하면 내적은 방향벡터 크기의 곱이고, 수직이면 $0$이다.
- $e_0^2 = |e_0|^2 = 0$이므로, 직선 $e_0$는 모든 직선과 수직인 동시에 평행하다.
# Intersection of Two Lines
- 2D PGA에서 bivector는 점이다.
- 두 직선 $\vec{u}$, $\vec{v}$에 대해 $\vec{u} \wedge \vec{v}$는 그 교점이다.
	- Bivector는 두 vector가 span하는 2D subspace이며, outer product로 계산한다.
	- 두 직선의 선형결합은 직선의 교점을 지나는 임의의 직선을 만든다.
	- 따라서 두 직선의 outer product는 교점을 지나는 임의의 직선인 subspace이다.
	- 이는 단순히 직선의 outer product를 그 교점이라 생각하는 것으로 치환 가능하다.
- $\vec{u} \wedge \vec{v} = pe_{12} + qe_{20} + re_{01}$라면 두 직선의 교점은 cartesian에서 $(q/p, r/p)$이다.
	- Bivector의 scaling은 object를 건드리지 않음을 기억한다.
- $\vec{u} \wedge \vec{v}$는 흔히 두 직선의 meet라고 부른다.
## Infinite Points
- $e_{12}$ 항의 계수가 $0$인 bivector는 방향만 정의되며 무한히 멀리 있는 점이다.
- 예시 - $e_0$와 직선의 교점
	- $(ae_1 + be_2 + ce_0) \wedge e_0 = ae_{10} + be_{20} = be_{20} - ae_{01}$
	- 둘의 교점은 직선의 방향벡터 방향으로 무한히 멀리 있는 점이라 할 수 있다.
	- 역으로 벡터 $e_0$는 무한히 멀리 있는 영역을 의미한다고 해석할 수 있다.
- 예시 - 평행한 두 직선의 교점
	- 직선 $\vec{u}$와 그에 평행한 직선 $\vec{u} + \alpha e_0$의 교점은 $\vec{u} \wedge (\vec{u} + \alpha e_0) = \vec{u} \wedge e_0$으로, $\vec{u}$의 방향에 무한히 멀리 있는 점이다.
# Lines Passing Two Points
- 두 점 $A$, $B$를 동시에 지나는 직선은 $A \vee B$이다.
	- Bivector가 근본적으로는 그 점을 지나는 임의의 직선을 의미한다는 것과, regressive product는 두 subspace의 교집합이라는 점에서부터 나온다.
- $A \vee B$는 흔히 두 점의 join이라고 부른다.
- 2D PGA에서의 regressive product는 다음을 활용하여 계산한다.
	- $\star e_{01} = e_2$
	- $\star e_2 = e_{01}$
	- $e_{01} \vee e_{01} = 0$
	- $e_{01} \vee e_{12} = e_1$ 안쪽 index를 공유하면 그 index가 살아 나온다.
	- $e_{12} \vee e_{01} = -e_1$ 바깥쪽 index를 공유하면 그 index가 살아 나오나 $-$가 붙는다.
	- 나머지는 적절히 cyclic하게 계산하면 된다.
# Inner Product
- 직선 $\vec{a}$와 점 $B$에 대해 $\vec{a} \cdot B$는 $B$를 지나면서 $\vec{a}$와 수직인 직선이다.
	- Inner product를 구하기 위해 $B$를 다시 그 점을 지나는 모든 직선으로 재해석한다.
	- $\vec{a}$의 $B$와 평행한 성분은 $B$를 지나면서 $\vec{a}$와 평행한 직선이다.
	- 이를 $\vec{a}$에서 빼면 $\vec{a}$와 수직인 성분만 남는다. 즉, $\vec{a}$와 수직인 직선이 된다.
	- 이 직선은 $B$를 지나므로 $\vec{a} \cdot B$는 $B$를 지나면서 $\vec{a}$와 수직인 직선이다.
- 점 $B$가 직선 $\vec{a}$ 위에 있다면 $\vec{a} \cdot B = \vec{a} B$이다.
	- $B$를 지나면서 $\vec{a}$에 수직인 직선을 $\vec{b}$라 하자.
	- $\vec{a}B = \vec{a} \cdot B + \vec{a} \wedge B = \vec{a} \cdot B + \vec{a} \wedge \vec{a} \wedge \vec{b} =  \vec{a} \cdot B$
- 점 $B$에서 직선 $\vec{a}$에 내린 수선의 발은 $(\vec{a} \cdot B) \vec{a}$이다.
	- 두 직선의 교점은 outer product로 구해야 하지만, $\vec{a} \cdot B$와 $\vec{a}$가 수직이므로 $(\vec{a} \cdot B) \wedge \vec{a} = (\vec{a} \cdot B) \vec{a}$이다.
- 점 $B$를 지나고 직선 $\vec{a}$에 평행한 직선은 $(\vec{a} \cdot B) B$이다.
	- 점 $B$는 직선 $\vec{a} \cdot B$ 위에 있으므로, $B$를 지나면서 $\vec{a} \cdot B$에 수직인 직선은 둘의 geometric product와 같다.
## General Projection
- 일반적으로 $A$를 $B$에 projection한 것은 $(A \cdot B) B$이다.
	- 2D PGA에서, 앞서 봤듯이 $(\vec{a} \cdot B) \vec{a}$는 $B$를 $\vec{a}$에 projection한 것이고, $(\vec{a} \cdot B) B$는 $\vec{a}$를 $B$에 projection한 것이다.
# Geometric Product
2D PGA는 근본적으로 3D이므로 $\vec{a}\hat{u}\hat{v}$가 rotation이라는 사실은 사용할 수 없다.
## Reflection
- 두 직선 $\vec{a}$, $\vec{u}$에 대해 $\vec{u}$로 $\vec{a}$를 대칭시킨 직선은 $\vec{u}\vec{a}\vec{u}$이다.
	- 유도는 $\vec{a}$를 $\vec{u}$에 평행한 성분과 그렇지 않은 성분으로 나누는 것에 기반한다.
	- 궁금하다면 영상의 22:46~ 참고
## Rotation and Transformation (2D Rigid Transformations)
- 직선 $\vec{u}$와 $\vec{v}$의 교점을 중심으로 직선 $\vec{a}$를 $\vec{u} \rightarrow \vec{v}$를 따라 회전시킨 직선은 $\vec{v}\vec{u}\vec{a}\vec{u}\vec{v}$이다.
	- 일반적으로 GA에서 짝수 개의 normalized vector의 geometric product를 "rotor"라고 부른다.
	- PGA에선 scaling이 object를 건드리지 않으므로 normalization을 신경 안 써도 된다.
- 달리 말하면 rotor $R := \vec{u}\vec{v}$에 대해 회전은 $R^\dagger \vec{a} R$이다.
- $\vec{u}$와 $\vec{v}$가 평행하다면 $R^\dagger \vec{a} R$은 $\vec{u}$와 $\vec{v}$의 거리의 두 배만큼 $\vec{a}$를 평행이동한다.
	- 방향은 $\vec{u}$에서 $\vec{v}$로 이동하는 방향이다.
	- 이때의 $R$은 rotor 대신 "motor"라고 하기도 하나, rotor라고 불러도 무방하다.
## Rigid Transformations of Points
- 점 $P$를 직선 $\vec{a}$에 대해 대칭시킨 점은 $\vec{a} P \vec{a}$이다. 직선의 경우와 같다.
	- $P$를 지나는 두 *수직*인 직선 $\vec{u}$, $\vec{v}$에 대해 $P = \vec{u}\vec{v}$이다.
	- 두 직선을 $\vec{a}$에 대해 대칭시킨 후의 교점은 $(\vec{a}\vec{u}\vec{a}) \wedge (\vec{a}\vec{v}\vec{a})$이다.
	- 대칭 전에 두 직선이 수직이었으면 대칭 후에도 수직이므로 이는 $\vec{a}\vec{u}\vec{a}^2\vec{v}\vec{a}$와 같다.
	- $\vec{a}^2$은 scalar인데, PGA에선 scalar는 object를 건드리지 않으므로 $\vec{a}\vec{u}\vec{v}\vec{a} = \vec{a}P\vec{a}$가 된다.
# Exponential Form of Points
- GA에선 rotor를 bivector의 exponential로 보는 게 가능하다.

- 점 $P$를 수직인 두 직선 $\hat{u}$, $\hat{v}$의 교점 $\hat{P}=\hat{u}\hat{v}$로 둘 때, $e^{P\theta}$는 object를 $P$를 중심으로 $2\theta$ 회전시킨 object이다.
- 쉽게 쓰면, $P = \hat{u} \hat{v}$에 대해 $A$를 $P$를 따라 $2\theta$ 회전시키는 변환은 $e^{-\hat{P}\theta} A e^{\hat{P}\theta}$이다.
	- $\hat{u}$, $\hat{v}$가 unit vector임에 유의한다. PGA지만 exponential에선 normalize가 필요하다.
	- $e^{P\theta} = e^{\hat{u}\hat{v}\theta} = \hat{u}(\hat{u}\cos\theta + \hat{v}\sin\theta)$
	- 우변은 두 vector의 geometric product이므로 rotor이다.
	- $\hat{u}\cos\theta + \hat{v}\sin\theta$는 직선 $\hat{u}$를 $\hat{v}$의 방향으로 $\theta$만큼 회전시킨 것이다.
- $e^{-\hat{u} e_0 x} A e^{\hat{u} e_0 x}$는 object $A$를 $\hat{u}$에 수직인 방향으로 $2x$ 평행이동한다.
	- 이 경우는 infinity point $\hat{P} = \hat{u}e_0$에 대한 회전이라 생각할 수 있다.
	- $(\hat{u} e_0 x)^2 = 0$이므로 Euler's formula를 적용할 수 없다.
	- 대신 Taylor series를 사용하여 전개하면 $e^{\hat{u} e_0 x} = 1 + \hat{u} e_0 x$임을 유도할 수 있다.
	- 이후의 논리 전개는 $\hat{P}$가 infinity point가 아닌 경우와 과정이 같다.

- 정리하면,
	- 점 $\hat{P}$에 대한 $2\theta$ 만큼의 회전은 $e^{-\hat{P}\theta}Ae^{\hat{P}\theta}$이다.
	- 무한점 $\hat{P}$에 수직인 방향으로 $2x$ 만큼의 평행이동은 $e^{-\hat{P}x} A e^{\hat{P}x}$이다.