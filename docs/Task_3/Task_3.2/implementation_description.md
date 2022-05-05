# Description for task 3.2

food_ordering_system.zip contains 2 folders - pages & component folders:
- pages folder consists of multiple pages or views of the food ordering system such as home page, ordering page, etc.
- component folder comprises of 5 files implementing 5 main components (foodcart.js, payment.js, fooditem.js, orders.js, possystem.js)

The system is composed by three main smaller subsystems: WebRestaurant, Kitchen, and Accounting and 2 separated components: BankDatabase and POSSystem
        
Main subsystem:
- The WebRestaurant subsystem contains two components related to food ordering - FoodCart & Payment: 
    - The FoodCart component provides the FoodOrdering interface for customers to select and order food. Furthermore, it utilizes OrderEntry interface provided by Orders component so that the customer can directly make the order from their current cart and wait for confirmation of the clerk.
    - The Payment component provides InvoiceDisplay interface to display the invoice for customers if required and CreditCardPayment interface for customers to pay by their credit cards. In addition, this component requires the PaymentMethod interface provided by BankDatabase component in order to make the transaction if the customer is willing to pay in credit card.

- The Accounting subsystem contains only Orders component. This component requires the OrderableItem interface provided by FoodItem component so as to notify the customer which food item is valid to be served by the restaurant. It also provides the OrderEntry interface so as to transform each valid food cart into an unique order.

- The Kitchen subsystem contains only FoodItem component. This components is to store the available food in the restaurant and also to check the quantity for each food ingredient.
        
Separated components to provide additional service:
- POSSystem component provides OrderConfirmation and OrderDisplay interfaces for the customers to confirm their orders and to display the order.
- BankDatabase component provides the PaymentMethod interface for making transaction valid on the Payment component and recording the transaction.