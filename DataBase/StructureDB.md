### **Database Structure:**  

#### **Users (users)**  
- **id**: Unique identifier  
- **name**: User's name  
- **email**: Email address (unique)  
- **password_hash**: Secure password  
- **role**: User role (admin, manager, employee)  
- **service_id**: The department/service the employee belongs to  
- **created_at**: Account creation date  

---

#### **Services (services)**  
- **id**: Unique identifier  
- **name**: Service/Department name  
- **description**: Service description  

---

#### **Customers (customers)**  
- **id**: Unique identifier  
- **name**: Customer's name  
- **email**: Email address (unique)  
- **phone**: Phone number  
- **address**: Customer's address  
- **created_at**: Registration date  

---

#### **Products (products)**  
- **id**: Unique identifier  
- **name**: Product name  
- **description**: Product description  
- **price**: Unit price  
- **stock_quantity**: Available stock quantity  
- **supplier_id**: Supplier of the product  
- **created_at**: Product addition date  

---

#### **Suppliers (suppliers)**  
- **id**: Unique identifier  
- **name**: Supplier name  
- **email**: Email address (unique)  
- **phone**: Phone number  
- **address**: Supplier's address  
- **created_at**: Registration date  

---

#### **Orders (orders)**  
- **id**: Unique identifier  
- **customer_id**: Customer who placed the order  
- **user_id**: Employee who processed the order  
- **total_price**: Total amount  
- **status**: Order status (pending, processing, shipped, completed, canceled)  
- **created_at**: Order date  

---

#### **Order Items (order_items)**  
- **id**: Unique identifier  
- **order_id**: Related order  
- **product_id**: Ordered product  
- **quantity**: Ordered quantity  
- **price**: Product price at purchase  

---

#### **Inventory (inventory)**  
- **id**: Unique identifier  
- **product_id**: Related product  
- **quantity**: Available stock quantity  
- **last_updated**: Last update date  

---

#### **Payments (payments)**  
- **id**: Unique identifier  
- **order_id**: Related order  
- **amount**: Paid amount  
- **payment_method**: Payment method (credit card, PayPal, bank transfer, cash)  
- **payment_status**: Payment status (pending, completed, failed)  
- **created_at**: Payment date  

---

#### **Employee Schedules (employee_schedule)**  
- **id**: Unique identifier  
- **user_id**: Related employee  
- **event_name**: Name of the scheduled event  
- **event_date**: Date of the event  
- **start_time**: Event start time  
- **end_time**: Event end time  
- **created_at**: Date the event was added  

---

#### **1.1 Messages (messages)**  
- **id**: Unique identifier  
- **sender_id**: User who sent the message  
- **receiver_id**: User who received the message  
- **subject**: Message subject  
- **message**: Message content  
- **sent_at**: Date and time the message was sent  
- **is_read**: Status indicating if the message has been read  

---

#### **1.2 Conversations (conversations)**  
- **id**: Unique identifier  
- **user1_id**: First participant in the conversation  
- **user2_id**: Second participant in the conversation  
- **created_at**: Date and time when the conversation was created  

---

#### **1.3 Conversation Messages (conversation_messages)**  
- **id**: Unique identifier  
- **conversation_id**: Related conversation  
- **sender_id**: User who sent the message  
- **message**: Message content  
- **sent_at**: Date and time the message was sent  

---

### **Relationships between tables:**  
- **Each employee (users) is assigned to a department/service (services).**  
- **A customer (customers) can place multiple orders (orders).**  
- **An employee (users) can manage multiple orders (orders).**  
- **An order (orders) contains multiple products (order_items).**  
- **A product (products) belongs to a supplier (suppliers).**  
- **Each order (orders) is linked to a payment (payments).**  
- **Each employee (users) has a personal schedule (employee_schedule).**  
- **Users (users) can send and receive messages (messages).**  
- **Users (users) can have direct conversations (conversations), and multiple messages are linked to a conversation (conversation_messages).**  
