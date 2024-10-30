# homework
## State Variables

## The Concept of State Variable
- **Inputs - System (States) - Outputs**
- 시스템 내에서 `state`를 정의하고, 이를 중심으로 문제를 해결할 것입니다.
- `state`는 입력과 상호작용하며 서로 영향을 주고받을 수 있습니다.
- 문제를 해결하는 과정에서 의미를 부여하고, 컴퓨터가 작업을 수행하기 쉽게 합니다.

### example 1.
## System Equation
스프링-질량-댐퍼 시스템의 운동 방정식은 다음과 같습니다:

$$
M \frac{d^2 y(t)}{dt^2} + b \frac{dy(t)}{dt} + k y(t) = r(t)
$$

## State Variables
상태 변수를 다음과 같이 정의합니다:

$$
x_1(t) = y(t), \quad x_2(t) = \frac{dy(t)}{dt}
$$

상태 공간 표현은 다음과 같습니다:

$$
\begin{cases}
\frac{dx_1(t)}{dt} = x_2(t) \\
\frac{dx_2(t)}{dt} = -\frac{b}{M} x_2(t) - \frac{k}{M} x_1(t) + \frac{1}{M} r(t)
\end{cases}
$$

그리고 출력 변수는 다음과 같이 정의됩니다:

$$
y(t) = x_1(t)
$$

### example 2.
## State Variables
이 RLC 회로 시스템의 상태 변수는 다음과 같이 정의됩니다:

$$
x_1(t) = v_C(t), \quad x_2(t) = i_L(t)
$$

여기서:
- \( x_1(t) \)는 커패시터의 전압 \( v_C(t) \)입니다.
- \( x_2(t) \)는 인덕터의 전류 \( i_L(t) \)입니다.
- `state`는 정하기 나름이며, 설정한 상태들이 항등식이 되지 않도록 주의해야 합니다.

## Equations for RLC Circuit System

### Input Equation
입력 전류 \( u(t) \)에 대한 방정식은 다음과 같습니다:

$$
u(t) = C \frac{dx_1(t)}{dt} + x_2(t) \Rightarrow \frac{dx_1(t)}{dt} = \frac{1}{C} [-x_2(t) + u(t)]
$$

### Inductor Voltage Equation
인덕터 전압에 대한 방정식은 다음과 같습니다:

$$
L \frac{dx_2(t)}{dt} + R x_2(t) - x_1(t) = 0 \Rightarrow \frac{dx_2(t)}{dt} = \frac{1}{L} [x_1(t) - R x_2(t)]
$$

### State Space Representation
위의 두 방정식을 상태 공간 형태로 정리하면 다음과 같습니다:

$$
\begin{cases}
\frac{dx_1(t)}{dt} = \frac{1}{C} [-x_2(t) + u(t)] \\
\frac{dx_2(t)}{dt} = \frac{1}{L} [x_1(t) - R x_2(t)]
\end{cases}
$$

그리고 출력 변수는 다음과 같이 정의됩니다:

$$
y(t) = R x_2(t)
$$

## State Space Equation
- **1차 미분 상태 방정식**
- 상태를 정의하면 다음과 같이 미분 방정식을 유도할 수 있습니다.
  
# Example: Differential and State Space Equations

## Differential Equation Solution
미분 방정식은 다음과 같습니다:

$$
\dot{x}(t) = a x(t) + b u(t)
$$

라플라스 변환을 적용하면:

$$
s X(s) - x(0) = a X(s) + b U(s)
$$

이를 정리하면:

$$
(s - a) X(s) = x(0) + b U(s)
$$

따라서:

$$
X(s) = \frac{1}{s - a} x(0) + \frac{1}{s - a} b U(s)
$$

역 라플라스 변환을 통해 시간 영역으로 변환하면:

$$
x(t) = e^{at} x(0) + \int e^{a(t - \tau)} b u(\tau) \, d\tau
$$

이 표현을 상태 전이 행렬로 나타내면:

$$
x(t) = \Phi(t) \cdot x(0) + \int \Phi(t - \tau) b u(\tau) \, d\tau
$$

여기서 $$ \Phi(t) = e^{at} $$입니다.

## State Vector and State Space Equation

### State Vector
상태 벡터는 다음과 같이 정의됩니다:

$$
x(t) = \begin{bmatrix} x_1(t) \\ x_2(t) \\ \vdots \\ x_n(t) \end{bmatrix}
$$

### State Space Equation
상태 공간 방정식은 다음과 같습니다:

- 상태 미분 방정식:

  $$
  \dot{x}(t) = A x(t) + B u(t)
  $$

- 출력 방정식:

  $$
  y(t) = C x(t) + D u(t)
  $$

## RLC Circuit Example
RLC 회로의 상태 공간 표현은 다음과 같습니다:

$$
\begin{cases}
\frac{dx_1(t)}{dt} = \frac{1}{C} \left[-x_2(t) + u(t)\right] \\ \,\frac{dx_2(t)}{dt} = \frac{1}{L} \left[x_1(t) - R x_2(t)\right]
\end{cases}
$$

출력은 다음과 같이 정의됩니다:

$$
y(t) = R x_2(t)
$$

이 방정식을 행렬 형식으로 나타내면:

$$
\dot{x}(t) = \begin{bmatrix} 0 & -\frac{1}{C} \\ \frac{1}{L} & -\frac{R}{L} \end{bmatrix} x(t) + \begin{bmatrix} \frac{1}{C} \\ 0 \end{bmatrix} u(t)
$$

출력 방정식은 다음과 같습니다:

$$
y(t) = \begin{bmatrix} 0 & R \end{bmatrix} x(t) + \begin{bmatrix} 0 \end{bmatrix} u(t)
$$

- 초기 미분 방정식을 `state space equation`으로 변환하는 것이 목표입니다.
- `state space equation`으로 변환하면 컴퓨터로 명령하기가 쉬워집니다.

## State Transition Matrix
- 상태 전이 행렬을 정의합니다:

# State Transition Matrix

## First Order Solution
1차 미분 방정식의 해는 다음과 같습니다:

$$
x(t) = e^{at} x(0) + \int e^{a(t - \tau)} b u(\tau) \, d\tau
$$

## n-th Order Solution
n차 미분 방정식의 해는 다음과 같이 일반화할 수 있습니다:

$$
x(t) = \exp(At) x(0) + \int \exp(A(t - \tau)) B u(\tau) \, d\tau
$$

## Laplace Transform and State Transition Matrix
라플라스 변환을 적용하면 상태 변수의 표현은 다음과 같습니다:

$$
X(s) = [sI - A]^{-1} x(0) + [sI - A]^{-1} B U(s)
$$

여기서 상태 전이 행렬 \( \Phi(s) \)는 다음과 같이 정의됩니다:

$$
\Phi(s) = [sI - A]^{-1}
$$

라플라스 역변환을 통해 시간 영역에서의 상태 전이 행렬을 얻을 수 있습니다:

$$
\Phi(t) = \mathcal{L}^{-1}[\Phi(s)]
$$

따라서 상태 변수 \( x(t) \)는 다음과 같이 표현됩니다:

$$
x(t) = \Phi(t) \cdot x(0) + \int \Phi(t - \tau) B u(\tau) \, d\tau
$4

여기서 $$\Phi(t) $$는 상태 전이 행렬입니다.

# Example 3.1: Coupled Cart System

## System Equations
두 개의 카트 시스템에 대한 방정식은 다음과 같습니다:

$$
M_1 \cdot \ddot{p}(t) = u(t) - b_1[\dot{p}(t) - \dot{q}(t)] - k_1[p(t) - q(t)]
$$

$$
M_2 \cdot \ddot{q}(t) = b_1[\dot{p}(t) - \dot{q}(t)] + k_1[p(t) - q(t)] - b_2 \dot{q}(t) - k_2 q(t)
$$

## State Vector and State Space Representation

상태 벡터는 다음과 같이 정의됩니다:

$$
x(t) = \begin{bmatrix} x_1(t) \\ x_2(t) \\ x_3(t) \\ x_4(t) \end{bmatrix} = \begin{bmatrix} p(t) \\ q(t) \\ \dot{p}(t) \\ \dot{q}(t) \end{bmatrix}
$$

상태 공간 방정식은 다음과 같이 표현됩니다:

$$
\dot{x}(t) = \begin{bmatrix} 0 & 0 & 1 & 0 : 0 & 0 & 0 & 1 : -\frac{k_1}{M_1} & \frac{k_1}{M_1} & -\frac{b_1}{M_1} & 0 : \frac{k_1}{M_2} & -\frac{k_1 + k_2}{M_2} & \frac{b_1}{M_2} & -\frac{b_2}{M_2} \end{bmatrix} x(t) + \begin{bmatrix} 0 \\ 0 \\ \frac{1}{M_1} \\ 0 \end{bmatrix} u(t)
$$

