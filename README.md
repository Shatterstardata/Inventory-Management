# Inventory-Management
Inventory Management Capstone Project for Purwadhika Digital Technology School

# Program Purpose
This program is designed to manage an inventory system. It allows users (managers) to add, update, delete, view, sort, and get low-stock alerts for products. It also includes features to manage backups of deleted products. The inventory data is stored as a list of dictionaries, with each dictionary representing a product. This allows us to easily access and manipulate individual product records.


# Key Libraries
1. re: The re module is used for regular expressions to validate inputs like SKU, availability, lead times, and supplier names.
2. tabulate: This is used to display the inventory and backup data in a neat, table format for better readability.

# Dataset
Dummy Inventory: A list of dictionaries is used to simulate an inventory with details like SKU, product type, availability, stock levels, shipping costs, etc. This makes it easy to visualize and manipulate product information during program execution.

# Input Validation Functions
get_validated_input: This is a general-purpose function that prompts the user for input and validates it against custom validation functions.
Validation functions: Each validation function (e.g., validate_sku, validate_availability, etc.) ensures that the user inputs valid data for each field.

# Manager Menu Functions
1. Add Product (add_product): This function guides the manager through the process of adding a new product. It uses the validation functions to ensure that all the necessary data is entered correctly. The SKU must be unique. Product details like stock levels, lead times, and shipping costs are collected and validated.
The product is added to the inventory list if all inputs are valid.

2. Update Product (update_product): This function allows updating existing products. It first searches for the SKU entered by the manager, then prompts for changes to each field. If a field is left blank, the original value is retained. Changes are displayed after the update is completed.

3. Delete Product (delete_product): Products can be deleted from the inventory, but a backup is stored in the backup_list. This allows for restoring the data if necessary.

4. Restore and Clear Backup: These features either restore deleted products or permanently clear the backup list.

5. View Inventory (view_inventory): Displays all the products in a neat tabulated format using tabulate. It also shows any deleted products stored in the backup list.

6. Sort Inventory (sort_inventory): This allows sorting the inventory by various fields such as product type, SKU, stock levels, lead times, or shipping costs. The user can choose the sorting field and the order (ascending or descending). After sorting, the inventory is reset to its original order.

7. Low Stock Alert (low_stock_alert)
The manager can enter a threshold value, and the program will display all products with stock levels below this threshold. The program also allows restocking of low-stock items by entering the SKU and the amount to restock.

# User Interface Functions
1. manager_menu(): Provides a simple text-based menu for the manager, allowing them to add, update, delete, view inventory, or check low stock.
   
2. login(): Verifies the user’s credentials before granting access to the system.
   
3. main_menu(): The main function that kicks off the program, calling the login() function and then displaying the manager menu.
