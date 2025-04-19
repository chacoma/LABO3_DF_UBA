# Filtro cancela banda

## 1. Conceptos básicos

```
                       __ C __
 _____ -(SIN,f)+ ______|_ L _|_____ R _____   
|                  |            |          |  
GND               Vin          VR=Vout     GND
```

El circuito L//C R es exitado por un señal sinusoide $V_{in}= v_{in} e^{j \phi_{in}}$, donde $v_{in}$ es la amplitud de la señal y $\phi_{in}$ la fase.

La tensión a la salida del filtro será $V_{out}= v_{out} e^{j \phi_{out}}$


Esta puede calcularse así:

$$
V_{out} = V_{in}  \frac{ R }{ R + Z_{LC}  }
$$

Donde la impedancia en paralelo $Z_{LC}$ es :

$$
Z_{LC} = \frac{j \omega L \times \frac{1}{j \omega C}}{j \omega L + \frac{1}{j \omega C}} = \frac{ \frac{L}{C} }{j ( \omega L - \frac{1}{\omega C}) } = -\frac{j}{ ( \omega C - \frac{1}{\omega L} ) }
$$

defino la reactancia como:

$$
X(\omega) = -\frac{1}{ ( \omega C - \frac{1}{\omega L} )}
$$


$$
V_{out} = V_{in} \frac{ 1 }{ 1 + j \frac{X(\omega)}{R} }
$$


En resonancia:

$$
\omega= \omega_0 = \sqrt{ \frac{1}{LC}} 
$$

En esta condición, $X(\omega_0) \to \infty$ y $V_{out} \to 0$, la señal de salida se anula.

Definimos la función de transferencia compleja como:

$$
T (\omega) = \frac{ 1 }{ 1 + j \frac{X(\omega)}{R}}
$$

Para cada frecuencia la relación entre las amplitudes de entrada y salida vienen dadas por el modulo de la función de transferencia:

$$
|T| = \frac{1}{ \sqrt{ 1 + (\frac{X(\omega)}{R})^2 } } = \frac{v_{out}}{v_{in}}
$$


Asimismo el desfasaje viene dado por:

$$
\Delta \phi = tan^{-1}\big( -\frac{X(\omega)}{R} \big)
$$

Note que las ecuaciones son igual que en el caso de pasa banda, lo que cambia es la reactancia $X(\omega)$.