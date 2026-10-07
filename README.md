# ⚡ Análisis Comparativo de Fuentes de Alimentación: Lineal vs. Conmutada

<div align="center">
  <b>Trabajo Final de Electrónica Industrial 2026-II</b><br>
  Universidad Industrial de Santander (UIS)<br>
  Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones (E3T)
</div>

---

## 👥 Integrantes del Proyecto

* **Jarol Nicolás Molano López** - Código: 2230391 - Correo: jarol2230391@correo.uis.edu.co
* **Elkin Fernando Largo Gómez** - Código: 2182334 - Correo: elkin2182334@correo.uis.edu.co

**Dirigido a:** Prof. J. Barrero - `jbarrero@e3t.uis.edu.co`

---

## 📝 Descripción del Proyecto

Este repositorio contiene la documentación técnica de soporte del **Trabajo Final de Electrónica Industrial**: hojas de datos de fabricante (*datasheets*), resultados de simulación, evidencias de laboratorio, presupuesto y código fuente del informe.

El objetivo es seleccionar, simular y probar en laboratorio dos módulos reguladores de tensión, uno lineal (**LM317**) y uno conmutado reductor tipo *Buck* (**LM2596**), y compararlos para determinar cuál ofrece la mejor relación **tamaño / costo / beneficio**. El informe se titula *"Implementación, Simulación y Análisis Comparativo de Eficiencia y Costo-Beneficio en Fuentes de Alimentación Lineales y Conmutadas"*.

### 🎯 Requerimientos Técnicos

* **Tensión de entrada ($V_{IN}$):** variable entre 8 y 12 VDC, con rizado de 120 Hz.
* **Tensión de salida ($V_{OUT}$):** 5 VDC.
* **Corriente de carga ($I_{OUT}$):** 1 A (carga resistiva de 5 Ω).
* **Rizado de salida:** menor a 50 mV.

---

## 📊 Resultados Principales

| Parámetro | LM317 (lineal) | LM2596 (conmutado) |
|---|---|---|
| Eficiencia en simulación | 44.3 % | ≈ 94.8 % |
| Eficiencia medida (12 VDC, 1 A) | 38.3 % | **69.2 %** |
| Potencia de entrada / salida medida | 12.64 W / 4.84 W | 6.77 W / 4.69 W |
| Potencia disipada medida | 7.80 W | **2.08 W** |
| Rizado simulado | 1.2 mV | 6.8 mV |
| Rizado medido | **14.4 mV** | 24.0 mV |
| Regulación de carga simulada (0.1 a 1.25 A) | 0.13 % (6.56 mV) | **0.030 % (1.51 mV)** |
| Temperatura de cápsula a 70 s | > 60 °C | **46.0 °C** |
| Requiere disipador | Sí (incluido en el módulo) | No |

**Conclusión:** ambos módulos cumplen el límite de rizado de 50 mV, pero el **LM2596** ofrece la mejor relación tamaño/costo/beneficio: casi duplica la eficiencia, reduce en 73 % la potencia perdida en calor y opera sin disipador externo, con un costo equivalente.

---

## 💰 Presupuesto del Proyecto

Gastos reales del grupo para la implementación y las pruebas de laboratorio:

| Ítem | Descripción | Proveedor | Valor (COP) |
|---|---|---|---|
| 1 | Módulos reguladores LM317 y LM2596 | Bucacentro (Bucaramanga) | $22.000 |
| 2 | Diodos y capacitor electrolítico de 50 V | Local de electrónica | $2.800 |
| 3 | Componentes adicionales | Pago por Nequi | $8.400 |
| | **Subtotal componentes electrónicos** | | **$33.200** |
| 4 | Termómetro digital infrarrojo sin contacto Berrcom | [Éxito](https://www.exito.com/termometro-digital-infrarrojo-corporal-sin-contacto-berrcom-100665838-mp/p) | $49.900 |
| | **Total del proyecto** | | **$83.100** |

**Notas:**
* El termómetro es un instrumento de medición reutilizable y no forma parte del costo de fabricación de los reguladores. El costo real de los circuitos es de **$33.200 COP**.
* El precio del termómetro corresponde al publicado en Éxito al momento de la consulta (octubre de 2026).
* Instrumentos usados del laboratorio de la universidad (sin costo para el grupo): multímetro Fluke, osciloscopio GW Instek GDS-2062 y fuente/transformador de laboratorio.
* En el informe (Tabla II) se comparan además los precios comerciales de referencia de los 10 módulos evaluados, con enlaces a cada tienda.

---

## 🔌 Circuitos Internos de los Módulos Comerciales

Para entender qué componentes trae cada módulo comercial, se tomaron como referencia los diagramas publicados por distribuidores:

* **Módulo LM317 (1.5 A, salida ajustable):** entrada de 5 a 20 V, salida de 1.5 a 15 V, disipador incluido, potenciómetro de 10 vueltas (10 kΩ), $R_1 = 200\ \Omega$, capacitor de entrada de 0.1 µF y de salida de 47 µF.
  Fuente: [Punto Flotante – Módulo regulador de voltaje LM317](https://www.puntoflotante.net/MODULO-REGULADOR-DE%20VOLTAJE-LM317.htm)
* **Módulo LM2596 ADJ (DC/DC Buck):** LM2596S-ADJ, capacitores de entrada y salida de 220 µF, capacitor de 100 nF, inductor de 33 µH ("330"), diodo Schottky SS34, red de realimentación con $R_1 = 330\ \Omega$ y potenciómetro de 10 kΩ, y capacitor de 10 nF en paralelo con el potenciómetro.
  Fuente: [Solo Electrónica – Circuito inversor con módulo DC/DC LM2596](https://www.soloelectronica.net/modulo%20inversor%20negativo.html)

Con este divisor, la tensión de salida del LM2596 se fija como $V_{OUT} = 1.235\,\text{V}\,(1 + R_{pot}/330\,\Omega)$, y la del LM317 como $V_{OUT} = 1.25\,\text{V}\,(1 + R_{pot}/200\,\Omega)$.

---

## 🗂️ Estructura del Repositorio

* 📁 [`/datasheets/lineales/`](datasheets/lineales): hojas de datos de LM317, LM7805, L78S05, AMS1117 y LM338, con fotografías en `imagenes_lineal/`.
* 📁 [`/datasheets/conmutados/`](datasheets/conmutados): hojas de datos de LM2596, LM2576, XL4015, MP1584 y Mini-360, con fotografías en `imagenes_conmutado/`.
* 📁 [`/datasheets/simulaciones/barridos/`](datasheets/simulaciones/barridos): gráficas y datos (CSV) de los barridos de carga y de temperatura obtenidos en OrCAD PSpice.
* 📁 [`/datasheets/esquematicos/`](datasheets/esquematicos): esquemáticos de simulación de los módulos seleccionados.
* 📁 [`/datasheets/latex/`](datasheets/latex): código fuente del informe en LaTeX (plantilla IEEEtran).
* 📁 [`/evidencias_laboratorio/`](evidencias_laboratorio): fotografías del montaje, capturas del osciloscopio y lecturas de los instrumentos.

### 🎥 Videos de termometría
* [Temperatura del módulo lineal LM317](https://youtube.com/shorts/fBBQKPr8xtA)
* [Temperatura del módulo conmutado LM2596](https://youtube.com/shorts/6KLcBZMcJUU)

---

## 🚀 Fases del Estudio

1. **Evaluación y selección:** análisis de 5 módulos lineales y 5 conmutados a partir de sus hojas de datos y precios. Se seleccionaron el **LM317** y el **LM2596**.
2. **Simulación:** verificación en OrCAD PSpice de eficiencia, rizado, barrido de temperatura y barrido de carga ($R_L$ de 4 a 50 Ω).
3. **Implementación de laboratorio:** medición de potencias, eficiencia, rizado y temperatura a 12 VDC y 1 A.
4. **Análisis comparativo:** contraste entre simulación y laboratorio, y matriz tamaño/costo/beneficio.

## 🛠️ Herramientas Utilizadas

* **Simulación:** OrCAD PSpice.
* **Documento:** LaTeX (plantilla IEEEtran) en Overleaf.
* **Instrumentación:** multímetro Fluke, osciloscopio GW Instek GDS-2062, termómetro infrarrojo Berrcom JXB-178, transformador reductor y carga resistiva de 5 Ω.
