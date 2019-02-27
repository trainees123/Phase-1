#  NORMALIZATION
**Normalization** is a technique of oraganizing the data into multiple realted tables, to minimize data redundancy
*DATA REDUNDANCY* is repetation of data in multiple places which increases size of database
and also gives issues like
+ insertion anomaly: to insert redundant data for every new row is a a data insertion problem
+ Deletion anomaly: loss of a related dataset when some other dataset is deleted
+ Updation anomaly: data inconsistency that results from data redundancy and partial update
*Example*:
we have a students table
*STUDENTS TABLE*
| roll_no | name | Branch | hod(head of department) | office_tel |
|----------|---------|-----------|-----------------------------------|--------------|  
|1| Bruno mars|CSE|Mr.Ramanujam|53337|

|2| Dennis|CSE|Mr.Ramanujam|53337|
|3|Bruce lee| CSE| Mr.Ramanujam|53337|
|4|Michael Jackson|ECE|Mr.Druva|54447|

Whenever we add a new student to students table  of samebranch,hod(head of department),office_tel keeps repeated
To avoid This we partition the table into two tables one is  students table and other is Branch table This is known as  Normalization
*STUDENTS TABLE*                                 
| roll_no | name | Branch |
|----------|---------|------|
|1| Bruno mars|CSE|
|2| Dennis|CSE|
|3|Bruce lee| CSE|
|4|Michael Jackson|ECE|

*BRANCH TABLE*
| Branch | hod(head of department) | office_tel |
|----------|---------|-----------|-----------------------------------|--------------|  
|CSE|Mr.Ramanujam|53337|
|CSE|Mr.Ramanujam|53337|
| CSE|Mr.Ramanujam|53337|
|ECE|Mr.Druva|54447|
There are  different types of Normalization
+ *1NF*
+ *2NF*
+ *3NF*

*1NF( 1st Normal Form)*: Every Database should at least follow the  1st Normal Form. There are few rules to satisfy 1NF
+ Each Column should contain atomic values

+ A column should contain values that are of same data type

+ Each colum should Have a unique name

+ Order in which data is saved doesn't matter
*2NF(2nd  Normal Form)*: For a table to be in  2NF
+ it should be in 1st Normal Form
+ And, it should not Have any Partial Dependencies
*Example*:we have a students table
*STUDENTS TABLE*
| student_id| name | Reg_no| Branch | address|
|----------|---------|-----------|-----------------------------------|--------------|  
|1| Bruno mars|100|CSE|United states|
|2| Dennis|101|CSE|New York|
|3|Bruce lee| 102| CSE|Hong-kong|
|4|Michael Jackson|103|ECE|United states|  
 Lets create subject table

*SUBJECT TABLE*
|subject_id|subject_name|
|-------------|------------------|
|1002|Maths|
  
Another table called scores table is created to save marks obtained by students in each subject
*SCORES TABLE*


| score_id |student_id | subject_id | marks| teacher|
|----------|---------|-----------|-----------------------------------|--------------|  
|1| 1000|1|85|Mr. Vijay|
|2|1001|3|73|Mr.Anand|
|3|1002| 2| 90|Mr.Ajay|
|4|Michael Jackson|1003|4|Mr.Devendre|
Here the primary key is student_id + subject_id.notice that teacher column only depends on subject_id but not on student_id  this is called Partial Dependency and for a table to be in 2NF this should not exist.To avoid partial dependency Move teacher column to subject table
*SUBJECT TABLE*
|subject_id|subject_name|teacher|
|--------------|------------------ |----------|
| | | |

*3NF(3rd Normal Form)* :For a table to be in 3NF
+ it should be in 2NF
+ it should not have Transitive Dependency
lets continue our previous example
in scores table add two more columns which are exam_name, total_marks
*SCORES TABLE*
|score_id|student_id|subject_id|marks|exam_name|total_marks|
|-----------|--------------|--------------|--------|----------------|-----------------|
| | | | | | |


student_id+subject_id is the primary key in scores table.Here total_marks depends only on exam_name which is a non-key attribute.This is Transitive Dependency
To satisfy 3NF Transitive Dependency should not exist. We make a new table exam where we take out exam_name and total_marks from scores table and add in exam table so that we can remove transitive dependency
*EXAM TABLE*
|exam_name|total_marks|
|----------------|----|
| |
