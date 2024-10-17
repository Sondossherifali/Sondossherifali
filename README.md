Step 1: Initial order with products A, B, C, D, E
order = [
    {"product": "A", "quantity": 2, "price_per_unit": 10},
    {"product": "B", "quantity": 5, "price_per_unit": 8},
    {"product": "C", "quantity": 7, "price_per_unit": 2},
    {"product": "D", "quantity": 4, "price_per_unit": 12},
    {"product": "E", "quantity": 3, "price_per_unit": 6}
]

# Step 2: Add products G and H to the order
order.extend([
    {"product": "G", "quantity": 20, "price_per_unit": 1},
    {"product": "H", "quantity": 6, "price_per_unit": 9}
])

# Step 3: Replace products E and G with M, N, and P
# Remove E and G from the order
order = [item for item in order if item["product"] not in ["E", "G"]]

# Add products M, N, and P
order.extend([
    {"product": "M", "quantity": 3, "price_per_unit": 10},
    {"product": "N", "quantity": 5, "price_per_unit": 3},
    {"product": "P", "quantity": 1, "price_per_unit": 7}
])

# Step 4: Retrieve product C (which means keeping it as is if already present)
# Since C is still present in the order, we don't need to make any changes.

# Step 5: Calculate the total price
# Detailed calculation for each product
price_details = [(item["product"], item["quantity"] * item["price_per_unit"]) for item in order]
total_price = sum(price for _, price in price_details)

# Prepare the final order with prices calculated for each product
final_order = [
    {"product": item["product"], 
     "quantity": item["quantity"], 
     "price": item["quantity"] * item["price_per_unit"]} 
    for item in order
]

# Step 6: Display the results
def display_final_order(order, price_details, total_price):
    print("Final Order:")
    for item in order:
        print(f"Product {item['product']}: Quantity {item['quantity']}, Price {item['price']}")
    
    print("\nPrice Details:")
    for product, price in price_details:
        print(f"Product {product}: Price {price}")

    print(f"\nTotal Price: {total_price}")

# Call the function with the final order, price details, and total price
display_final_order(final_order, price_details, total_price)
