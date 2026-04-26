# 🦵 Planificador CPAK

Planifica la alineacion coronal en protesis total de rodilla. Introduce las medidas radiologicas y obtén la clasificacion CPAK con el fenotipo del paciente.

![HTML5](https://img.shields.io/badge/HTML5-single--file-E34F26?logo=html5&logoColor=white)
![Fenotipos](https://img.shields.io/badge/fenotipos-9-1a3a5c)
![Sin dependencias](https://img.shields.io/badge/dependencias-ninguna-grey)

---

## Acceso

> Acceso protegido — requiere autenticacion previa desde el [portal principal](https://jmacot.github.io/).

[Abrir la aplicacion](https://jmacot.github.io/CPAK/)

No requiere instalacion. Funciona en cualquier navegador, incluyendo movil y tablet.

---

## Que es el CPAK?

El sistema **CPAK** es una clasificacion de la alineacion constitucional de la rodilla basada en MacDessi et al. (2021). Define **9 fenotipos** segun dos parametros:

| Parametro | Descripcion |
|-----------|-------------|
| **aHKA** | Arithmetic Hip-Knee-Ankle angle — estima la alineacion constitucional pre-artrosica |
| **JLO** | Joint Line Obliquity — orientacion de la interlinea articular |
| **JLCA** | Joint Line Convergence Angle — estimacion del desgaste articular adquirido |

Esta clasificacion permite **individualizar el objetivo de alineacion** en la artroplastia total de rodilla.

---

## Funcionalidades

- **Calculo automatico** de aHKA y JLO a partir de LDFA y MPTA
- **Clasificacion en 9 fenotipos CPAK** con descripcion clinica
- **Clasificacion de normalidad de Hirschmann (2024)** sobre angulos constitucionales
- **Matriz visual 3x3** con el fenotipo del paciente resaltado y representacion SVG de piernas
- **Indicador de desgaste articular** con D3.js: calcula JLCA a partir del mHKA, con gradiente de severidad
- **Barras de prevalencia**: porcentaje de cada fenotipo en poblacion sana vs artrosica
- **Panel de evidencia clinica** con referencias y recomendaciones
- **Informacion clinica detallada**: estrategia quirurgica, diferencias por sexo, riesgo
- **Formulas matematicas** visibles para verificacion
- **Modo oscuro** con sky toggle CSS puro y deteccion automatica
- **Accesibilidad**: skip link, focus-visible, reduced-motion, aria-labels
- **Responsive**: adaptado para uso en escritorio, tablet y movil

---

## Parametros de entrada

| Parametro | Descripcion | Requerido |
|-----------|-------------|-----------|
| **LDFA** | Lateral Distal Femoral Angle | Si |
| **MPTA** | Medial Proximal Tibial Angle | Si |
| **mHKA** | Mechanical Hip-Knee-Ankle angle | Opcional (para JLCA) |

---

## Los 9 fenotipos CPAK

|  | Apex Distal (JLO < 177°) | Neutral (177-183°) | Apex Proximal (JLO > 183°) |
|--|---------------------------|---------------------|----------------------------|
| **Varo (aHKA < -2°)** | Tipo I | Tipo II | Tipo III |
| **Neutro (-2° a 2°)** | Tipo IV | Tipo V | Tipo VI |
| **Valgo (aHKA > 2°)** | Tipo VII | Tipo VIII | Tipo IX |

---

## Como usar

1. Introduce los valores radiologicos de **LDFA** y **MPTA**
2. La herramienta calcula automaticamente el fenotipo CPAK
3. Consulta la **matriz visual** y la **descripcion clinica**
4. Opcionalmente, introduce el **mHKA** para analizar el desgaste articular (JLCA)
5. Revisa la **estrategia quirurgica** recomendada para el fenotipo

---

## Estructura del proyecto

```
CPAK/
├── index.html    ← aplicacion completa (archivo unico)
├── icon.svg      ← icono de la app
├── LICENSE       ← All Rights Reserved
└── README.md     ← este archivo
```

---

## Tecnologia

- **HTML5 + CSS3 + JavaScript vanilla** en archivo unico (Sistema B "Radiologia Glass")
- Tipografias: Source Serif 4 + Source Sans 3 + Source Code Pro (Google Fonts)
- **D3.js v7** para el indicador de desgaste articular (cargado por CDN con fallback)
- Visualizaciones SVG generadas dinamicamente
- Glassmorphism con `backdrop-filter` y mesh gradient animado de fondo
- Sin frameworks, sin build tools, sin backend
- Compatible con Chrome, Firefox, Safari, Edge

---

## Referencias

- MacDessi SJ et al. *Coronal Plane Alignment of the Knee (CPAK) classification*. Bone Joint J. 2021.
- Hirschmann MT et al. *Functional knee phenotypes*. Knee Surg Sports Traumatol Arthrosc. 2019.
- Hirschmann MT et al. *Phenotype-specific normality of the constitutional knee alignment*. KSSTA 2024.

---

## Licencia

All Rights Reserved — Uso interno hospitalario.
