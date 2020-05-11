# Week 2 report
This week I have followed the official This week I have followed the [official django tutorial](https://docs.djangoproject.com/en/3.0/intro/tutorial01/)
from part 4 to 7.

### Cheatsheet
1. I accidently messed up my local mysql setup. To get a hard uninstallation, check this tutorial.[link](https://gist.github.com/vitorbritto/0555879fe4414d18569d)

### Part 4: Form processing
1. Write a minimal form for detail.html to have a vote function.
2. Implement a real vote function in views.py
3. After user finishs the vote, it redirects it to the poll result page. Create a results function in views.py
4. Create a results.html template to render the poll's result page.
5. Turtorial mentioned a simontanely vote problem. If two users vote at the exact same time, you will get wrong vote
number. See here [Avoiding race conditions using F()](https://docs.djangoproject.com/en/3.0/ref/models/expressions/#avoiding-race-conditions-using-f)
6. Use generic views. The previous detail() and result() views are redundant.
7. Convert the URLconf: change question_id to pk for detail and results url in urls.py
8. Convert the index, detail, and results views into class in views.py

### Part 5: Automated testing
```shell script
# Run the test under the app name. In this case, the app is polls
python manage.py test polls
```
1. Automated tests is essential. It will save your time, prevent problem, make your code more attractive, and create a
good team work.
2. A current bug of the system is that: problems created in future date will count as published recently.
3. Create a tests.py under polls and test if published recently return false for future created problem.
4. Write multiple tests in the same tests.py file.
5. Then we need to improve our view so it doesn't show the questions created in the future date. 
6. Create multiple functions to test future and past question senarios.
7. Modify the detail view so it doesn't show future questions.
8. Write a automate test for detail future view.
9. For automated test, the more is better.
10. Framework like Selenium is also great for simulating real-user interaction with the browser.

#### Questions:
1. When you run a automated test, why doesn't it save actual data to the database?
2. How to hook up the local database to the s3?

### Part 6: Add static files, a stylesheet and an image
1. All the images, Javascript, and CSS files are static files, and thus, stored in a static folder.
2. Create a static folder inside the app folder, polls in this case.
3. Create another folder name app, in this case, it's polls. You will get something like ```polls/static/polls```
4. Put a style.css inside the polls. You will get:```polls/static/polls/style.css```
5. Load the CSS file in index.html by use the ```{% load static %}```
6. Create a folder called image inside the most inner app folder. ```polls/static/polls/images```
7. You can set background images using the images in this folder.

### Part 7: Customize the admin site
1. Reordering the form using list order.
2. Use fieldsets to set names for each field.
3. Register choice to admin so you can add choice from the admin portal.
4. Add ChoiceInline class in admin so you can add choice while you are creating the question.
5. Use list_display to show more attributes from the model.
6. Create a templates folder in project directory. Go to setting.py to change DIRS pointing to your templates
7. Copy the base_site.html from django source file to here. Then modify it.