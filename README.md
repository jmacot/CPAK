# 🦵 Planificador CPAK

**Herramienta web interactiva para la clasificación CPAK y planificación de alineación coronal en artroplastia total de rodilla.**

---

## 🔗 Acceso directo

👉 **[https://jmacot.github.io/CPAK/](https://jmacot.github.io/CPAK/)**

No requiere instalación. Funciona directamente en el navegador, incluyendo desde el móvil o tablet.

---

## ¿Qué es el CPAK?

El sistema **CPAK** (*Coronal Plane Alignment of the Knee*) es una clasificación de la alineación constitucional de la rodilla basada en el trabajo de MacDessi et al. (2021). Define 9 fenotipos según dos parámetros:

- **aHKA** (*Arithmetic Hip-Knee-Ankle angle*): estima la alineación constitucional pre-artrósica a partir de la geometría ósea (LDFA y MPTA).
- **JLO** (*Joint Line Obliquity*): orientación de la interlínea articular.

Esta clasificación permite **individualizar el objetivo de alineación** en la artroplastia total de rodilla, abandonando el paradigma de la alineación neutra mecánica universal.

---

## ¿Qué hace esta herramienta?

- Calcula automáticamente el **aHKA** y el **JLO** a partir de LDFA y MPTA
- Clasifica al paciente en uno de los **9 fenotipos CPAK**
- Calcula el **JLCA** (*Joint Line Convergence Angle*) si se introduce el mHKA, estimando el grado de desgaste articular adquirido
- Muestra la **matriz visual de fenotipos** con el tipo del paciente resaltado
- Proporciona una descripción clínica de cada fenotipo y orientación quirúrgica
- Compatible con **iOS y Android** como aplicación web

---

## Parámetros de entrada

| Parámetro | Descripción |
|-----------|-------------|
| **LDFA** | Lateral Distal Femoral Angle |
| **MPTA** | Medial Proximal Tibial Angle |
| **mHKA** | Mechanical Hip-Knee-Ankle angle (opcional, para calcular JLCA) |

---

## Uso

1. Introduce los valores radiológicos de LDFA y MPTA
2. La herramienta calcula automáticamente el fenotipo CPAK
3. Opcionalmente, introduce el mHKA para analizar el desgaste articular (JLCA)
4. Consulta la descripción clínica y la orientación para la planificación quirúrgica

---

## Tecnología

Aplicación de archivo único (`index.html`) sin dependencias externas ni servidor. Todo el cálculo se realiza localmente en el navegador del usuario.

---

## Referencias

- MacDessi SJ et al. *Coronal Plane Alignment of the Knee (CPAK) classification*. Bone Joint J. 2021.
- Hirschmann MT et al. *Functional knee phenotypes*. Knee Surg Sports Traumatol Arthrosc. 2019.

---

## Autor

**Javier Martín** — Cirujano Ortopédico, Unidad de Rodilla
