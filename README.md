# SistemaRestaurante (SGR)

Proyecto académico: Sistema de Gestión para Restaurantes (SGR) con arquitectura basada en API REST y diagramas de componentes.

## Objetivo General
Desarrollar un sistema que digitalice y optimice el flujo de trabajo en un restaurante:
- Toma de pedidos en tablet.
- Visualización de órdenes en cocina.
- Facturación inalámbrica en mesa.
- Reportes gerenciales en tiempo real.

## Componentes del Sistema
- Tablet Camarero → Menú, pedidos y facturación.  
- Pizarra Cocina → Órdenes de platos organizadas por mesa y hora.  
- Interfaz del Gerente → Control de mesas, camareros y reportes.  
- Servidor Backend (API REST) → Procesa pedidos y conecta dispositivos.  
- Base de Datos → Registra pedidos, usuarios, facturas y reportes.  
- Subsistema de RRHH → Datos de camareros desde sistema externo.  
- Impresora Inalámbrica → Boletas y facturas.  

## Diagrama de Componentes
```text
+-----------------+           +------------------+  
|  Tablet         |           | Pizarra Cocina   |  
| Camarero        |           | - Muestra ordenes|  
| - Menú          | <-------> | - Mesa/Hora      |  
| - Pedidos       |           +------------------+  
| - Facturas      |  
+--------+--------+  
         |  
         v  
+---------------------+  
| Servidor Backend    |  
| (API REST)          |  
| - Reglas de negocio |  
| - Orquestación      |  
+---+---+---+---+-----+  
    |   |   |   |  
    v   v   v   v  
+-------+   +----------+   +---------------+   +-------------------+  
|  BD   |   | Gerente  |   | Subsistema    |   | Impresora         |  
|Datos  |   | Reportes |   |   RRHH        |   | Inalámbrica       |  
+-------+   +----------+   +---------------+   +-------------------+  
## Explicación del Diagrama
El diagrama muestra cómo los distintos componentes del sistema interactúan entre sí:  
- El **Camarero** usa una **Tablet** para tomar pedidos, ver el menú y generar facturas.  
- La **Pizarra de Cocina** recibe en tiempo real las órdenes organizadas por mesa y hora.  
- El **Servidor Backend (API REST)** centraliza la lógica del negocio, recibe los pedidos, los procesa y los distribuye a los demás módulos.  
- La **Base de Datos** almacena información clave como pedidos, usuarios, facturas y reportes.  
- El **Gerente** accede a reportes y análisis para la toma de decisiones.  
- El **Subsistema de RRHH** proporciona datos de los camareros desde un sistema externo.  
- La **Impresora Inalámbrica** genera boletas y facturas directamente en las mesas.  

## Patrón Arquitectónico
El sistema sigue el patrón **Cliente-Servidor** complementado con una arquitectura en **capas**:

- **Capa de Presentación** → Tablet del camarero, Pizarra de Cocina y Panel del Gerente.  
- **Capa de Negocio** → Servidor Backend con API REST que gestiona reglas de negocio.  
- **Capa de Datos** → Base de Datos y Subsistema de RRHH.  
- **Capa de Servicios Externos** → Impresora inalámbrica.  

Este enfoque garantiza **modularidad, escalabilidad y facilidad de mantenimiento**.
