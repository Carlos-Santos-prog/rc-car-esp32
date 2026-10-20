# RC Car ESP32 🏎️

**Vehículo RC de combate con seguimiento de línea, controlado por ESP32.**

Proyecto final del **Laboratorio de Electrónica II** del Instituto Tecnológico de las Américas (ITLA). Este repositorio reúne el diseño electrónico completo —esquemático, PCB, BOM y documentación— y servirá también como base para el firmware del vehículo.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![KiCad](https://img.shields.io/badge/KiCad-10.0-blue.svg)](https://www.kicad.org/)

---

## 📋 Descripción

El carrito combina dos modos de operación:

- **Seguidor de línea:** dos sensores ópticos CNY70 detectan el trazado y el ESP32 corrige la trayectoria en tiempo real.
- **Funciones de batalla:** servos para barrera y pala, luces direccionales intermitentes y bocina, pensados para competencias entre vehículos.

La etapa de potencia maneja **cuatro motores DC de forma independiente** mediante cuatro puentes H con MOSFETs, aislados por optoacopladores para proteger la lógica del ESP32.

## ✨ Características

- Control central con **ESP32 DevKitC V4**.
- **4 puentes H** independientes (IRF3205 + IRF9540N) para tracción 4WD.
- Aislamiento de señal de los puentes H con **optoacopladores PC817**.
- **2 sensores de línea CNY70** para seguimiento de pista.
- **3 servos** (barrera, pala y dirección auxiliar).
- **Luces direccionales** izquierda/derecha e intermitentes.
- **Bocina** con amplificador de audio **TDA2003**.
- Fuentes reguladas para lógica y servos: **LM7805**, **LM317** y rieles de +15 V, +7.5 V, +5 V y +3.3 V.
- PCB de **2 capas**, **80 × 130 mm**, con conectores JST EH para periféricos.

## 🧩 Arquitectura de hardware

| Bloque | Componentes principales |
|---|---|
| Control lógico | ESP32-DevKitC, MMBT3904, resistencias de pull-up |
| Seguidor de línea | 2 × CNY70 |
| Puentes H | 4 × IRF3205 (N), 4 × IRF9540N (P), 6 × PC817 |
| Servos | 3 × conectores JST EH de 3 pines |
| Luces | LED direccionales e intermitentes |
| Audio | TDA2003 + parlante (conector BOCINA) |
| Alimentación | LM7805, LM317, LM317 ajustable, capacitores de filtrado |
| Conectores | Batería principal, batería auxiliar, 4 motores, 3 servos, bocina, LEDs |

## 📁 Estructura del repositorio

```text
.
├── electronic_design_kicad/          # Diseño electrónico (KiCad 10)
│   ├── ProyectoFinalCarrito2.kicad_pro
│   ├── ProyectoFinalCarrito2.kicad_sch
│   ├── ProyectoFinalCarrito2.kicad_pcb
│   ├── ProyectoFinalCarrito2.csv     # Lista de materiales (BOM)
│   ├── ProyectoFinalCarrito2-schematic.pdf
│   ├── fabrication-toolkit-options.json
│   ├── docs/
│   │   └── esp32_devkitC_v4_pinlayout.png
│   └── README.md
├── .gitignore
├── .gitattributes
├── LICENSE
└── README.md
```

## 🚀 Cómo abrir el proyecto

1. Instala **KiCad 10.0** o superior.
2. Abre `electronic_design_kicad/ProyectoFinalCarrito2.kicad_pro`.
3. Desde KiCad puedes revisar:
   - **Esquemático** → `ProyectoFinalCarrito2.kicad_sch`
   - **PCB** → `ProyectoFinalCarrito2.kicad_pcb`
   - **ERC/DRC** para validar el diseño antes de fabricar.

> Los archivos conservan el nombre original del proyecto (`ProyectoFinalCarrito2`) para no romper las referencias internas entre hoja, placa y proyecto en KiCad.

## 🏭 Fabricación

- La **BOM** está en `electronic_design_kicad/ProyectoFinalCarrito2.csv`.
- El **esquemático en PDF** está en `electronic_design_kicad/ProyectoFinalCarrito2-schematic.pdf`.
- Los Gerbers se pueden generar con el plugin **Fabrication Toolkit** usando la configuración incluida (`fabrication-toolkit-options.json`).

## 🗺️ Roadmap

- [x] Diseño electrónico (esquemático + PCB)
- [ ] Firmware del ESP32 (control de motores, sensores y servos)
- [ ] Validación del prototipo y ajuste de PID del seguidor de línea
- [ ] Diseño de carcasa / estructura 3D
- [ ] Documentación de montaje y pruebas

## 📄 Licencia

Este proyecto se distribuye bajo la licencia **MIT**. Consulta [LICENSE](LICENSE) para más detalles.

## 👤 Autor

**Carlos Alexander Arias Santos**
Instituto Tecnológico de las Américas (ITLA) — Laboratorio de Electrónica II
