@startuml

abstract class Vehiculo {
    - matricula: String
    - marca: String
    - modelo: String
    - añoFabricacion: int
    - kilometraje: int
    - precio: double
    - estado: Estado
    - propietario: Persona

    + calcularRiesgo(): String
    + imprimirDatos(): void
}

abstract class Coche {
    - numPuertas: int
    - tipoCombustible: Combustible
    - capacidadMaletero: int
    - traccion: Traccion
}

class Sedan {
    - espacioInterior: double
    - nivelConfort: Confort
}

class Suv {
    - capacidadOffroad: boolean
    - alturaLibreSuelo: double
}

class Deportivo {
    - aceleracion0a100: double
    - potenciaCV: int
    - tieneModoPista: boolean
}

abstract class Moto {
    - cilindrada: int
    - peso: int
    - alturaAsiento: double
    - tipoTransmision: Transmision
}

class Scooter {
    - espacioBajoAsiento: int
}

class MotoDeportiva {
    - velocidadMaxima: double
    - tieneQuickShifter: boolean
}

class Camion {
    - capacidadCarga: double
    - numEjes: int
    - longitudRemolque: double
    - potenciaMotor: int
}

class Persona {
    - nombreApellidos: String
    - dni: String
    - fechaCaducidadCarnet: Date
    - añoNacimiento: int
}

interface Valorable {
    + calcularDepreciacion(): double
}


Vehiculo "1" *-- "0..1" Coche
Vehiculo "1" *-- "0..1" Moto
Vehiculo "1" *-- "0..1" Camion




Vehiculo "1" --> "0..1" Persona : es propietario
Vehiculo "1" ..|> "0..1" Valorable

Coche "1" <|-- "0..1" Sedan
Coche "1" <|-- "0..1" Suv
Coche "1" <|-- "0..1" Deportivo

Moto "1" <|-- "0..1" Scooter
Moto "1" <|-- "0..1" MotoDeportiva

@enduml# UT5_ED_Prog
