# Ejercicio1

Crea el diagrama de secuencia de un usuario que quiere reservar un libro con la aplicación de la biblioteca.

El usuario primero debe poder buscar usando el servicio Catálogo.
El servicio catálogo comprobará si el libro está disponible en la base de datos.
El usuario podrá reservar el libro usando el servicio Reserva.
El servicio Reserva llamará al servicio pago para realizar el pago.
El servicio catálogo imprimirá el recibo.
