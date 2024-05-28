# Entités

Les entités de l'application warehouse-stock-app sont:

```mermaid
classDiagram
    Employee "1" <--> "0..*" HolidayRequest
    HolidayRequest "0..*" --> "1" HolidayType

    class Employee {
        id: int
        firstName: String
        lastName: String
        userId: int
        mailAddress: String
        phoneNumber: String
        position: String
        
    }

    class ProductReference {
        id: int
        brand: String
        weight: int
        lenght: int
        width: int
        height: int
    }

    class HolidayType {
        id: int
        name: String
    }