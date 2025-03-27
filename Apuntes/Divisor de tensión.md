## Apunte sobre divisor de tensión

### Derivación

Tenemos 1 fuente de tensión $V_0$ que alimenta 2 resistencias en serie $R'$ y $R$:

![div](images/divisor.jpg)

Queremos estudiar la caida de tensión sobre la resistencia $R$:

$$
V = I R
$$

La corriente que circula sobre las 2 resistencias es la misma:

$$
I = \frac{V_0}{(R' + R)}
$$

Reemplazando la segunda en la primera ecuación, nos queda la tensión que cae sobre la resistencia $R$:

$$
V = V_0 \frac{R}{R' + R}
$$

Note que la tensión de entrada se *divide* por un factor $\frac{R}{R' + R}$.

-Si $R' = 0$, entonces $V=V_0$ la tensión de entrada cae completamente sobre $R$.

-Si $R' \to \infty$, entonces $V=0$ la tensión de entrada cae completamente sobre $R'$.

---

### Sensibilidad en la medición

La caída de tensión en la resistencia $R$ puede escribirse así:

$$
V = V_0 \frac{1}{x + 1}, \quad  x= \frac{R'}{R}
$$

Graficando la relacion $V/V_0$ vs $R'/R$, podemos ver como evoluciona $V$ en función de la relación entre las resistencias:

![v_x](images/v_x.png)

Para simplificar el análisis del gráfico, pensemos en valores de $V_0$ y $R$ fijos.

Lo primero que vemos es que en $x=0$, la tensión de salida es máxima $V=V_0$. Significa que cuando $R'=0$ toda la tensión de entrada cae sobre $R$.

Por otro lado, podemos ver que entre $x=0$ y $x=5$, la tensión cambia significativamente. Así mismo, para $x>5$ la tensión no cambia mucho. 

Entonces, en el intervalo $x\in(0,5)$ podemos decir que la tensión de salida $V$ es **sensible** a los cambios de $R'$, comparado con lo que ocurre con el rango $x>5$.

**Determinacion del rango de mayor sensibilidad**

Se puede determinar analizando la derivada de $V$ respecto de $x$:

$$
\frac{dV}{dx} =V_0 \frac{-1}{(1+x)²}
$$

Vamos a pedir que el cambio en resistencia produzca un cambio significativo en la caída de la tensión:

$$
V_0 \frac{1}{(1+x)²} \geq \alpha
$$

$$
\frac{1}{(1+x)²} \geq \frac{\alpha}{V_0}
$$

por ejemplo, si fijamos la  relación $\alpha=0.1 V_0 $, es decir pedimos que el cambio en $R'$ produzca cambios en $V$ mayores o iguales al $10%$, se debe cumplir:

$$
\frac{1}{(1 + x)^2} \geq 0.1
$$

Resolviendo esta desigualdad:

$$
(1 + x)^2 \leq 10
$$

$$
1 + x \leq \sqrt{10}
$$

$$
x \leq \sqrt{10} - 1 \approx 2.16
$$

Esto indica que la sensibilidad es mayor cuando \( x \) está en el rango **$0 \leq x \leq 2.16$**.

Dentro de este intervalo, los cambios en $x$ generan diferencias más notorias en la caída de tensión sobre $R$.

En términos de la resistencia $R'$:

$$
0 \leq R' \leq 2R
$$

En ese rango tendremos una buena resolución para efectuar nuestra medicion.

### Caso ejemplo:

Tenemos un circuito alimentado con una fuente de tensión $V_0=5V$. Con una resistencia de carga de $R= 1 k\Omega$ y un potenciometro $R'$ que puede variar desde $R'=0$ hasta $R'=2 k\Omega$.

Cuando $R'\sim 0$ obtenemos los siguiente valores:

![i1](images/dt1.png)

Cuando $R'\sim 2R$ obtenemos los siguiente valores:

![i2](images/dt2.png)

Podemos ver que el rango de tensiones $V$ accesibles es $(1.68V, 4.9V)$.

Así mismo, el rango de corrientes accesibles es $I$ es $(1.68mA, 4.9mA)$.

Si estamos usando resistencias de carbon que admite una potencia máxima de $P=0.25W$, la corriente de limitación será: 

$$ I_{Max}= \sqrt{P/R} = \sqrt{0.25/1000} = 15.8 mA$$

Vemos que es bastante mayor a nuestro rango de corrientes de trabajo, esto nos asegura una medición dentro de los rangos de seguridad.
