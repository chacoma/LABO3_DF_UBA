##  Circuito RLC


### 1. Conceptos básicos

A $t=0$ el inductor se opone al cambio, genera un pico de tensión igual a la fuente y hace que la corriente sea nula. En este tiempo el capacitor funciona como un cortocircuito.

A $t>0$ empieza a circular corriente, la tensión en el inductor decae, la tensión en el capacitor crece hasta igualar la tensión de la fuente. En este transitorio, la corriente evoluciona dependiendo de los valores de los parámetros.

- **Caso sub amortiguado.** Oscilaciones amortiguadas alrededor de cero, tiempo característico $\tau= \frac{2L}{R}$.

$$
R < 2 \sqrt{ \frac{L}{C} } 
$$

- **Caso crítico.** Curva suave con un pico antes de decaer, la corriente alcanza un máximo, tiempo característico $\tau= \frac{2L}{R}$.

$$
R = 2 \sqrt{ \frac{L}{C} } 
$$

- **Caso sobre amortiguado.** Decaimiento exponencial sin oscilaciones, la corriente puede alcanzar un máximo dependiendo de las CI. Tiempo caracterísitico $\tau= \frac{2L}{R-\sqrt{ R^2 - 4L/C }}$.

$$
R > 2 \sqrt{ \frac{L}{C} } 
$$

A $t \to \infty$ el capacitor se carga completamente e iguala la tensión de la fuente, deja de circular corriente, y el inductor funciona como un cortocircuito.

En todo el proceso el circuito empieza con conrriente nula y termina con corriente nula, dependiendo de los parámetros del sistema trancurrira por ese transitorio de una manera u otra.


---

### 2. Ecuaciones de $I(t)$, $V_L(t)$ y $V_C(t)$ en los distintos regimenes

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

definimos **coeficiente de amortiguamiento** como,

$$
\gamma = \frac{R}{2L}
$$

y la **frecuencia natural** del sistema como,

$$
\omega_0^2 = \frac{1}{LC}
$$

Luego la ec. diferencial puede expresarse,

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

Donde $s_1$ raiz de decaimiento lento y $s_2$ raiz de decaimiento rápido. Dependiendo el valor del discriminante, tendremos distinto tipo de soluciones

 #### **Caso Sub amortiguado**: $\gamma^2 < \omega_0^2$

Definimos $\omega^2 = \omega_0^2 - \gamma^2 $.



$$
I(t) = \frac{V_0}{L \omega} e^{-\gamma t} sin(\omega t)
$$


$$
V_L(t) = V_0 e^{-\gamma t} \left( \cos(\omega t) - \frac{\gamma}{\omega} \sin(\omega t) \right)
$$

$$
V_C(t) = V_0 \left( 1 - e^{-\gamma t} \left( \cos(\omega t) + \frac{\gamma}{\omega} \sin(\omega t) \right) \right)
$$




 #### **Caso crítico**: $\gamma^2 = \omega_0^2$



$$
I(t) = \frac{V_0}{L} t  e^{-\gamma t}.
$$


$$
V_L(t) = V_0 e^{-\gamma t} (1 - \gamma t).
$$


$$
V_C(t) = V_0 \left( 1 - e^{-\gamma t} (1 + \gamma t) \right).
$$


#### **Caso sobre amortiguado**: $\gamma^2 > \omega_0^2$


$$
I(t) = \frac{V_0}{L (s_1 - s_2)} \left( e^{s_1 t} - e^{s_2 t} \right).
$$

$$
V_L(t) = \frac{V_0}{s_1 - s_2} \left( s_1 e^{s_1 t} - s_2 e^{s_2 t} \right).
$$


$$
V_C(t) = V_0 \left( 1 - \frac{s_2 e^{s_1 t} - s_1 e^{s_2 t}}{s_2 - s_1} \right).
$$


---

### 3. Experimento propuesto

La idea es medir los transitorios para los casos Sub y Sobre Amortiguado. Para esto hay que elegir los componentes electronicos de manera adecuada, en este link:

[Colab para el cálculo del tiempo carcterístico](https://colab.research.google.com/drive/1yhTcZA-GSk9p4tQdrW828Y4U56DDYV1Q?usp=sharing)

Se puede encontrar un programa que facilita la elección de los valores de componentes en función de los parámetros y tiempos caracterísiticos deseados.


Uno vez calculado el tiempo característico, $\tau$, este se utiliza para generar un tren de pulsos cuadrados, $f \approx \frac{1}{20 \tau}$, para poder ver el transitorio completo.

La idea es adquirir con el osciloscopio la salida generador de funciones $V_{in}$ y los bornes del capacitor $V_C$, uno en cada canal. Recordar que las masas del osci y el gen deben coincidir.

