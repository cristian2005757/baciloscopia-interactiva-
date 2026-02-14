# Baciloscopía Interactiva

Herramienta educativa interactiva para entrenamiento en lectura de baciloscopía (BAAR), diseñada para apoyar la enseñanza de Bacteriología mediante práctica guiada, métricas y reporte del desempeño.

## Contexto

Este proyecto fue desarrollado como herramienta didáctica para un profesor/curso de Bacteriología, con el fin de que estudiantes practiquen la identificación y conteo en campos microscópicos de forma más clara y medible (aciertos, errores, precisión y reporte).

## 🔗 Demo en vivo

- **App (Vercel/Netlify):** *(sustituir por tu URL tras desplegar)*

## ¿Qué permite hacer?

- Practicar por **niveles** (6 campos microscópicos) con dificultad creciente.
- **Marcar bacilos** con clic sobre la imagen (feedback visual en canvas: verde = acierto, rojo = error).
- **Deshacer** y **Limpiar** para corregir marcaciones.
- Ver métricas en tiempo real:
  - Bacilos encontrados
  - Bacilos reales del campo
  - Clics erróneos
  - Precisión
- Generar un **reporte** del nivel (conteo, diferencia, clasificación según escala internacional).
- **Exportar resultados**: Copiar JSON al portapapeles o descargar `reporte_bacilos.json`.
- **Detector de coordenadas** (herramienta auxiliar en `/src/tools/detector.html`) para obtener coordenadas de nuevos campos.

## Arquitectura

**Frontend (Vite) → Lógica JS (coordenadas/métricas/canvas) → Reporte (UI + export JSON)**

> No requiere backend. Todo corre del lado del cliente.

## Estructura del proyecto

```
/
├── index.html              # App principal
├── public/
│   └── assets/             # Imágenes de los campos (imagen1.jpeg, imagen2.jpeg, ...)
├── src/tools/
│   └── detector.html       # Herramienta para extraer coordenadas de bacilos
└── package.json
```

> Las imágenes deben estar en `public/assets/` para que se sirvan en `/assets/`.

## Instalación local

### Requisitos

- Node.js 18+ recomendado

### Ejecutar

```bash
npm install
npm run dev
```

Se abrirá un servidor de desarrollo (por defecto en `http://localhost:5173`).

### Otros scripts

- `npm run build` — Genera la build de producción en `dist/`
- `npm run preview` — Previsualiza la build generada
