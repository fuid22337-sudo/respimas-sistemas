
# RESPIMAS – Sistema Integrado de Gestión

**Sistema de gestión integral para comercializadora de productos de inhaloterapia y circuitos de anestesia.**

---

## Descripción del proyecto

RESPIMAS es una empresa dedicada a la comercialización de productos médicos (inhaloterapia y circuitos de anestesia). Actualmente, toda su operación (almacén, cobranzas, pagos a proveedores, cotizaciones y órdenes de pedido) se gestiona mediante archivos Excel independientes, lo que genera:

- Conciliaciones manuales que consumen ~8 horas semanales.
- Duplicidad de clientes y productos por falta de identificadores únicos (RFC y SKU).
- Inconsistencias en los datos (formatos de fecha variables, errores en fórmulas).
- Desfase entre inventario y ventas porque no existe vinculación automática.
- Retraso en el cierre contable de hasta 5 días adicionales cada mes.

Este proyecto propone un **sistema integrado** que centraliza toda la información en una base de datos SQL, automatiza los procesos críticos y proporciona información oportuna y confiable para la toma de decisiones.

---

## Objetivo del sistema

- Centralizar los datos actualmente dispersos en Excel (almacén, cobranza, pagos, cotizaciones, pedidos).
- Eliminar duplicidades mediante claves únicas (SKU para productos, RFC para clientes y proveedores).
- Automatizar el control de inventario (entradas por compra, salidas por venta).
- Gestionar cuentas por cobrar con abonos parciales, cálculo de saldos y antigüedad de cartera.
- Gestionar cuentas por pagar a proveedores con fechas de vencimiento y pagos.
- Integrar con el sistema de facturación externo mediante importación automática de facturas (CSV/XML).
- Generar reportes gerenciales de inventario, cartera y cuentas por pagar en menos de 3 segundos.

---

## Tecnologías utilizadas

- **Frontend (prototipo):** HTML5, CSS3 (Tailwind CSS), JavaScript (vanilla)
- **Backend (propuesto):** MySQL (base de datos relacional)
- **Herramientas CASE:** MySQL Workbench (diagrama ER y modelo relacional)
- **Control de versiones:** Git + GitHub

---

## Prototipo navegable

El prototipo es una maqueta HTML que simula las principales funcionalidades del sistema. Puedes abrirlo directamente en tu navegador sin necesidad de instalar nada.

### ¿Cómo navegar el prototipo?

1. Abre el archivo `index.html` que se encuentra en la carpeta `/prototipo`.
2. La interfaz está organizada en 5 pestañas principales (módulos funcionales):

| ID Pantalla | Nombre | Funcionalidad que cubre |
| :--- | :--- | :--- |
| PNT-01 | Catálogo & Inventario | Gestión de productos, stock, movimientos de inventario (RF-01, RF-02, RF-07) |
| PNT-02 | Ventas y Cuentas por Cobrar | Facturas, abonos, antigüedad de cartera, conciliación bancaria (RF-03, RF-04, RF-09) |
| PNT-03 | Cuentas por Pagar | Facturas de compra, pagos a proveedores (RF-05) |
| PNT-04 | Cotizaciones / Órdenes | Cotizaciones, órdenes de compra (RF-06) |
| PNT-05 | Reportes y Trazabilidad | Reportes de inventario, cartera, movimientos históricos (RF-10, RF-14) |

**Nota:** En la barra superior, puedes cambiar el rol (Administración, Almacén, Cobranzas) para simular el control de acceso (RNF-04, RF-12).

---

## Estructura del repositorio

```
/respimas-sistema
├── /prototipo
│   └── index.html                # Prototipo navegable (HTML + CSS + JS)
├── /documentacion
│   ├── Especificacion_Final_Proyecto.docx   # Documento integrador del proyecto
│   ├── Matriz_Requerimientos.xlsx           # Matriz de requerimientos (RF + RNF)
│   └── Matriz_Trazabilidad.xlsx             # Trazabilidad requerimientos ↔ prototipo
├── /diagramas
│   ├── Diagrama_AS-IS.pdf         # Proceso actual (con problemas identificados)
│   ├── Diagrama_TO-BE.pdf         # Proceso futuro con el sistema
│   ├── Diagrama_ER.png            # Diagrama Entidad-Relación (imagen)
│   └── Diagrama_ER.mwb            # Modelo ER en MySQL Workbench (editable)
├── /minutas
│   ├── Minutas_Entrevistas.pdf    # Minuta 1, 2 y 3 (levantamiento y prototipo)
│   └── Minuta_Validacion_Prototipo.docx   # Validación formal con firma del cliente
└── README.md                      # Este archivo
```

---

## Entregables incluidos

| Entregable | Archivo | Ubicación |
| :--- | :--- | :--- |
| Especificación Final del Proyecto | `Especificacion_Final_Proyecto.docx` | `/documentacion` |
| Matriz de Requerimientos | `Matriz_Requerimientos.xlsx` | `/documentacion` |
| Matriz de Trazabilidad | `Matriz_Trazabilidad.xlsx` | `/documentacion` |
| Diagrama AS-IS | `Diagrama_AS-IS.pdf` | `/diagramas` |
| Diagrama TO-BE | `Diagrama_TO-BE.pdf` | `/diagramas` |
| Diagrama ER (imagen) | `Diagrama_ER.png` | `/diagramas` |
| Diagrama ER (Workbench) | `Diagrama_ER.mwb` | `/diagramas` |
| Minutas de entrevistas | `Minutas_Entrevistas.pdf` | `/minutas` |
| Minuta de validación (firmada) | `Minuta_Validacion_Prototipo.docx` | `/minutas` |
| Prototipo HTML | `index.html` | `/prototipo` |

---

## Validación con el cliente

El prototipo fue presentado y **aprobado formalmente** por el cliente (Sra. Aurea Beatriz Aldana Ramírez, representante de RESPIMAS) el 13 de mayo de 2026. La minuta de validación (con firma) se encuentra en la carpeta `/minutas`.

Durante la sesión, el cliente solicitó ajustes menores que no afectan los requerimientos críticos y quedaron documentados para implementarse en la siguiente fase del proyecto (Diseño de Software).

---

## Trabajo futuro (siguiente fase)

- Refinar el modelo ER y generar el esquema físico en MySQL.
- Implementar el backend (lógica de negocio, APIs) conectado a la base de datos.
- Desarrollar los requerimientos Should-have pendientes (RF-13: cancelaciones y devoluciones, RF-14: log de auditoría).
- Implementar la interfaz de arrastre para la conciliación bancaria (RF-09).
- Incorporar el logotipo y colores corporativos en los reportes PDF.
- Realizar pruebas de carga para validar los requisitos de rendimiento (RNF-01).

---

## Equipo desarrollador

- **Ian Paulo Acevedo Aldana** – Facilitador y observador  
- **Juan Emiliano Muñoz Ibarra** – Tomador de notas  

**Institución:** Universidad Autónoma de Aguascalientes (UAA)  
**Departamento:** Sistemas de Información  
**Materia:** Ingeniería de Requerimientos  
**Semestre:** 2025-B

---


**Ultima actualización:** Junio de 2026  
**Versión del proyecto:** 1.0
```

---
