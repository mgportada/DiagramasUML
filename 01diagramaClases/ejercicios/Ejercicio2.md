# Ejercicio 2

Se desea modelar un sistema de gestión de órdenes de compra en una tienda en línea.

- Cada orden de compra está representada por la clase 'Orden', que contiene información como el ID de la orden, el cliente que realizó la compra, los detalles de los artículos comprados, el estado actual de la orden, el método de pago utilizado y el monto total de la orden.
- Cada detalle de orden, representado por la clase 'DetallesOrden', incluye información sobre el artículo comprado, la cantidad y el subtotal.
- Los artículos disponibles para la compra están representados por la clase 'Artículo'.
- Los clientes que realizan las compras están representados por la clase 'Cliente', que incluye información como el ID del cliente, el nombre, el correo electrónico, la dirección y el teléfono.

- El proceso de pago se maneja mediante la clase 'Pago'
  - El pago puede ser de diferentes tipos, como 'PagoConTarjeta' o 'PagoEnEfectivo'. Cada tipo de pago tiene sus propios atributos y métodos específicos.

Las direcciones de origen y destino de la orden están representadas por la clase 'Dirección'.

Las asociaciones entre las clases indican la relación entre ellas, como la relación entre:

- una orden y sus detalles
- una orden y su estado
- una orden y un cliente
- una orden y un pago
- una orden y las direcciones de origen y destino
