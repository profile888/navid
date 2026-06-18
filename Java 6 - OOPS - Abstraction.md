### 1. Java Abstract OOPS concept

```
// Purpose:
// Show abstraction using a simple payment system.
// Any child classes to Payment must have a method called Pay

```

```
abstract class Payment {
    abstract void pay(double amount);

    void receipt() {
        System.out.println("Receipt generated");
    }
}

class CardPayment extends Payment {
    void pay(double amount) {
        System.out.println("Card Payment: $" + amount);
    }
}

public class BusinessDemo {
    public static void main(String[] args) {

        Payment p = new CardPayment();
        p.pay(1000);
        p.receipt();
    }
}






```
