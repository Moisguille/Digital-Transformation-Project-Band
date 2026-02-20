Aquí tienes la arquitectura y especificación de requisitos para el **DMS** (Document Management System) de **Callearte**, extraída y organizada de forma limpia a partir del documento proporcionado.

# Callearte DMS: Document Management System

Este documento detalla la especificación de requisitos para el sistema de gestión documental de **Callearte**, diseñado para centralizar y proteger el patrimonio intelectual y administrativo de la banda.

## 📖 Contexto de Negocio

Callearte es una agrupación de flamenco de El Puerto de Santa María integrada por 15 profesionales, divididos en áreas de marketing, músicos y equipo técnico. Actualmente, la organización carece de un sistema centralizado, lo que provoca duplicidad de archivos y riesgo de pérdida de información al depender de WhatsApp y discos duros individuales.

### Objetivos del DMS

* 
**OBJ-0001 (Gestión):** Organizar y gestionar toda la documentación según las necesidades operativas de la banda.


* 
**OBJ-0003 (Seguridad):** Proteger información confidencial mediante cifrado y permisos, asegurando la continuidad del negocio con copias de seguridad automáticas.



---

## 🛠️ Catálogo de Requisitos de Información (IRQ)

El sistema debe capturar y almacenar los siguientes metadatos para cada tipo de documento:

| ID | Entidad | Datos Específicos a Almacenar |
| --- | --- | --- |
| **IRQ-0001** | **Reservas** | Nombre del cliente, correo, fecha del evento, dirección, fecha de reserva y trimestre.

 |
| **IRQ-0002** | **Facturas** | Servicio, duración, importe, fecha de emisión, estado y trimestre.

 |
| **IRQ-0003** | **Partituras** | Autor, fecha de creación y nombre de la canción.

 |
| **IRQ-0004** | **Contratos** | Nombre del contratado, fecha, tipo (indefinido/temporal), vencimiento y estado.

 |
| **IRQ-0005** | **Letras** | Nombre de la canción (para uso de los cantantes).

 |
| **IRQ-0006** | **Inf. Técnico** | Código del material, fecha de última revisión y estado (nuevo/desgastado/deplorable).

 |
| **IRQ-0007** | **Multimedia** | Archivo, fecha del evento, tipo de archivo y nombre del evento.

 |
| **IRQ-0008** | **Marketing** | Planes estratégicos, tipo (logos/folletos) y versión del documento.

 |

---

## 🔄 Casos de Uso Principales (UC)

### Gestión Administrativa

* 
**Consulta de Reservas y Facturas:** El mánager localiza estos documentos filtrando por **trimestre** y **nombre de cliente**.


* 
**Control de Pagos:** Revisión semanal de facturas filtrando exclusivamente por su **estado**.


* 
**Renovación de Contratos:** Actualización de registros indicando el **tipo de contrato** y el **nombre del contratado**.



### Operación y Marketing

* 
**Ensayos:** Los músicos acceden a letras y partituras buscando por el **nombre de la canción**.


* 
**Mantenimiento Técnico:** El técnico consulta el estado de equipos mediante su **código** y **estado** actual.


* 
**Promoción:** El equipo de marketing recupera fotos y vídeos por **nombre de evento**. Para imprenta, filtran por **tipo de archivo** y **última versión** para evitar errores de producción.



---

## 🔐 Reglas de Negocio (Control de Acceso)

El sistema impone las siguientes restricciones de seguridad según el rol del usuario:

* 
**Mánager (Mari Carmen Atienza):** Permisos de **Lectura y Escritura** en Reservas, Facturas y Contratos.


* 
**Músicos y Cantantes:** Permisos de **solo Lectura** exclusivamente para letras y partituras.


* 
**Técnico de Sonido (Rocío Atienza):** Permisos de **Lectura y Escritura** para informes técnicos.


* 
**Equipo de Marketing:** Permisos de **Lectura y Escritura** en documentación de marketing y **solo Lectura** en archivos multimedia.



---

## 👥 Participantes del Proyecto

* 
**Cliente (Callearte):** Representado por Mari Carmen Atienza (Mánager), Rocío Atienza (Técnico), Julio Martín (Músico) y Fran Márquez (Marketing).


* 
**Equipo de Desarrollo (Gsi):** Sergio Díaz Vázquez, Moisés Guillermo Godoy Nava, Marco Granja Quinto y Ricardo Fernández Rodríguez Navas.



---


graph TD
    %% Centro del Sistema
    DMS((Callearte DMS))

    %% Rol: Mánager
    Manager[Mánager: Mari Carmen Atienza] -->|Lectura/Escritura| Admin_Data[Reservas, Facturas y Contratos]
    Admin_Data --- UC_Admin[UC-0001: Gestionar Reservas<br/>UC-0002: Consultar Facturas<br/>UC-0003: Comprobar Pagos<br/>UC-0005: Renovar Contratos]
    UC_Admin --> DMS

    %% Rol: Músicos
    Musicians[Músicos y Cantantes: Julio Martín] -->|Solo Lectura| Artist_Data[Letras y Partituras]
    Artist_Data --- UC_Artist[UC-0006: Consulta para Ensayos]
    UC_Artist --> DMS

    %% Rol: Técnico de Sonido
    Tech[Técnico: Rocío Atienza] -->|Lectura/Escritura| Tech_Data[Informes Técnicos]
    Tech_Data --- UC_Tech[UC-0007: Revisión de Equipos]
    UC_Tech --> DMS

    %% Rol: Marketing
    Marketing[Marketing: Fran Márquez] -->|Lectura/Escritura| Mkt_Data[Planes y Diseños de Marketing]
    Marketing -->|Solo Lectura| Multi_Data[Multimedia: Fotos y Vídeos]
    Mkt_Data --- UC_Mkt[UC-0009: Gestionar Planes<br/>UC-0010: Impresión Final<br/>UC-0011: Revisión de Borradores]
    Multi_Data --- UC_Multi[UC-0008: Uso de Multimedia por Evento]
    UC_Mkt --> DMS
    UC_Multi --> DMS


