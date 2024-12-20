# Welcome to EasyShop!
 ## Description: 
EasyShop is a solo development of an E-Commerce API that focuses on managing categories,
along with products, shopping carts, user profiles, and orders. The platform makes it easy
to organize products into categories, retrieve category details, and update or delete them
as needed. Built using Java, Spring Boot, and MySQL.

## Features
EasyShop includes a powerful category management feature with the following capabilities:
    Create Categories: Allows you to add new categories to organize products.
    Retrieve Categories: View all categories or details of a specific category.
    Update Categories: Modify category names or descriptions as needed.
    Delete Categories: Remove categories that are no longer needed.

# Categories Endpoints
## 1. Get All Categories
    GET /categories
    Returns a list of all categories.
![Getall.png](capstone-starter%2Fdatabase%2FPhotos%2FGetall.png)

## 2.Get Category by ID
    GET /categories/{id}
    Returns details of a specific category. 
![get1.png](capstone-starter%2Fdatabase%2FPhotos%2Fget1.png)

## 3. Create a Category
    POST /categories Request Body:
    Only users with the admin role can create, and this action requires an authentication token. 
![Createinsert.png](capstone-starter%2Fdatabase%2FPhotos%2FCreateinsert.png)

## 4. Update a Category  
    PUT /categories/{id} Request Body:
    Only users with the admin role can update, and this action requires an authentication token. 
![Update.png](capstone-starter%2Fdatabase%2FPhotos%2FUpdate.png)
![AfterUpdate.png](capstone-starter%2Fdatabase%2FPhotos%2FAfterUpdate.png)

## 5. Delete a Category
    DELETE /categories/{id}
    Removes a category.
    Only users with the admin role can delete, and this action requires an authentication token.
![Delete.png](capstone-starter%2Fdatabase%2FPhotos%2FDelete.png)
![AfterDelete.png](capstone-starter%2Fdatabase%2FPhotos%2FAfterDelete.png)


## Interesting 
It’s interesting that we can test the Categories API directly in Postman, 
using endpoints to create, update, or delete categories. 

## Bug 1
Bug 1 was fixed by adding the missing condition AND (price <= ? OR ? = -1) to the SQL query, 
ensuring correct filtering by price range in the product search. 
![Bug 1.png](capstone-starter%2Fdatabase%2FPhotos%2FBug%201.png)

## Bug 2 
For Bug 2, the issue was resolved by replacing `productDao.create(product)` with 
`productDao.update(id, product)` to ensure that the product is updated correctly in the
database instead of creating a duplicate.
![Bug2.png](capstone-starter%2Fdatabase%2FBug2.png)