# Reto2-POO-grupo-4

Para este reto, se eligió el caso de un edificio de apartamentos, modelado con clases como "Piso", "Apartamento" y clases específicas (heredadas de una clase general "Residente") para representar a las personas que pueden interactuar de manera cotidiana con el edificio, como los inquilinos y los trabajadores.

```mermaid
classDiagram
    class Edificio {
        +nombre : String
        +direccion : String
        +numeroPisos: int
    }
    class Piso {
        +numeroApartamentos : int
        +numeroDelPiso : int
    }
    class Apartamento {
        +numero : String
        +area : float
        +numeroHabitaciones : int
        +valorArriendo: int
        +numeroResidentes()
    }
    class Inquilino {
        +ingresos: int
        +contrato: string
        +fiador: String
        pagar()
    }
    class Administrador {
        +puesto: String
        +codigoTrabajador: int
        +salario: int
        +gestionarEdificio()
        +cobrarArriendo()
        +pagarDeuda()
        +solucionarInconvenientes()
    }
    class Seguridad {
        +puesto: String
        +codigoTrabajador: int
        +salario: int
        +mantenerSeguroEdificio()
        +permitirEntradas()
        +permitirSalidas()
        +VigilarEdificio()
    }
    class Limpieza {
        +puesto: String
        +codigoTrabajador: int
        +salario: int
        +mantenerLimpiezaEdificio()
    }
    class Residente {
        +nombre : String
        +identificacion: int
        +telefono : String
        +direccion: String
        +correo: String
    }

    Edificio *-- Piso : compuesto de
    Piso *-- Apartamento: compuesto de
    Apartamento o-- Inquilino : ocupado por
    Edificio o-- Administrador : administrado por
    Residente <|-- Administrador
    Residente <|-- Seguridad
    Residente <|-- Limpieza
    Residente <|-- Inquilino

```
