# Forces and Moments(Chap 4.)

---

<aside>
📌 **MAV에 가해지는 Force, Moment**

- `Gravity` Force : $\bold{f_g}$
- `Aerodynamic` Forces : $(\bold{f_a, m_a})$
- `Propulsion` Forces : $(\bold{f_p, m_p})$

$$
\bold{f = f_g+f_a+f_p}\\
\bold{m = m_a+m_p}
$$

</aside>

### Chapters

1. [Gravitational Forces](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)
2. [Aerodynamic Forces and Moments](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)
    1. [Control Surfaces](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)
    2. [Longitudinal Aerodynamics](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)
    3. [Lateral Aerodynamics](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)
    4. [Aerodynamic coefficients](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)
3. [Forces and torques due to propulsion](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)
    1. [Propeller Thrust](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)
    2. [Propeller Torque](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)
4. [Atmospheric disturbances](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)

---

## Gravitational Forces

MAV에 가해지는 지구의 중력장의 효과는 $\bold{k^i}$의 방향으로 작용하며 **MAV의 질량**에 비례한다.

따라서 vehicle frame $\mathcal{F}^v$에서 MAV의 질량중심 GM에 작용하는 중력은 다음 $\bold{f^v_g}$로 나타낼 수 있다.

$$
\bold{f^v_g} = \left(\begin{matrix}0\\0\\mg\end{matrix}\right)
$$

![Untitled](Forces%20and%20Moments(Chap%204%20)%207315f570e3474c9a88b678d18073ab0e/Untitled.png)

Body frame에서 느끼는 gravitational force는 좌표계 회전을 통해 다음과 같이 얻을 수 있다.

$$
\begin{aligned}
\bold{f^b_g} &= \mathcal{R}^b_v\left(\begin{matrix}0\\0\\mg\end{matrix}\right)\\
&=\left(\begin{matrix}c\theta c\psi& c\theta s\psi&-s\theta\\
s\phi s\theta c\psi-c\phi s\psi&s\phi s\theta s\psi+c\phi c\psi& s\phi c\theta\\
c\phi s\theta c\psi+s\phi s\psi& c\phi s\theta s\psi-s\phi c\psi& c\phi c\theta
\end{matrix}\right)\left(\begin{matrix}0\\0\\mg\end{matrix}\right)\\
&=\left(\begin{matrix}-mg\sin{\theta}\\mg\cos{\theta}\sin{\phi}\\mg\cos{\theta}\cos{\phi}\end{matrix}\right)
\end{aligned}
$$

---

## Aerodynamic Forces and Moments

`Lift force`, `Drag force`

$$
\text{Dynamic Pressure : }\frac12\rho V_a^2
$$

![Untitled](Forces%20and%20Moments(Chap%204%20)%207315f570e3474c9a88b678d18073ab0e/Untitled%201.png)

$$
\begin{aligned}
\mathscr{L}&=\frac12\rho V_a^2SC_L\\
\mathscr{D}&=\frac12\rho V_a^2SC_D\\
\bold{m}&=\frac12\rho V_a^2ScC_m
\end{aligned}
\begin{cases}
S : \text{platform area of the MAV wing}\\
c : \text{mean chord of the MAV wing}\\
C_L, C_D, C_m : \text{Nondimensional aerodynamic coefficients}\\
\end{cases}
$$

<aside>
📌 **Airfoil’s nondimensional coefficients**

- Airfoil’s `shape`, $`Re`$, $`Ma`$, 받음각($`\alpha`$)에 영향을 받음
</aside>

MAV(Micro Air Vehicle)에 관해선 $`Re`$, $`Ma`$는 상수로 추정할 수 있다.

### Control Surfaces

![Untitled](Forces%20and%20Moments(Chap%204%20)%207315f570e3474c9a88b678d18073ab0e/Untitled%202.png)

 

$$
\text{Aileron angle : }\delta_a\\
\text{Elevator angle : }\delta_e\\
\text{Rudder angle : }\delta_r\\
$$

$$
\delta_a = \frac12(\delta_{a-left}-\delta_{a-right})
$$

- 오른손 법칙에 의해 elevator가 body 기준 아래로 꺾였을 때, rudder가 좌측으로 꺾였을 때 $`+`$를 띈다.
- Aileron 각 $\delta_a$는 $\bold{i_b}$기준 오른손 법칙을 따라 좌측 aileron의 꺾임이 아래로 향할 때 $`+`$를 , 우측 aileron의 꺾임이 위로 향할 때 $`+`$를 의미한다.

![Untitled](Forces%20and%20Moments(Chap%204%20)%207315f570e3474c9a88b678d18073ab0e/Untitled%203.png)

- 다음 [V-tail MAV](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)의 꼬리 날개의 control surface를 `ruddervator`라고 한다.($\delta_{rr},\; \delta_{rl}$)
- 두 ruddervator를 다른 방향으로 작동할 시($+, -$), rudder와 같이 $\bold{k_b}$에 대해서 토크를 생성해낸다.
- 두 ruddervator를 같은 방향으로 작동할 시($+, +$),($-,-$), elevator처럼  $\bold{j_b}$에 대해서 토크를 생성해낸다.

$$
\left(\begin{matrix}\delta_{e}\\\delta_{r}\end{matrix}\right)=\left(\begin{matrix}1&1\\-1&1\end{matrix}\right)\left(\begin{matrix}\delta_{rr}\\\delta_{rl}\end{matrix}\right)
$$

![Untitled](Forces%20and%20Moments(Chap%204%20)%207315f570e3474c9a88b678d18073ab0e/Untitled%204.png)

- 다음 [Figure 4.5](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)의 기체처럼 생긴 control surface를 `elevons`라고 부른다.
- 두 elevon을 다른 방향으로 작동할 시($+, -$), aileron처럼 $\bold{i_b}$에 대해서 토크를 생성해낸다.
- 두 elevon을 같은 방향으로 작동할 시($+, +$),($-,-$), elevator처럼 $\bold{j_b}$에 대해서 토크를 생성해낸다.

$$
\left(\begin{matrix}\delta_{e}\\\delta_{a}\end{matrix}\right)=\left(\begin{matrix}1&1\\-1&1\end{matrix}\right)\left(\begin{matrix}\delta_{er}\\\delta_{el}\end{matrix}\right)
$$

### Longitudinal Aerodynamics

<aside>
📌 **종 방향의 공기역학적 힘과 모멘트(longitudinal aerodynamic forces and moments)**

$\bold{i^b}\_\bold{k^b}$ 평면에 대해서 body의 motion을 이끌어냄

Lift, Drag 힘들은 stability frame의 축에서, 받음각 $\alpha$, `pitch rate` $q$, `elevator deflection` $\delta_e$에 크게 영향을 받는다.

따라서 Lift, Drag, Moment에 대해서 다음과 같이 재정의할 수 있다.

</aside>

$$
\begin{aligned}
\mathscr{L}&=\frac12\rho V_a^2SC_L(\alpha, q, \delta_e)\\
\mathscr{D}&=\frac12\rho V_a^2SC_D(\alpha, q, \delta_e)\\
\bold{m}&=\frac12\rho V_a^2ScC_m(\alpha, q, \delta_e)
\end{aligned}
$$

보통의 경우엔 이 힘과 모멘트 방정식들은 비선형적

작은 받음각 $\alpha$의 경우에 날개를 따라 흐르는 공기의 흐름은 날개 표면에 붙은 laminar flow(층류)이다.

따라서 이런 조건 하에 Lift, Drag, Moment들은 선형 추정을 사용해 적용할 수 있다.

$$
\mathscr{L}=\frac12\rho V_a^2S\left[C_{L_{0}}+\frac{\partial{C_L}}{\partial{\alpha}}\alpha+\frac{\partial{C_L}}{\partial{q}}q+\frac{\partial{C_L}}{\partial{\delta_e}}\delta_e\right]\\
\mathscr{L}=\frac12\rho V_a^2S\left[C_{L_{0}}+{C_{L_{\alpha}}}{\alpha}+C_{L_{q}}\frac{c}{2V_a}q+C_{L_{\delta_e}}\delta_e\right]
$$

$$
C_{L_0},\;C_{L_\alpha}\triangleq\frac{\partial{C_L}}{\partial{\alpha}},\;C_{L_q}=\frac{\partial{C_L}}{\partial{\frac{qc}{2V_a}}},\;C_{\delta_e}\triangleq\frac{\partial{C_L}}{\partial{\delta_e}}
$$

$C_{L_\alpha}$, $C_{L_q}$이 두 무차원 파라미터들은 주로 stability derivatives로서 정의되며, $C_{\delta_e}$는 control dervative로 정의된다.

$$
\mathscr{D}=\frac12\rho V_a^2S\left[C_{D_{0}}+{C_{D_{\alpha}}}{\alpha}+C_{D_{q}}\frac{c}{2V_a}q+C_{D_{\delta_e}}\delta_e\right]\\
\bold{m}=\frac12\rho V_a^2Sc\left[C_{m_{0}}+{C_{m_{\alpha}}}{\alpha}+C_{m_{q}}\frac{c}{2V_a}q+C_{m_{\delta_e}}\delta_e\right]
$$

받음각이 작은 condition에선, 위 세 식이 비교적 정확한 수치를 보여주는 것을 알 수 있다.

MAV body를 따라 흐르는 공기는 laminar, attached. 준정상 상태(`quasi-steady state`) $\Rightarrow$ 시간에 따른 변화가 작음

받음각 $\alpha$, pitch rate, elevator deflection에 따라 반응하며 변화하는 flow filed는 예측 가능하다.

![Untitled](Forces%20and%20Moments(Chap%204%20)%207315f570e3474c9a88b678d18073ab0e/Untitled%205.png)

Quasi-steady state한 상태에서의 aerodynamics는 예측이 가능하지만 위 그림처럼 unsteady state에선 불가능하다.

<aside>
📌 **Unsteady aerodynamics**

- Non-linear
- 3-Dimensional
- Time-varying
- Separated flows that significantly affect the forces and moments experienced by the aircraft
</aside>

[Figure 4.6](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)처럼 바람이 airfoil의 윗면을 타지 못하고 유동 분리가 발생할 시, `stall`이란 현상이 발생, Lift force가 상당이 감쇠한다.

![Untitled](Forces%20and%20Moments(Chap%204%20)%207315f570e3474c9a88b678d18073ab0e/Untitled%206.png)

[Figure 4.7](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)처럼 $C_D$와 $C_L$이 [받음각 $\alpha$에 대해서 비선형 함수로 표현됐을 때, 더 정확한 모델을 보여준다.](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)

$$
\mathscr{L}=\frac12\rho V_a^2S\left[{C_{L}}(\alpha)+C_{L_{q}}\frac{c}{2V_a}q+C_{L_{\delta_e}}\delta_e\right]\\
\mathscr{D}=\frac12\rho V_a^2S\left[C_{D}(\alpha)+C_{D_{q}}\frac{c}{2V_a}q+C_{D_{\delta_e}}\delta_e\right]
$$

$$
C_{L, \text{flat plate}}=2\text{sign}(\alpha)\sin^2{\alpha}\cos{\alpha}
$$

`Linear lift behavior`와 `stall`의 효과를 동시에 포함하는 [Lift force coefficient](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)는 다음과 같이 표현할 수 있다

$$
C_L(\alpha)=(1-\sigma(\alpha))[C_{L_0}+C_{L_\alpha}\alpha]+\sigma(\alpha)[2\text{sign}(\alpha)\sin^2{\alpha}\cos{\alpha}]\\
\sigma(\alpha)=\frac{1+e^{-M(\alpha-\alpha_0)+e^{M(\alpha-\alpha_0)}}}{(1+e^{-M(\alpha-\alpha_0)})(1+e^{M(\alpha+\alpha_0)})}
$$

[Small aircraft에 대해서 선형 lift coefficient](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)는 다음과 같이 추정할 수 있다.

$$
C_{L_\alpha}=\frac{\pi AR}{1+\sqrt{1+(AR/2)^2}}
$$

다음 $AR$은 wing aspect ratio(날개 종횡비)로 다음과 같이 정의된다.

$$
AR\triangleq\frac{b^2}{S}\quad\begin{cases}
b\text{ : wingspan}\\
S\text{ : wing area}
\end{cases}
$$

Drag coefficient $C_D$ 또한 $C_L$과 마찬가지로 **[받음각에 대한 비선형 함수**로](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21) 나타낼 수 있다.

$$
C_D(\alpha)=C_{D_p}+\frac{(C_{L_0}+C_{L_\alpha}\alpha)^2}{\pi \mathcal{e} AR}
$$

다음 함수에서 $e$는 `Oswald efficiency factor`로 0.8과 1.0 사이의 값을 가진다.

![Untitled](Forces%20and%20Moments(Chap%204%20)%207315f570e3474c9a88b678d18073ab0e/Untitled%207.png)

다음 [Figure 4.8](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)은 받음각($\alpha$)에 대해서 이차 함수 모델과 선형 함수 모델을 나타낸 것이다.

- $C_D$는 우함수 형태의 이차 함수 모델을 통해 선형 모델보다 더 정확하게 표현한다.
    - Drag force는 aircraft의 전진에 따라 언제나 받음각 $\alpha$의 부호와 상관없이 반대 방향으로 힘이 작용한다.
    - 그래서 선형 함수 모델의 경우 받음각이 일정 음수 이하로 떨어지게 되면 Drag coefficient의 부호가 $-$로 뒤바뀌는 오류가 발생하기에 이차 함수 모델이 더 정확하다.
- Parasitic drag $C_{D_p}$와 선형 모델에서 $\alpha$가 $0$일 때의 drag coefficient $C_{D_0}$
- 선형 모델과 이차 모델이 만나는 지점 $\alpha^*$에서의 drag coefficient $C_{D}^*$

<aside>
📌 **Figure 4.8**

- Quadratic model provides a more accurate representation of the influence of the angle of attack over a wider range of $\alpha$
- The linear model is sometimes used because of its simplicity and its fidelity(정확성) under typical flight conditions
</aside>

다음 [Lift force와 Drag force](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)는 stability frame에서 표현된다.

Body에서 [Lift force와 Drag force](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)를 표현하기 위해선 받음각$(\alpha)$에 대해서 힘을 회전시킬 필요가 있다.

$$
\left(\begin{matrix}f_x\\f_z\end{matrix}\right)=
\left(\begin{matrix}\cos{\alpha}&-\sin{\alpha}\\
\sin{\alpha}&\cos{\alpha}
\end{matrix}\right)
\left(\begin{matrix}-F_{drag}\\-F_{lift}\end{matrix}\right)
$$

$$
\left(\begin{matrix}f_x\\f_z\end{matrix}\right)=\frac12\rho V_a^2S\left(\begin{matrix}
-\cos{\alpha}\left[{C_{L}}(\alpha)+C_{L_{q}}\frac{c}{2V_a}q+C_{L_{\delta_e}}\delta_e\right]+\sin{\alpha}\left[C_{D}(\alpha)+C_{D_{q}}\frac{c}{2V_a}q+C_{D_{\delta_e}}\delta_e\right]\\\\
-\sin{\alpha}\left[{C_{L}}(\alpha)+C_{L_{q}}\frac{c}{2V_a}q+C_{L_{\delta_e}}\delta_e\right]-\cos{\alpha}\left[C_{D}(\alpha)+C_{D_{q}}\frac{c}{2V_a}q+C_{D_{\delta_e}}\delta_e\right]
\end{matrix}\right)
$$

위 모델에서 사용된 $C_L(\alpha)$와 $C_D(\alpha)$는 [비선형](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21) [모델](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)을 사용할 수 있다.

특정 경우, 다음과 같은 [선형 모델](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)이 사용될 수 있음을 알아두기만 하면 된다.

$$
C_L(\alpha)=C_{L_0}+C_{L_\alpha}\alpha\\
C_D(\alpha)=C_{D_0}+C_{D_\alpha}\alpha
$$

Aircraft의 pitching moment는 주로 $\alpha$에 대해 비선형 함수 모델(wind tunnel과 flight experiment를 통해 도출)을 사용하지만 간단한 시뮬레이션의 경우 [다음 선형 모델](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)을 사용할 수 있다.

$$
C_m(\alpha)=C_{m_0}+C_{m_\alpha}\alpha
$$

<aside>
📌 $C_m$

- $C_{m_\alpha}<0$은 airframe이 pitch 각에서 안정적인 거동을 보임을 의미한다.
</aside>

### Lateral Aerodynamics

Lateral aerodynamic force, moment는 translational motion과 roll, yaw rotational motion을 야기한다.

다음 함수 식을 통해 측면 힘 $f_y$, roll, yaw moment $l$, $n$을 각각 표현할 수 있다.

$$
\begin{aligned}
f_y &= \frac12\rho V_a^2SC_Y(\beta, p, r, \delta_a, \delta_r)\\
l &= \frac12\rho V_a^2SbC_l(\beta, p, r, \delta_a, \delta_r)\\
n &= \frac12\rho V_a^2SbC_n(\beta, p, r, \delta_a, \delta_r)
\end{aligned}
$$

$C_Y$, $C_l$, $C_n$은 각각 nondimensional coefficients, $b$는 aircraft의 `wingspan`, $S$는 `wing area`

$$
\begin{aligned}
f_y&=\frac12\rho V_a^2S\left[C_{Y_0}+C_{Y_\beta}\beta+C_{Y_p}\frac{b}{2V_a}p+C_{Y_r}\frac{b}{2V_a}r+C_{Y_{\delta_a}}\delta_a+C_{Y_{\delta_r}}{\delta_r}\right]\\
l&=\frac12\rho V_a^2Sb\left[C_{l_0}+C_{l_\beta}\beta+C_{l_p}\frac{b}{2V_a}p+C_{l_r}\frac{b}{2V_a}r+C_{l_{\delta_a}}\delta_a+C_{l_{\delta_r}}{\delta_r}\right]\\
n&=\frac12\rho V_a^2Sb\left[C_{n_0}+C_{n_\beta}\beta+C_{n_p}\frac{b}{2V_a}p+C_{n_r}\frac{b}{2V_a}r+C_{n_{\delta_a}}\delta_a+C_{n_{\delta_r}}{\delta_r}\right]
\end{aligned}
$$

<aside>
📌 **Lateral forces and moments**

이 힘과 모멘트들은 body axis와 나란히 정렬됐으므로 EoM에 적용 시 rotational transformation이 적용될 필요가 없다.

$C_{Y_0}$는 $\beta=p=r=\delta_a=\delta_r = 0$일 때의 force coefficient 이다.

$\bold{i^b}$-$\bold{k^b}$ 평면에 대해서 대부분의 비행 동체는 대칭을 이루기 때문에 $C_{Y_0}$는 대체적으로 $0$이다. 그리고 이는 $C_{l_0}$, $C_{n_0}$도 마찬가지이다.

</aside>

### Aerodynamic Coefficients

$C_{m_\alpha}$, $C_{l_\beta}$, $C_{n_\beta}$, $C_{m_q}$, $C_{l_p}$, $C_{n_r}$은 `stability derivatives`(안정 도함수)에서 MAV의 정적, 동적 안정성을 나타내는 지표로서 사용된다.

<aside>
📌 **Static stability**

- Moment가 MAV의 자세를 복원하려는 경향성을 보인다면 그 MAV는 정적 안정이라고 할 수 있다.
- $C_{m_\alpha}$, $C_{l_\beta}$, $C_{n_\beta}$가 MAV의 `statically stable`(정적 안정성)을 결정한다.
- `Angle of attack` $\alpha$와 `Side slip angle` $\beta$으로 나타나는 relative airspeed의 방향에 따라 이 계수들이 변한다.
</aside>

- $C_{m_\alpha}$(**Longitudinal static stability derivative**)
    - **MAV가 `statically stable`하기 위해선 $0$보다 작아야함.**
- $C_{l_\beta}$(**Roll static stability derivative**)
    - 날개들이 이루는 각에 의해 결정된다.
    - **MAV가 `statically stable`하기 위해선 $0$보다 작아야함.**
    - $C_{l_\beta}$가 음수여야 sideslip의 방향의 바람의 moment에 저항할 rolling moment를 생성해 $\beta$를 $0$으로 만들 수 있다.
- $C_{n_\beta}$(**Yaw static stability derivative**)
    - Weathercock stability derivative라고 불리기도 함
    - Yaw 축 기준으로 비행 동체가 statically stable하다면 weathercock처럼 비행체는 바람이 불어오는 방향을 향할 것이다.
    - 비행 동체의 꼬리 날개에 의해 크게 영향을 받으며 동체의 꼬리 날개가 커지면 커질수록 $C_{n_\beta}$가 커진다.
    - **MAV가 `statically stable`하기 위해선 0보다 커야한다.**
    - 위 부호는 positive side slip angle $\beta$에 대해서 positive yawing moment를 발생시킴을 의미한다.

<aside>
📌 **Dynamic stability**

- Disturbance에 대해서 비행 동체가 동적 안정성을 확보하기 위해 고려
- Mass_Spring_Damper System을 통해 비유를 하자면 $C_{m_\alpha}$, $C_{l_\beta}$, $C_{n_\beta}$는 비행 동체의 `torsional spring`으로 볼 수 있고,  $C_{m_q}$, $C_{l_p}$, $C_{n_r}$는 비행 동체의 `torsional damper`라고 할 수 있다.
</aside>

- $C_{m_q}$(Pitch damping derivative)
- $C_{l_p}$(Roll damping derivative)
- $C_{n_r}$(Yaw damping derivative)
    
    위 계수들은 보통 motion 방향에 반대 방향으로 모멘트가 생성됨을 의미하기에 negative하다.
    

<aside>
📌 **Primary control derivatives**

</aside>

- $C_{m_{\delta_e}}$, $C_{l_{\delta_a}}$, $C_{n_{\delta_r}}$는 특정 control surface의 deflection과 연관된 파라미터들이다.
- $C_{m_{\delta_e}}$은 `elevator deflection` $\delta_e$로부터 야기돼 `pitching moment` $m$을 초래한다.
- $C_{l_{\delta_a}}$, $C_{n_{\delta_r}}$들은 `cross-control derivatives`로 해당 alieron, rudder의 control surface deflection이 발생 시, off-axis moment를 일으킴.

---

## Propulsion Froces and moments

### Propeller Thrust

<aside>
📌 **Propeller Thrust**

- 프로펠러의 전방, 후방의 압력 차이를 계산해 Bernoulli의 원리를 적용해 propeller thrust를 간단히 구할 수 있다.
</aside>

$$
P_{\text{upstream}} = P_0+\frac12\rho V_a^2\\
P_{\text{downstream}} = P_0+\frac12\rho V_{\text{exit}}^2
$$

<aside>
📌 $V_{\text{exit}}$은 다음과 같이 구할 수 있다.

모터에서의 transient를 무시한다면 PWM(Pulse Width Modulation) 제어command $\delta_t$를 통해 $V_{\text{exit}}$은 다음 식과 같은 선형적 관계로 표현할 수 있다.

$$
V_{\text{exit}}=k_{\text{motor}}\delta_{t}
$$

</aside>

$S_{prop}\triangleq\text{Area swept out by the propeller}$

$$
\begin{aligned}
F_{x_p}&=S_{prop}C_{prop}(P_{\text{downstream}}-P_{\text{upstream}})\\
&=\frac12\rho S_{prop}C_{prop}\left[(k_{motor}\delta_t)^2-V_a^2\right]
\end{aligned}
$$

$$
\bold{f_p}=\frac12\rho S_{prop}C_{prop}
\left(
\begin{matrix}
(k_{motor}\delta_t)^2-V_a^2\\
0\\
0
\end{matrix}
\right)
$$

대부분의 MAV들은 $\bold{i^b}$를 방향을 따라 추력을 주게끔 설계되기에 무게중심에 대해 어떤 모멘트도 발생시키지 않는다.

### Propeller Torque

MAV의 프로펠러가 회전하면서 반토크가 형성된다.

$$
T_p=-k_{T_p}(k_\Omega\delta_t)^2
$$

프로펠러 속도 $\Omega=k_{\Omega}\delta_t$

$k_{T_p}$는 실험을 통해 얻어지는 파라미터

$$
\bold{m_p}=\left(
\begin{matrix}
-k_{T_p}(k_\Omega\delta_t)^2\\
0\\
0
\end{matrix}
\right)
$$

---

## Atmospheric Disturbances

<aside>
📌 **Review of chapter 2**

- $\bold{V_g}$ : the velocity of the airframe relative to the ground
- $\bold{V_a}$ : the velocity of the airframe relative to the surrounding air mass
- $\bold{V_w}$ : the velocity of the air mass relative to the ground,
</aside>

$$
\bold{V}_g=\bold{V}_a+\bold{V}_w
$$

Simulation에서 total wind vector는 다음과 같이 표현할 수 있다.

$$
\bold{V}_w=\bold{V}_{w_s}+\bold{V}_{wg}
$$

$\bold{V}_{w_s}$ : steady ambient wind를 나타내는 상수 벡터

$\bold{V}_{w_g}$ : wind gusts and other atmospheric disturbances를 나타내는 확률론적 벡터

- `[Ambient(steady) wind` expressed in the `inertial frame`](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)
    - $w_{n_s}, w_{e_s}, w_{d_s}$는 각각 북쪽, 동쪽, 아래쪽 방향으로 부는 바람을 의미한다.

$$
\bold V_{w_s}^i=
\left(
\begin{matrix}
w_{n_s}\\
w_{e_s}\\
w_{d_s}
\end{matrix}
\right)
$$

- `[Stochastic(gust) wind` expressed in the `body frame`](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)

$$
\bold V_{w_g}^b=
\left(
\begin{matrix}
u_{w_g}\\
v_{w_g}\\
w_{w_g}
\end{matrix}
\right)
$$

<aside>
📌 **Non-steady gust portion of the wind model**

- Pass `white noise` through a LTI(Linear Time Invariant) filter $\Rightarrow$ good model(`von Karmen turbulence spectrum`)
- `von Karmen turbulence spectrum`은 적절한 전달함수를 제공하지 못함
- `von Karmen turbulence spectrum model`에 대한 적절한 추정을 `[Dryden transfer function](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)`으로 나타낼 수 있다.
</aside>

$$
\begin{aligned}
H_u(s)&=\sigma_u\sqrt{\frac{2V_a}{L_u}}\frac{1}{s+\frac{V_a}{L_u}}\\
H_v(s)&=\sigma_v\sqrt{\frac{3V_a}{L_v}}\frac{\left(s+\frac{V_a}{\sqrt3L_v}\right)}{\left(s+\frac{V_a}{L_v}\right)^2}\\
H_w(s)&=\sigma_w\sqrt{\frac{3V_a}{L_w}}\frac{\left(s+\frac{V_a}{\sqrt3L_w}\right)}{\left(s+\frac{V_a}{L_w}\right)^2}
\end{aligned}
$$

- $\sigma_u, \sigma_v, \sigma_w$ : turbulence intensities along vehicle frame axes
- $L_u, L_v, L_w$ : spatial wavelength
- $V_a$ : airspeed of vehicle

위 Dryden model들은 constant nominal airspeed $V_{a0}$를 상정하고 적용한 것

![Untitled](Forces%20and%20Moments(Chap%204%20)%207315f570e3474c9a88b678d18073ab0e/Untitled%208.png)

![Untitled](Forces%20and%20Moments(Chap%204%20)%207315f570e3474c9a88b678d18073ab0e/Untitled%209.png)

- 다음 [table 4.1](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)에서 low, medium altitude & light, moderate turbulence 환경에 적용 가능한 파라미터들을 나타낸다.
- 다음 [Figure 4.9](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)는 steady wind와 atmospheric disturbance component들이 EoM에 어떻게 적용할 수 있는지 나타낸 블록선도
    - Dryden fileter에 white noise를 통과시켜 vehicle frame 내에서 gust가 어떻게 표현됐는지를 나타냄
    - 바람의 steady component들은 inertial frame에서 body frame으로 rotate
    - Gust component들을 더해 body frame에서 `[total wind](https://www.notion.so/Forces-and-Moments-Chap-4-7315f570e3474c9a88b678d18073ab0e?pvs=21)`를 구할 수 있다.

$$
\bold V_w^b=\left(\begin{matrix}
u_w\\
v_w\\
w_w
\end{matrix}\right)=
\mathcal R^b_v(\phi, \theta, \psi)\left(\begin{matrix}
w_{n_s}\\
w_{e_s}\\
w_{d_s}
\end{matrix}\right)+
\left(\begin{matrix}
u_{w_g}\\
v_{w_g}\\
w_{w_g}
\end{matrix}\right)
$$

**Body frame components of the airspeed vector**

Wind velocity $\bold{V}^b_w$, ground velocity $\bold V^b_w$이 두 컴포넌트들을 통해 body frame에서의 airspeed vector를 구할 수 있다.

$$
\bold{V}^b_a=
\left(\begin{matrix}
u_r\\
v_r\\
w_r
\end{matrix}\right)=
\left(\begin{matrix}
u-u_w\\
v-v_w\\
w-w_w
\end{matrix}\right)
$$

다음 body frame airspeed component들을 통해 `airspeed magnitude`$(V_a)$, `angle of attack`$(\alpha)$, `sideslip angle`$(\beta)$을 구할 수 있다.

$$
\begin{aligned}
V_a&=\sqrt{u_r^2+v_r^2+w_r^2}\\
\alpha&=\tan^{-1}\left(\frac{w_r}{u_r}\right)\\
\beta&=\sin^{-1}\left(
\frac{v_r}{\sqrt{u_r^2+v_r^2+w_r^2}}
\right)
\end{aligned}
$$

위 `airspeed magnitude`$(V_a)$, `angle of attack`$(\alpha)$, `sideslip angle`$(\beta)$이 세 컴포넌트들을 통해 기체에 작용하는 aerodynamic force와 moment를 구할 수 있다.