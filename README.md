<img src="./CRISTHOPHER/imgg/R.png" alt="Proyecto" width="500">
# pinguinokbron

## 📌 Descripción del Proyecto
Este repositorio contiene el diseño, ruteo y documentación técnica integral para la fabricación de una placa de desarrollo de hardware libre basada en la plataforma Pinguino de 32 bits. El diseño arquitectónico se centra en el microcontrolador PIC32MX220F032D-I/PT en encapsulado TQFP-44, una solución robusta que introduce el procesamiento de alto rendimiento a entornos de prototipado rápido. 

A diferencia de los sistemas tradicionales, este hardware aprovecha el motor USB nativo del silicio para permitir la programación directa y la comunicación con el host sin requerir circuitos integrados puente de conversión serial. Para optimizar la integridad de la señal a altas frecuencias y reducir el área física de la PCB, el diseño implementa una transición completa hacia componentes pasivos de montaje superficial en formato 0603, complementado con un sistema versátil de gestión de energía diseñado para aplicaciones tanto de escritorio como autónomas.

## 🎯 Misión
Desarrollar y documentar una placa de hardware libre de 32 bits, compacta y eficiente, que facilite la creación de prototipos y sistemas de control. Buscamos democratizar el acceso a arquitecturas avanzadas y técnicas de montaje superficial (SMD), ofreciendo una herramienta accesible que no dependa de programadores externos para impulsar el aprendizaje práctico en la ingeniería.

## 👁️ Visión
Convertir este diseño en un referente dentro de la comunidad Open Hardware para facilitar la transición tecnológica de microcontroladores de 8 a 32 bits. Aspiramos a inspirar a otros desarrolladores a diseñar, manufacturar y programar sus propios circuitos impresos profesionales de manera autónoma.

## 🎯 Objetivo General
Diseñar, rutear y documentar una tarjeta de desarrollo de código abierto de 32 bits compatible con el ecosistema Pinguino, optimizando el espacio físico mediante tecnologías de montaje superficial (SMD) y garantizando la estabilidad del sistema para aplicaciones avanzadas de control y sistemas embebidos.

## 📋 Objetivos Específicos
* Desarrollar el diagrama esquemático completo utilizando la suite KiCad, asegurando la correcta interconexión del microcontrolador PIC32 y sus componentes de soporte críticos.
* Implementar el diseño físico de la PCB priorizando la reducción de inductancias parásitas mediante el uso de componentes pasivos en formato 0603 y una distribución estratégica de capas.
* Diseñar un subsistema de alimentación triple e híbrido que acepte fuentes de energía por USB, conector de batería Li-Po de 3.7V y Jack de corriente de 5V DC, garantizando portabilidad y aislamiento ante ruidos transitorios.
* Aplicar reglas de diseño de alta velocidad para el ruteo del bus USB, implementando pistas con geometría de par diferencial y planos de masa sólidos para el retorno eficiente de corriente.
* Generar los archivos estándar de manufactura industrial (Gerber y NC Drill) y configuraciones de aislamiento para compatibilidad con sistemas de fresado local mediante herramientas como FlatCAM.

## ⚙️ Características Técnicas del Hardware
* Microcontrolador Principal: Microchip PIC32MX220F032D con núcleo RISC MIPS32 M4K, operando a frecuencias de hasta 40 MHz mediante síntesis por PLL interno.
* Memoria Interna: 32 KB de memoria Flash para programa y 8 KB de SRAM para datos.
* Conectividad USB: Puerto USB Mini-B con pines de datos protegidos y líneas trazadas con impedancia controlada para comunicación Full-Speed de 12 Mbps.
* Periféricos Avanzados: Soporte para Peripheral Pin Select (PPS) que permite la reasignación dinámica de pines, módulos ADC de alta velocidad, comparadores analógicos y temporizadores de precisión.
* Formato de Componentes: Encapsulado principal TQFP-44 y componentes pasivos distribuidos en encapsulados SMD 0603.
* Gestión de Potencia: Regulador LDO integrado de baja caída para la línea lógica de 3.3V y un circuito de filtrado específico con capacitores de bajo ESR para el núcleo interno de 1.8V (VCORE/VCAP).

## 🔄 Funcionamiento del Sistema
El funcionamiento de la tarjeta se divide en dos fases operativas gobernadas por un Bootloader de clase HID (Human Interface Device) preprogramado en la memoria de arranque dedicada del chip:

* Modo de Programación: Al energizar la tarjeta o presionar el botón de Reset mientras se mantiene activo el botón de Usuario (USER), el microcontrolador entra en modo de inicialización USB. Al ser detectado como un dispositivo HID nativo por el sistema operativo de la computadora, no requiere controladores específicos. El IDE de Pinguino se comunica directamente con este cargador para inyectar el nuevo firmware en la memoria Flash principal de manera transparente.
* Modo de Ejecución: Si el botón de Usuario no está presionado al arrancar, el flujo de ejecución salta el bloque del bootloader y se dirige directamente a la dirección de memoria de la aplicación de usuario, iniciando el ciclo de trabajo del firmware de manera determinista y de baja latencia.

## 🔀 Diferencias Clave
* Frente a Plataformas de 8 bits (AVR/PIC18): El núcleo MIPS32 procesa palabras completas de 32 bits por ciclo de instrucción, cuenta con un multiplicador/divisor por hardware para algoritmos complejos como el control PID, y posee una arquitectura de memoria virtual más eficiente para el manejo de pilas de datos y sistemas operativos de tiempo real (RTOS).
* Frente a Diseños de Desarrollo Comunes: Elimina la dependencia de convertidores externos como el FT232 o el CH340, lo que reduce el costo de la lista de materiales (BOM) y el consumo de corriente general. Además, el uso de componentes pasivos SMD 0603 frente a los de orificio pasante (THT) garantiza un desempeño superior frente a ruidos electromagnéticos a altas frecuencias.

## 📊 Resultados Esperados
* Disponibilidad de los diagramas esquemáticos y archivos de ruteo de la PCB completamente verificados bajo reglas de diseño eléctrico (ERC/DRC).
* Generación de la documentación de manufactura lista para su envío a plantas de fabricación de circuitos impresos o para su procesamiento en maquinaria CNC local.
* Una plataforma de desarrollo de código abierto completamente funcional, capaz de programarse de forma sencilla y que sirva como base para proyectos académicos y profesionales de ingeniería electrónica.

## 📂 Estructura del Repositorio
* `/Hardware`: Archivos fuente del esquemático y diseño de la PCB en KiCad.
* `/Fabricacion`: Archivos Gerber, NC Drill y perfiles de configuración para aislamiento o FlatCAM.
* `/Documentacion`: Justificación técnica de componentes, análisis de ruteo y lista de materiales (BOM).
* `/Imagenes`: Capturas del flujo de diseño, diagramas de bloques y renders tridimensionales de la tarjeta.

## Software
* [Descargar Manual Técnico (PDF)](CRISTHOPHER/81f7bb81b439db166ceb4c125af8d72d3f33c15a)

