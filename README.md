This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

Índice de Contenidos
Introducción
Requisitos Previos
Instalación
Estructura del Proyecto
Descripción de Componentes Principales
Dashboard
ProductRow
Popup
NavBar
Cart
Banner
API Endpoints
GET /api/get_products
PUT /api/edit_product/
Palabras Claves
Pruebas y Depuración
Conclusiones
1. Introducción
Este proyecto es un panel de administración que permite gestionar productos en una tienda de comercio electrónico. Los administradores pueden visualizar, editar y gestionar productos a través de una interfaz de usuario amigable, y estos cambios se reflejan en tiempo real gracias a la conexión con una base de datos MongoDB.

1. Requisitos Previos
Antes de comenzar, asegúrate de tener los siguientes requisitos instalados:

Node.js (v14+)
MongoDB
Un manejador de paquetes como npm o yarn
3. Instalación
Clona este repositorio en tu máquina local.

bash
Copiar código
git clone https://github.com/tu-proyecto.git
Instala las dependencias del proyecto.

bash
Copiar código
npm install
Configura el archivo .env con las variables de entorno necesarias, como la conexión a MongoDB.

env
Copiar código
MONGODB_URI=mongodb://localhost:27017/nombre_db
Inicia el servidor de desarrollo.

bash
Copiar código
npm run dev
4. Estructura del Proyecto
El proyecto está organizado de la siguiente manera:

arduino
Copiar código
├── app/
│   ├── components/
│   │   ├── admin-panel/
│   │   │   ├── ProductRow.tsx
│   │   │   ├── Popup.tsx
│   │   ├── front-end/
│   │   │   ├── NavBar.tsx
│   │   │   ├── Cart.tsx
│   │   │   ├── Banner.tsx
│   ├── api/
│   │   ├── get_products.ts
│   │   ├── edit_product.ts
├── redux/
│   ├── features/
│   │   ├── loadingSlice.ts
│   ├── hooks.ts
├── libs/
│   ├── models/Products.ts
│   ├── MongoConnect.ts
app/components/admin-panel/: Componentes relacionados con la administración de productos.
app/components/front-end/: Componentes relacionados con el frontend del sitio web.
redux/: Implementaciones de Redux para manejar el estado global de la aplicación.
libs/: Conexiones a MongoDB y modelos de datos.
5. Descripción de Componentes Principales
Dashboard
Este es el componente principal del panel de administración. Renderiza todos los productos almacenados en la base de datos y permite la interacción para editar o visualizar detalles adicionales. Utiliza useEffect para cargar los productos y actualizar la tabla cuando sea necesario.

ProductRow
Este componente renderiza una fila de la tabla en el Dashboard. Cada fila representa un producto con sus respectivas acciones: ver, editar y eliminar.

Popup
Popup es el componente modal que se activa cuando el usuario quiere editar o agregar un producto. Tiene campos para ingresar la nueva información del producto y guarda los cambios al enviar el formulario.

NavBar
Es la barra de navegación que aparece en la parte superior del sitio. Incluye un campo de búsqueda y la posibilidad de ver el carrito de compras.

Cart
Este componente muestra el carrito de compras con todos los productos añadidos por el usuario. Está diseñado para permitir al usuario revisar los productos y proceder al pago.

Banner
El componente de Banner muestra promociones y productos destacados en la página principal.

6. API Endpoints
GET /api/get_products
Este endpoint obtiene la lista de todos los productos disponibles en la base de datos.

Respuesta Exitosa:
json
Copiar código
[
  {
    "_id": "613b3fcf1d71a7a10b23db12",
    "name": "Freidora de Aire Thomas",
    "category": "Electrodomésticos",
    "price": "100",
    "imgSrc": "/images/product-1.jpg"
  },
  ...
]
PUT /api/edit_product/
Este endpoint permite actualizar los detalles de un producto existente.

Parámetros:
id: El ID del producto a actualizar.
Cuerpo de la Solicitud:
json
Copiar código
{
  "name": "Nuevo Nombre",
  "category": "Nueva Categoría",
  "price": "Nuevo Precio"
}
Respuesta Exitosa:
json
Copiar código
{
  "message": "Product updated successfully"
}
7. Palabras Claves
React: Biblioteca de JavaScript para construir interfaces de usuario.
Next.js: Framework para construir aplicaciones web React con capacidades de renderizado en servidor (SSR).
MongoDB: Base de datos NoSQL utilizada para almacenar la información de los productos.
Redux: Utilizado para manejar el estado global de la aplicación.
Axios: Librería para realizar solicitudes HTTP desde el frontend.
API REST: Conjunto de servicios web que permiten la interacción entre el frontend y el backend.
Dashboard: Panel de administración para gestionar productos.
CRUD: Operaciones de Crear, Leer, Actualizar y Eliminar productos.
8. Pruebas y Depuración
Es importante realizar pruebas después de cada modificación en el proyecto para asegurar que todo esté funcionando correctamente. Aquí hay algunas sugerencias:

Pruebas unitarias: Implementar pruebas unitarias para componentes como ProductRow y Popup para asegurar que el flujo de datos sea correcto.
Errores comunes: Asegúrate de que la API esté conectada correctamente a la base de datos y que los endpoints respondan con los datos esperados.
9. Conclusiones
Este proyecto permite una gestión eficiente de productos dentro de un entorno de e-commerce. La arquitectura modular y el uso de herramientas como Redux y Next.js lo hacen escalable y fácil de mantener.
