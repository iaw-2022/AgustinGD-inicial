# Proyecto Inicial - 🐄🧑‍🌾 shopping de la granja 🥩🥛

## Idea a Implementar 💡

La idea es realizar un aplicacion que permita administrar un catalogo de productos de la granja, donde se pueden buscar ciertos productos segun alguna palabra clave o caracteristica, y tambien reservar uno o varios productos usando un carrito de compras.

## Diagrama ER 👷
```mermaid
erDiagram
    CLIENTE ||--o{ PEDIDO : hace
    CLIENTE{
        int id
        string nombre
        string email
        timestamp created_at
        timestamp updated_at
    }
    PEDIDO }o--|{ PRODUCTO : contiene
    PEDIDO{
        int id
        int cliente_id
        int producto_id
        int cantidad
        timestamp created_at
        timestamp updated_at
    }
    PRODUCTO }o--|| CATEGORIA : pertenece
    PRODUCTO{
        int id
        int categoria_id
        boolean disponible
        string nombre
        string descripcion
        float precioPorUnidad
        string imagen_dir
        timestamp created_at
        timestamp updated_at
    }
    CATEGORIA{
        int id
        string nombre
        string descripcion
        timestamp created_at
        timestamp updated_at
    }
    
    USER }o--|| ROL : tiene
    USER{
        int id
        int rol_id        
        string name
        string email
        timestamp email_verified_at
        string password
        string remember_token
        timestamp created_at
        timestamp updated_at
    }
    ROL{
        int id
        string nombre
        timestamp created_at
        timestamp updated_at
    }
```

## Actualizaciones a los datos ✏️

### Proyecto Framework PHP - Laravel

usuarios con rol "user":
  * solo puede ver el Home

usuarios con rol "ventas" podran:
  * ver productos.
  * ver clientes.
  * ver pedidos.
  
usuarios con rol "actualizacion" podran:
  * editar la disponibilidad e imagen de los productos.

usuarios con rol "edicion" podran:
  * cargar, borrar y editar productos.
  * cargar, borrar y editar categorias.
  * cargar, borrar y editar clientes.
  * cargar, borrar y editar pedidos.
    
usuarios con rol "administrador" podran:
  * administar usuarios
  * ver timestamps de cuando fueron creados/actualizados los:
     * Productos
     * Categorias
     * Clientes
     * Pedidos
     * Usuarios     
  * lo mismo que el rol "edicion"

## Información del Servicio Web 📰

El Servicio Web permitira inspeccionar y reservar productos relacionados con la granja, se pueden buscar según:
  * Categoria
  * Precio -> mayor/menor
  * Palabra clave
  * Disponibilidad

## Visualización y Acceso a la Información 👀

### Proyecto Javascript - React/Vue

El usuario para buscar productos de la manera mas intuitiva posible,
navegando con el mouse o ingresando texto por teclado podrá:
  * Scrollear a traves del catagolo de categorias
  * Ver productos de una categoria
  * Buscar algun producto especifico segun palabra clave
  * Ordenar segun precio ascendente/descendente
  * Ordenar segun nombre ascendente/descendente
  * Agregar productos al carrito de compras
  * Autenticarse en la Aplicacion Web, es decir, login/registro
  * Realizar un pedido
  * Ver "mis pedidos"
