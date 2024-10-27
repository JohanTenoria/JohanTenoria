def generate_invoice(items):
    print("\n====== INVOICE ======")
    total = 0
    for item in items:
        name, quantity, price = item
        subtotal = quantity * price
        print(f"{name} (x{quantity}) - ${subtotal:.2f}")
        total += subtotal
    
    tax = total * 0.12  # 12% tax
    grand_total = total + tax
    
    print(f"\nSubtotal: ${total:.2f}")
    print(f"Tax (12%): ${tax:.2f}")
    print(f"Grand Total: ${grand_total:.2f}")
    print("=====================\n")

def main():
    items = []
    while True:
        name = input("Enter item name (or 'done' to finish): ")
        if name.lower() == 'done':
            break
        quantity = int(input("Enter quantity: "))
        price = float(input("Enter price: "))
        items.append((name, quantity, price))
    
    generate_invoice(items)

if __name__ == "__main__":
    print("Welcome to the Simple Invoicing System")
    main()
