# Diseño electrónico — RC Car ESP32

Diseño completo en **KiCad 10.0** del vehículo RC de combate con seguimiento de línea basado en ESP32.

## Contenido

| Archivo | Descripción |
|---|---|
| `ProyectoFinalCarrito2.kicad_pro` | Proyecto KiCad (abrir este archivo) |
| `ProyectoFinalCarrito2.kicad_sch` | Esquemático |
| `ProyectoFinalCarrito2.kicad_pcb` | Placa de circuito impreso (2 capas, 80 × 130 mm) |
| `ProyectoFinalCarrito2.csv` | Lista de materiales (BOM) |
| `ProyectoFinalCarrito2-schematic.pdf` | Esquemático exportado a PDF |
| `fabrication-toolkit-options.json` | Configuración del plugin Fabrication Toolkit |
| `docs/esp32_devkitC_v4_pinlayout.png` | Pinout de referencia del ESP32 DevKitC V4 |

## Bloques del diseño

- **Control lógico / ESP32:** ESP32-DevKitC V4 y etapa de acoplamiento con transistores MMBT3904.
- **Seguidor de línea:** 2 sensores ópticos CNY70.
- **Puentes H:** 4 etapas independientes con IRF3205 / IRF9540N y aislamiento por PC817.
- **Funciones de batalla:** 3 servos, luces direccionales e intermitentes y bocina con TDA2003.
- **Alimentación:** LM7805, LM317 y rieles de +15 V, +7.5 V, +5 V y +3.3 V.

## Notas

- Los archivos conservan el nombre original del proyecto para mantener las referencias internas de KiCad.
- `ProyectoFinalCarrito2.kicad_prl` y `fp-info-cache` son archivos locales de KiCad y están excluidos del repositorio mediante `.gitignore`.
- Las copias de seguridad automáticas (`*-backups/`) se conservan localmente, pero no se versionan.
- Antes de fabricar, ejecuta **ERC** y **DRC** en KiCad y genera los Gerbers con Fabrication Toolkit.

## Cómo abrir

1. Abre KiCad 10.0 o superior.
2. Selecciona `ProyectoFinalCarrito2.kicad_pro`.
3. Revisa el esquemático y la PCB desde el administrador de proyectos.
