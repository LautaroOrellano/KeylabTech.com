# KeylabTech.com.ar
Repositorio de demostración que muestra la arquitectura y estructura del backend y frontend del e-commerce KeyLab, incluyendo tecnologías utilizadas y flujo general de la aplicación.
Es un proyecto de e-commerce fullstack que demuestra buenas prácticas de arquitectura y estructura de código profesional, mostrando cómo se organiza un backend con Spring Boot y un frontend moderno en React.

## Decisiones de Arquitectura:
- **Spring Boot & Java::** Elegido por su robustez en el manejo de concurrencia y tipado estático, crítico para el manejo financiero del e-commerce.
- **Arquitectura Hexagonal (Ports & Adapters):** Implementada para desacoplar la lógica de negocio (Dominio) de los frameworks externos, permitiendo cambiar la base de datos o pasarelas de pago sin reescribir el núcleo.
- **Docker:** Utilizado para garantizar la paridad entre el entorno de desarrollo y producción (Vercel/Oracle).

## Arquitectura del proyecto

             ┌─────────────┐
             │ Frontend    │
             │ React / Vite│
             └─────┬───────┘
                   │
                   ▼
             ┌─────────────┐
             │ Backend     │
             │ Spring Boot │
             └─────┬───────┘
                   │
          ┌────────┴────────┐
          │                 │
          ▼                 ▼
    ┌─────────────┐   ┌─────────────┐
    │ MySQL DB    │   │ Servicios   │
    │             │   │ Externos    │
    │             │   │ -Cloudinary │
    │             │   │ -MercadoPago│
    │             │   │ -Supabase   │
    └─────────────┘   └─────────────┘
                         
## Estructura del proyecto

### Backend

<img width="342" height="1022" alt="Captura de pantalla 2025-09-22 141258" src="https://github.com/user-attachments/assets/150d38e6-c7f4-41e8-940d-d3a21c58facb" />


### Frontend 

<img width="331" height="1000" alt="Captura de pantalla 2025-09-22 140040" src="https://github.com/user-attachments/assets/a268dd5c-ae82-4ab8-bc82-ed116c153fbb" />

---
  
## **Flujo de la aplicación / Ejemplo de uso**
KeyLabTech es un e-commerce fullstack con arquitectura moderna, donde el **frontend en React** interactúa con el **backend en Java / Spring Boot** a través de endpoints REST bien definidos para usuarios, clientes y administradores.
  
**Flujo general:**
1. El usuario interactúa con la aplicación en React (navegación de productos, carrito, checkout).
2. El frontend realiza peticiones a los **controllers del backend**, los cuales procesan la lógica de negocio y gestionan la persistencia en la base de datos.
3. El backend valida usuarios con JWT y maneja la seguridad de cada endpoint según el rol (usuario, cliente, admin).
4. El backend y frontend están desplegados en la nube:
   - **Frontend:** Vercel
   - **Backend:** Render / Oracle / Supabase
5. Se consumen APIs externas para funcionalidades clave:
   - **Pagos:** Mercado Pago, PayPal
   - **Almacenamiento de archivos e imágenes:** Cloudinary
6. La aplicación incluye buenas prácticas profesionales:
   - Estructura modular y escalable
   - Manejo de logs para backend y frontend
   - Testeo unitario y de integración en ambas capas
   - Gestión de errores y validaciones consistentes
7. La arquitectura permite escalabilidad futura y facilita integración con nuevos servicios y microservicios.

> ⚠️ Todas las interacciones mostradas en el proyecto utilizan datos ficticios para proteger información sensible.

## Por qué estas tecnologías

- **Spring Boot:** rápido desarrollo y robustez para APIs.
- **React + Vite:** SPA moderna y eficiente.
- **JWT:** seguridad en autenticación.
- **Docker:** despliegue reproducible.

## Capturas de la app en funcionamiento

### Home

<img width="1917" height="934" alt="Captura de pantalla 2025-09-22 142223" src="https://github.com/user-attachments/assets/29c4bc5e-fa82-4932-ad14-3e350650f40d" />

### Carrito

<img width="1912" height="931" alt="Captura de pantalla 2025-09-22 142313" src="https://github.com/user-attachments/assets/78d93bfd-f19a-4fc7-a409-2764509175bc" />

### Panel Admin

<img width="1916" height="935" alt="Captura de pantalla 2025-09-22 142405" src="https://github.com/user-attachments/assets/70df1e0c-4597-40cc-89b0-e40f19693dcb" />

Las capturas muestran la interfaz de KeyLab con datos ficticios para proteger información sensible.

## Licencia y variables de entorno

- El código completo se mantiene privado por motivos de seguridad ⚠️.
- Se incluye `.env.example` para mostrar qué variables de entorno se necesitan.
- Este proyecto está protegido y no se permite uso comercial sin autorización.
