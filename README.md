<img src="./pinguinokbron/CRISTHOPHER/imgg/R.png" alt="Proyecto" width="500">
# pinguinokbron

## 📌 Descripción del Proyecto
Este repositorio contiene el diseño, ruteo y documentación técnica para la fabricación de una placa de desarrollo **Pinguino de 32 bits**. El proyecto se basa en la filosofía de hardware libre, ofreciendo una alternativa robusta a las plataformas tradicionales de 8 bits al integrar la potencia de la arquitectura MIPS32.

El diseño está centrado en el microcontrolador **PIC32MX220F032D-I/PT**, destacando por su capacidad de comunicación USB nativa (sin requerir puentes seriales externos) y su optimización para prototipado avanzado.

## 🎯 ¿Qué se estará desarrollando en este repositorio?
El objetivo principal es documentar todo el ciclo de vida del diseño de hardware, desde la concepción del esquemático hasta la generación de los archivos de manufactura. Específicamente, este repositorio alojará:

1. **Diseño de PCB y Esquemáticos:** Archivos fuente de ruteo y diagramas esquemáticos (desarrollados en KiCad) listos para su edición o revisión.
2. **Archivos de Manufactura:** Generación de archivos Gerber y de taladrado (Drill files), aptos tanto para la fabricación industrial como para procesos de mecanizado local (como FlatCAM).
3. **Lista de Materiales (BOM):** Gestión de la lista de componentes, priorizando tecnología de montaje superficial (SMD en formato 0603) y encapsulados TQFP-44 para optimizar el área de la tarjeta.
4. **Documentación Técnica:** Justificación de diseño, cálculos de potencia y guías de ensamblaje redactadas bajo estándares profesionales.

## ⚙️ Características Principales del Hardware
La placa en desarrollo incluye las siguientes especificaciones técnicas:
* **Microcontrolador:** PIC32MX220F032D a 40 MHz (Núcleo MIPS32® M4K®).
* **Memoria:** 32 KB Flash, 8 KB SRAM.
* **Interfaz USB:** Conector USB Mini-B SMD para programación directa vía Bootloader HID (sin necesidad de programadores externos como PICKit).
* **Gestión de Energía Híbrida:** * Operación lógica a 3.3V con regulador LDO dedicado.
  * Puerto JST integrado para alimentación autónoma mediante baterías Li-Po de 3.7V.
  * Entrada auxiliar por Jack de 5V DC.
* **Formato de Componentes:** Transición a componentes pasivos SMD (0603) para minimizar inductancias parásitas y mejorar la integridad de señal a altas frecuencias.

## 📂 Estructura del Repositorio

* `/Hardware`: Archivos fuente del esquemático y diseño de la PCB.
* `/Fabricacion`: Archivos Gerber, NC Drill y configuraciones para manufactura.
* `/Documentacion`: Reportes técnicos, justificación de componentes y lista de materiales (BOM).
* `/Imagenes`: Renders 3D de la placa y diagramas explicativos.

## 🚀 Próximos Pasos
- [ ] Finalización del diagrama esquemático.
- [ ] Asignación de huellas (footprints) para componentes SMD.
- [ ] Ruteo de pistas, priorizando pares diferenciales para la línea USB y planos de masa.
- [ ] Verificación de Reglas de Diseño (DRC).
- [ ] Exportación de archivos de producción.

---
*Este proyecto es de código abierto y está diseñado para impulsar el aprendizaje en el diseño de sistemas embebidos 3D"
