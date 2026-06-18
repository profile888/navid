### 1. Java Inheritance OOPS concept

```
//Purpose:
//Demonstrate Java Inheritance functionality.
//The Employee class inherits common properties and methods from the CompanyMember class.

```

```
package demo_inheritancce;

class Company {

 String company = "Tech Solutions Inc.";

 public void displayCompanyInformation() {
     System.out.println("Company Name: " + company);
 }
}

class Employee extends Company {

 String employeeName = "John Smith";

 public void displayEmployeeInformation() {
     System.out.println("Employee Name: " + employeeName);
 }
}

public class BusinessInheritanceDemo {

 public static void main(String[] args) {

     Employee employee = new Employee();

     // Inherited method from parent class
     employee.displayCompanyInformation();

     // Method from child class
     employee.displayEmployeeInformation();
 }
}



```
