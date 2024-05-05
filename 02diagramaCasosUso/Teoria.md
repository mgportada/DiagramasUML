# UML - DIAGRAMA CASOS DE USO

## Componentes

- **Actores**: Representan roles que interactúan con el sistema. Pueden ser personas, sistemas externos u otros sistemas.
- **Casos de Uso**: Representan las distintas formas en que los actores interactúan con el sistema para lograr un objetivo específico. Son acciones que el sistema realiza en respuesta a las solicitudes de los actores.

En un caso de uso puede invervenir varios actores. Estarán relacionados con una linea continua.

## Relación entre casos de uso

Un actor suele realizar de forma secuencial diferentes casos de usos interdependientes en un orden específicos:

### Include

Un caso A incluye realizar una llamada a un caso B para su ejecución.

```plantUML
@startuml

left to right direction
actor Cliente
Cliente --> (Realizar Pedido)
(Realizar Pedido) ..> (Login) : include
@enduml

```

### Extend

Un caso A puede hacer una llamado a caso B para su ejecución, si se cumple una condición.

```plantUML
@startuml

left to right direction
actor Cliente
Cliente --> (Realizar Pedido)
(Aplicar Descuento) ..> (Realizar Pedido) : (si codigo descuento)\nextend
@enduml
```

### Herencia

Un caso puede heredar un caso más genérico

```plantUML
@startuml

left to right direction
actor Cliente
Cliente --> (Pagar)
(Pagar con tarjeta) --|> (Pagar)
(Pagar con efectivo) --|> (Pagar)
@enduml
```

Un actor puede heredar los casos de uso de otro actor más genérico. Para luego añadir casos específicos.

```plantUML
@startuml

left to right direction

actor Cliente
actor ClienteVIP

Cliente --> (Compra ticket) : compra ticket
ClienteVIP --|> Cliente
ClienteVIP --> (snack gratis)

@enduml
```

## Ejemplo

```plantUML
@startuml

left to right direction

actor Vendedor as V
actor Huesped as H

rectangle "Sistema de Reservas" as S {
    usecase "Vender Reserva" as VR
    usecase "Confirmar Información de Pago" as CIP
    usecase "Consultar Disponibilidad" as CD
    usecase "Ingresar a la Sección de Habitaciones" as ISH
    usecase "Reservar" as R
    usecase "Seleccionar Fechas" as SF
    usecase "Aplicar Promoción" as CP
    usecase "Ingresar Información de Pago" as IIP
}

V --> VR
VR ..> CIP : include

H -> R
R ..> CD : include
CD ..> ISH: include
R ..> SF: include

CP ..>R : extend (si codigo)
IIP ..>R : include
@enduml

```
