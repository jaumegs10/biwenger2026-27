# Liga Fantasy Hub: Deudas, Clasificación y Pique

Una aplicación web diseñada para gestionar los pagos, las deudas y el pique sano de una liga privada de Biwenger. 

Esta herramienta elimina los problemas de llevar las cuentas en una hoja de cálculo o en un grupo de WhatsApp, automatizando el control de pagos, generando resúmenes de morosos y castigando públicamente a los peores mánagers de la jornada.

## Acceso a la aplicación

El proyecto se encuentra desplegado y accesible online a través de Netlify:

**Enlace web:** [https://ligabiwenger2627.netlify.app/](https://ligabiwenger2627.netlify.app/)

## Características principales

* **Login dinámico:** Cada usuario selecciona su perfil para entrar y es recibido con un mensaje personalizado.
* **Panel de deudas individual:** Muestra al instante la deuda activa del usuario y desglosa el motivo (sanción por posición en la jornada o por tarjetas rojas).
* **Clasificación general:** Tabla en tiempo real con el dinero total recaudado, proyecciones del bote a 38 jornadas y estimación del presupuesto final por persona.
* **Muro de penalizaciones:**
  * **El Pringado de la Jornada:** Calcula automáticamente el jugador con peor rendimiento en la última jornada registrada, mostrando su foto de perfil y un mensaje de castigo aleatorio desde la base de datos.
  * **El Farolillo Rojo:** Expone al jugador con mayor deuda histórica acumulada, facilitando un botón para exportar la burla a WhatsApp.
* **Panel de Tesorería:** Acceso protegido por contraseña para la gestión de pagos y deudas. Permite:
  * Importación manual o masiva de deudas mediante archivos CSV.
  * Liquidación de deudas o corrección de errores.
  * Generación automática de reportes de deuda listos para enviar al grupo de Whatsapp.

## Stack tecnológico

El proyecto está construido con una arquitectura serverless sencilla:

* **Frontend:** HTML5, CSS3 y Vanilla JavaScript (sin frameworks). Interfaz responsive enfocada a Mobile-First.
* **Backend y Base de Datos:** Supabase (PostgreSQL).
* **Hosting:** Netlify.

## Estructura de datos (Supabase)

El sistema se alimenta de 4 tablas relacionales:

1. `jugadores`: Contiene el ID, nombre, ruta de la fotografía y credenciales de administración.
2. `detalle_pagos`: Registro histórico de deudas. Incluye el ID del jugador, número de jornada, importes separados por concepto y estado de liquidación (booleano).
3. `mensajes_bienvenida`: Textos dinámicos mostrados durante el inicio de sesión.
4. `mensajes_ultimo`: Banco de frases humillantes asociadas al ID de cada jugador para la sección de penalizaciones.

## Despliegue en local

Para visualizar o modificar el proyecto en un entorno local:

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/TU_USUARIO/TU_REPOSITORIO.git](https://github.com/TU_USUARIO/TU_REPOSITORIO.git)