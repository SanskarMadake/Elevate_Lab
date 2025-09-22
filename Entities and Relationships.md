Entities and Relationships (E-commerce Database)
Entities
1. Users

Attributes:

user_id (PK)

name

email

phone

created_at

2. Categories

Attributes:

category_id (PK)

category_name

3. Products

Attributes:

product_id (PK)

name

price

stock

category_id (FK → Categories.category_id)

4. Orders

Attributes:

order_id (PK)

user_id (FK → Users.user_id)

order_date

status

5. Order_Items

Attributes:

order_item_id (PK)

order_id (FK → Orders.order_id)

product_id (FK → Products.product_id)

quantity

price

6. Payments

Attributes:

payment_id (PK)

order_id (FK → Orders.order_id, UNIQUE)

amount

payment_date

method

status

Relationships

Users → Orders

One User can place many Orders.

(1 : M relationship)

Orders → Order_Items → Products

One Order can contain many Products.

One Product can be in many Orders.

Implemented via Order_Items (junction table).

(M : M relationship)

Products → Categories

Each Product belongs to one Category.

(M : 1 relationship)

Orders → Payments

Each Order has exactly one Payment.

(1 : 1 relationship)