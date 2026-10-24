# Class Diagram

## پروژه
سامانه هوشمند اتصال تعمیرکار موبایل به مشتری

```mermaid
classDiagram

class User {
  +id
  +name
  +phone
  +password
}

class Customer {
}

class Technician {
  +specialty
  +rating
}

class Admin {
}

class RepairRequest {
  +id
  +deviceModel
  +problem
  +status
  +cost
}

class Part {
  +id
  +name
  +price
}

class Review {
  +id
  +score
  +comment
}

User <|-- Customer
User <|-- Technician
User <|-- Admin

Customer "1" --> "*" RepairRequest : creates
Technician "1" --> "*" RepairRequest : repairs
RepairRequest "*" --> "*" Part : uses
Customer "1" --> "*" Review : writes
Technician "1" --> "*" Review : receives
```