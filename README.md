# Inventario de Ropa - Unidad 3

## Lenguajes de Interfaz

**Proyecto:** Sistema de Ventas e Inventario de Ropa con Descuentos por Mayoreo

**Unidad:** 3 - Macros, Procedimientos y USES

**Integrantes:**
- Oscar Javier Chaidez Salazar
- Ángel Daniel Vega Hernández

## Descripción del proyecto

Este proyecto consiste en un sistema de ventas e inventario de ropa desarrollado en lenguaje ensamblador MASM x86 de 32 bits, utilizando la librería Irvine32.

Es una continuación del proyecto de la Unidad 2. En esta nueva versión se agregaron macros, se reutilizaron procedimientos y se aplicó USES para reducir código repetido y facilitar su comprensión.

## Funciones del programa

1. Registrar prendas de ropa.
2. Mostrar el inventario.
3. Buscar prendas por código.
4. Recibir mercancía.
5. Realizar ventas.
6. Mostrar el resumen del inventario.
7. Guardar inventario en ropa.dat.
8. Cargar inventario desde ropa.dat.

## Descuentos por mayoreo

El programa aplica descuentos según la cantidad de prendas compradas en una venta:

| Cantidad | Descuento |
|---|---|
| 1 a 9 prendas | 0 % |
| 10 a 19 prendas | 10 % |
| 20 o más prendas | 15 % |

Cada venta corresponde a un solo producto y se comprueban las existencias antes de aceptarla.

## Mejoras realizadas en la Unidad 3

**Macros:**
- `MOSTRAR`: muestra mensajes sin repetir las mismas instrucciones.
- `MOSTRAR_IMPORTE`: muestra cantidades de dinero con dos decimales y la etiqueta MXN.

**Procedimientos:**
- Se agregó `PedirCantidad` para reutilizar la captura y conversión de cantidades.
- Se conservaron los procedimientos de registro, búsqueda, ventas, resumen y archivos.

**USES:**
- Se utiliza para conservar los registros necesarios durante la ejecución de los procedimientos.
- Se evita conservar EAX con USES cuando debe devolver un resultado.

## Archivos del proyecto

- `Projectu3.slnx`: solución de Visual Studio.
- `ProjectPract/main.asm`: código fuente de la Unidad 3.
- `ProjectPract/ProjectPract.vcxproj`: configuración del proyecto.
- `ProjectPract/ProjectPract.vcxproj.filters`: organización de los archivos.
- `ProjectPract/ropa.dat`: inventario de prueba.
- `Informe_Proyecto.pdf`: informe de la Unidad 2.
- `Informe_U3_A.pdf`: informe de la Unidad 3.
- `Tabla_Pruebas_U3.xlsx`: tabla de pruebas actualizada.

## Compilación y ejecución

1. Descargar el repositorio de GitHub.
2. Extraer los archivos.
3. Abrir `Projectu3.slnx` en Visual Studio.
4. Tener configurado MASM e Irvine32 de 32 bits.
5. Seleccionar la configuración `Debug | x86`.
6. Presionar `Ctrl + Shift + B` para compilar.
7. Presionar `Ctrl + F5` para ejecutar.
8. Utilizar el menú del programa para registrar, vender, guardar o cargar productos.

## Pruebas

El proyecto cuenta con una tabla de pruebas que incluye registro de prendas, búsqueda, recepción de mercancía, ventas con y sin descuento, validaciones, resumen, guardado y carga del inventario.

Los resultados obtenidos deben completarse después de comprobar la ejecución de la versión U3 en Visual Studio.

## Objetivo de la Unidad 3

Mejorar la organización del código de la Unidad 2 mediante macros, procedimientos reutilizables y USES, conservando el funcionamiento del sistema y sus descuentos por mayoreo.
