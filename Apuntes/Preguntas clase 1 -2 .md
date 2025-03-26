## Para traer buscado / pensado

### 1. ¿Cuál es la resistencia típica de un voltímetro, amperímetro?

- Resistencia del voltimetro ~10 $M\Omega$
- Orden $1\Omega$, no especificado en el manual

---

### 2. ¿Cuál es la corriente máxima del amperímetro?

---

### 3. ¿Cuál es el rango de voltajes de las fuentes de laboratorio?

---

### 4. ¿Cuál es la corriente / potencia máxima que tolera una resistencia de carbono?

La corriente y potencia máxima que tolera una resistencia de carbono depende principalmente de su **tamaño físico** (que determina su capacidad de disipación de calor) y de su **construcción**. A continuación, te doy una guía general:

1. **Potencia máxima (P)**
   Las resistencias de carbono estándar suelen venir en valores típicos de potencia, comúnmente:
- **1/8 W** (0.125 W) – Tamaño pequeño (como las de 1/4W pero con menor disipación).
- **1/4 W** (0.25 W) – Las más comunes en circuitos de baja potencia.
- **1/2 W** (0.5 W) – Para aplicaciones con mayor disipación.
- **1 W o más** – Menos comunes en carbono, ya que suelen ser de película metálica o alambre.
2. **Corriente máxima (I)**
   La corriente máxima se calcula a partir de la potencia y la resistencia (R) usando la ley de Joule:  

$$
I_{\text{máx}} = \sqrt{{\frac{P}{R}}}
$$

**Ejemplo:**  
Para una resistencia de **1kΩ a 1/4 W**:  

$$
I_{\text{máx}} = \sqrt{{\frac{0.25}{1000}}} \approx 0.016 \text{ A} \ (16 \text{ mA})
$$

3. **Límites prácticos**
- **Tensión máxima**: Aunque la potencia sea el factor principal, también hay un límite de tensión (usualmente 200–350 V para resistencias de 1/4 W).

- **Temperatura**: Si se supera la potencia nominal, la resistencia puede sobrecalentarse, quemarse o cambiar su valor (las de carbono son sensibles al calor).
4. **Recomendaciones**
   - **No excedas la potencia nominal** (usa una resistencia de mayor wattaje si es necesario).
   - **Considera el ambiente**: En entornos calurosos, reduce la potencia máxima usable.

---

### 5. Teniendo en cuenta (1), (2),(3) y (4), ¿Cuál es el rango de valores de resistencias para usar en los distintos experimentos?
