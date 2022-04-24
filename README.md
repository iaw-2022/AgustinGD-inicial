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

usuarios con rol "user" podran:
  * no tienen acceso a nada (se les debe asignar un rol distinto)
 
usuarios con rol "edicion" podran:
  * cargar, borrar y editar productos.
  * cargar, borrar y editar categorias.
    
usuarios con rol "actualizacion" podran:
  * editar la disponibilidad e imagen de los productos.
    
usuarios con rol "administrador" podran:
  * administar usuarios
  * ver timestamps de cuando los Productos y Categorias fueron creados/actualizados
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
  * Scrollear a traves del catagolo
  * Buscar algo especifico segun palabra clave
  * Ver productos de una categoria
  * Ordenar segun precio

Mientras podra ir agregando productos a un carrito y finalmente hacer una reserva.
