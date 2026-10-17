## Exercise 1

* Add a login view with an appropriate form (you can use the code from class).
* The view should be available at `/login`/.
* Upon successful login, the user should be redirected to the `/products/` page.


## Exercise 2

* Secure the application in such a way that the product and category editing views are available only to users who have the rights to the appropriate actions:
    * "add\_product",
    * "add\_category",
    * "edit\_product",
    * etc.
* The above permissions should apply to corresponding models.


## Exercise 3

* Secure templates so that links to certain actions (add product, modify product, etc.) were only displayed to users with appropriate permissions.


## Exercise 4

* Add models created during homework to the **admin** panel.
To do so, write your own models that inherit from `admin.ModelAdmin`
* Ensure readability of the admin panel by properly overriding the `__str__()` method
(only product and category names should appear).
* Ensure ease of use by adding appropriate fields for the above mentioned models.
