# Possible Solutions

### Task 1

You should create a **Makefile** that reads the content of the file `example.txt`, parses each URL listed (one per line), and creates individual `.html` files for each feed item.

___SOLUTION:___ See the attached Makefile.


### Task 2

The attached Makefile downloads the list of **LEIC** and **MEIC** courses from SIGARRA. So far, this Makefile reads the HTML of each course. However, it needs a shell script called `parse-program-html.sh` so that it is possible to know the **id** and **name** of each course (which will be later written in a `.tsv` file). 

Therefore, you should develop a `parse-program-html.sh` file that:

1. Reads the `.html` created for each program;
2. Checks the different courses in each file;
3. Extracts the **id** and **name** of each course;
4. Sorts the occurrences alphabetically.

___SOLUTION:___ See the attached shell script `parse-program-html.sh`