### 1. Java Encapsulation OOPS concept with set and get methods
```
// Purpose:
// Demonstrate how data can be stored in a business-related class,
// updated through a method, retrieved using a getter method,
// and displayed in another class.

```

```
package encapsulation;

class CompanyRevenue {
	private int revenue;
	
	CompanyRevenue(int revenue) {
		this.revenue = revenue;
	}
	
	public void setRevenue() {
		revenue += 200;
	}
	
	public int getRevenue() {
		return revenue;
	}
	
}

class RevenueReport {
	private int revenue;
	
	RevenueReport(int revenue) {
		this.revenue = revenue;
	}
	
	public void displayRevenue() {
		System.out.println("Company Revenue is: " + revenue);
	}
	
}


public class Revenue {

	public static void main(String[] args) {

		CompanyRevenue companyrevenue = new CompanyRevenue(100);
		
		companyrevenue.setRevenue();
		
		RevenueReport RevenueReport = new RevenueReport(companyrevenue.getRevenue());
		
		RevenueReport.displayRevenue();
		
	}

}



```
