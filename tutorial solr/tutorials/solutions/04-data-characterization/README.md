# Possible Solutions

* **Task 1:** Read the information of each odd column.

___SOLUTION:___ `csvstat example.csv -c 1,3,5,7`

* **Task 2:** Read only the standard deviation, maximum, and minimum values of each even column.


___SOLUTION:___ 

```bash
csvstat example.csv --stdev -c 2,4,6

csvstat example.csv --max -c 2,4,6

csvstat example.csv --min -c 2,4,6
```

OR

You can create a Makefile:

```makefile
all: 
	csvstat example.csv --stdev -c 2,4,6 >> results.txt
	csvstat example.csv --max -c 2,4,6 >> results.txt
	csvstat example.csv --min -c 2,4,6 >> results.txt
	cat results.txt
```

* **Task 3:** Create a bar chart showing the difference between male and female customers. 

___SOLUTION:___ `rush plot --x gender example.csv > chart.png`

* **Task 4:** Show the difference of tips over the different meal times. 

___SOLUTION:___ `rush plot --x tip --fill time example.csv > chart.png`
