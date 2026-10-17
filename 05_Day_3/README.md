## Exercise 1 &ndash; done with the lecturer

* Add a superuser using `./manage.py`.
* Write a view and share it at `/list_users/`. When accessed using the GET method it should:
    * retrieve the details of all users from the database,
    * display their logins and surnames on the page.


## Exercise 2

* Write a `/login/` view that:
    * when accessed using the GET method, will display a login form. It should contain the fields: **username** and **password**,
    * When accessed using the POST method, will perform authentication and login.
        * If there are errors, it will inform the user.

* Write a `/logout/` view that will log the user out.

* Create a base view that:
    * will show the currently logged in user in the footer.
    * depending on whether a user is logged in or not, will show a link to the view `/login/` or `/logout/`,
    * make the view available at `/`.


## Exercise 3

* Write a view for adding a user. Make it available at the URL `/add_user/`. The view should:
    * when accessed using the GET method, display the form for adding a user. Fields to fill in:
        * login,
        * enter password (remember the appropriate widget),
        * re-enter password,
        * name,
        * surname,
        * email,
    * when accessed using the POST method, check the correctness of the form:
        * whether the login is already in use,
        * if the password and re-entered password are the same,
        * if the email is correct,
    * if the data is correct &ndash; create a user account,
    * if the data is incorrect &ndash; inform the user about the error.


## Exercise 4

* Write a password resetting view. Make it available at the URL `/reset_password/{id}`, id being the user ID. The view should:
    * when accessed using the GET method, display the user password changing form. Fields to fill in:
        * enter the new password,
        * re-enter the new password,
    * when accessed using the POST method, check the form correctness:
        * whether the new password and re-entered password are the same,

    * if the data is correct &ndash; change the user's password,
    * if the data is incorrect &ndash; inform the user about the error.

Remember the relevant widgets.


## Exercise 1 &ndash; done with the lecturer

Modify exercise 4 from the previous chapter so that only a user with the "change_user" permission can access this view.


## Exercise 2

In your application, you have a view provided at `/notices/` that you wrote a few days ago.
Modify this view (or template) so that only a user with the `add_studentnotice` permission can send a notice to a student.

Then add a regular user to the application and test this view by granting/deleting appropriate permissions.
Use the login view you wrote in the previous section to log into this user's account.


## Exercise 3

* Manually add a "teachers" group that will have rights to add notices and check attendance.
* Manually add a regular user who will be added to the "teachers" group.
* Manually add a regular user who will not be added to the above group
and will not have the above permissions.

Test the user permissions.
