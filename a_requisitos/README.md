# Requisitos y Especificaciones del Trabajo Práctico Integrador

Esta carpeta contiene la documentación de base, especificaciones técnicas y consignas del Trabajo Práctico Integrador para regularizar la asignatura **Instrumentación y Control de Procesos** (Lic. en Automatización y Control, UTN FRC).

## Contenido de la Carpeta

*   **[trabajoIntegrador.md](trabajoIntegrador.md)**: Consigna textual detallada provista por la cátedra.
*   **`assets/planta.png`**: Imagen de la función de transferencia y del diagrama de bloques de la planta a compensar.

---

## Resumen de Especificaciones de Diseño

La planta dada está descrita por la función de transferencia:
$$ G_p(s) = \frac{s + 40}{s^3 + 60s^2 + 875s} = \frac{s + 40}{s(s + 25)(s + 35)} $$

El objetivo es diseñar un lazo de control con realimentación unitaria negativa que cumpla con los siguientes requerimientos dinámicos y estacionarios:

| Parámetro | Símbolo | Valor Requerido | Descripción |
| :--- | :---: | :---: | :--- |
| **Coeficiente de Amortiguamiento** | $\zeta$ | $0.628$ | Define el sobrepico máximo ante escalón ($\approx 8.1\%$). |
| **Frecuencia Natural Amortiguada** | $\omega_n$ | $21.324 \text{ rad/s}$ | Controla la velocidad de respuesta del transitorio. |
| **Constante de Error de Velocidad** | $K_v$ | $3 \text{ rad/s}$ | Define la precisión ante entrada rampa (error estacionario $e_{ss} = 1/3$). |

### Ubicación del Punto de Diseño Deseado ($s_d$):
A partir de los requerimientos dinámicos ($\zeta$ y $\omega_n$), se determinan los polos dominantes en lazo cerrado:
$$ s_d = -\zeta\omega_n \pm j\omega_n\sqrt{1 - \zeta^2} = -13.3915 \pm j 16.5944 $$

---


> **Modelo Estándar Obligatorio:**
> La consigna exige que las simulaciones principales utilicen los modelos estándar del compensador y la planta, lo cual condiciona el diseño de primer orden (**C1**) y adelanto-atraso (**C2**), relegando el compensador de asignación de polos (**C3**) a una sección de análisis complementario debido a sus polos complejos no estándar.
