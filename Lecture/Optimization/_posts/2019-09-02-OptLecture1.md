---
layout: post
title: Optimization Lecture 1
author: Yeonjee Jung
use_math: true
---

딥러닝에서 objective function의 설계는 중요하다. 이 때 문제를 더 간단하게 만들기 위해 convex의 개념을 도입한다.

### Convex set

$$\text{For } x \in C \text{ and } y \in C \Rightarrow (1-\alpha)x+\alpha y \in C, \forall\alpha\in[0, 1]$$

convex set을 쓰면 line 전체가 constraint 안에 있기 때문에 line search를 할 때 쓴다. convex set을 가정한 방법들은 non-convex에서도 사용할 수 있다. local minima 부근에서는 convex이기 때문인데, 이 때 convex 방법들을 적용하면 global minima는 아니다.

### Convex function

$$\alpha f(x_1)+(1-\alpha)f(x_2) \ge f(\alpha x_1 + (1-\alpha)x_2), \forall x_1, x_2, \forall \alpha \in [0, 1]$$

convex function의 가장 큰 특징은 global minima가 하나이고, 2차 미분식(또는 해시안 함수)이 항상 양수라는 점이다. 이또한 분석이 쉽다는 장점을 가지고 있다. 사실, unimodal function도 global minima가 하나지만, 이차미분항이 양수와 음수를 왔다갔다 할 수 있기 때문에 convex function보다는 더 분석이 어렵다.

이차미분항이 양수라는 점에서 오는 장점은, convergence behavior를 알기가 쉽다는 점이다. 보통 잘 알고 있는 gradient descent 방법의 식은 다음과 같다.

$$x_{t+1} \leftarrow x_t + \gamma\triangledown f(x)$$

이 때 이차미분항이 양수이면, $\triangledown f(x)$의 양상을 더 쉽게 알 수 있다.
