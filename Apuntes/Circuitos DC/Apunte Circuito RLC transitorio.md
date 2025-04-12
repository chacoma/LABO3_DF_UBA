##  Circuito RLC


### 1. Conceptos básicos

A $t=0$ el inductor se opone al cambio, genera un pico de tensión igual a la fuente y hace que la corriente sea nula. En este tiempo el capacitor funciona como un cortocircuito.

A $t>0$ empieza a circular corriente, la tensión en el infuctor decae, la tensión en el capacitor crece hasta igualar la tensión de la fuente. En este transitorio, la corriente evoluciona dependiendo de los valores de los parámetros.

- Caso sub amortiguado, **Oscilaciones amortiguadas alrededor de cero**, tiempo característico $\tau= \frac{2L}{R}$.

$$
R < 2 \sqrt{ \frac{L}{C} } 
$$

- Caso crítico amortiguado, **Curva suave con un único pico antes de decaer**, alcanza un máximo en un único pico, tiempo característico $\tau= \frac{2L}{R}$.

$$
R = 2 \sqrt{ \frac{L}{C} } 
$$

- Caso sobre amortiguado, **Decaimiento exponencial sin oscilaciones** puede alcanzar un máximo dependiendo de las CI. Tiempo caracterísitico $\tau= \frac{2L}{R-\sqrt{ R^2 - 4L/C }}$.

$$
R > 2 \sqrt{ \frac{L}{C} } 
$$

A $t \to \infty$ el capacitor se carga completamente e iguala la tensión de la fuente, deja de circular corriente, y el inductor funciona como un cortocircuito.


---

### 2. Ecuaciones para ajustar en los distintos regimenes

Queremos obtener la evolución de la corriente en el circuito, empezamos planteando la igualdad entre las caídas de tensión:

$$
V_0 = V_R + V_L + V_C
$$

En términos de la corriente:

$$
V_0 = I R + L \dot{I} + \frac{1}{C} \int I dt
$$

derivamos respecto del tiempo para sacarnos de encima la integral:

$$
\ddot{I} + \frac{R}{L} \dot{I} + \frac{1}{LC} I = 0
$$

definimos $\gamma = \frac{R}{2L}$ como el *coeficiente de amortiguamiento*, $\omega_0^2 = \frac{1}{LC}$ como la *frecuencia natural*. Luego,

$$
\ddot{I} + 2 \gamma \dot{I} + \omega_0^2 I = 0
$$

Se propone una solución del tipo $I(t)= A e^{st}$ con $s\in \mathbb{C}$. Reeplazando obtenemos una condición para $s$:

$$
s^2 + 2 \gamma s + \omega_0^2 = 0
$$

$$
s_{1,2} = -\gamma \pm \sqrt{ \gamma^2 - \omega_0^2 }
$$

Dependiendo el valor del discriminante, tendremos distinto tipo de soluciones:

**Caso Sub amortiguado**: $\gamma^2 - \omega_0^2 < 0$

Definimos $\omega = \omega_0^2 - \gamma^2 $, luego la solución se puede escribir como:

$$
I(t) = A e^{-\gamma t} sin( \omega t + \phi  )
$$

Para sacar el valor de las constantes, usamos las condiciones inciales (1) $I(t=0)=0$ y (2) $\dot{I}(t=0)= V_0/L$. Entonces la corriente se puede escribir como: 

$$
\boxed{
I(t) = \frac{V_0}{L \omega} e^{-\gamma t} sin(\omega t)
}
$$

Para obtener las tensión que cae en el inductor, tenemos que considerar que $V_L(t) = L \dot I$, entonces,

$$
\boxed{
    V_L(t) = V_0 e^{-\gamma t} \left( \cos(\omega t) - \frac{\gamma}{\omega} \sin(\omega t) \right)
}
$$


Para obtener la caida de tensión en el capacitor, consideramos $V_C(t)= \frac{1}{C} \int I dt$, luego se puede probar que,

$$
\boxed{
V_C(t) = V_0 \left( 1 - e^{-\gamma t} \left( \cos(\omega t) + \frac{\gamma}{\omega} \sin(\omega t) \right) \right)
}
$$


