# Fase de Prototipado y Biblioteca de Control Clásico

Esta carpeta contiene los cuadernos Jupyter que actúan como bibliotecas de software y prototipos para la implementación de herramientas personalizadas de control clásico en Python. Estas utilidades simplifican el análisis frecuencial, el dibujo del Lugar Geométrico de las Raíces (LGR) y las simulaciones temporales sin depender exclusivamente de software privativo.

## Contenido de la Carpeta

*   **[lib_basicaControlClasico.ipynb](lib_basicaControlClasico.ipynb)**: Prototipo inicial de funciones de análisis. Contiene scripts básicos de simulación temporal y formateo de gráficas con `matplotlib`.
*   **[lib_coreControlClasico.ipynb](lib_coreControlClasico.ipynb)**: Biblioteca core consolidada y avanzada. Implementa funciones unificadas y parametrizables de visualización de sistemas lineales e invariantes en el tiempo (LTI):
    *   Cálculo y graficado personalizado del Lugar Geométrico de las Raíces (LGR) con interpolación de ganancia.
    *   Trazado interactivo de Diagramas de Bode de lazo abierto, indicando los márgenes de fase ($P_m$) y ganancia ($G_m$).
    *   Algoritmos de verificación numérica de especificaciones del lazo cerrado: cálculo automático de factor de amortiguamiento $\zeta$, frecuencia natural $\omega_n$, tiempo de establecimiento $t_s$ y error estático de rampa $K_v$.

---

## Funciones Core Destacadas

Las herramientas desarrolladas en esta etapa fueron esenciales para agilizar el diseño de los compensadores finales:

1.  **Cálculo Automático del LGR normalizado:**
    Permite trazar la trayectoria de las raíces de la ecuación característica $1 + k G(s) = 0$ barriendo un vector de ganancias discreto `k_vals`.
    
2.  **Verificación de Especificaciones Temporales:**
    Rutina que aísla los polos dominantes en lazo cerrado de un sistema de orden superior para calcular sus parámetros equivalentes ($\zeta, \omega_n$) y comparar la aproximación dominante frente a la respuesta real.

3.  **Simulaciones Especiales:**
    Ajustes finos para la simulación numérica de entradas tipo rampa e impulso continuo a partir de la aproximación de respuesta a lazo cerrado con `scipy.signal.lsim` y `scipy.signal.step`.
