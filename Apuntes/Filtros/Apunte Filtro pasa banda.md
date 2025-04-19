# Filtro pasa banda

## 1. Conceptos básicos

```
 _____ -(SIN,f)+ _____ L _____ C _____ R _____   
|                  |               |          |  
GND               Vin             VR=Vout     GND
```

El circuito RLC es exitado por un señal sinusoide $V_{in}= v_{in} e^{j \phi_{in}}$, donde $v_{in}$ es la amplitud de la señal y $\phi_{in}$ la fase.

La tensión a la salida del filtro será $V_{out}= v_{out} e^{j \phi_{out}}$


Esta puede calcularse así:

$$
V_{out} = V_{in}  \frac{ R }{ R + Z_{LC}  }
$$

Donde la impedancia en serie $Z_{LC}$ es :

$$
Z_{LC} = j \omega L + \frac{1}{j \omega C}
$$

Luego,

$$
V_{out} = V_{in}  \frac{ 1 }{ 1 + j \omega \frac{L}{R} + \frac{1}{j \omega C R}  }
$$

Definimos la función de transferencia compleja $T$ como:

$$
V_{out} = T V_{in}  
$$

$$
T(\omega) = \frac{ 1 }{ 1 + j \big( \omega \frac{L}{R} - \frac{1}{\omega R C} \big)}
$$

La relación entre las amplitudes de entrada y salida viene dada por el modulo de la función de transferencia:

$$
|T| = \frac{v_{out}}{v_{in}} = \frac{1}{ \sqrt{1 + \big( \omega \frac{L}{R} - \frac{1}{\omega R C} \big)^2}}
$$

La diferencia de fase será la fase de la función de transferencia:

$$
\Delta \phi = tan^{-1} \big( \frac{Im(T)}{Re(T)} \big) = -tan^{-1} \big( \omega \frac{L}{R} - \frac{1}{\omega R C}  \big)
$$

Note que cuando, 

$$
\omega \frac{L}{R}=\frac{1}{\omega R C}
$$

La transferencia es máxima y el desfasaje es nulo. A la frecuencia que cumple esto se la llama frecuencia de resonancia:

$$
\omega_0 = \sqrt{ \frac{1}{L C} }
$$

$$
f_0 = \frac{1}{2 \pi} \sqrt{ \frac{1}{L C} }
$$

A esa frecuencia la energía que se libera en el capacitor es igual a la que absorve la inductancia, y viceversa. El circuito se comporta como si solo estuviera presente la resistencia (100 % resistivo).



## 2. Factor de mérito

El factor de merito del filtro se define en resonancia como:

$$
Q = 2 \pi \frac{Energía \ Almacenada}{Energía \ Disipada \ \times \ ciclo }
$$

donde la energía almacenada es:

$$
E_{Alm} = \frac{1}{2} L I^2 + \frac{1}{2} C V^2 
$$

La energía disipada por ciclo en resonancia es:

$$
E_{Dis \ ciclo} = I^2 R \times \frac{1}{\tau} =  I^2 R \times \frac{2 \pi}{\omega_0} 
$$

Es importante aclarar que aquí la corriente $I$ es la misma la misma en todo el circuito, en otras configuraciones de filtros RLC esto puede cambiar, así que hay que ser cuidadosos al calcular las energías.

En resonancia los dos términos de la energía almacenada son iguales, entonces

$$
E_{Alm} = L I^2
$$

con esto, podemos calcular $Q$:

$$
Q = 2 \pi \frac{L I^2}{ I^2 R \times \frac{2 \pi}{\omega_0}}=  \frac{\omega_0 L}{R}
$$

Note que cuando $R$ crece, $Q$ se hace más pequeño.


## 3. Potencia


La potencia total en el sistema puede expresarse en forma compleja como:

$$
S = V I^* = V(\frac{V}{Z})^* = |V|^2 \frac{1}{ R - j X }
$$

Donde $R$ es la resistencia y $X$ es la impedancia reactiva.

La parte real de este objeto será la potencia activa:

$$
P_a = v_{in}^2 \frac{R}{R^2 + X^2}
$$

Esta es la potencia que se gasta en el sistema. Asimismo definimos la potencia reactiva como:

$$
P_{reac} = v_{in}^2 \frac{X}{R^2 + X^2}
$$

Esta potencia no se disipa en trabajo útil, se transfiere entre los componentes inductivos y capacitivos del sistema. Note que en resonancia $X=0$ de modo que toda la potencia que se disipa es activa.

En terminos de la función de transferencia note que:

$$
\frac{|T|^2}{R} = \frac{R}{R^2 + X^2}
$$

luego,

$$
P_a = v_{in}^2 \frac{|T|^2}{R} = \frac{v_{in}^2 \times \frac{v_{out}^2}{v_{in}^2}}{R} = \frac{v_{out}^2}{R}
$$


El factor de mérito también puede ser expresado en terminos de la potencia como:

$$
Q = \frac{f_0}{BWD}
$$

donde $BWD$ es el ancho de banda y esta definido como:

$$
BWD = f_1 -f_2
$$

Aquí $f_1$ y $f_2$ se extraen del gráfico de la potencia activa. Se traza una horizontal a la mitad de la potencia máxima, se toman los valores de frecuencia donde la horizontal corta el gráfico de la potencia.