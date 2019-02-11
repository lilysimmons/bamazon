# Bamazon

Amazon-like storefront via the terminal using Node.js and the MySQL. This CLI-app will take in orders from customers and deplete stock from the store's inventory using a MySQL database.

### Prerequisites

```
required node packages: `mysql`, `inquirer`.  You will also need to set up a mySQL database.  I did this via mySQL Workbench.  Refer to schema.sql and seeds.sql files for creating and structuring your database.
```

```
optional node packages: `cli-table` (makes the table pretty), `dotenv` (to hide your database info)
```

### Installing

```
npm install...
```

example:  
```
npm install mysql
```

## USER FLOW

Navigate to the repository. In the command line, start the application by typing "node bamazonCustomer.js" into the command line.  This calls a function to immediately render a table of all the products for sale.  You will then be prompted by Inquirer to enter your name and choose the ID of the product you would like to buy, and the number of units:

![insufficient inventory](images/insufficient-inventory.png)


As you can see in the screen shot above, you cannot purchase more than is stocked in the database.  If you over-draw the database you will get a message for `insufficient quantity!`.


If there is sufficient quanity in the database, your purchase will be fulfilled and your total cost will display:

![completeing a purchase](images/completing-a-purchase.png)


Your purchase will automatically deduct from the database.  Notice that we started with 10 lamps, and after a purchase of 3, the stock is now 7 lamps:

![deducts from database](images/deducts-from-database.png)


If you choose to make another purchase, the app will start over.  If you choose not to make another purchase, it terminates the connection:

![terminate connection](images/terminating-connection.png)
