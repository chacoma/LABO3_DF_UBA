# Circuito equivalente de Thevenin

En un **circuito "caja negra"** lineal con dos terminales 

## **Método Práctico para Hallar $V_{th}$ y $R_{th}$**

#### **1. Medir el Voltaje de Thévenin ($V_{th}$)**

- **Qué hacer**:  
- Conecta un **voltímetro** (en modo DC o AC, según sospeches que hay dentro) directamente a los terminales **A** y **B**.  
- **Importante**: No conectes ninguna carga externa (deja los terminales en **circuito abierto**).  
- **Resultado**:  
- La lectura del voltímetro es $V_{th}$.  

#### **2. Medir la Resistencia de Thévenin ($R_{th}$)**

Usando una resistencia de carga conocida ($R_L$):

1. Conecta una **resistencia de carga**$R_L$(valor conocido) entre **A** y **B**.

2. Mide el **voltaje $V_L$** en $R_L$ con el voltímetro.  

3. Calcula $R_{th}$ con la fórmula:  

$$
R_{th} = R_L \cdot \left( \frac{V_{th}}{V_L} - 1 \right)
$$

   *Derivación*: Usando el divisor de tensión del equivalente de Thévenin cargado: $V_L = V_{th} \cdot \frac{R_L}{R_{th} + R_L}$.  

---

### **Precauciones**

1. **Fuentes dependientes**: Si el circuito tiene fuentes controladas internas, estos métodos siguen válidos (el equivalente de Thévenin aún existe).  
2. **No linealidades**: Si el circuito tiene componentes no lineales (ej. diodos), el método no aplica.  
3. **Seguridad**: No cortocircuites terminales si sospechas altas corrientes o voltajes peligrosos.  

---

### **Ejemplo Completo**

Medimos:

- $V_{th} = 12V$ (en circuito abierto).  

- Al conectar $R_L = 4Ω$, mides $V_L = 8V$.  

Entoncesla resistencia de thev:

$$
R_{th} = 4Ω \cdot \left( \frac{12V}{8V} - 1 \right) = 4Ω \cdot (1.5 - 1) = 2Ω
$$

**Equivalente de Thévenin**:  

- Fuente de **12V** en serie con **2Ω**.  

---

## **Pasos para calcular el Equivalente de Thévenin**

#### **1. Identificar los terminales A y B**

- Selecciona los dos puntos del circuito donde quieres hallar el equivalente.  

#### **2. Calcular $V_{th}$ (Tensión de Thévenin)**

- Abre el circuito entre A y B (sin conectar ninguna carga).  
- Usa leyes de Kirchhoff, divisores de voltaje, etc.  

#### **3. Calcular $R_{th}$ (Resistencia de Thévenin)**

- **Pasos**:  
  
  1. **Anula todas las fuentes independientes**:  
     - Fuentes de voltaje → **Cortocircuito** (reemplázalas por un cable).  
     - Fuentes de corriente → **Circuito abierto** (elimínalas).  
  2. **Mira la resistencia entre A y B**:  
     - Si no hay fuentes dependientes, calcula la resistencia equivalente normalmente.  
     - Si hay fuentes dependientes, usa el **método de la fuente de prueba** (explicado abajo).  

- **Métodos para calcular $R_{th}$** (elige uno):  
  
  - **a) Análisis directo**:  
    - Usa reducción serie/paralelo o transformaciones delta-estrella.  
  - **b) Método de la fuente de prueba**:  
    - Conecta una fuente de voltaje $V_{\text{test}}$ entre A y B.  
    - Mide la corriente $I_{\text{test}}$ que sale de la fuente.  
    - Calcula: $R_{th} = \frac{V_{\text{test}}}{I_{\text{test}}}$.  

### **Casos Especiales**

1. **Si hay fuentes dependientes**:  
   - **No se pueden anular**. Usa el método de la fuente de prueba para $R_{th}$.  
2. **Si el circuito ya tiene una carga entre A y B**:  
   - Remueve la carga temporalmente para calcular $V_{th}$ y $R_{th}$.  
3. **Si $R_{th} = 0$**:  
   - El circuito es una fuente de voltaje ideal.  
4. **Si $R_{th} = \infty$**:  
   - El circuito es una fuente de corriente ideal.  
