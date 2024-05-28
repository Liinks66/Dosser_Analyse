# Entités

Les entités de l'application warehouse-stock-app sont:

```mermaid
classDiagram
    Employee "1" <--> "0..*" Product
    Employee "1" <--> "0..*" TransferOrder
    Employee "1" <--> "0..*" SupplierDetail
    SupplierDetail "1" <--> "0..*" TransferOrder
    Brand "1" <--> "0..*" TransferOrder
    Employee "1" <--> "1" SupplierDetail

    class Employee {
        id: int
        firstName: String
        lastName: String
        mailAddress: String
        phoneNumber: String
        position: String
        
    }

    class Product {
        id: int
        weight: int
        lenght: int
        width: int
        height: int
        creationDate: LocalDate
        modificationDate: LocalDate
        isActive: boolean
        employeeId: int
        modificationEmployeeId: int
        
    }

    class TransferOrder {
        id: int
        name: String
        creationDate: LocalDate
        modificationDate: LocalDate
        comments: String
        isShipped: boolean
        brandId: int
        supplierDetailId: int
        employeeId: int
        modificationEmployeeId: int
    }

       class SupplierDetail {
        id: int
        country: String
        isActive: boolean
        address: String
        city: String
        brandId: int
        creationDate: LocalDate
        modificationDate: LocalDate
        
    }

    class Brand{
        id: int
        name: String
    }