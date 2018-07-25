# COJ_MIS_Problems

# Pizza Store Application

<h3>PizzaStore.java</h3>
<hr/>
<h4>Specification</h4>
<pre>
<ol>
<li>The following are the data members of pizza store</li>
<ul>
  <li>Define the pizza array of int:SIZE=30</li>
  <li>Define static int:token=0</li>
</ul>
<li>The following are the methods specification:</li>
  <ul>
      <li>Add Method</li>
      Name of Method: add
      Arguments     : one of type Pizza
      Return Type   :void
      Specification : * Check if token is less then pizza length then add pizza info inside pizza array of index token.
                      * Otherwise throw the exception with message colsed for today!!.
      <li>Print Order</li>
      Name of Metohd : printOrders
      Arguments      : no argument
      Return Type    : void
      Specification  : * If tokens is equal to zero then display "No orders till now" and return control.
                       * Otherwise display Token and display 
                         eg:
                          Pizza Type : Veg
                          Pizza Size : Small
                          Pizza BreadBase : Pan
                          **Pizz Topping selecteed are*****
                          Extra Cheese
                          Olives
                          Bill Calucuated is :335.0
     <li>Print Size</li>
     Name of Method   : printSizes
     Arugument        : No
     Return Type      : void
     Purpose          : Display All sizes of Pizza
                      Eg:  1.Samll 2.Medium  3. Large
     <li>Choose Size</li>
     Name of Method   : chooseSize
     Argument         : No   // at method throws Exception
     Return Type      : String
     Purpose          : Asked user to enter the size of Pizza and select it in the form of string and return it otherwise return execption with "invalid size!!" message.
   
   <li>Print Types</li>
     Name of Method : printTypes
     Argument       : No
     Return Type    : void
     Purpose        : Display to the customer  information of Pizza Type 
                         eg:  1.Veg  2.Non-Veg
    <li>Choose Type</li>  
     Name of Method  : chooseType
     Argument        : No
     Return Type     : String
     Purpose         : Asked user to enter the type of pizza and select it in the form of string and return it.
                       Otherwise return Exception with "Invalid type!!" message.
    
   <li>Print Toppings</li>
     Name of Method : printToppings
     Argument       : No
     Return Type    : void
     Purpose        : Display to the customer  information of toppings 
                         eg:  1.Extra Cheese  2.Olives
    <li>Choose Toppings</li>  
     Name of Method  : chooseTooping
     Argument        : No
     Return Type     : String
     Purpose         : Asked user to enter the toppings and select it in the form of string and return it.
                       Otherwise return Exception with "Invalid Toppings!!" message.
    
     
   <li>Print BreadBases</li>
     Name of Method : printBreadBases
     Argument       : No
     Return Type    : void
     Purpose        : Display to the customer  information about breadbases 
                         eg:  1.Pan  2.Thin Crust
    <li>Choose BreadBases</li>  
     Name of Method  : chooseBreadBase
     Argument        : No
     Return Type     : String
     Purpose         : Asked user to enter the breadBases and select it in the form of string and return it.
                       Otherwise return Exception with "Invalid BreadBase!!" message.
     
  </ul>
  </ol>
</pre>

# Pizza.java
<pre>
<ol>
<li>The following are the data members of Pizza</li>
<ul>
  <li>string:size</li>
  <li>string:type</li>
  <li>string:breadBase</li>
  <li>string[]:toppings</li>
  <li>Define static int:token=0</li>
</ul>
<li>The following are Constructor</li>
Arugments     : Four arguments(String size,String type,String breadBase,String[] toppings) throws Exception.
Specification : 
               *  If !isValidSize(size)  then throw new Exception with message "Invalid Size: Pizza is available in Small,Medium,Large"
               *  If !isValidType(type) then throw new Exception with message "Invalid Type : We sell only Veg and Non-Veg Pizza".
               *  If !isValidBreadBase(breadBase) then throw new Exception with message "Invalid Bread Base: We make only Pan and Thin-Crust".
               * If !areValidToppings(toppings) then throw new Exception with message "Invalid Toppings: One of toppings selected is not available".
               * otherwise initialize the size,type,breadBase,and topping to instance var.
               
 <li>The following are the methods </li>
  <ul>
  <li>Validsize</li>
  Name of Method : isValidSize
  Arguments      : One of type String 
  Return Type    : boolean
  Purpose        : * If size is equal to small or medium or large return true otherwise return false.
  
  <li>ValidType</li>
  Name of Method : isValidType
  Arguments      : One of type String 
  Return Type    : boolean
  Purpose        : * If type is equal to veg or non-veg return true otherwise return false.
  
  
  <li>ValidBreadBase</li>
  Name of Method : isValidBreadBase
  Arguments      : One of type String 
  Return Type    : boolean
  Purpose        : * If type is equal to Thin-Crust or Pan return true otherwise return false.
  
  
  <li>ValidToppings</li>
  Name of Method : areValidToppings
  Arguments      : One of type array String[] 
  Return Type    : boolean
  Purpose        : * If type is not equal to Extra Cheese and Olive return false otherwise return true.
  
 <li>Setter and getter for Instance variables</li>

<li> Caluclate Price</li>
  Name of Method : calculatePrice
  Arguments      : No 
  Return Type    : double
  Specification  : * If size is equal to "small" then price  = price + 100.00;
                   * If size is equal to "medium" then price = price +250.00;
                   * If size is equal to "large" then  price = price +450.00;
                   * If type is equal to Veg then price = price+50.00;
                   * If type is equal to Non-Veg then price = price+100.00;
                   * If type is equal to Thin-Crust then price = price+75.00;
                   * If type is equal to Pan then price = price+55.00;
                   * If toppings is equal to Extra Cheese then price = price + 90.00 
                      otherwise if toppings is equal to Olives then price = price+40.00;
                   * Then final return price.
                 
                   
  


  
  </ul>
  </ul>
</pre>

<hr/>
# Solution
# PizzaStore.java
<pre>
import java.util.Scanner;

public class PizzaStore {
	private Pizza[] pizzas = new Pizza[30];
	private static int tokenNo = 0;

	public void add(Pizza pizza) throws Exception {
		if (tokenNo < pizzas.length) {
			this.pizzas[tokenNo] = pizza;
			tokenNo++;
		} else {
			throw new Exception("Closed For Today !!!");
		}

	}

	public void printOrders() {
		if (tokenNo == 0) {
			System.out.println("No orders till now");
			return;
		} else {
			System.out.println("-->tokenNo:" + tokenNo);
			for (int i = 0; i < tokenNo; i++) {
				System.out.println("Pizza Type : " + pizzas[i].getType());
				System.out.println("Pizza Size : " + pizzas[i].getSize());
				System.out.println("Pizza BreadBase : " + pizzas[i].getBreadBase());
				System.out.println("**Pizz Topping selecteed are*****");
				for (String topping : pizzas[i].getToppings()) {
					System.out.println(topping);
				}
				System.out.println("Bill Calucuated is :" + pizzas[i].calculatePrice());
			}
		}

	}

	private static void printSizes() {
		System.out.println("1.Small");
		System.out.println("2.Medium");
		System.out.println("3.Large");
	}

	private static String chooseSize() throws Exception {
		System.out.print("Enter size : ");
		int choice = new Scanner(System.in).nextInt();
		String size = null;
		if (choice == 1) {
			size = "Small";
		} else if (choice == 2) {
			size = "Medium";
		} else if (choice == 2) {
			size = "Large";
		} else {
			throw new Exception("Invalid Size !!!");
		}
		return size;
	}

	private static void printTypes() {
		System.out.println("1. Veg");
		System.out.println("2. Non-Veg");
	}

	private static String chooseType() throws Exception {
		System.out.print("Enter  Type : ");
		int choice = new Scanner(System.in).nextInt();
		String type = null;
		if (choice == 1) {
			type = "Veg";
		} else if (choice == 2) {
			type = "Non-Veg";
		} else {
			throw new Exception("Invalid Type !!!");
		}
		return type;

	}

	private static void printToppings() {
		System.out.println("1. Extra Cheese ");
		System.out.println("2. Olives ");
	}

	private static String chooseTopping() throws Exception {
		System.out.print("Enter Toppings : ");
		int choice = new Scanner(System.in).nextInt();
		String toppings = null;
		if (choice == 1) {
			toppings = "Extra Cheese";
		} else if (choice == 2) {
			toppings = "Olives";
		} else {
			throw new Exception("Invalid Topping !!!");
		}
		return toppings;
	}

	private static void printBreadBases() {
		System.out.println("1. Pan ");
		System.out.println("2. Thin Crust ");
	}

	private static String chooseBreadBase() throws Exception {
		System.out.print("Enter bread base : ");
		int Choice = new Scanner(System.in).nextInt();
		String breadBase = null;
		if (Choice == 1) {
			breadBase = "Pan";
		} else if (Choice == 2) {
			breadBase = "Thin-Crust";
		} else {
			throw new Exception("Invalid breadBase !!!");
		}
		return breadBase;
	}

	public static void main(String[] args) throws Exception {

		Scanner scanner = new Scanner(System.in);
		PizzaStore pizzaStore = new PizzaStore();

		do {
			System.out.println("1. Order Pizza ");
			System.out.println("2. List Orders ");
			System.out.println("3. For Exit");
			System.out.print("Enter Choice : ");
			int choice = scanner.nextInt();
			switch (choice) {
			case 1:
				printSizes();
				String size = chooseSize();
				printTypes();
				String type = chooseType();
				printToppings();
				String[] toppings = new String[2];
				toppings[0] = chooseTopping();
				toppings[1] = chooseTopping();
				printBreadBases();
				String breadBase = chooseBreadBase();
				Pizza pizza = new Pizza(size, type, breadBase, toppings);
				pizzaStore.add(pizza);
				break;

			case 2:
				pizzaStore.printOrders();
				break;
			case 3:
				System.exit(1);
			default:
				System.out.println("Invalid choice...");
				break;
			}

		} while (true);

	}

}
//---------------------------------------------------------------PizzaStore.java-------------------------

//------------------------------------------------------------------Pizza.java--------------------------


</pre>

# Pizza.java
<pre>
public class Pizza {
	private String size;
	private String type;
	private String breadBase;
	private String[] toppings;

	public Pizza() {

	}

	public Pizza(String size, String type, String breadBase, String[] toppings) throws Exception {

		if (!isValidSize(size)) {
			throw new Exception("Invlaid Size : Pizza is available in small, medium and large !!!");
		}
		if (!isValidType(type)) {
			throw new Exception("Invlaid type : We sell only Veg and Non-veg Pizza !!!");
		}
		if (!isValidBreadBase(breadBase)) {
			throw new Exception("Invlaid Bread Base : We make only Thin Crust and Pan !!!");
		}
		if (!areValidToppings(toppings)) {
			throw new Exception("Invlaid Toppings : One of the toppings selected is not availble !!!");
		}
		this.size = size;
		this.type = type;

		this.breadBase = breadBase;
		this.toppings = toppings;
	}

	public boolean isValidSize(String size) {
		return size.equalsIgnoreCase("small") || size.equalsIgnoreCase("medium") || size.equalsIgnoreCase("large");
	}

	public boolean isValidType(String type) {

		return type.equalsIgnoreCase("Veg") || type.equalsIgnoreCase("Non-Veg");
	}

	public boolean isValidBreadBase(String breadBase) {
		return breadBase.equalsIgnoreCase("Thin-Crust") || breadBase.equalsIgnoreCase("Pan");
	}

	public boolean areValidToppings(String[] toppings) {

		for (int i = 0; i < toppings.length; i++) {
			if (!toppings[i].equalsIgnoreCase("Extra Cheese") && !toppings[i].equalsIgnoreCase("Olives")) {
				return false;
			}
		}
		return true;
	}

	public String getSize() {
		return size;
	}

	public void setSize(String size) throws Exception {
		if (isValidSize(size)) {
			this.size = size;
		}

	}

	public String getType() {
		return type;
	}

	public void setType(String type) throws Exception {
		if (isValidType(type)) {
			this.type = type;
		}

	}

	public String getBreadBase() {
		return breadBase;
	}

	public void setBreadBase(String breadBase) throws Exception {
		if (isValidBreadBase(breadBase)) {
			this.breadBase = breadBase;
		}

	}

	public String[] getToppings() {
		return toppings;
	}

	public void setToppings(String[] toppings) throws Exception {
		if (!areValidToppings(toppings)) {
			throw new Exception("Invlaid Toppings : One of the toppings selected is not availble !!!");
		}
		this.toppings = toppings;

	}

	public double calculatePrice() {
		 
		double price = 0.0;

		if (size.equalsIgnoreCase("small")) {
			price += 100.0;
		}
		if (size.equalsIgnoreCase("medium")) {
			price += 250.0;
		}
		if (size.equalsIgnoreCase("large")) {
			price += 450.0;
		}

		if (type.equalsIgnoreCase("Non-Veg")) {
			price += 100.0;
		}
		if (type.equalsIgnoreCase("Veg")) {
			price += 50.0;
		}
		if (breadBase.equals("Thin Crust")) {
			price += 75.00;
		}
		if (breadBase.equals("Pan")) {
			price += 55.00;
		}

		for (int i = 0; i < toppings.length; i++) {
			if (toppings[i].equalsIgnoreCase("Extra Cheese")) {
				price += 90.0;
			}
			if (toppings[i].equalsIgnoreCase("Olives")) {
				price += 40.0;
			}
		}
		
		return price;

	}
}

	


</pre>
