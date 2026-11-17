[README (1).md](https://github.com/user-attachments/files/34959803/README.1.md)
# Sistema de Ventas e Inventario de Ropa - Unidad 3

**Materia:** Lenguajes de Interfaz  
**Lenguaje:** Ensamblador MASM x86 de 32 bits con Irvine32  
**Proyecto:** Macros, procedimientos y USES

## Integrantes

- Oscar Javier Chaidez Salazar
- Angel Daniel Vega Hernandez

## Descripcion

Este proyecto es una mejora del sistema de ventas e inventario de ropa realizado en la Unidad 2. Permite registrar prendas, consultar el inventario, recibir mercancia, vender y guardar los productos en el archivo `ropa.dat`.

En la Unidad 3 se organizaron mejor varias partes del codigo, usando **macros**, **procedimientos reutilizables** y **USES**, sin cambiar las funciones principales ni la regla de descuentos por mayoreo.

## Funciones del programa

1. Registrar prendas.
2. Mostrar inventario.
3. Buscar una prenda por codigo.
4. Recibir mercancia.
5. Vender prendas con descuento por mayoreo.
6. Mostrar resumen de inventario e ingresos.
7. Guardar el inventario en `ropa.dat`.
8. Cargar el inventario desde `ropa.dat`.
0. Salir.

**Limites:** hasta 10 productos distintos; cada producto admite de 0 a 100 unidades. Los precios se almacenan como centavos enteros y los codigos siguen el formato `ABC-123`.

## Descuentos por mayoreo

| Cantidad en una venta | Descuento |
|---|---:|
| 1 a 9 prendas | 0 % |
| 10 a 19 prendas | 10 % |
| 20 o mas prendas | 15 % |

El descuento se aplica a una sola prenda por venta, siempre que existan unidades suficientes.

## Cambios de la Unidad 3

- **Macro `MOSTRAR mensaje`:** reemplaza instrucciones repetidas para mostrar mensajes.
- **Macro `MOSTRAR_IMPORTE mensaje, valor`:** muestra un importe con dos decimales y la etiqueta MXN; se utiliza en `Vender` y `Resumen`.
- **Procedimiento `PedirCantidad`:** se reutiliza en `Recibir` y `Vender`; devuelve la cantidad en `EAX` y la validez en `EDX`.
- **`USES`:** conserva los registros que deben recuperar su valor original al terminar ciertos procedimientos. Los registros utilizados para devolver resultados se dejan fuera de `USES`.

Las macros no usan `LOCAL` porque no contienen etiquetas internas. MASM expande las instrucciones de cada macro donde se utiliza.

## Comparacion con la Unidad 2

| Criterio | Unidad 2 | Unidad 3 |
|---|---:|---:|
| Lineas fisicas del archivo fuente | 901 | 873 |
| Lineas no vacias y sin comentarios completos | 825 | 785 |

Se uso el mismo criterio para ambas versiones. Las macros reducen el codigo repetido del archivo `.asm`, pero no necesariamente el codigo maquina generado.

## Archivos del proyecto

```text
Inventario-Ropa-Macros-U3/
|-- Projectu2.slnx
|-- README.md
|-- Informe_U2_y_U3_Actualizado.pdf
|-- Tabla_Pruebas_U3.xlsx
`-- ProjectPract/
    |-- main.asm
    |-- ProjectPract.vcxproj
    |-- ProjectPract.vcxproj.filters
    `-- ropa.dat
```

El informe actualizado contiene la explicacion de la Unidad 2 y la seccion **Version de la Unidad 3** con los cambios realizados. La tabla de pruebas debe completarse con resultados obtenidos durante la ejecucion real.

## Requisitos

- Windows y Visual Studio con herramientas de compilacion C++ y MASM.
- Biblioteca Irvine32 para 32 bits.
- El proyecto esta configurado para buscar Irvine32 en `C:\Irvine`. Si esta instalada en otra ubicacion, ajustar las rutas del proyecto.
- Usar la plataforma **x86 / Win32**, no x64.

## Como compilar y ejecutar

1. Descargar el repositorio con **Code > Download ZIP** y extraerlo.
2. Abrir `Projectu2.slnx` en Visual Studio.
3. Seleccionar **Debug | x86 (Win32)**.
4. Presionar **Ctrl + Shift + B** para compilar.
5. Presionar **Ctrl + F5** para ejecutar el programa.
6. Para consultar el inventario de prueba, elegir **8. Cargar inventario** y luego **2. Mostrar inventario**.

**Nota sobre `ropa.dat`:** el programa busca este archivo en su directorio de trabajo. Si no lo encuentra, copiarlo al directorio de trabajo configurado en Visual Studio, o cambiar esa configuracion.

## Pruebas

Las pruebas incluyen registro, busqueda, entrada de mercancia, ventas aceptadas y rechazadas, descuentos del 0 %, 10 % y 15 %, resumen, guardado y carga.

**Estado:** la compilacion y los resultados obtenidos de la version U3 deben comprobarse en Visual Studio y registrarse en `Tabla_Pruebas_U3.xlsx` antes de la entrega final.
