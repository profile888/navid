### 1. Java Polymorphism Overloading OOPS concept

```
// Purpose:
// Demonstrate method overloading by calculating company revenue
// using same method names with different numbers of parameters.

```

```
package polymorphism;

class RevenueCalculator {

    public void calculateRevenue(int revenue) {
        System.out.println("Revenue: $" + revenue);
    }

    public void calculateRevenue(int revenue, int bonus) {
        System.out.println("Revenue: $" + (revenue + bonus));
    }

    public void calculateRevenue(int revenue, int bonus, int taxCredit) {
        System.out.println("Revenue: $" + (revenue + bonus + taxCredit));
    }
}

public class BusinessDemo {

    public static void main(String[] args) {

        RevenueCalculator calculator = new RevenueCalculator();

        calculator.calculateRevenue(10000);
        calculator.calculateRevenue(10000, 2000);
        calculator.calculateRevenue(10000, 2000, 500);
    }
}


```

### 2. Java Polymorphism Overriding OOPS concept

```
// Purpose:
// Demonstrate runtime polymorphism using method overriding
// in a business-related application.

```

```
package polymorphism;

class CorporateOffice {

    public void displayReport() {
        System.out.println("Displaying report from Corporate Office");
    }
}

class SalesDepartment extends CorporateOffice {

    @Override
    public void displayReport() {
        System.out.println("Displaying report from Sales Department");
    }
}

public class BusinessDemo {

    public static void main(String[] args) {

        CorporateOffice office = new SalesDepartment();

        office.displayReport();
    }
}






```
