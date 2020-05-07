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
1. Automated tests is essential. It will save your time, prevent problem, make your code more attractive, and create a
good team work.
2.

erase the mysql, import the downloaded files