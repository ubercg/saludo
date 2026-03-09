# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**VLD (Saludo)** — a full-screen LED display system (target resolution: 7680x2560 px) for public spaces. It shows a greeting, clock, date, and live weather data over dynamic video backgrounds. Everything is built as standalone HTML files with inline CSS and JavaScript (no build tools, no framework, no bundler).

## Project Structure

```
saludo/
├── index.html              # Primera versión del display principal
├── index2.html             # Segunda iteración con mejoras
├── index3.html             # Versión actual más completa (PRINCIPAL)
├── lobby-p1-v1.html        # Layout alternativo para lobby (variante 1)
├── lobby-p2-v1.html        # Layout alternativo para lobby (variante 2)
├── README.md               # Documentación del proyecto
├── LICENSE                 # Licencia del proyecto
├── .gitignore              # Archivos excluidos del repositorio
│
├── videos/                 # Videos de fondo dinámicos (~39MB total)
│   ├── bloque_welcome.mp4  # Video por defecto/bienvenida
│   ├── sunny.mp4           # Cielo despejado (01)
│   ├── partly_cloudy.mp4   # Pocas nubes (02)
│   ├── cloudy.mp4          # Nubes dispersas (03)
│   ├── overcast.mp4        # Nubes rotas (04)
│   ├── rain-light.mp4      # Lluvia ligera (09)
│   ├── rain.mp4            # Lluvia (10)
│   ├── lluvioso.mp4        # Variante de lluvia
│   ├── thunderstorm.mp4    # Tormenta (11)
│   ├── tormenta.mp4        # Variante de tormenta
│   └── mist.mp4            # Niebla (50)
│
├── recursos/               # Recursos estáticos
│   ├── background/         # Imágenes de fondo alternativas
│   └── iconos/             # Iconografía del proyecto (~13 archivos)
│
└── documentacion/          # Prototipos y archivos de desarrollo
    ├── pantalla.html       # Prototipo inicial
    ├── screenvideoclock.html     # Prueba de video + reloj
    ├── screenclima.html          # Prueba de integración clima
    └── screenclima_fake.html     # Prueba con datos simulados
```

### Archivos Principales

- **index3.html**: Versión más reciente y completa. Incluye:
  - Sistema de video dinámico según clima
  - Algoritmo de luz ambiental día/noche
  - Glassmorphism UI con paneles translúcidos
  - Integración completa con OpenWeatherMap API

- **lobby-p1-v1.html / lobby-p2-v1.html**: Variantes de diseño para pantallas de lobby con layouts diferentes

- **videos/**: Mapeo de condiciones climáticas (códigos OpenWeatherMap) a archivos de video específicos

## Architecture

- Each HTML file is a **self-contained** single-page application (HTML + inline `<style>` + inline `<script>`). There is no shared CSS or JS — styles and logic are duplicated per file.
- **index.html / index2.html / index3.html**: Progressive iterations of the main display. `index3.html` is the latest/most complete version.
- **lobby-p1-v1.html / lobby-p2-v1.html**: Alternate layouts for lobby screens.
- **videos/**: `.mp4` background videos mapped to weather conditions (sunny, cloudy, rain, thunderstorm, etc.).
- **recursos/**: Static assets (background images, icons).
- **documentacion/**: Design specs, prototypes, and requirements docs (git-ignored).

## Key Technical Details

- Weather data comes from **OpenWeatherMap API**. The API key and coordinates (lat/lon) are configured as constants at the top of each file's `<script>` block.
- Video backgrounds switch dynamically based on the weather icon code returned by the API.
- A day/night ambient light algorithm adjusts brightness, contrast, and opacity based on astronomical sunrise/sunset times.
- Fonts: **Montserrat** (900/600/400) and **Inter** (700) loaded from Google Fonts. Icons via **Font Awesome 6** from CDN.
- The UI uses a Glassmorphism style (backdrop-filter blur, translucent panels).

## Development

No build step. Open any HTML file directly in a browser. For the best preview, use a browser window sized to the target resolution or use DevTools device emulation.

## Language

All user-facing text is in **Spanish**. Code comments are mostly in Spanish.
