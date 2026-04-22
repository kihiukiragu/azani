# Azani ISP Information System

## E-R Diagram

```mermaid
erDiagram
    institution ||--o{ invoice : places
    invoice ||--o{ invoice_item : contains
    invoice ||--o{ invoice_adjustment : "has"
    invoice ||--o{ payment : "settled by"
    product ||--o{ invoice_item : "is part of"

    invoice_adjustment {
        integer id PK
        integer invoice_id FK
        string type "Surcharge, Reconnection, Discount"
        double amount
        string description
    }

    institution {
        integer id PK
        string name
        string contact_name
        string phone
        string email
        string address
    }

    product {
        integer id PK
        string name
        double price
    }

    invoice {
        integer id PK
        integer customer_id FK
        datetime order_date
        double total_amount
        string status "e.g., Pending, Completed, Overdue"
    }

    invoice_item {
        integer id PK
        integer order_id FK
        integer product_id FK
        integer quantity
        double unit_price
    }

    payment {
        integer id PK
        integer order_id FK
        double amount_paid
        datetime payment_date
        datetime due_date
    }
```
