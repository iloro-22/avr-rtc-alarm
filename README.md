# Reloj Calendario RTC y Alarma por I2C (AVR)

## Descripción del Proyecto
Desarrollo de firmware en C para un microcontrolador AVR que implementa un reloj calendario con sistema de alarmas. El proyecto se comunica vía I2C con un módulo RTC DS3231 y cuenta con una interfaz de comandos serie (UART) para configuración y monitoreo.

*Nota: Proyecto desarrollado en equipo. Mi contribución principal fue el diseño de la concurrencia en la recepción UART, implementando un buffer circular para evitar el bloqueo del sistema durante la lectura de comandos.*

## Tecnologías y Periféricos
* **Lenguaje:** C (Bare-metal)
* **Protocolos:** I2C (Comunicación con RTC), UART (Interfaz con PC).
* **Entorno:** Microchip Studio y simulación en Proteus.

## Características Principales y Arquitectura
* **Arquitectura Background/Foreground:** Sistema no bloqueante impulsado por interrupciones de recepción y transmisión UART.
* **Buffer Circular (Ring Buffer):** Implementación de una cola circular para el almacenamiento temporal de los datos entrantes por UART, permitiendo el procesamiento asincrónico de comandos (`SET TIME`, `SET ALARM`, `ON`, `OFF`).
* **Drivers Personalizados:** Desarrollo a medida para el control de los buses I2C y UART sin depender de librerías externas.

## Estructura del Repositorio
* `/src`: Código fuente modularizado (`I2C.c`, `RTC.c`, `UART.c`, `states.c`, `main.c`).
* `/docs`: Archivo de simulación en formato Proteus (`.pdsprj`).
