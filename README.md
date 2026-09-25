# ⚡ Análisis Comparativo de Fuentes de Alimentación: Lineal vs. Conmutada

<div align="center">
  <b>Trabajo Final de Electrónica Industrial 2026-II</b><br>
  Universidad Industrial de Santander (UIS)<br>
  Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones (E3T)
</div>

---

## 👥 Integrantes del Proyecto

* **[Tu Nombre Completo]** - Código: [Tu Código] - Correo: [tu.correo@correo.uis.edu.co]
* **[Nombre de tu Compañero]** - Código: [Código de tu compañero] - Correo: [correo.companero@correo.uis.edu.co]

**Dirigido a:** Prof. [Nombre del Profesor] - `jbarrero@e3t.uis.edu.co`

---

## 📝 Descripción del Proyecto

Este repositorio contiene toda la documentación técnica, manuales de fabricante (*datasheets*), resultados de simulación y esquemáticos respaldando el **Trabajo Final de Electrónica Industrial**.

El objetivo central es implementar, simular y probar en laboratorio dos módulos reguladores de tensión (uno de topología lineal y otro de topología conmutada reductora o *Buck*) para realizar un análisis comparativo riguroso de su rendimiento. Esto sirve como material de apoyo directo para el documento principal del proyecto, titulado *"Comparative Analysis of Linear and Switching Power Regulators"*.

### 🎯 Requerimientos Técnicos

Ambos módulos han sido sometidos a pruebas bajo las siguientes restricciones operativas estandarizadas:
* **Tensión de Entrada ($V_{IN}$):** Variable entre 8 y 12 VDC con una frecuencia de rizado de 120 Hz.
* **Tensión de Salida ($V_{OUT}$):** 5 VDC estrictos.
* **Corriente de Carga Máxima ($I_{OUT}$):** 1 A.
* **Rizado de Salida (Ripple):** $< 50$ mV.

## 🗂️ Estructura del Repositorio

Para evitar la saturación del informe escrito (formato IEEE), la información técnica de soporte se ha organizado en los siguientes directorios:

* 📁 `/datasheets/`: Contiene las hojas de datos originales de los 10 módulos evaluados durante la fase de selección.
  * `/lineales/`: LM317, 7805, L78S05, AMS1117-5.0, LM338.
  * `/conmutados/`: LM2596, LM2576, XL4015, MP1584, Mini-360.
* 📁 `/simulaciones/`: Archivos de simulación y análisis de tolerancias (Monte Carlo) desarrollados en OrCAD y LTspice.
* 📁 `/esquematicos/`: Diagramas de circuito en alta resolución de los módulos seleccionados (LM317 y LM2596).
* 📁 `/laboratorio/`: Capturas de oscilogramas, tablas de datos térmicos y fotografías del montaje físico.
* 📁 `/latex/`: Código fuente del documento final estructurado bajo la plantilla de conferencias de IEEE.

## 🚀 Fases del Estudio

El desarrollo de este proyecto y su correspondiente informe se divide en las siguientes etapas clave:

1. **Evaluación y Selección Tecnológica:** Análisis teórico de 5 módulos lineales y 5 conmutados para justificar la elección óptima para los requerimientos de 5W (5V, 1A). Los seleccionados fueron el **LM317** y el **LM2596**.
2. **Diseño y Simulación:** Verificación de las condiciones de entrada a 120 Hz, comprobación teórica de eficiencia y rizado utilizando OrCAD y LTspice.
3. **Análisis de Monte Carlo y Ajuste:** Evaluación del impacto del 10% de tolerancia en componentes pasivos y la variación de los activos. Procedimiento matemático para ajustar los *trimmers* de calibración.
4. **Implementación de Laboratorio:** Pruebas físicas midiendo rizado real, caída de tensión y temperatura de los disipadores a plena carga (1 A).
5. **Análisis Comparativo (Costo/Beneficio):** Cruce final de datos reales vs. teóricos para determinar qué módulo presenta la mejor relación de Tamaño, Costo y Rendimiento (Beneficio).

## 🛠️ Herramientas Utilizadas

* **Simulación Electrónica:** OrCAD y LTspice.
* **Edición de Documentos:** LaTeX (Plantilla IEEEtran).
* **Instrumentación:** Osciloscopio digital, multímetros de precisión, fuentes DC de laboratorio, cargas electrónicas/resistivas.
