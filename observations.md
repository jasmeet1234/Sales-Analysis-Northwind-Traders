## Encoding Observations
* customers.csv: The file contain "latin-1" encoding rather than UTF-8
* products.csv: The file contain "latin-1" encoding rather than UTF-8

---

# Table Schemas

## Schema for table: `categories`

# Table Schemas

## Schema for table: `categories`

| column_name   | column_type   | null   | key   | default   | extra   |
|:--------------|:--------------|:-------|:------|:----------|:--------|
| categoryID    | BIGINT        | YES    |       |           |         |
| categoryName  | VARCHAR       | YES    |       |           |         |
| description   | VARCHAR       | YES    |       |           |         |

## Schema for table: `customers`

| column_name   | column_type   | null   | key   | default   | extra   |
|:--------------|:--------------|:-------|:------|:----------|:--------|
| customerID    | VARCHAR       | YES    |       |           |         |
| companyName   | VARCHAR       | YES    |       |           |         |
| contactName   | VARCHAR       | YES    |       |           |         |
| contactTitle  | VARCHAR       | YES    |       |           |         |
| city          | VARCHAR       | YES    |       |           |         |
| country       | VARCHAR       | YES    |       |           |         |

## Schema for table: `employees`

| column_name   | column_type   | null   | key   | default   | extra   |
|:--------------|:--------------|:-------|:------|:----------|:--------|
| employeeID    | BIGINT        | YES    |       |           |         |
| employeeName  | VARCHAR       | YES    |       |           |         |
| title         | VARCHAR       | YES    |       |           |         |
| city          | VARCHAR       | YES    |       |           |         |
| country       | VARCHAR       | YES    |       |           |         |
| reportsTo     | BIGINT        | YES    |       |           |         |

## Schema for table: `order_details`

| column_name   | column_type   | null   | key   | default   | extra   |
|:--------------|:--------------|:-------|:------|:----------|:--------|
| orderID       | BIGINT        | YES    |       |           |         |
| productID     | BIGINT        | YES    |       |           |         |
| unitPrice     | DOUBLE        | YES    |       |           |         |
| quantity      | BIGINT        | YES    |       |           |         |
| discount      | DOUBLE        | YES    |       |           |         |

## Schema for table: `orders`

| column_name   | column_type   | null   | key   | default   | extra   |
|:--------------|:--------------|:-------|:------|:----------|:--------|
| orderID       | BIGINT        | YES    |       |           |         |
| customerID    | VARCHAR       | YES    |       |           |         |
| employeeID    | BIGINT        | YES    |       |           |         |
| orderDate     | DATE          | YES    |       |           |         |
| requiredDate  | DATE          | YES    |       |           |         |
| shippedDate   | DATE          | YES    |       |           |         |
| shipperID     | BIGINT        | YES    |       |           |         |
| freight       | DOUBLE        | YES    |       |           |         |

## Schema for table: `products`

| column_name     | column_type   | null   | key   | default   | extra   |
|:----------------|:--------------|:-------|:------|:----------|:--------|
| productID       | BIGINT        | YES    |       |           |         |
| productName     | VARCHAR       | YES    |       |           |         |
| quantityPerUnit | VARCHAR       | YES    |       |           |         |
| unitPrice       | DOUBLE        | YES    |       |           |         |
| discontinued    | BIGINT        | YES    |       |           |         |
| categoryID      | BIGINT        | YES    |       |           |         |

## Schema for table: `shippers`

| column_name   | column_type   | null   | key   | default   | extra   |
|:--------------|:--------------|:-------|:------|:----------|:--------|
| shipperID     | BIGINT        | YES    |       |           |         |
| companyName   | VARCHAR       | YES    |       |           |         |

---



# Data Dictionary

| table        | field           | description                                                                                      |
|:--------------|:----------------|:-------------------------------------------------------------------------------------------------|
| orders        | orderID         | Unique identifier for each order                                                                 |
| orders        | customerID      | The customer who placed the order                                                                |
| orders        | employeeID      | The employee who processed the order                                                             |
| orders        | orderDate       | The date when the order was placed                                                               |
| orders        | requiredDate    | The date when the customer requested the order to be delivered                                   |
| orders        | shippedDate     | The date when the order was shipped                                                              |
| orders        | shipperID       | The ID of the shipping company used for the order                                                |
| orders        | freight         | The shipping cost for the order (USD)                                                            |
| order_details | orderID         | The ID of the order this detail belongs to                                                       |
| order_details | productID       | The ID of the product being ordered                                                              |
| order_details | unitPrice       | The price per unit of the product at the time the order was placed (USD - discount not included) |
| order_details | quantity        | The number of units being ordered                                                                |
| order_details | discount        | The discount percentage applied to the price per unit                                            |
| customers     | customerID      | Unique identifier for each customer                                                              |
| customers     | companyName     | The name of the customer's company                                                               |
| customers     | contactName     | The name of the primary contact for the customer                                                 |
| customers     | contactTitle    | The job title of the primary contact for the customer                                            |
| customers     | city            | The city where the customer is located                                                           |
| customers     | country         | The country where the customer is located                                                        |
| products      | productID       | Unique identifier for each product                                                               |
| products      | productName     | The name of the product                                                                          |
| products      | quantityPerUnit | The quantity of the product per package                                                          |
| products      | unitPrice       | The current price per unit of the product (USD)                                                  |
| products      | discontinued    | Indicates with a 1 if the product has been discontinued                                          |
| products      | categoryID      | The ID of the category the product belongs to                                                    |
| categories    | categoryID      | Unique identifier for each product category                                                      |
| categories    | categoryName    | The name of the category                                                                         |
| categories    | description     | A description of the category and its products                                                   |
| employees     | employeeID      | Unique identifier for each employee                                                              |
| employees     | employeeName    | Full name of the employee                                                                        |
| employees     | title           | The employee's job title                                                                         |
| employees     | city            | The city where the employee works                                                                |
| employees     | country         | The country where the employee works                                                             |
| employees     | reportsTo       | The ID of the employee's manager                                                                 |
| shippers      | shipperID       | Unique identifier for each shipper                                                               |
| shippers      | companyName     | The name of the company that provides shipping services                                          |
