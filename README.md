here is a redme code of the pyhton file
class Ticket:
    def __init__(self, number, creator, staff_id, email, description, response=None, status='Open'):
        self.number = number
        self.creator = creator
        self.staff_id = staff_id
        self.email = email
        self.description = description
        self.response = response
        self.status = status

class TicketManager:
    def __init__(self):
        self.tickets = []
    
    def create_ticket(self, ticket):
        self.tickets.append(ticket)
    
    def resolve_ticket(self, ticket_number, response):
        for ticket in self.tickets:
            if ticket.number == ticket_number:
                ticket.response = response
                ticket.status = 'Closed'
                break
    
    def display_statistics(self):
        total_tickets = len(self.tickets)
        resolved_tickets = sum(1 for ticket in self.tickets if ticket.status == 'Closed') # Fixed capitalization
        open_tickets = total_tickets - resolved_tickets
        print("Displaying Ticket Statistics")
        print(f"Tickets Created: {total_tickets}")
        print(f"Tickets Resolved: {resolved_tickets}")
        print(f"Tickets To Solve: {open_tickets}")
    
    def print_tickets(self):
        print("Printing Tickets:")
        for ticket in self.tickets:
            print(f"Ticket Number: {ticket.number}")
            print(f"Ticket Creator: {ticket.creator}")
            print(f"Staff ID: {ticket.staff_id}")
            print(f"Email Address: {ticket.email}")
            print(f"Description: {ticket.description}")
            if ticket.response:
                print(f"Response: {ticket.response}")
            print(f"Ticket Status: {ticket.status}")
            print()

# Example usage
if __name__ == "__main__":
    manager = TicketManager()

    # Creating tickets
    manager.create_ticket(Ticket(2001, "Inna", "INNAM", "inna@whitecliffe.co.nz", "My monitor stopped working"))
    manager.create_ticket(Ticket(2002, "Maria", "MARIAH", "maria@whitecliffe.co.nz", "Request for a videocamera"))
    manager.create_ticket(Ticket(2003, "John", "JOHNS", "john@whitecliffe.co.nz", "Password change", "New password generated: Jhon21", 'pending'))

    # Displaying initial statistics
    manager.display_statistics()

    # Resolving a ticket
    manager.resolve_ticket(2001, "The monitor has been replaced.")

    # Printing tickets
    manager.print_tickets()
This script defines two classes: Ticket and TicketManager.

Ticket class represents a ticket with attributes like number, creator, staff ID, email, description, response, and status. The response attribute is optional and defaults to None, and the status defaults to 'Open'.
TicketManager class manages a collection of tickets. It has methods to create tickets, resolve tickets, display statistics, and print tickets.
In the example usage part:

A TicketManager object is created.
Three tickets are created using the create_ticket method of TicketManager.
Initial statistics are displayed.
One ticket is resolved using the resolve_ticket method.
All tickets are printed using the print_tickets method.# Tirth
