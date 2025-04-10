## Circuito RL

### 1. Conceptos básicos

#### Carga

En $t=0$ el circuito se comporta como un circuito abierto. Para oponerse al cambio, el inductor en el circuito genera una tensión en sus bornes igual que la tensión de la fuente,

$$
V_L(t=0) = V_0
$$

Eso hace que no circule corriente en el circuito,

$$
I(t=0)=0
$$

En $t>0$ la tensión en la inductancia disminuye exponencialmente porque la fem inducida disminuye a medida que la corriente se estabiliza,

$$
V_L(t) = V_0 \; e^{-\frac{t}{\tau}}, \quad \tau= \frac{L}{R}
$$

asimísmo la corriente aumenta demanera exponencial como,

$$
I(t) = \frac{V_0}{R} \big( 1- e^{-\frac{t}{\tau}} \big)
$$


Para $t \to \infty$, al estabilizarse la corriente el inductor no tiene tiene cambio al cual oponerse entonces no genera ninguna fem, por tal motivo los bornes del inductor se comportan como un cortocircuito:

$$
V_L(t\to\infty)=0
$$

La corriente entonces, alcanza su valor máximo:

$$
I_{M} = \frac{V_0}{R} 
$$


La constante de tiempo $\tau=L/R$ depende de los valores de los componentes del circuito. Si $R$ es chica respecto a $L$ tardará mucho tiempo en estabilizar la corriente. Si $R$ es grande la estabilización será rápida.

#### Descarga

Mientras la fuente esta encendida, el inductor almacena energía en forma de campo magnético,

$$
E_L = \frac{1}{2} L I_{M}^2
$$

Si se corta la fuente abruptamente el inductor se opone al cambio de corriente en el circuito generando una tensión para mantener el flujo de corriente. Es decir, genera una "fuente" con la cara positiva mirando hacia donde sale la corriente, para "empujarla" y que no pare de circular. Entonce a $t=0$ la tensión será:

$$
V_L = - V_0
$$

Para $t>0$ la corriente que genera el inductor se disipa en la resistencia por efecto Joule decayendo exponcialmente:

$$
I(t) = I_M\; e^{-\frac{t}{\tau}}
$$

la tensión decae tambien de manera exponencial pero con la polaridad invertida:

$$
V_L(t) = - V_0\; e^{-\frac{t}{\tau}}
$$