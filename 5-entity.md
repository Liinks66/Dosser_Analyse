# Entités

Les entités de l'application warehouse-stock-app sont:

```mermaid
classDiagram
    Employee "1" <-"create"-> "0..*" Product
    Employee "1" <--> "0..*" TransferOrder
    Employee "1" <--> "0..*" SupplierDetail
    SupplierDetail "1" <--> "0..*" TransferOrder
    Brand "1" <--> "0..*" TransferOrder
    Brand "1" <--> "1" SupplierDetail
    Employee "1.create"<--> "0..*" ManagedObject
    Employee "1.modify"<--> "0..*" ManagedObject
    ManagedObject <|-- Product
    ManagedObject <|-- SupplierDetail
    ManagedObject <|-- TransferOrder
    Employee "1" <--> "0..*" Product
    Employee "1" <--> "0..*" SupplierDetail
    Employee "1" <--> "0..*" TransferOrder

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
        
        
    }

    class TransferOrder {
        id: int
        creationDate: LocalDate
        modificationDate: LocalDate
        comments: String
        isShipped: boolean
    }

       class SupplierDetail {
        id: int
        country: String
        isActive: boolean
        address: String
        city: String
        
    }

    class Brand{
        id: int
        name: String
    }
    class ManagedObject{
        creationDate: LocalDate
        modificationDate: LocalDate
        employeeId: int
        modificationEmployeeId: int

    }
```


## Employee

La classe Employee représente un employé. Ses attributs sont:

- id : l'identifiant unique de l'employé
- firstName: prénom
- lastName : nom de famille
- mailAddress: email
- phoneNumber: numéro de téléphone
- position: le poste de l'employé

## Product

La classe représente un produit. Ses attributs sont:

- id: identifiant unique du produit
- weight: le poids
- lenght: la longueur
- width: la largeur
- height: la hauteur
- creationDate: date d'ajout du produit
- modificationDate: date de modification du produit
- isActive: permet de savoir si un produit est en vente ou non
- employeeId: référence vers l'employé qui a scanner le produit
- modificationEmployeeId: référence vers l'employé qui a modifié le produit   

## TransferOrder

La classe TransferOrder représente un OT. Ses attributs sont:

- id: identifiant unique de l'OT
- creationDate: date de création de l'OT
- modificationDate: date de modification de l'OT
- comments: commentaire lié à l'OT, il est facultatif
- isShipped: permets de savoir si un OT a été expédié
- brandId: référence vers la marque incluse dans l'OT
- supplierDetailId: référence vers le fournisseur inclus dans l'OT
- employeeId: référence vers l'employé qui a créé l'OT
- modificationEmployeeId: référence vers l'employé qui a modifié l'OT

## SupplierDetail

La classe SupplierDetail représente un fournisseur. Ses attributs sont:

- id: identifiant unique du fournisseur
- country: pays dans lequel se trouve le fournisseur
- isActive: permet de savoir si le fournisseur est actif
- address: adresse du fournisseur
- city: ville du fournisseur
- brandId: référence vers le nom de la marque
- creationDate: date d'ajout du fournisseur
- modificationDate: date de modification du fournisseur

## Brand

La classe SupplierDetail représente une marque. Ses attributs sont:
- id: identifiant unique de la marque
- name: nom de la marque







 
