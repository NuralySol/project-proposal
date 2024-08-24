# DashAndDeliver App

## User Story

### MVP

### 1. Guest User Orders
- Story 1:
As a guest user,
I want to browse the menu and place an order without signing in,
So that I can quickly order food without creating an account.

- Story 2:
As a guest user,
I want to see the fees applied to my order at checkout,
So that I understand the additional costs associated with not signing in.

- Story 3:
As a guest user,
I want to receive an order confirmation after placing an order,
So that I know my order was successfully placed.

- Story 4:
As a guest user,
I want to filter the available restaurants and dishes by region,
So that I can see options that are available for delivery to my location.

- Story 5:
As a guest user,
I want to add items from multiple restaurants to my order,
So that I can order from different places in a single transaction.
I want to be able to edit my order/delete items.

### 2. Sign-Up/Sign-In User Experience
- Story 1:
As a user,
I want to sign up or sign in easily,
So that I can access benefits like fee waivers and priority service.

- Story 2:
As a user,
I want to be reminded of the benefits of signing up when I try to place an order as a guest,
So that I am encouraged to create an account for better service.

- Story 3:
As a signed-in user,
I want my preferred region to be remembered,
So that I can quickly see food options available in my area without re-selecting my region each time.

- Story 4:
As a signed-in user,
I want to add items from multiple restaurants to my order,
So that I can order from different places in a single transaction.

### 3. Signed-In User Orders
- Story 1:
As a signed-in user,
I want to place an order with waived delivery fees,
So that I can save money compared to guest users.

- Story 2:
As a signed-in user,
I want my orders to be prioritized,
So that I receive faster service compared to non-signed-in users.

- Story 3:
As a signed-in user,
I want to track my order and see its priority status,
So that I know when to expect my delivery.

- Story 4:
As a signed-in user,
I want to receive personalized recommendations based on my region and past orders,
So that I can discover new restaurants and dishes in my area.

- Story 6:
As a signed-in user,
I want to be able to delete my order if I change my mind,
So that I am not charged for an order I no longer want.

### 5. User Notifications
- Story 1:
As a signed-in user,
I want to receive notifications when my order is being prepared and when it’s out for delivery,
So that I am informed about the status of my order.

- Story 2:
As a guest user,
I want to receive a confirmation of my order details,
So that I have a record of my purchases.

### 6. Fee Management
- Story 1:
As a system,
I want to automatically apply fees to guest users at checkout,
So that they are charged appropriately for their orders.

- Story 2:
As a system,
I want to waive fees for signed-in users at checkout,
So that they receive the benefits of being a registered user.


## Stretch Goals

- **Pre-Order Scheduling:** Allow customers to schedule their orders well in advance, not just for immediate delivery. This could be useful for planning meals around specific events or times.

- **Enhanced Dietary Filters:** Provide more detailed filters for dietary preferences, allergies, and nutritional information, allowing customers to find meals that precisely meet their needs.

- **Detailed Nutritional Profiles:** Include comprehensive nutritional information for each menu item, such as calorie count, macronutrients (carbohydrates, proteins, fats), micronutrients (vitamins and minerals), and allergens. This could help customers make healthier choices and manage dietary needs.

- **Integrating an AI chat feature:** Personalized assistance, offer tailored menu recommendations and dietary guidance based on user preferences and health needs, provide nutritional advice and suggest healthier alternatives based on user data and preferences, etc.

## Team Expectations

[Team Expectations](https://docs.google.com/document/d/1cJsnRTeMD8zwStb7M6jFdcLx1ro5UoGyzrmQ1iOCzB0/edit?usp=sharing)

## Wireframe

<details>

![Food Delivery App Frame1](./Wireframe%20Food%20Delivery%20App%20-%20Frame%201.jpg)
![Food Delivery App Frame2](./Wireframe%20Food%20Delivery%20App%20-%20Frame%202.jpg)
![Food Delivery App Frame3](./Wireframe%20Food%20Delivery%20App%20-%20Frame%203.jpg)
![Food Delivery App Frame4](./Wireframe%20Food%20Delivery%20App%20-%20Frame%204.jpg)
![Food Delivery App Restaurant Choice](./Wireframe%20Food%20Delivery%20App%20-%20Frame%205.jpg)

</details>

## ERD

> This the ERD for food delivery app which includes all the data types, and relationships. It also includes our stretch goals.
> ![Food Delivery App ERD](./Food%20Delivery%20App%20ERD%20-%20ERD%20Table.jpg)

## Routes for the App
<details>

| **Route**                 | **HTTP Method** | **Description**                                        |
| ------------------------- | --------------- | ------------------------------------------------------ |
| **Users**                 |                 |                                                        |
| `/users`                  | GET             | Retrieve a list of all users.                          |
| `/users/:id`              | GET             | Retrieve details of a specific user by ID.             |
| `/users`                  | POST            | Create a new user.                                     |
| `/users/:id`              | PUT             | Update an existing user by ID.                         |
| `/users/:id`              | DELETE          | Delete a user by ID.                                   |
| **Addresses**             |                 |                                                        |
| `/addresses`              | GET             | Retrieve a list of all addresses.                      |
| **Customer Addresses**    |                 |                                                        |
| `/customer-addresses`     | GET             | Retrieve a list of all customer addresses.             |
| `/customer-addresses/:id` | GET             | Retrieve details of a specific customer address by ID. |
| `/customer-addresses`     | POST            | Create a new customer address.                         |
| `/customer-addresses/:id` | PUT             | Update an existing customer address by ID.             |
| `/customer-addresses/:id` | DELETE          | Delete a customer address by ID.                       |
| **Restaurants**           |                 |                                                        |
| `/restaurants`            | GET             | Retrieve a list of all restaurants.                    |
| `/restaurants/:id`        | GET             | Retrieve details of a specific restaurant by ID.       |
| **Menu Items**            |                 |                                                        |
| `/menu-items`             | GET             | Retrieve a list of all menu items.                     |
| **Food Orders**           |                 |                                                        |
| `/food-orders`            | GET             | Retrieve a list of all food orders.                    |
| `/food-orders/:id`        | GET             | Retrieve details of a specific food order by ID.       |
| `/food-orders`            | POST            | Create a new food order.                               |
| **Order Menu Items**      |                 |                                                        |
| `/order-menu-items`       | GET             | Retrieve a list of all order menu items.               |
| `/order-menu-items/:id`   | GET             | Retrieve details of a specific order menu item by ID.  |
| **Order Status**          |                 |                                                        |
| `/order-status`           | GET             | Retrieve a list of all order statuses.                 |
| `/order-status/:id`       | GET             | Retrieve details of a specific order status by ID.     |

</details>

## Basic Schemas

```Javascript 
const UserSchema = new Schema({
  name: {
    type: String,
    required: true,
  },
  password: {
    type: String,
    required: true,
  },
});

const RestaurantSchema = new Schema({
  name: {
    type: String,
    required: true,
  },
  address: {
    type: String,
    required: true,
  },
  phone: {
    type: Number,
    required: true,
  },
}); 
Javascript
```

## Timeline

## August 24, 2024 (Saturday)

- Research API's, create a proposal and start brain-storming!

## August 25, 2024 (Sunday)

- Create folder structure and work on the skeleton of the project.

## August 26, 2024 (Monday)

- Create a basic mock up of the project and create the Mongo Database.

## August 27, 2024 (Tuesday)

- Work on implementing CRUD operations and routes.

## August 28, 2024 (Wednesday)

- Work on user stories and attempt to deploy.

## August 29, 2024 (Thursday)

- Work on user stories.

## August 30, 2024 (Friday)

- Create CSS files and work on the aesthetics of the pages.

## August 31, 2024 (Saturday)

- Work on CSS and complete user stories.

## September 1, 2024 (Sunday)

- Work on CSS and add any finishing touches.

## September 2, 2024 (Monday)

- Add any finishing touches, make sure project is completely debugged, functional and ready.

## September 3, 2024 ​⬤ (Tuesday)​⬤

- Presentation day

## Technologies used
MERN Stack (MongoDB, Express, React, Node.JS/Javascript)

