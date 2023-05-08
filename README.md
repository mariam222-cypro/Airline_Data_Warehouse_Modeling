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

### There are sixteen dimension tables in three different processes:

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
15. The fact will measure the Total_Payment (sum of fare, taxes and extra fees)

## Customer Care fact
The Customer Care fact connects the passenger with the interaction and the survey.

1. The fact will measure the Customer_Inquiry_Count (count the number of interactions related to inquiries)
2. The fact will measure the Customer_Complaint_Count (count the number of interactions related to complaints)
3. The fact will measure the Customer_Feedback_Count (count the number of interactions related to feedback)
4. The fact will measure the Problem_Severity (severity level of the problem reported by the customer)

## Flight activity fact

The Flight activity fact connects the flight with the airport, location, route, airplane, flight type, and date.

1. The fact will measure the Number_of_Passengers (total number of passengers on the flight)
2. The fact will measure the Total_Revenue (total fare amount for all passengers on the flight)
3. The fact will measure the Flight_Duration (time duration of the flight)
4. The fact will measure the Departure_Delay (time delay in departure from the scheduled time)
5. The fact will measure the Arrival_Delay (time delay in arrival from the scheduled time)

## Logical Design
The logical design consists of the entity-relationship diagram (ERD) that represents the entities and their relationships in the data model. The ERD for the Airline System Data model is shown below:

[DWH_Project_Diagram.pdf](https://github.com/mariam222-cypro/Airline_Data_Warehouse_Modeling/files/11425865/DWH_Project_Diagram.pdf)


## Physical Design
The physical design includes the schema for the database tables and their attributes, primary and foreign keys, data types, and constraints. The schema for the Airline System Data model is shown below:

[TABLES.pdf](https://github.com/mariam222-cypro/Airline_Data_Warehouse_Modeling/files/11425874/TABLES.pdf)

## Demonstrative Layering Methodology
The demonstrative layering methodology includes a layered architecture for the data model, starting from the source data at the bottom and ending with the presentation layer at the top. The layers include:

1. Data Sources Layer - includes the raw data sources for the Airline System Data, such as CSV files, XML files, or JSON files.
2. Data Storage Layer - includes the Data Vault schema for storing the raw data from the data sources.
3. Data Integration Layer - includes the ETL (extract, transform, load) process for integrating the raw data into the Data Vault schema.
4. Dimensional Modeling Layer - includes the dimensional schema for reporting, querying, and aggregating the data from the Data Vault schema.
5. Business Intelligence Layer - includes the data visualization and reporting tools for presenting the data to the end-users.

# Conclusion
In conclusion, the Airline System Data model is designed to support decision-making for the airline company by analyzing the flight activity, reservation process, and customer care interaction. The Data Vault modeling technique is used for storing the raw data, and the dimensional modeling technique is used for reporting and querying the data. The logical and physical design of the data model is presented, and the demonstrative layering methodology is used for designing the layered architecture of the data model.



