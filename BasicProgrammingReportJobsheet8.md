# JOBSHEET 8 - LOOPS 2

**Student Identity:**
* **Name:** Fathan Nur Hidayat
* **NIM:** 26410702084
* **Class / Student Attendance:** 1I / 12

---

## 1: OBJECTIVE

The following are the objectives of the practical work in this chapter:

1. Understand the concept of nested loops in algorithms
2. Understand the flow of nested loops
3. Recognize the syntax of nested loops
4. Be able to apply nested loops to solve a simple case study.


---

## 2: PRACTICUM

### 2.1 Experiment 1: Review of Loops 1

In this section, this experiment revisits the FOR loop before learning nested loops. 
The program prints the character * n times horizontally (side by side). 
Use n as a positive integer input.

#### 2.1.1 Program Code Java
```java
import java.util.Scanner;

public class Star12 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter the value of n = ");
        int n = input.nextInt();

        for(int i = 1; i <= n; i++){
            System.out.print("*");
        }
        System.out.println();
        input.close();
    }
}
```

#### 2.1.2 Execution Result / Screenshot Output
The following is an example of the *output* display after the program is run.:

![Experiment1Output1](/Experimen1Output(1).png)

![Experiment1Output2](/Experimen1Output(2).png)

The number of * characters printed in each test:
n = 5: 5 times
n = 3: 3 times
n = 7: 7 times

#### 2.1.3 Answers to Questions / Reflection Questions
* **Question 1:** If the initialization i = 1 is changed to i = 0 without changing the condition, how many * characters are printed when n = 5? Explain.
  * **Answer:** The loop runs for i = 0, 1, 2, 3, 4, 5. That is 6 iterations, so the program prints 6 *. Starting one step earlier adds one extra round.
* **Question 2:** If the condition i <= n is changed to i < n, how many times does the loop run when n = 5? Why is the result different?
  * **Answer:** When n = 5 and the condition is changed from i <= n to i < n, the loop runs 4 times. Because the loop starts at i = 1, not i = 0. When n = 5, the condition i < n means i must be smaller than 5.
* **Question 3:** Predict the output of the following code fragment when n = 9, then verify it by replacing the FOR loop in your program and running it.
```java
for (int i = 2; i <= n; i += 2) {
 System.out.print(i + " ");
}
```
Modify this code so that it prints the odd positive numbers that do not exceed n.
  * **Answer:** The output of that modified code is:
  ![Experiment1QOutput(3)](/Experiment1QOutput(3).png)
  And then modify that code so that it print the odd positive numbers that do not exceed n:
  ![Experiment1QOutput(4)](/Experiment1QOutput(4).png)

* **Question 4:** Explain why changing the increment i++ to i-- (with the condition still i <= n) makes the loop run endlessly, so that it does not stop in a reasonable time for positive n. Do not run that version; if it has already started running, stop the program by pressing Ctrl + C in the terminal.
  * **Answer:** Changing i++ to i-- makes the loop run endlessly because the value of i decreases instead of increases. The value of i keeps decreasing, so it will always be less than or equal to 5. Therefore, the condition never becomes false, and the loop does not stop.

---

### 2.2 Experiment 2: Rectangle Star Pattern (Nested FOR)

In this experiment a nested loop of FOR statements is used to print a rectangle of stars. The number of rows and columns is entered separately, so the role of each loop can be observed clearly: the outer loop controls the rows, while the inner loop controls the columns (recall the shelf/locker analogy from the lecture material).

#### 2.2.1 Program Code Java
```java
import java.util.Scanner;

public class Rectangle12 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter the number of rows: ");
        int rows = input.nextInt();
        System.out.print("Enter the number of columns: ");
        int columns = input.nextInt();

        for(int i = 1; i <= rows; i++){
            for(int j = 1; j <= columns; j++){
                System.out.print("*");
            }
            System.out.println();
        }
        input.close();
    }    
}
```
#### 2.2.2 Execution Result / Screenshot Output
The following is an example of the *output* display after the program is run.:
![Experiment2Output](/Experiment2Output(1).png)

#### 2.2.3 Answers to Questions / Reflection Questions
* **Question 1:** Explain the function of the variables i and j in the program.
  * **Answer:** 
  Variable i determines how many rows are printed, while variable j determines how many stars are printed in each row. The inner loop (j) finishes printing one row before the outer loop (i) moves to the next row.
* **Question 2:** How many times are the outer loop, the inner loop, and the statement print("*") executed for rows = 4 and columns = 7?
  * **Answer:** 
  a. Outer loop (i): Executes 4 times because there are 4 rows.
  b. Inner loop (j): Executes 7 times for each outer loop iteration, so a total of 4 x 7 = 28 times.
  c. Statement System.out.print("*"): Executes 28 times because it is inside the inner loop.
* **Question 3:** What happens if the bounds of the outer and inner loops are swapped (the outer loop
uses columns and the inner loop uses rows)? Use rows = 3 and columns = 6 to explain.
  * **Answer:** If the bounds of the outer and inner loops are swapped, the program will print a rectangle with 6 rows and 3 columns instead of 3 rows and 6 columns.
```java
for (int i = 1; i <= columns; i++) {
    for (int j = 1; j <= rows; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```
The output: ![Experiment2QOutput(2)](/Experiment2QOutput(2).png)

* **Question 4:** Explain the effect of removing System.out.println(); after the inner loop.
  * **Answer:** All the stars will be printed on one single line instead of forming a rectangle.
* **Question 5:** Modify the program so that the printed character is #, then commit and push the changes
to GitHub.
![Experiment2QOutput(3)](/Experiment2QOutput(3).png)

---

### 2.3 Experiment 3: Debugging a Star Triangle – Nested WHILE
The starting code in this experiment is intentionally written so that it does not yet produce
the correct triangle format. Your task is to identify the errors and fix them without changing
the WHILE structure into FOR.

#### 2.2.1 Program Code Java
```java
import java.util.Scanner;

public class Triangle12 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter the value of n: ");
        int n = input.nextInt();

        int i = 0;
        while(i <= n) {
            //System.out.print("[i=" +  i + "] "); //temporary debug
            int j = 0;
            while(j < i){
                System.out.print("*");
                j++;
            }
            System.out.println();
            i++;
        }
        input.close();
    }    
}
``` 

Output program:
![Experiment3Output](/Experiment3Output(1).png)

*Add a temporary debug command right after the line while (i <= n) {. This command displays the value of i each time the outer loop starts.

```java
import java.util.Scanner;

public class Triangle12 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter the value of n: ");
        int n = input.nextInt();

        int i = 0;
        while(i <= n) {
            //System.out.print("[i=" +  i + "] "); //temporary debug
            int j = 0;
            while(j < i){
                System.out.print("*");
                j++;
            }
            i++;
        }
        input.close();
    }    
}
```
#### 2.3.2 Execution Result / Screenshot Output
The following is an example of the *output* display after the program is run.:
![Experiment3Output(2)](/Experiment3Output(2).png)

5. Run the program again with n = 5, then observe the result:
a. How many times does the outer loop run? Is this the same as the desired number of rows?
   The outer loop runs 6 times (i = 0, 1, 2, 3, 4, 5) because the condition is i <= n. The desired output is 5 rows, so it's not the same.
b. How many * characters are printed when i = 0?
   Zero. The inner loop condition j < i becomes 0 < 0, which is false immediately, so the body never executes.
c. Why are all the characters displayed on a single line?
   Because the program only uses System.out.print, and nothing prints a newline after each inner loop.

6. Fix the code one step at a time, and run the program after each fix:
a. Add System.out.println(); after the inner loop finishes, before i++. Run it and observe: is there still any line that does not contain *?
   Yes, on the first line
b. Change the initialization and/or the condition of the outer loop so that the loop runs
exactly n times without any empty lines. Run it again.

**Modified Program Code:**
```java
int i = 1;
        while(i <= n) {
            //System.out.print("[i=" +  i + "] "); //temporary debug
            int j = 0;
            while(j < i){
                System.out.print("*");
                j++;
            }
            System.out.println();
            i++;
        }
```
Modify the program so that, after the triangle above is printed, it also prints an inverted triangle. Write a second nested WHILE below the first nested WHILE (still inside main()), without changing the WHILE into FOR.

**Modified Triangle and Inverted Triangle Code:**
```java
import java.util.Scanner;

public class Triangle12 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter the value of n: ");
        int n = input.nextInt();

        int i = 1;
        while(i <= n) {
            //System.out.print("[i=" +  i + "] "); //temporary debug
            int j = 0;
            while(j < i){
                System.out.print("*");
                j++;
            }
            System.out.println();
            i++;
        }
        int k = n;
        while (k >= 1) {
            int m = 0;
            while (m < k) {
                System.out.print("*");
                m++;
            }
            System.out.println();
            k--;
        }

        input.close();
    }    
}

```
The output: ![EXperiment3Output(3)](/Experiment3OUtput(3).png)

#### 2.2.3 Answers to Questions / Reflection Questions
* **Question 1:** Identify the mismatches in the initial output, and at least two fixes needed to produce a nested triangle pattern.
  * **Answer:** 
  1. Line breaks: there is only 1 single line before, because print is used and nothing prints a newline after each inner loop
  2. Row count: there is 6 outer iterations (i = 0 to 5) before, because i = 0 with i <= n runs one extra time.
  3. First row: The first iterations print 0 stars, because at i = 0, j < i is 0 < 0, so the inner loop never runs

  **Fix 1**: Add a new line after each inner loop (System.out.println();)
  **Fix 2**: Change the initialization into i = 1; so that the loop runs exactly n times without any empty lines.
* **Question 2:** Explain the roles of the variables i and j. Why must the value of j be reset to 0 in every iteration of the outer loop? What happens if j is not reset?
  * **Answer:**
  a. i is the row counter (outer loop). Its value is the current row number, which is also the number of stars that row should contain. The outer loop runs once per row.

  b. j is the star counter (inner loop). It counts how many stars have been printed so far in the current row. The inner loop while (j < i) keeps printing * until j reaches i, so row i gets exactly i stars.

  c. Why j must be reset to 0 every iteration?
  The inner loop works by counting up from 0 to i. At the end of each row, j has the value i (the loop only stops once j < i is false). If j is not set back to 0 at the start of the next row, the counter begins where the last row left off instead of at the beginning, so it no longer measures “stars printed in this row”.
* **Question 3:** Explain the changes to the initialization, the condition, and the update of the outer loop that are needed to form the inverted triangle
  * **Answer:** 
  1. Initialization: 1 becomes n.
  The inverted triangle begins with its widest row, so the star count must start at n instead of 1. If you kept the start at 1, the first row would have only one star.
  2. Condition: i <= n becomes k >= 1.
  The comparison flips from “not yet above the maximum” to “not yet below the minimum”. The loop now stops once k drops under 1. If you left k <= n in place, the condition would be true at the start and (with a decreasing k) would stay true forever, which is an infinite loop. The condition has to test the end point you are moving toward.
  3. Update: i++ becomes k--.
  Each row must be one star shorter than the previous one, so the counter goes down by 1. Keeping k++ would make the rows grow and move k away from the stopping point of k >= 1, which again never terminates.

---

### 2.2 Experiment 4: Case Study of Group Project Scores

In assessing a group project, each group receives scores from a number of graders. The program receives the number of groups and the number of graders (the same for every group), then calculates the average score of each group and determines the group with the highest average. This case is solved with nested loops without storing all the scores: a WHILE (outer) for the groups, a FOR (middle) for the graders, and a DO-WHILE (inner) to repeat
invalid score input.

#### 2.2.1 Program Code Java
```java
import java.util.Scanner;

public class Rectangle12 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter the number of rows: ");
        int rows = input.nextInt();
        System.out.print("Enter the number of columns: ");
        int columns = input.nextInt();

        for(int i = 1; i <= rows; i++){
            for(int j = 1; j <= columns; j++){
                System.out.print("*");
            }
            System.out.println();
        }
        input.close();
    }    
}
```

#### 2.2.2 Execution Result / Screenshot Output
The following is an example of the *output* display after the program is run.:
![Experiment2Output](/Experiment2Output(1).png)

#### 2.2.3 Answers to Questions / Reflection Questions
* **Question 1:** Explain the function of the variables i and j in the program.
  * **Answer:** 
  Variable i determines how many rows are printed, while variable j determines how many stars are printed in each row. The inner loop (j) finishes printing one row before the outer loop (i) moves to the next row.
* **Question 2:** How many times are the outer loop, the inner loop, and the statement print("*") executed for rows = 4 and columns = 7?
  * **Answer:** 
  a. Outer loop (i): Executes 4 times because there are 4 rows.
  b. Inner loop (j): Executes 7 times for each outer loop iteration, so a total of 4 x 7 = 28 times.
  c. Statement System.out.print("*"): Executes 28 times because it is inside the inner loop.
* **Question 3:** What happens if the bounds of the outer and inner loops are swapped (the outer loop
uses columns and the inner loop uses rows)? Use rows = 3 and columns = 6 to explain.
  * **Answer:** If the bounds of the outer and inner loops are swapped, the program will print a rectangle with 6 rows and 3 columns instead of 3 rows and 6 columns.
```java
for (int i = 1; i <= columns; i++) {
    for (int j = 1; j <= rows; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```
The output: ![Experiment2QOutput(2)](/Experiment2QOutput(2).png)

* **Question 4:** Explain the effect of removing System.out.println(); after the inner loop.
  * **Answer:** All the stars will be printed on one single line instead of forming a rectangle.
* **Question 5:** Modify the program so that the printed character is #, then commit and push the changes
to GitHub.
![Experiment2QOutput(3)](/Experiment2QOutput(3).png)

---
## 3: ASSIGNMENT

The following is a list of tasks to be performed in this Jobsheet:

- [x] **Task 1:** In this section, students are required to apply a *WHILE loop* with *Multiple IF-ELSE (IF-ELSE IF)* conditions to process the ticket sales of several customers at a cinema. For each customer, the program reads the ticket quantity, rejects negative values and asks for re-entry, then applies the discount rules (10% for more than 4 tickets, 15% for more than 10 tickets) to the ticket price of Rp 50,000. The program accumulates the total number of tickets sold and the total revenue for the day.
- [x] **Task 2:** In this section, students are required to apply a *WHILE loop* and *IF-ELSE* conditions to process the parking fees of several vehicles. For each vehicle, the program reads the parking duration and the vehicle type, then calculates the fee using the rate of Rp 3,000 per hour for cars or Rp 2,000 per hour for motorcycles. The loop continues as long as the input is not 0, and the program then displays the total parking fees collected, following the flowchart provided.

### 3.1 Implementation Task Code

#### Task 1:  Total Daily Cinema Ticket Sales
#### 3.1.1 Program Code Java
```java
import java.util.Scanner;

public class Assignment112 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int ticketQuantity, ticketPrice = 50000, totalTickets = 0;
        
        while(true) {
            System.out.print("Enter ticket quantity: ");
            ticketQuantity = sc.nextInt();
            if(ticketQuantity == 0){
                break;
            }
            if(ticketQuantity < 0 ){
                System.out.println("Invalid ticket quantity! Please enter the quantity again.");
                continue;
            }
        totalTickets += ticketQuantity;
        int subtotal = ticketQuantity * ticketPrice;
        double discountRate = 0;
        
            if(ticketQuantity > 10){
                discountRate = 0.15;
            }else if(ticketQuantity > 4){
                discountRate = 0.10;
            }
        double discount = subtotal * discountRate;
        double totalPayment = subtotal - discount;

        System.out.println("Subtotal: Rp. " + subtotal);
        System.out.println("Discount: Rp. " + discount);
        System.out.println("Total payment: Rp. " + totalPayment);

        }
        System.out.println("--- Daily Sales Report ---");
        System.out.println("Total tickets sold: " +totalTickets);
        System.out.println("Total ticket revenue: Rp. " + (totalTickets * ticketPrice));

        sc.close();
    }
}
```
#### 3.1.2 Execution Result / Screenshot Output
![Task1Result](/Task1Result.png)

#### Task 2: Parking Lot Fee Calculation

#### 3.2.1 Program Code Java
```java
import java.util.Scanner;

public class ParkingDoWhile12 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int type, duration;
        int total = 0; 
        
        do {
            System.out.println("Vehicle Type (1 = Car, 2 = Motorcycle, 0 = Exit)");
            System.out.print("Enter vehicle type: ");
            type = sc.nextInt();

            if (type == 1 || type == 2) {
                System.out.print("Enter parking duration (hours): ");
                duration = sc.nextInt();

                if (type == 1) {
                    total += duration * 3000;
                } else {
                    total += duration * 2000;
                }
            }
        } while (type != 0);

        System.out.println("Total parking fees: Rp " + total);

        sc.close();
    }
}
```

#### 3.1.2 Execution Result / Screenshot Output
![Task2Result](/Task2Result.png)

---

## 4: CONCLUSION

In this jobsheet, students learned and practiced the three loop structures in Java through four case studies. The **FOR loop** is used when the number of repetitions is known in advance, as in finding the highest and lowest quiz scores of 10 students, where the loop counter controls the repetition. The **WHILE loop** is used when the loop depends on a condition that is checked before each iteration, as in the SIAKAD letter grade program, where `continue` and the placement of `i++` at the end of the loop ensure an invalid score is ignored and the same student is asked again. The **DO-WHILE loop** is used when the loop body must run at least once, as in the café transaction program, where `while (true)` combined with `break` stops the loop when the sentinel value "cancel" is entered.

Students also learned that loops work together with selection statements (IF, IF-ELSE IF, and nested IF) to validate input, classify data, and apply business rules such as discounts and parking rates. The `break` and `continue` statements give extra control over the flow of a loop. In the assignments, students implemented the cinema ticket sales case and the parking fee flowchart as Java programs, which shows that a flowchart can be translated directly into a working loop-based program.

Overall, choosing the right loop depends on the problem: **FOR** for a fixed number of repetitions, **WHILE** for condition-based repetition that may run zero times, and **DO-WHILE** for repetition that must run at least once. Understanding the components of each loop (initialization, condition, update, and loop body) is the key to avoiding errors such as infinite loops and wrong results.