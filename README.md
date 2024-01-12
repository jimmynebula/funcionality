# this is a simple booking software for Comedians, DJ, or any freelancer
import datetime 

 

# Example services with their costs 

services = { 

    'Karaoke Night’: 200, 

    'DJ Club Night’: 250, 

    'Trivia Night’: 175, 

    'Comedy Night’: 400, 

} 

 

# Function to display available dates 

def display_dates(): 

    today = datetime.date.today() 

    available_dates = [today + datetime.timedelta(days=i) for i in range(1, 30)] 

    print("Available dates:") 

    for date in available_dates: 

        print(date) 

 

# Function to choose a service 

def choose_service(): 

    print("Available services:") 

    for service, cost in services.items(): 

        print(f"{service}: ${cost}") 

    selected_service = input("Please select a service: ") 

    return selected_service 

 

# Function to process payment 

def process_payment(service): 

    cost = services[service] 

    deposit = cost * 0.25 

    print(f"Your deposit for the {service} is: ${deposit:.2f}") 

 

# Main booking function 

def book_appointment(): 

    print("Welcome to the Appointment Booking System") 

    display_dates() 

    date = input("Please choose your appointment date (YYYY-MM-DD): ") 

    service = choose_service() 

    process_payment(service) 

    print(f"Appointment booked for {service} on {date}. Thank you!") 

 

# Run the booking system 

book_appointment() 
