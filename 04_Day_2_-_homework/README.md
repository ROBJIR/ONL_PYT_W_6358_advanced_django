## Exercise 1

* Write a form for adding product categories to the database. Make it available at the URL `/add_category/`.
    * when accessed using the **GET** method, an empty form should appear where you can add a new category,
    * when accessed using the **POST** method, the category should be saved to the database,
    * after adding a new category we should be redirected to `/categories/`.
    
* Add category editing view:
    * the view should allow to change the category data and save this change to the database,
    * category editing form should be available at `/edit_category/{slug}/`,
    * after the data change we should be redirected to `/categories/`.

* Modify the view with the list of all categories (URL `/categories/`) as follows:
    * next to the description of each category add a link: **modify**, the link should redirect to the address `/edit_category/{slug}/`
    * at the bottom of the category list add a link: **add category**, the link should redirect to the address `/add_category/`.

Try to do **exercises 1 and 2 from Day 2** using ModelForms and/or generic views.


## Exercise 2

* Write a form for adding products to the database. Add the following views:

    * product list (available at `/products/`):
        * displays a list of **all** products, regardless of the category
        (you can modify the `/category/` view for this),
        * at the description of each product it has a link to edit - `/edit_product/{product_id}/`
        * at the bottom of the product list it has a link **add product** leading to the address `/add_product/`,

    * edit product (available at `/edit_product/{product_id}`):
        * when you enter the editing link, it displays the product editing form,
        * it allows you to change the product data and save them,
        * after changing data, it redirects to the page with all products (`/products/`),

    * adding a product (available at `/add_product/`):
        * when you enter the **add product** link, it displays a blank form,
        * it allows you to add a new product and save it,
        * after adding a new product, it redirects to the page with all products (`/products/`).

Try to do **exercises 1 and 2 from Day 2** using ModelForms and/or generic views.


## Exercise 3 (*)

* Add a search form. It should have only one field: search.
* If the form is filled in correctly, it should search for the entered phrase in the names of products **and** categories, and return the found results.
* Create a view to present the search results.
* The view should be available at `/search/`.
