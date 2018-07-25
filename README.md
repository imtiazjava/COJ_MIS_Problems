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

