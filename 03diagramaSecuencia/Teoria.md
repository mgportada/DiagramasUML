# UML - DIAGRAMA DE SECUENCIA

## Componentes

- **Objetos**: Actores (usuarios) y clases
  - El objeto aparecerá y desaparecerá en la linea vertical según este creado.
- **Linea de vida** (vertical)
  - Periodo activo del objeto.
- **Flujo de mensajes** (horizontal)
  - Linea continua: Flujo sincrono
  - Línea discontinua: Flujo asíncrono (respuestas)

## Ejemplo:

```plantUML
@startuml

participant User
participant Cajero
participant Banco

activate User
User -> Cajero: Inserta tarjeta
activate Cajero
Cajero -> User: Solicita PIN
deactivate Cajero

User -> Cajero: Introduce PIN
activate Cajero
Cajero -> Banco: VerificaPIN(PIN)
activate Banco
Banco -> Cajero: PIN válido
deactivate Banco

Cajero -> User: Muestra opciones
deactivate Cajero

User -> Cajero: Solicita dinero
activate Cajero
Cajero -> Banco: ActualizarSaldo(cantidad)
activate Banco
Banco -> Cajero: OK
deactivate Banco
Cajero -> User: Devuelve dinero
deactivate Cajero
deactivate Cajero
@enduml

```
