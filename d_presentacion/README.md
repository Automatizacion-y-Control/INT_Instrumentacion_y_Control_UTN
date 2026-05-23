# Fase de Presentación y Diseños del Trabajo Práctico Integrador

Esta carpeta contiene los cuadernos Jupyter dedicados al diseño individual, análisis y simulación comparativa de los tres compensadores propuestos para resolver las especificaciones de la consigna. También contiene los informes consolidados de la entrega formal.

## Contenido de la Carpeta

*   **[TP_Integrador.ipynb](TP_Integrador.ipynb)**: Cuaderno preliminar unificado de simulación y cálculo de la entrega académica.
*   **[TP_Integrador_Vera.pdf](TP_Integrador_Vera.pdf)**: Reporte formal compilado en PDF para la presentación y defensa del trabajo práctico.
*   **[TP_analisis_planta_control.ipynb](TP_analisis_planta_control.ipynb)**: Cuaderno dedicado al estudio dinámico de la planta sin compensar, analizando sus polos en $0, -25, -35$ y su cero en $-40$, con su respuesta natural al escalón y velocidad transitoria.
*   **[TP_compensacion_planta_control.ipynb](TP_compensacion_planta_control.ipynb)**: Cuaderno de simulación e integración preliminar de los lazos compensados.
*   **[TP_compensadorAdelanto.ipynb](TP_compensadorAdelanto.ipynb)**: Cuaderno específico para el diseño analítico y numérico del **C1 Compensador Adelanto (lead), de primer orden**.
*   **[TP_compensadorAdelanto-Atraso.ipynb](TP_compensadorAdelanto-Atraso.ipynb)**: Cuaderno específico para el diseño de la cancelación polo-cero y etapas de adelanto y atraso en baja frecuencia del **C2 Compensador Adelanto-Atraso (lead-lag), de segundo orden**.
*   **[TP_compensadorAsignacionPolos.ipynb](TP_compensadorAsignacionPolos.ipynb)**: Cuaderno dedicado al diseño del **C3 Compensador por asignación de polos, de segundo orden** (polos complejos conjugados).
*   **[TP_informe_compensadorAsignacionPolos.ipynb](TP_informe_compensadorAsignacionPolos.ipynb)**: Informe técnico y discusión complementaria enfocados exclusivamente en la justificación matemática y viabilidad de C3 en comparación con los esquemas clásicos.

---

## Nomenclatura Oficial del Trabajo Práctico

Los compensadores han sido clasificados y estandarizados bajo el siguiente esquema:

1.  **C1 = C1 Compensador Adelanto (lead), de primer orden**
    $$ G_{c1}(s) = K_{c1} \frac{s + a_1}{s + b_1} = 337.94 \frac{s + 0.93}{s + 4.79} $$
    *   *Limitación:* Introduce un polo lento en lazo cerrado ($s \approx -0.74$) que ralentiza el transitorio real de la salida.

2.  **C2 = C2 Compensador Adelanto-Atraso (lead-lag), de segundo orden**
    $$ G_{c2}(s) = K_c \frac{s+z_1}{s+p_1} \frac{s+z_2}{s+p_2} = 428.01 \frac{(s+25)(s+0.05)}{(s+29.69)(s+0.276)} $$
    *   *Ventaja:* Cancela el polo lento en $-25$ de la planta dinámica mediante el cero del adelanto. Cumple con $K_v \approx 2.98 \text{ rad/s}$.

3.  **C3 = C3 Compensador por asignación de polos, de segundo orden**
    $$ G_{c3}(s) = \frac{37.96 s^2 + 2277.87 s + 33218.99}{s^2 + 30.12 s + 506.19} $$
    *   *Análisis:* Tiene polos complejos conjugados en $-15.06 \pm j 16.71$. Ofrece una respuesta transitoria ideal y reduce drásticamente el pico de esfuerzo de control inicial ($u(0^+) \approx 38$ frente a $428$ de C2), pero viola la topología estándar clásica por lo que se presenta como anexo.
