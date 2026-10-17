## Exercise 1 &ndash; project preparation &ndash; done with the lecturer

1. Study the project `project`. Look at the **settings.py** file:
* check the name of the database that this project uses,
* set up a database with the correct name in PostgreSQL,
* do the first migration.

2. Configure the template system. Use the knowledge from the presentation and:
* set BACKEND to `django.template.backends.django.DjangoTemplates`
* set DIRS so that all templates are located in the **/templates** directory in the application folder (not project folder).

3. Run the command: `python manage.py populateschool` and read the contents of the database used in the exercises.


## Exercise 2 &ndash; base template &ndash; done with the lecturer

1. Study the `SchoolView` in the **views.py** file. You will find there an HTML variable that stores the page appearance. Create a base template for the entire application based on it.
From now on, whenever you create a new template for "school" exercises, you should inherit from this base template.

2. Modify `SchoolView` so that the HTML with the page appearance is loaded from the template.
This template should inherit from the base template.


## Exercise 3 &ndash; list of students

Study the `SchoolClassView`. Check in the **urls.py** file how this view is made available in the application. Write a template that will present a list of students in the class shown.

There is a small bug in the view code. Can you find it?

**Hint:** use template commands to render context data
`{% for ... in ... %} ... {% endfor %}` and `{% if ... %} ... {% endif %}`


## Exercise 4 &ndash; student sheet

Write a view to share at the URL `/student/{student_id}`, {student_id} being the identifier (primary key) of the student. The view should show the student's sheet:

* name,
* surname,
* class.

At the bottom of the page, add a list of all subjects. Each subject should be a separate link that will redirect the user to the (not yet existing) view `/grades/{student_id}/{subject_id}`, `{student_id}` being the student ID (primary key), and `{subject_id}` - the subject ID.

You will write the `/grades...` view in the next exercise.


## Exercise 5 &ndash; student grade generator &ndash; done with the lecturer

Analyze the command `python manage.py populateschool`, which was used in exercise 1 to populate the database with random data. This command creates students and subjects but does not add any grades.

Write your own command `populategrades` that adds random grades to randomly selected students and subjects.


## Exercise 6 &ndash; student's grades

Write a view and share it at the URL `/grades/{student_id}/{subject_id}`, `{student_id}` being the identifier (primary key) of the student, and `{subject_id}` - the subject identifier.

The view should show:
* student's surname and their class,
* subject name and teacher's surname,
* all grades of the student in a subject,
* average grade of the student in a subject.
