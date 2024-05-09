# Possible Solutions

* **Task 1:** Print the first 10 lines of the file using the `sed` command.

___SOLUTION:___ `cat example.txt | sed 10q`

* **Task 2:** Replace the word _"light"_ with _"dark"_.

___SOLUTION:___ `cat example.txt | sed 's/light/dark/g'`

* **Task 3:** Print all the lines that contain numbers. 

___SOLUTION:___ `cat example.txt| grep "[0-9]"`
