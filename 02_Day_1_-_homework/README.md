## Exercise 1

In the folder **3_Django** there is a **coderslab** project. Inside the project there are two applications:
* **exercises_app** - intended for work during class,
* **homework_app** - intended for solving homework assignments.

Make sure that the project is properly configured. In particular, pay attention to:
* whether both applications are added to `settings.py`,
* whether the database exists and is connected to the project,
* whether the correct template language is configured,
* whether the templates are downloaded from the proper directory (`templates` directory inside the application).


## Exercise 2

Imagine software for an online shop. The store can sell any merchandise, so it will need a data structure that stores information about the product and its category. 
Each product can have multiple categories.
Each category may contain multiple commodities.
The categories are user-defined, so they must be stored in the database.

Define the following models:

* `Category` - that stores data about the category, and in it the following fields:
    * `category_name` string with max length of 64 characters,
    * `slug` string with max length of 64 characters, unique.

Slug is a field that stores a character identifier for the category.
It may contain only lowercase letters, digits, and the character `-` instead of spaces. It should be unique.

* `Product` - that stores data about the product, and in it the following fields:
    * `name`: string with maximum length of 128 characters,
    * `description`: string with unlimited number of characters,
    * `price`: net price of the product, floating point number (let's ignore the imperfections of the float type),
    * `vat`: can take the following numeric values: 0.23, 0.08, 0.05, 0,
    * `stock`: number of products in stock, integer,
    * `categories`: many-to-many relationship between `Product`, and `Category`.

Fill models with data: define some arbitrary categories, add some products to the categories.


## Exercise 3

* Define a base template from which all other templates in the application will inherit.
The template should be named `base.html`.

* Write a view and make it available at `/categories`.
The view should show a list of all categories in alphabetical order.
Each category should be a link (empty for now), which in the future will lead to a list of products of a given category.


## Exercise 4

Write a view and make it available at `/category/{slug}`, {slug} being the text identifier of the category.
In the view, retrieve product data from that category, then display the product information in alphabetical order. The data to be shown on the screen:
* **product name** - should be a link that leads to the page `/product/{id}`, `{id}` being the product's primary key. You will create a detailed product view later.
* **gross price** - the price of the product increased by the amount of the **VAT** tax.


## Exercise 5

Write a view and make it available at `/product/{id}`, {id} being the identifier (primary key) of the product.
The view should display metrics (all data) about the product.
