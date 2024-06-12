# fitnest
Fitness e-commerce for Encora Tech Titans 2024.

## Entity Relation Diagram

```mermaid
erDiagram
    USER ||--o{ ORDER : places
    ORDER ||--o{ ORDERITEM : contains
    PRODUCT ||--o{ ORDERITEM : included_in
    CATEGORY ||--o{ PRODUCT : categorizes
    PRODUCT ||--o{ REVIEW : receives
    USER ||--o{ REVIEW : writes
    ORDER ||--|{ PAYMENT : has

    USER {
        string id PK
        string username
        string email
        string password
        string address
    }

    PRODUCT {
        string id PK
        string name
        float price
        string description
        string imageUrl
        string categoryId FK
    }

    CATEGORY {
        string id PK
        string name
    }

    ORDER {
        string id PK
        string userId FK
        date orderDate
        float totalAmount
    }

    ORDERITEM {
        string id PK
        string orderId FK
        string productId FK
        int quantity
        float price
    }

    REVIEW {
        string id PK
        string userId FK
        string productId FK
        int rating
        string comment
    }

    PAYMENT {
        string id PK
        string orderId FK
        string paymentMethod
        date paymentDate
        float amount
    }

    USER ||--o{ ORDER : places
    ORDER ||--o{ ORDERITEM : contains
    PRODUCT ||--o{ ORDERITEM : included_in
    CATEGORY ||--o{ PRODUCT : categorizes
    PRODUCT ||--o{ REVIEW : receives
    USER ||--o{ REVIEW : writes
    ORDER ||--|{ PAYMENT : has
```
