# Proyecto Inicial - 🐄🧑‍🌾 shopping de la granja 🥩🥛

## Idea a Implementar 💡

La idea es realizar un aplicacion que permita administrar un catalogo de productos de la granja, donde se pueden buscar ciertos productos segun alguna palabra clave o caracteristica, y tambien reservar uno o varios productos usando un carrito de compras.

## Diagrama ER 👷
```mermaid
erDiagram
    PRODUCTO }o--|| CATEGORIA : pertenece
    PRODUCTO{
        int id
        boolean disponible
        string nombre
        float precioPorUnidad
    }
    CATEGORIA{
        int id
        string nombre
    }
```

## Actualizaciones a los datos ✏️

### Proyecto Framework PHP - Laravel

usuarios con rol "edicion" podran:
    * cargar, borrar y editar productos.
    * cargar, borrar y editar categorias.
    
usuarios con rol "actualizacion" podran:
    * editar la disponibilidad e imagen de los productos.
    
usuarios con rol "administrador" podran:
    * administar usuarios
    * lo mismo que el rol "edicion"

## Información del Servicio Web 📰

El Servicio Web permitira inspeccionar y reservar productos relacionados con la granja, se pueden buscar según:
  * Categoria
  * Precio -> mayor/menor
  * Palabra clave
  * Disponibilidad

## Visualización y Acceso a la Información 👀

### Proyecto Javascript - React/Vue

El usuario para buscar productos de la manera mas intuitiva posible, navegando con el mouse o ingresando texto podrá:
  * Scrollear a traves del catagolo
  * Buscar algo especifico segun palabra clave
  * Ver productos de una categoria
  * Ordenar segun precio

Mientras podra ir agregando productos a un carrito y finalmente hacer una reserva.
