# Azani ISP Information System

## E-R Diagram

```mermaid
erDiagram
customer ||--o{ product : "has"
customer_product }o--|| customer : "belongs to"
customer_product }o--|| payment : "belongs to"

product {
    integer id
    string name    
    string category
    double cost
}

customer {
    integer id
    string name
    string contact_name
    string phone
    string email
}

payment {
    integer id
    integer product_id
    integer customer_id
    string quantity
    double total_amount
}

customer_product {
    interger id
    integer customer_id
    integer product_id
    double date
    double total_cost
}
```
