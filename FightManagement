class FlightTicketBookingSystem:
    available_seats = {
        'E': 50,
        'B': 20,
        'FC': 10
    }

    prices = {
        'E': 300,
        'B': 600,
        'FC': 1000
    }

    booked_seats = {
        'E': 0,
        'B': 0,
        'FC': 0
    }

    destinations = {
        'New York': 'NYC',
        'Los Angeles': 'LAX',
        'Chicago': 'ORD',
        'Miami': 'MIA'
    }

    payment_methods = ['CC', 'DC', 'PP']

    @staticmethod
    def display_available_seats():
        print("\nAvailable Seats:")
        for class_code, seats in FlightTicketBookingSystem.available_seats.items():
            class_name = {'E': 'Economy', 'B': 'Business', 'FC': 'First Class'}[class_code]
            print(f"{class_name}: {seats} seats")

    @staticmethod
    def display_destinations():
        print("\nAvailable Destinations:")
        for city, code in FlightTicketBookingSystem.destinations.items():
            print(f"{city} ({code})")

    @staticmethod
    def display_payment_methods():
        print("\nAvailable Payment Methods:")
        for method in FlightTicketBookingSystem.payment_methods:
            print(method)

    @staticmethod
    def book_ticket():
        class_name = input("Enter class (Economy/Business/First Class): ").strip()
        num_tickets = int(input("Enter the number of tickets to book: ").strip())
        destination = input("Enter destination (NYC/LAX/ORD/MIA): ").strip()
        payment_method = input("Enter payment method (CC/DC/PP): ").strip()

        class_code = {'Economy': 'E', 'Business': 'B', 'First Class': 'FC'}.get(class_name)
        if class_code not in FlightTicketBookingSystem.available_seats:
            print("Invalid class.")
            return
        
        if destination not in FlightTicketBookingSystem.destinations.values():
            print("Invalid destination.")
            return
        
        if payment_method not in FlightTicketBookingSystem.payment_methods:
            print("Invalid payment method.")
            return

        if num_tickets <= FlightTicketBookingSystem.available_seats[class_code]:
            FlightTicketBookingSystem.available_seats[class_code] -= num_tickets
            FlightTicketBookingSystem.booked_seats[class_code] += num_tickets
            total_price = FlightTicketBookingSystem.prices[class_code] * num_tickets
            print(f"Booking successful! {num_tickets} {class_name} ticket(s) to {destination}. Total Price: ${total_price}")
            print(f"Payment successful using {payment_method}.")
        else:
            print(f"Sorry, there are not enough available {class_name} seats.")

    @staticmethod
    def cancel_ticket():
        class_name = input("Enter class (Economy/Business/First Class): ").strip()
        num_tickets = int(input("Enter the number of tickets to cancel: ").strip())
        destination = input("Enter destination (NYC/LAX/ORD/MIA): ").strip()
        payment_method = input("Enter payment method for refund (CC/DC/PP): ").strip()

        class_code = {'Economy': 'E', 'Business': 'B', 'First Class': 'FC'}.get(class_name)
        if class_code not in FlightTicketBookingSystem.available_seats:
            print("Invalid class.")
            return
        
        if destination not in FlightTicketBookingSystem.destinations.values():
            print("Invalid destination.")
            return
        
        if payment_method not in FlightTicketBookingSystem.payment_methods:
            print("Invalid payment method.")
            return

        if num_tickets <= FlightTicketBookingSystem.booked_seats[class_code]:
            FlightTicketBookingSystem.available_seats[class_code] += num_tickets
            FlightTicketBookingSystem.booked_seats[class_code] -= num_tickets
            total_refund = FlightTicketBookingSystem.prices[class_code] * num_tickets
            print(f"Cancellation successful! {num_tickets} {class_name} ticket(s) to {destination} cancelled. Total Refund: ${total_refund}")
            print(f"Refund processed to your {payment_method}.")
        else:
            print("Invalid number of tickets to cancel.")

    @staticmethod
    def menu():
        while True:
            print("\nMenu:")
            print("1. Display Available Seats")
            print("2. Display Destinations")
            print("3. Display Payment Methods")
            print("4. Book Ticket")
            print("5. Cancel Ticket")
            print("6. Quit")

            choice = input("Enter your choice: ").strip()

            if choice == '1':
                FlightTicketBookingSystem.display_available_seats()
            elif choice == '2':
                FlightTicketBookingSystem.display_destinations()
            elif choice == '3':
                FlightTicketBookingSystem.display_payment_methods()
            elif choice == '4':
                FlightTicketBookingSystem.book_ticket()
            elif choice == '5':
                FlightTicketBookingSystem.cancel_ticket()
            elif choice == '6':
                print("Exiting...")
                break
            else:
                print("Invalid choice. Please try again.")

# To run the menu, instantiate the class and call the menu method
if __name__ == "__main__":
    FlightTicketBookingSystem.menu()
