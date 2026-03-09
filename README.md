# Sistema de Visualización LED Dinámica (VLD) - Versión "Saludo"

El **VLD (Saludo)** es una experiencia visual inmersiva diseñada para pantallas de gran formato (**8096 × 2560 px**). Combina videografía dinámica, diseño de interfaz "Glassmorphism" y lógica ambiental reactiva para ofrecer infoentretenimiento estético en espacios públicos.

---

## 🚀 Características Principales

*   **Fondos de Video Dinámicos**: Sistema inteligente que cambia el background de video (`.mp4` / `.mov`) según las condiciones climáticas reales (Soleado, Nublado, Lluvia, Tormenta, etc.), creando una atmósfera envolvente.
*   **Ciclo Día/Noche & Luz Ambiental**: Algoritmo que ajusta el brillo, contraste y opacidad de toda la interfaz basándose en las horas astronómicas de amanecer y atardecer, garantizando una visualización óptima en cualquier momento.
*   **Interfaz Glassmorphism**: Paneles flotantes con efectos de *backdrop-filter blur*, bordes translúcidos y sombras suaves que se integran elegantemente sobre el video de fondo.
*   **Resiliencia Meteorológica**: Integración robusta con OpenWeatherMap, manteniendo la integridad visual incluso si fallan las actualizaciones de datos.
*   **Saludo Inteligente**: Mensajes de bienvenida ("¡Buenos días!", "¡Buenas tardes!", "¡Buenas noches!") sincronizados con el ciclo diario.

## 🛠️ Stack Tecnológico

*   **Estructura**: HTML5 optimizado para renderizado en resoluciones ultra-wide.
*   **Estilos**: CSS3 Avanzado (Flexbox, CSS Variables para luz ambiental, Glass effects).
*   **Lógica**: JavaScript ES6+ (Fetch API, Async/Await, Timers de actualización).
*   **Fuentes**: 
    *   **Montserrat**: Pesos Black (900), SemiBold (600) y Regular (400) para jerarquía visual clara.
    *   **Inter**: Utilizada como fallback del sistema.
*   **Iconos**: Font Awesome 6 (Integración dinámica por código de clima).

## ⚙️ Configuración

Las variables clave se encuentran al inicio del bloque `<script>` en `index3.html`:

```javascript
// API OpenWeather (Reemplazar con key propia para producción)
const apiKey = "TU_API_KEY"; 
const lat = 21;      // Latitud
const lon = -99.9167; // Longitud

// Mapeo de Videos (Carpeta /videos)
const weatherVideos = {
    "01": "sunny",
    "02": "partly_cloudy",
    // ... otros códigos
    "default": "bloque_welcome"
};
```

## 📐 Arquitectura de Pantalla

La interfaz utiliza un diseño flexible (`flex: 1` para ambos paneles) con márgenes generosos para centrar el contenido en pantallas ultra-panorámicas:

1.  **Panel Izquierdo (Info Principal)**:
    *   Logo Institucional (BLOQUE).
    *   Saludo gigante y Fecha completa.
2.  **Panel Derecho (Datos Clave)**:
    *   Hora en formato 24h gran escala.
    *   Temperatura actual y Ubicación.
3.  **Elementos Flotantes**:
    *   Detalles de Clima y Humedad posicionados absolutamente para equilibrio visual.
    *   URL del sitio web institucional.

---
© 2026 - Sistema VLD Bloque.
