# Fase de Investigación y Modelado de Sistemas Dinámicos

Esta carpeta contiene los cuadernos Jupyter dedicados a la investigación teórica, modelado dinámico y análisis en frecuencia que sirvieron como fundamentos conceptuales para encarar el Trabajo Práctico Integrador.

## Contenido de la Carpeta

*   **[intro1_Modelado_S1erOrden.ipynb](intro1_Modelado_S1erOrden.ipynb)**: Cuaderno introductorio centrado en la respuesta temporal de sistemas de primer orden (parámetros de constante de tiempo $\tau$, ganancia estática $K$, tiempo de establecimiento y de subida).
*   **[intro2_Modelado_S2doOrden.ipynb](intro2_Modelado_S2doOrden.ipynb)**: Análisis exhaustivo del comportamiento dinámico de sistemas de segundo orden. Cubre las respuestas transitorias subamortiguada, críticamente amortiguada y sobreamortiguada frente a escalones, y la influencia del factor de amortiguamiento $\zeta$ y frecuencia natural $\omega_n$.
*   **[intro3_FT_convolucion_compensadores.ipynb](intro3_FT_convolucion_compensadores.ipynb)**: Estudio avanzado de la función de transferencia y del análisis temporal. Implementa la simulación de sistemas lineales mediante convolución temporal en Python y aborda la teoría en frecuencia y respuesta en régimen permanente de los compensadores clásicos de adelanto y atraso de fase.

---

## Conceptos Teóricos Clave Abordados

1.  **Respuesta al Escalón de Primer Orden:**
    $$ y(t) = K(1 - e^{-t/\tau}) $$
    Permite comprender la velocidad de carga de un actuador simple y la obtención práctica de la constante de tiempo.

2.  **Dinámica de Segundo Orden Subamortiguado ($\zeta < 1$):**
    $$ y(t) = 1 - \frac{e^{-\zeta\omega_n t}}{\sqrt{1-\zeta^2}} \sin(\omega_d t + \theta) $$
    Sirve como base para el diseño del compensador, ya que define la relación matemática exacta entre la ubicación de los polos conjugados complejos deseados $s_d$ y el sobrepico / velocidad de asentamiento requeridos por la cátedra.

3.  **Simulación de Sistemas LTI mediante Convolución:**
    Verificación temporal discreta:
    $$ y(t) = \int_0^t u(\tau) g(t - \tau) d\tau \implies y[n] = \sum_{k=0}^n u[k] g[n-k] \Delta t $$
    donde $g(t)$ es la respuesta al impulso del sistema. Esta aproximación numérica ratifica los resultados teóricos obtenidos analíticamente.
