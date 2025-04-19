# Filtros pasa bajos



## 1. Con Circuito RC

```
 _____ -(SIN,f)+ _____ R ________ C ____   
|                  |         |          |  
GND               Vin      VC=Vout      GND
```

Tenemos una tensión de entrada alterna expresada en forma de *fasor rms*:

$$
V_{in} = v_{in}^{rms} e^{j \phi_{in}}
$$

La tensión de salida se calcula a partir del divisor de impedancias:

$$
V_{out} =  V_{in} \frac{Z_C}{Z_C + R}
$$

Definimos la función de transferencia como:

$$
T = \frac{Z_C}{Z_C + R} =   \frac{1}{1+ j \omega RC}
$$

Definimos la frecuencia de corte del filtro como:

$$
f_c = \frac{1}{2 \pi R C}
$$

Entonces, la función de transferencia compleja queda:

$$
T = \frac{1}{1+ j \frac{f}{f_c}} \quad (1)
$$

Note que la función de transferencia compleja contiene la información de como se modifica la amplitud y la fase de la señal $V_{in}$ al pasar por el filtro:

$$
V_{out} = T V_{in}
$$

$$
\frac{V_{out}}{V_{in}} = \frac{v_{out}^{rms} e^{j \phi_{out}}}{v_{in}^{rms} e^{j \phi_{in}}} = \frac{v_{out}^{rms} }{v_{in}^{rms} } e^{j (\phi_{out}-\phi_{in})} = |T| e^{j \phi_T}
$$

luego la relación entre amplitudes:

$$
v_{out}^{rms} = |T| v_{in}^{rms}
$$

$$
v_{out}^{rms} = \frac{1}{ \sqrt{1 + (\frac{f}{f_c})^2} } v_{in}^{rms} \quad (2)
$$

y el desfasaje:

$$
\phi_{out} - \phi_{in} = \phi_T
$$

$$
\Delta \phi = - tan^{-1} (\frac{f}{f_c}) \quad (3)
$$




## 2. Con Circuito RL


```
 _____ -(SIN,f)+ _____ L ________ R ____   
|                  |         |          |  
GND               Vin      VR=Vout      GND
```


Tenemos una tensión de entrada alterna expresada en forma de *fasor rms*:

$$
V_{in} = v_{in}^{rms} e^{j \phi_{in}}
$$

La tensión de salida se calcula a partir del divisor de impedancias:

$$
V_{out} =  V_{in} \frac{R}{R + Z_L}
$$

Definimos la función de transferencia como:

$$
T = \frac{R}{R + Z_L} =   \frac{1}{1+ j \omega \frac{L}{R}}
$$

Definimos la frecuencia de corte del filtro como:

$$
f_c = \frac{1}{2 \pi \frac{L}{R}}
$$

Entonces, la función de transferencia compleja queda:

$$
T = \frac{1}{1+ j \frac{f}{f_c}}
$$

Note que es la misma expresión que para el caso del filtro RC, lo que cambia es como se cálcula la frecuencia de corte.

Por lo tanto la relación entre amplitudes ec.(2) y el desfasaje ec.(3), siguen la misma expresión.


## 3. Atenuación 

La atenuación que subre la señal a la salida se expresa como:

$$
A (f) = -20 log_{10}\big[ T(f)\big]\quad [dB]
$$

Utilizando la función de transferencia asociada a nuestros filtros, la atenuación para los filtros pasa-bajos queda:


$$
A (f) = -20 log_{10}\big[ ( 1 + (f/f_c)^2  )^{-\frac{1}{2}} \big]
$$

$$
A (f) = 10 log_{10} \big [ 1 + \big(\frac{f}{f_c} \big)^2  \big]
$$

A la frecuencia de corte la atenuación es $A(f_c)\approx 3dB$.

Para $f > f_c$, la atenuación decrece a una razón constante de $20 dB$ por década.


## 4. Experimento propuesto

Armar un circuito filtro pasa-bajos

Hacer un barrido de frecuencias y para cada una medir la amplitud de entrada y la de salida con el osciloscopio utilizando medición tipo CRMS. 

Obtener $v_{in}^{rms}$ y  $v_{out}^{rms}$ en función de $f$, definir el modulo de la función de transferencia como el cociente.

Hacer un ajuste de la ec. (2) para obtener $f_c$
 
Tambien se puede graficar la atenuación.




