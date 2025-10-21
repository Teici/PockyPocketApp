# PockyPocket

## 1. Short Description

PockyPocket is a simple mobile app that helps people manage their personal finances more easily. It is designed for anyone who wants to keep track of their spending, shopping lists, and budgets without needing to understand technical or complicated tools. The app lets users write down their daily expenses, plan how much they want to spend, keep a list of items they want to buy, and track their subscriptions. It works even without internet, and when the phone goes online again, all data is safely synchronized with a server. The main goal is to make everyday money management clear, fast, and stress-free.


## 2. Domain Details

The app uses five main entities: **Expense**, **Item**, **BudgetItem**, **Product**, and **Subscription**.
Each entity has several fields, with a clear explanation of their purpose.

### 2.1 Expense

* **id**: Unique identifier for the expense.
* **title**: A short name for the expense (for example “Groceries”).
* **amount**: The amount of money spent.
* **category**: The category of spending (for example Food, Transport, etc.).
* **date**: The date of the expense.
* **notes**: Optional extra information.
* **createdAt / updatedAt**: Timestamps used to keep track of when data was changed.

### 2.2 Item (Shopping List)

* **id**: Unique identifier.
* **name**: The name of the item to buy.
* **quantity**: How many units are needed.
* **price**: Optional estimated price per unit.
* **bought**: Yes or No, depending on whether the item was purchased.
* **store**: Optional store name.
* **notes**: Optional extra information.
* **createdAt / updatedAt**: Timestamps for syncing.

### 2.3 BudgetItem

* **id**: Unique identifier.
* **category**: The category the budget applies to.
* **limit**: The maximum amount allowed for the period.
* **spent**: The current total spent in this category.
* **startDate / endDate**: The period the budget covers.
* **notes**: Optional notes.
* **createdAt / updatedAt**: Timestamps.

### 2.4 Product (Wishlist)

* **id**: Unique identifier.
* **name**: The name of the product.
* **price**: Optional target or current price.
* **store**: Optional store name.
* **priority**: Priority level (Low, Medium, High).
* **notes**: Optional notes.
* **createdAt / updatedAt**: Timestamps.

### 2.5 Subscription

* **id**: Unique identifier.
* **name**: The name of the subscription (for example “Netflix”).
* **amount**: Monthly or yearly cost.
* **renewalDate**: When it renews.
* **category**: For example “Entertainment”.
* **status**: Active, Paused, or Cancelled.
* **notes**: Optional notes.
* **createdAt / updatedAt**: Timestamps.


## 3. CRUD Operations

The app supports Create, Read, Update, and Delete for each entity.

### Expense

* **Create**: Add a new expense with title, amount, category, and date.
* **Read**: View all expenses in a list, filter by category or date, and open details.
* **Update**: Change amount, category, date, or notes.
* **Delete**: Mark the expense as deleted (soft delete).

### Item

* **Create**: Add a shopping item with name and quantity.
* **Read**: View shopping list, filter by store, and check off items when bought.
* **Update**: Edit item details or mark as bought.
* **Delete**: Remove item (soft delete).

### BudgetItem

* **Create**: Add a new budget with category, limit, and date range.
* **Read**: View all budgets and see progress.
* **Update**: Edit limits or date range.
* **Delete**: Mark as deleted.

### Product (Wishlist)

* **Create**: Add a new wishlist item.
* **Read**: View wishlist and filter by priority or store.
* **Update**: Change price, priority, or notes.
* **Delete**: Mark as deleted.

### Subscription

* **Create**: Add a subscription with amount, category, and renewal date.
* **Read**: See upcoming renewals and active subscriptions.
* **Update**: Change status, amount, or date.
* **Delete**: Cancel subscription (soft delete).



## 4. Persistence Details (Local and Server)

The app uses a local database so it works without internet. When a connection is available, the data is also saved on the server.

| Operation | Local DB | Server |
| --------- | :------: | :----: |
| Create    |    Yes   |   Yes  |
| Read      |    Yes   |   Yes  |
| Update    |    Yes   |   Yes  |
| Delete    |    Yes   |   Yes  |

All operations are stored locally first and synchronized with the server later if necessary.


## 5. Offline Scenarios

The app can be used offline without losing data. When the device connects to the internet again, the changes are sent to the server.

* **Create**: If a user adds a new expense, item, or subscription offline, it is stored locally and marked as pending. When online again, the app sends it to the server automatically.
* **Read**: Lists and details of expenses, items, and other entities are loaded directly from the local database even when offline.
* **Update**: If an entry is updated offline, the changes are stored locally and synced when the connection returns.
* **Delete**: If an entry is deleted offline, it is marked locally and the server is updated later.


## 6. App Mockup

Two mockup screens have been created using Figma

1. **List screen** – shows lists of expenses, items, and other entries.
2. **Add/Edit screen** – used to create or modify entries.
<img width="336" height="413" alt="image" src="https://github.com/user-attachments/assets/8fb9924f-0b5e-4b55-a3a7-96da126b23cc" />
<img width="240" height="293" alt="image" src="https://github.com/user-attachments/assets/8cccdf09-2125-44e6-b7b1-d5ca786f32a8" />



