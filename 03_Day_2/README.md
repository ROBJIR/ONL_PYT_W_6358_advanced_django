## Exercise 1 &ndash; done with the lecturer

You will find the file **logo.png** in the exercise directory.

* Create and configure the static files directory.
* Copy the **logo.png** file to the static files directory.
* Add the **logo.png** image to the school's base template.


## Exercise 1 &ndash; done with the lecturer

* Write a student search form. The form should display one field: **name**.
* Write a view that:
    * upon entering using the **GET** method, will display the student search form,
    * upon entering using the **POST** method, will receive the data, then
    * will search the data in the database, using the model (just enter a fragment of the surname, the program should find all students whose names match the pattern), then will pass it to the template and display the results on the page,
    * share the view at the URL: `/student_search`.


## Exercise 2

* Write a form that takes 3 parameters: name, surname, and the class the student attends.
The student's class field should take values that are in the constant `SCHOOL_CLASS`.
* Write a view to and share it at `/add_student` that:  
    * when accessed using the GET method, will display an empty form,
    * when accessed using the POST method, will receive the data from the form and add the student to the database, then redirect the user to the page with the given student's data.


## Exercise 3

Modify the view, model, and/or form from the previous exercise. Add a field `year_of_birth` to the model, which will store a value of the **integer** type. Allow the user to add this value using the form.


## Exercise 4

* Write a currency conversion form. The form should have the following fields:
    * `currency1`: field accepting a floating point number,
    * `currency2`: field accepting a floating point number,
    * `conversion`: dropdown taking one of two values: **EURtoUSD** and **USDtoEUR**.
* Write a view available at `/exchange` that:
    * when accessed using the GET method, will display an empty form,
    * when accessed using the POST method, will convert currencies from EUR to USD (or vice versa, it depends on the value of the `conversion` field) and display the result.

For volunteers:
 
Change the view so that the result is displayed in the second form field.
For example, if you fill in the field currency1 (EUR) and click EURtoUSD, the program will fill in the field currency2 (USD) with an appropriate value.


## Exercise 5

* Write a form for adding grades of a student. The form should contain the following fields:
    * student: a field with the student's surname,
    * subject: a field with the name of the subject,
    * grade: a field with grade that should only take values from the constant `GRADES`.

* Write a view and share it at `/add_grade`. The view should define the following functionalities:
    * when accessed using the GET method, it should display an empty form,
    * when accessed using the POST method, it should:
        * receive data from the form,
        * check if the student exists in the database, if not &ndash; display the message:
        "There is no such student!",
        * check if the subject exists in the database, if not &ndash; display the message:
        "There is no such subject!",
        * if the data is correct, give the student a grade in the subject and save it to the database,
        * redirect the user to the page with the student's data.

For volunteers:

Change the form so that the subject is selected from a list of available subjects.

---

Hint: you will learn about the different types of form fields later in the presentation.
Useful fields:
* `forms.CharField`
* `forms.IntegerField`
* `forms.ChoiceField`
* `forms.FloatField`

For more on this topic, see the [documentation](https://docs.djangoproject.com/en/4.0/ref/forms/fields/).


## Exercise 1 &ndash; done with the lecturer

* Write a form that will allow you to compose toppings for a pizza.
* It should have only one field, but a multiple choice one. The values that you will be able to select are:
    * olives,
    * tomatoes,
    * extra cheese,
    * anchovies,
    * onions.
* Write a view that, when accessed using the **GET** method, displays a form.
* Change the field widget to `CheckboxSelectMultiple` and compare the differences.

The 4_Snippets directory contains ready-made models for this exercise.


## Exercise 2

* Write a model `PresenceList` that will store a student's attendance record for a class.
The model should have the following fields:
    * student: foreign key to the `Student` model,
    * day: date field (date only) &ndash; school day,
    * present: boolean value, should allow the lack of value (null).

* Write a form that will contain data as in the model above,

* Write a view available at `/class_presence/{student_id}/{date}`, {student_id} being the student ID and {date} - a school day.
    * when accessed using the GET method, the view should display the form for the date specified in the parameter.
    The `day` field should be hidden (use the `HiddenInput` widget),
    * when accessed using the POST method, the view should save the student attendance data.
 


## Exercise 3

* Write a form with one field: `background_color`. This field should allow you to enter 5 values:
black, white, red, yellow, and blue.

* Write a view and share it at `/set_color`.
    * when accessed using the GET method, the view should show the form.
    The `background_color` field should use the `RadioSelect` widget,
    * when accessed using the POST method, the view should show the above form.
    Additionally, the background should change to the color selected by the user.


## Exercise 4

* Write a login form with two fields: `login` and `password`.
The `password` field should use the `PasswordInput` widget.
* Write a view and make it available at `/login`.
The view should display an empty login form when accessed using the GET method.
* Write a `post()` method to the previous exercise that:
    * receives data from the form,
    * checks if the user is **root**,
    * checks if the password is **very\_secret**.
    If so, it shows on the browser screen: "Nice to see you". Otherwise, it displays: "Shoo, hacker!"


## Exercise 1 &ndash; done with the lecturer

* Write a form that accepts the following fields from the user:
    * name,
    * surname,
    * email,
    * favorite website.
* Let the mail and www fields be validated with the appropriate validators
(check the documentation at: [https://docs.djangoproject.com/en/4.0/ref/validators/#emailvalidator](https://docs.djangoproject.com/en/4.0/ref/validators/#emailvalidator)).
* Write a view available at `/d2_p3_e1` that:
    * when accessed using the GET method, will display an empty form,
    * when accessed using the POST method, will check the correctness of the data and print out any errors.
    If the data is correct, the view will show it in the browser.


## Exercise 2

* Write a validator that checks that the number being validated is in the range 2000 - 2004.
* Use this validator to validate the data in the form from Exercise 3 of the **1_Forms** section.


## Exercise 3

* Write a form that allows you to enter a name and a surname.
* Add a validator to the form to check if the name is female. If not, inform the user of the error.
* Write a view available at `/d2_p3_e3` that:
    * when accessed using the GET method, will display an empty form,
    * when accessed using the POST method, will check the correctness of the data and print out any errors.
    If the data is correct, the view will show it in the browser.
 
##### Hint: For the sake of this exercise, assume that female names are those that end with the letters "a" or "e". Exceptions (e.g. Cole, Ezra) can be ignored.


## Exercise 4

* Write a form containing two fields, taking a **number** and a **string** respectively,
* Add a validator to the form to check if the number is in the range 1 - 100.
* Write a view available at `/d2_p3_e4` that:
    * when accessed using the GET method, will display an empty form,
    * when accessed using the POST method, will check the correctness of the data and print out any errors.
    If the data is correct, the view will print the string as many times as the number entered in the second field.


## Exercise 1 &ndash; done with the lecturer

* Write a form that inherits from the ModelForm class, and will add an item to the database.
* Write a view that:
    * When accessed using the GET method, will display an empty form,
    * When accessed using the POST method, will save the database data (using the model associated with the form).


## Exercise 2

* Write a `Message` model to represent an email to the teacher of a subject.
The model should have the following fields:
    * `subject`: text field, max. 256 characters,
    * `content`: text field, unlimited number of characters,
    * `to`: foreign key to teacher,
    * `from`: foreign key to student,
    * `date_sent`: datetime field, autocompleted on save.

* Write a form inheriting from the ModelForm class that will allow the handling of the `Message` model.
The form should provide all fields except `date_sent`.

* Write a view (share it at the URL `/send_message`) that:
    * when accessed using the GET method, will display a form,
    * when accessed using the POST method, will save the email to the database.


## Exercise 3

* Write a `StudentNotice` model to represent notices from teachers for students.
The model should have the following fields:
    `from`: foreign key to teacher,
    `to`: foreign key to student,
    `content`: text field with unlimited length.

* Write a form inheriting from the ModelForm class that will allow the `StudentNotice` model to be handled.

* Write a view that you provide at `/notices/{student_id}`.
The view should retrieve all the notices for a given student from the database and present them on the page.
In the template, also put appropriate links for the teacher to add and remove existing notices.


## Exercise 4

* Write views, inheriting from generic views, that will allow you to add and remove a notice of a student.
