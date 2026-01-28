# Sistema de Visualización LED Dinámica (VLD)

El **Sistema de Visualización LED Dinámica (VLD)** es una aplicación web de alto rendimiento diseñada específicamente para paneles LED de gran formato con una resolución de **8096 × 2560 px**. La aplicación proporciona información en tiempo real sobre el clima, la hora y ofrece saludos contextuales basados en el momento del día.

---

## 🚀 Características Principales

*   **Resolución Ultra-High**: Optimizado para pantallas de 8K+ mediante el uso estratégico de Flexbox y unidades de medida proporcionales.
*   **Saludos Contextuales**: Lógica inteligente que cambia el mensaje de bienvenida ("¡Buenos días!", "¡Buenas tardes!", "¡Buenas noches!") según la hora del sistema.
*   **Meteorología en Tiempo Real**: Integración con la API de OpenWeather para mostrar temperatura, humedad y estado del cielo con iconos vectoriales dinámicos.
*   **Resiliencia de Datos**: El sistema está diseñado para mantener la última información válida en pantalla incluso si hay fallas de conectividad con la API, evitando errores visuales (RNF-5).
*   **Diseño de Alto Impacto**: Fondo negro puro (`#000000`) para optimizar el consumo de energía en paneles LED y maximizar el contraste de luminancia.

## 🛠️ Stack Tecnológico

*   **Estructura**: HTML5 Semántico.
*   **Estilos**: CSS3 (Modelado de Flexbox 70/30).
*   **Lógica**: JavaScript Vanilla (ES6+) con orquestación asíncrona (`async/await`).
*   **Fuentes**: [Inter](https://fonts.google.com/specimen/Inter) para máxima legibilidad a larga distancia.
*   **Iconos**: Font Awesome 6 (Mapeo semántico dinámico).

## ⚙️ Configuración

Para configurar el sistema, edita las constantes en el bloque `<script>` de `index.html`:

```javascript
const apiKey = ""; // Tu OpenWeather API Key
const lat = ;       // Latitud geográfica
const lon = ;  // Longitud geográfica
```

> [!TIP]
> El intervalo de actualización del clima está configurado a 10 minutos (600,000ms) para cumplir con los límites de cuota de la API y asegurar la frescura de los datos.

## 📐 Arquitectura de Pantalla

La interfaz cumple con una división estricta de paneles:
1.  **Zona de Impacto (Izquierda - 70%)**: Saludo masivo, fecha extendida en español, ubicación y hora en formato 24h.
2.  **Zona de Detalle (Derecha - 30%)**: Desglose técnico de condiciones meteorológicas.

---
© 2026 - Sistema VLD para Paneles de Gran Formato.
