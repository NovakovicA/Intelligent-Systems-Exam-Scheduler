# Intelligent Systems Exam Scheduler
------------------------------------

This was the second homework of the course Intelligent Systems, where it was given as a task to implement an algorithm that will schedule exams in an exam term so that the schedule has a minimal price and the rules from the documentation are respected (one education branch cannot have two or more exams from the same year in a single day and that one term cannot contain multiple exams of the same education branch that are from adjacent years).

The project takes 2 input files in JSON format:
- sale.json which contains an array of available classrooms at the time, with their name, capacity, information if they have computers or not, the required number of assistants to manage the classroom and a flag which shows if those classrooms are located in the faculty or not. 
- rok.json which has exam term length in days and an array of exams which have exam code, computer requirement, number of enrolled students and the study branches that have the exam in education plan. 

The output is a CSV format file which contains the exam schedule in a tabular form, for each day and term (08:00, 11:30, 15:00, 18:30).

The algorithm implemented represents my own idea, which contains CSP (Constraint satisfaction problem) algorithm elements, but the main advantage that it is much much faster than the classic algorithms. First it generates an exam schedule which can pack all of the exams so that the documentation rules are respected and then it proceeds to improve the schedule by swapping different exams according to the pricing formula from the documentation so that we get a new schedule that has a better overall price. The algorithm runs while there are any changes to the schedule.

How to run - extract files from Homework.zip and copy them into a new Java Project made in a Java IDE of choice. Then import json.jar as an external JAR library, which is used as a tool to parse JSON files. Main class is runnable - it contains the main method and in it there are three variables which control input and output files:
	private static String inputRok="javni_testovi/rok5.json";
	private static String inputSale="javni_testovi/sale5.json";
	private static String outputFile = "javni_testovi/out5.csv";
  
In order to run the tests extract tests.zip to the project main directory (not in src) and change the variables to test/rok.json etc.
You can use the score calculator provided, or use the built-in one I made for this project by changing showbrojBodova variable within Main class to true.
