# Airline_Data_Warehouse_Modeling
Analyze Airline business processes and expand the company by discovering new opportunities

## Introduction:

A major airline company has hired you to analyze their current business processes and discover new opportunities to expand the company. The first deliverable for this project is to focus on flight activity and ensure good ongoing business processes. The marketing department wants to analyze the flights taken by frequent flyers, fare basis they pay, their upgrade frequency, how they earn and redeem frequent flyer miles, their response to special fare promotions, length of overnight stays, and the proportion of frequent flyers with gold, platinum, or titanium status. Additionally, the finance team is interested in analyzing the reservation process to analyze company profits. Lastly, the company provides customer care interaction before, within, and after the trip to handle inquiries, complaints, and feedback.

The aim is to use modeling techniques to support decision making and analysis for the airline business processes.

## Modelling Technique:

The chosen modeling technique is Data Vault, a way to store airline system data. Dimensional modeling was built to report and query the data from the system. Data Vault was chosen because the passenger data changes frequently, and the entire table is rewritten every time there is a change. The parallel loading also increases performance and optimization.

## The Modelling Process:

The business has three main processes, and the grain will be measured as follows:

1. Reservation fact, measured per transaction
2. Customer care fact, measured per transaction
3. Flight activity fact, measured per day

There are sixteen dimension tables in three different processes:

1. Booking_Channel: Represents the way that passengers book, whether online or through an agent.
2. Airport: Represents information about the airport, such as its name, ID, and code.
3. Flight: Represents information about the flight, such as its ID, departure time, arrival time, duration, and if the flight is canceled.
4. Location: Represents information about the airport location, such as its ID, city, state, country, latitude, and longitude.
5. Route: Represents information about the route of the flight, such as the origin airport, destination airport, and distance.
6. Airplane: Represents information about route airplanes, such as the airplane name and model number, manufacture code, capacity, and weight.
7. Flight_Type: Represents information about the flight type, whether it's a non-stop flight or connected flight, the number of stops of the connected flights, and the number of layover hours.
8. D_Date: Represents the date, date of week, date of month, date of year, month number, quarter, and year.
9. Interaction: Represents the ID of the interaction and its type of time, whether it's before, after, or within the flight.
10. Survey: Represents the way customers give feedback, the type whether it's online by email or offline as paper, and the category of the survey, such as the type of services that the customer gave a score.
11. Fare: Represents the fare of the ticket, how the fare is calculated like base fare and taxes, and if there are extra fees.
12. Ticket: Represents the ticket ID, status (paid or unpaid), and its type (e-ticket or paper) and the class of his ticket.
13. Passenger: Represents the information about each passenger, such as passenger ID, first name, last name, gender, date of birth, phone number, address, and the status as to whether this passenger is a frequent flyer or not.
14. Booking_Class: Represents the booking class ID and its type, whether it's an economy with its types and how much the price will increase by a percentage or business class with its type and how much the price will increase by a percentage or first class with its type and how much the price will increase by a percentage by calculating Class_Fare_Per%.
