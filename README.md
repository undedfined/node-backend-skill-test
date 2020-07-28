# Back End skill-test

Hola y bienvenidx a esta prueba de habilidades, en esta ocasión mediremos tus habilidades como desarrolladorx Back End desarrollando una API REST para ser utilizada en una "tienda de tarjetas coleccionables".

![](https://media0.giphy.com/media/RyXVu4ZW454IM/200.gif)

Los puntos que estaremos evaluando en esta prueba serán:

- Habilidad usando NodeJS y MongoDB
- Creatividad en el diseño de la REST API
- Modelado de la base de datos
- Legibilidad del código
- Estructura del proyecto
- Documentación del API

## Descripción

En esta prueba estarás creando una API REST para una "tienda de tarjetas coleccionables", algo similar a una tienda en línea pero solo de un tipo de Item. Tendrás que diiseñar y posteriormente desarrollar la funcionalidad necesaria para que la aplicación cumpla con las siguientes características:

- Registro y login de usuarios
- Usuario registra un nuevo item para su venta
- Usuario consulta items de otros usuarios (catálogo de tarjetas)
- Usuario consulta información de una tarjeta en específico
- Usuario consulta items propios (inventario)
- Usuario realiza "compra" de una tarjeta a otro usuario (emular)
- Usuario consulta historial de compras
- Usuario consulta historial de ventas

##### A tomar en cuenta:

- Las acciones descritas anteriormente solo podrán ser ejecutadas por un usuario autenticado
- Las consultas a inventario, catálogo e historial de ventas/compras al menos deberán contar con un filtro opcional
- No hay un concepto como "saldo" o "metodo de pago" en esta prueba, imagina que el cobro a realizar por cada pago es meramente simbólico pero aún así deberá tener representación en tu modelo de datos.

A continuación se describen dos ejemplos de petición que podrían ayudarte a tener una idea más clara de como representar la documentación y como atacar y resolver este problema: 

> Nueva tarjeta
> Añade un nuevo item/tarjeta disponible para catálogo de venta e inventario de usuario.

* URL
/item

* Method: 
POST

* Body:
```json
    {
        "title": "El Mago Oscuro",
        "rarityId": "XXXXYYYYZZZZ",
        "price": 80.00,
        "img": "data:image/png;base64,iVBORw0 ...",
        "etc": "etcétera",
        "...": "...",
        "...": "...",
    }
```

* Response:
```json
{
    "success": true,
    "item": {
        "_id": "XXXXYYYYZZZZ",
        "title": "El Mago Oscuro",
        "rarity": {
            "_id": "XXXXYYYYZZZZ",
            "value": "Common",
        },
        "imgUrl": "https://hipertextual.com/files/2015/03/rickroll.jpg",
        "price": 80.00,
        "user": {
            "_id": "XXXXYYYYZZZZ",
            "name": "Aaaaa Mssss",
            "email": "mail@example.com",
            "etc": "etcétera",
            "...": "...",
            "...": "...",
        },
        "etc": "etcétera",
        "...": "...",
        "...": "...",
    }
}
```

> Inventario
> Retorna todos los items dentro del inventario del usuario que ejecuta esta petición.

* URL
/inventory

* URL params
rarity=[string] (optional)
category=[string] (optional)

* Method: 
GET

* Response
```json
[
    {
        "_id": "XXXXYYYYZZZZ",
        "title": "El Mago Oscuro",
        "rarity": {
            "_id": "XXXXYYYYZZZZ",
            "value": "Common",
        },
        "imgUrl": "https://hipertextual.com/files/2015/03/rickroll.jpg",
        "price": 80.00,
        "user": {
            "_id": "XXXXYYYYZZZZ",
            "name": "Aaaaa Mssss",
            "email": "mail@example.com",
            "etc": "etcétera",
            "...": "...",
            "...": "...",
        },
        "etc": "etcétera",
        "...": "...",
        "...": "...",
    },
    { "...": "..." },
    { "...": "..." },
    { "...": "..." }
]
```

## Reglas

- Máximo de 5 días naturales para la entrega
- La aplicación deberá ser codificada usando las tecnologías descritas anteriormente (NodeJS y MongoDB)
- Puedes utilizar Express o Sails para la construcción del API REST
- Puedes utilizar Mongoose o cualquier otra librería para establecer conexión con la base de datos desde NodeJS
- El proyecto deberá entregarse en un repositorio con un manual de uso y ejecución

## Recomendaciones

- Desplegar en heroku / firebase functions / etc. suma puntos!
- Has código legible y bien documentado!
- Sé lo más creativo posible!

#### Buena suerte :) 
