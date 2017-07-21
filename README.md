"# PartsAvatar.ca-Intern" 
The objective of this problem is to allocate the orders from a shopping cart to our warehouses while minimzing the cost of shipment.

Our warehouses contain different products in varying quantity, and we want to figure out a way to take a shopping cart from a user, and distribute the order among the warehouses. The distribution is dependent on the distance of the warehouses from the user, and the quantity of the ordered product each warehouse contains. Minimzing the total distance will help us minimize the cost of shipment. 

In code, our warehouses are represented through an enum like so;

public enum Warehouse {
    EDMONTON, MONTREAL, TORONTO, VANCOUVER
}
The values in the enum represent the locations of our warehouses.

We want to optimize the distribution by using the warehouses closest to the user. A helper function is provided to assist you with this. 

/**
This function returns a List of Warehouse sorted by distance from the provided Address.

Input: Address object that will be used to compare warehouses' distance
Output: A List of Warehouse sorted by distance from the inputted Address
**/
public List<Warehouse> getNearestWarehouses(Address addressOfCustomer);
For the scope of this problem, you won't have to be concerned with innards of an Address.

Since we also need to know the quantity of a product in the warehouses,  another helper function will be provided to assist you with this.

/**
Given a product ID this function will return a Map with a warehouse as key, and the quantity of the
given product in that warehouse as the value

Input: A String representing the product ID
Output:  Map with a warehouse (Warehouse) as key, and the quantity (Integer) of the
given product in that warehouse as the value
**/
public Map<Warehouse, Integer> getInventory(String product);
Using the given information, you will implement the following function.

/**
This function will take a shopping cart (Map with product ID as key, and desired quantity as Integer),
and an Address and return the inventory allocation.

Input: Shopping cart (map between product ID and desired quantity) and Address
Output: 
Map<String, Map<Warehouse, Integer>>  will be the structure that you will output from your function.

The outer map's key will be the product ID, and the value will be the inner map.

The inner map's key is a Warehouse and the value is the quantity that will be retrieved from that warehouse for the product ID (outer map's key). 
**/

public Map<String, Map<Warehouse, Integer>>  getInventoryAllocation(Map<String, Integer> shoppingCart, Address addressOfCustomer) {
 
}
You may assume all warehouses collectively contain enough inventory to fulfil the shopping cart, every entry in the shopping cart has a quantity > 0 and that the shopping cart contains at least one entry. Output should not contain any warehouse or any product with 0 quantity. 

Example:

A shopping can contain the following entries;

{"Product1" -> 15}

{"Product2" -> 4}

{"Product3" -> 2}

If the address is from Toronto we should have the following output from your function:

{"Product1" ->    { Toronto -> 10
                            Montreal -> 5 }}

{"Product2 -> {EDMONTON -> 4}}

{"Product3" -> {Toronto -> 2}}

Input
Product1 15
Product2 4
Product3 2
Toronto

Output
Product1
MONTREAL 5
TORONTO 10
Product2
EDMONTON 4
Product3
TORONTO 2