
class Train:
    def __init__(self, train_no, name, source, destination):
        self.train_no = train_no
        self.name = name
        self.source = source
        self.destination = destination

    def display_train(self):
        print("Train No:", self.train_no)
        print("Train Name:", self.name)
        print("Source:", self.source)
        print("Destination:", self.destination)


class Ticket:
    def __init__(self, pnr, passenger, amount):
        self.pnr = pnr
        self.passenger = passenger
        self.amount = amount
        self.status = "Confirmed"

    def new_ticket(self):
        print("Ticket Booked Successfully!")
        print("PNR Number:", self.pnr)

    def make_payment(self):
        print("Payment Amount:", self.amount)

    def cancel_ticket(self):
        self.status = "Cancelled"
        print("Ticket Cancelled")


class Passenger:
    def __init__(self, name, age, gender):
        self.name = name
        self.age = age
        self.gender = gender

    def search_train(self):
        print("Searching Train...")

    def book_ticket(self, pnr, amount):
        self.ticket = Ticket(pnr, self.name, amount)
        self.ticket.new_ticket()

    def make_payment(self):
        self.ticket.make_payment()

    def cancel_ticket(self):
        self.ticket.cancel_ticket()


class Payment:
    def make_payment(self, amount):
        print("Payment Successful:", amount)

    def get_refund(self, amount):
        print("Refund Amount:", amount)


class RailwayDatabase:
    def response(self):
        print("Railway Database Response Successful")


# Main Program
train = Train(12627, "Karnataka Express", "Bengaluru", "Delhi")
passenger = Passenger("Moulya", 22, "Female")
payment = Payment()
database = RailwayDatabase()

train.display_train()
passenger.search_train()
passenger.book_ticket(1234567890, 1500)
payment.make_payment(1500)
database.response()

# Cancel Ticket
passenger.cancel_ticket()
payment.get_refund(1500)
