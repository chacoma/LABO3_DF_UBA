## Conceptos básicos

Un transistor es un componente circuital no lineal basado en semiconductores. No es la idea explicar aquí el detalle de su funcionamiento, sino más bien adquirir una cierta intuición de como y para que se utiliza.

La forma más intuitiva de pensarlo es como un tubo con agua mas un grifo: Si cerramos el grifo no circula agua (CORTE), si lo abrimos un poquito, circulará algo de agua (ACTIVA), y  si lo abrimos todo circulará toda el agua disponible (SATURACIÓN).

Como ven, el grifo me permite **controlar** la circulación de agua.


![trans_1](images/esquema_transistor.jpg)


Ahora bien, volviendo a la electronica, el transistor es un elemento de tres patas: Base, Colector y Emisor. La base nos permite abrir el grifo: haciendo circular una pequeña corriente por esa rama, controlamos la corriente que circula por las ramas Colector - Emisor.

Notar que vale la ley de mallas,

$$
I_B = I_C + I_E
$$

Asimismo, hay dos tensiones importantes que tendremos que analizar: 

1) La tensión $V_{BE}$. Tenemos que pensar que entre B y E hay un diodo de silicio, por lo tanto para que el transistor salga de CORTE tenemos que asegurarnos de que caigan $0.7 V$ entre B y E.

2) La tensión $V_{CE}$. Setear de manera correcta esta tensión, me permite definir de que manera trabajará el transistor. 


En terminos generales el transistor trabaja en dos configuraciones: ACTIVA y CORTE-SATURACIÓN. De eso hablo en el apartado siguiente.

### Configuración y puntos de trabajo

Hay dos formas de utilizar un transistor. Para configurar alguna de ellas tenemos que elgir cuidadosamente los valores de las resistencias del circuito y de las fuentes para que se cumplan las condiciones que se indican a continuación.


**1. Activa**

En esta configuración se cumple una relación muy importante entre la corriente de base y la corriente de colector,

$$
I_C = \beta I_B
$$

donde $\beta$ se conoce como ganancia. Su valor depende del modelo del transistor, un valor típico es $\beta=100$. En concreto, con una pequeña corriente de base podemos controlar una gran corriente de colector.

La tensión entre colector y emisor, $V_{CE}$, en esta configuración tiene que ser mayor $0.3V$.

En esta configuración el transistor se usa como **amplificador**. Las variaciones en la corriente de base se reflejan en la corriente de colector. Como la corriente de base es chica sus pequeñas variaciones serán capturadas con grandes variaciones en la corriente de colector, lo cual permite amplificar la señal.


**2. Corte - Saturación**

En esta configuración utilizamos el transistor como una **llave electronica**, quiero que si no hay corriente en la base, la llave este cerrada, y que cuando haya corriente en la base, la llave se abra por completo. Es decir, en esta configuración quiero crear una especie de ON-OFF (0-1) controlado por la corriente de base. Esto que parece una pavada es el fundamento de toda la electronica digital moderna así que respeten.

En la configuración Corte-saturación la corriente de base y de colector ya no siguen la relación lineal que teniamos en Activa. En saturación ya abrimos la llave por completo, por más que SE siga aumentando la corriente de base no se va a abrir más, por eso se dice que esta "saturado". No obstante, para hacer los calculos, la relación entre $I_B$ y $I_C$ se puede estimar definindo un $\beta_{sat}$,

$$
I_C(sat) \approx \beta_{sat} I_B
$$

$$
\beta_{sat} = \beta/10
$$

Resepcto a la tensión colector - emisor, tiene que ser menor a $0.3V$, idealmente para los calculos podemos trabajar con $V_{CE}=0$.

---
### Ejemplos de cálculo y propuesta de experimentos

#### (1) Interruptor, encender un Led

En este ejemplo vemos como obtener los valores para que el transistor, funcionando en Corte-saturación, funcione como un interruptor para encender un led.

![led](images/trans_led.jpg)

La rama vertical tiene un Led que quiero encender. Para eso necesito que la diferencia de potencial en sus bornes sea $V_{LED}=2V$ y que la corriente $I_C\leq20mA$, para no quemarlo. En función de eso tendremos que calcular los valores de los otros parámetros del circuito.

Queremos hacer un interruptor ON/OFF, tal que cuando la tensión de control es $V_{BB}=0$ el led esta apagado, y cuando setee $V_0\geq5V$ el led se prenda.

**Paso 1) Determinación de $R_C$**. 

En la rama vertical se tiene que cumplir

$$
V_{CC} = I_C R_C + V_{LED} + V_{CE}
$$

sabemos que $V_{LED}=2V$, $I_C\leq20mA$. Además queremos trabajar en saturación, entonces hacemos $V_{CE}=0$. Supongamos que seteamos $V_{cc}=5V$, algo típico. Con eso puedo calcular el valor de $R_C$ como,

$$
R_C = \frac{V_{cc} - V_{LED}}{I_C}
$$

$$
R_C = \frac{5 - 2 }{20.10^{-3}} [\Omega]
$$

$$
R_C = 150\Omega
$$

Como hice la cuenta con el valor límite que soporta el led, para estar tranquilo pongo una resistencia mas grande, por ejemplo tomo $R_C=200$ $\Omega$

**Paso 2) Determinación de $I_B$ necesaria**.

La relación $I_B$ vs. $I_C$ no es lineal en saturación. Por eso, para un diseño riguroso en esta zona de trabajo, es crucial tener las curvas de trabajo del transistor.

Si no tenemos las curvas, una forma practica de estimar la relación entre $I_C$ e $I_B$ en saturación, es definir una ganancia efectiva $\beta_{sat}= \beta/10$, donde $\beta$ es la ganancia que da el fabricante para la zona activa, luego,

$$
I_B = \frac{I_C}{\beta_{sat}}
$$


Si en nuestro caso $\beta=100$ entonces $\beta_{sat}=10$, luego pordemos estimar,

$$
I_B = 20mA/10 = 2mA
$$

**Paso 3) Determinación de $R_B$**.

En la rama horizontal se tiene que cumplir,

$$
V_{BB} = I_B R_B + V_{BE}
$$

Tomando $V_0=5V$ y sabiendo que $V_{BE}=0.7$, entonces,

$$
R_B = \frac{V_{BB} - V_{BE}}{I_B}
$$

$$
R_B = \frac{5-0.7}{2.10^{-3}} [\Omega]
$$

$$
R_B \approx 2150 \Omega
$$

De nuevo, tomo una resistencia un poco más grande, supongamos $R_B=2.2k\Omega$.

Hice una simulación con esos valores y obtuve lo siguiente,

![simu1](images/simu_transistor_interruptor.gif)


