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

El factor de merito del filtro se define como:

$$
Q = 2 \pi \frac{Energía \ Almacenada}{Energía \ Disipada \ \times \ ciclo }
$$




