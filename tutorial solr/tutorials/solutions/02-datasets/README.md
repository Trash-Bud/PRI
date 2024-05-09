# Possible Solutions
 
* **Task 1:** Obtain a `csv` file from the `example.xlsx` file.

___SOLUTION:___ `in2csv example.xlsx | tee example.csv | trim`

* **Task 2:** Print the data of the last column of the `csv` file.

___SOLUTION:___ `< example.csv csvcut -c '"Wins"' | csvlook`

* **Task 3:** Print all lines that contain a **'y'** in the first column, and count these occurrences (_hint_, to count lines, you can use the command _`wc`_).

___SOLUTION:___ `csvgrep example.csv --columns 'Team' --regex '.*[y|Y].*' | wc -l`