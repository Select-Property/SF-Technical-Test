# Salesforce Technical Test

## Objective:
Develop Salesforce functionality to manage room units and reservations for a hypothetical property management system.

## Instructions:
Please complete the following tasks and submit your source code files along with any deployment instructions and test class results. Ensure your code adheres to Salesforce best practices, particularly in handling bulk data operations and error handling.

## Task 1: Custom Object Creation
Create the following two custom objects with the specified fields:

### Room Unit

- Unit_Name (Text)
- Unit_Type (Picklist: Studio, 1 Bedroom, 2 Bedroom, Suite)
- Floor (Number)
- Status (Picklist: Available, Occupied, Maintenance)

### Reservation

- First_Name (Text)
- Last_Name (Text)
- Email_Address (Email)
- Phone_Number (Phone)
- Unit (Lookup to Room Unit)
- Start_Date (Date)
- End_Date (Date)

## Task 2: Apex Class for Conflict Checking
Write an Apex class named ReservationManager with methods to handle creating and checking for reservation conflicts. Implement the following functionality:

Check for Conflicts: Method should accept Start_Date and End_Date for a new reservation and a unit, and return a boolean indicating if there is a conflict with existing reservations for the same unit.
Create Reservation: Method should create a new reservation record only if there is no conflict. If there is a conflict, it should throw a custom exception.

## Task 3: Apex REST API Endpoints
Develop custom Apex REST API endpoints to manage reservations:

POST /api/reservation: Endpoint to create a new reservation. It should use the ReservationManager class to check for conflicts and create the reservation if no conflict exists.
GET /api/reservations/{unitId}: Endpoint to retrieve all reservations for a specific room unit.
GET /api/reservations?start={startDate}&end={endDate}: Endpoint to retrieve all reservations that start and end between the provided dates.
GET /api/reservations/all: Endpoint to retrieve all reservations in the system.

## Task 4: Testing
Write comprehensive test classes for your Apex classes and REST API endpoints, ensuring at least 85% code coverage. Test various scenarios including:

- Creating a reservation without conflicts.
- Attempting to create a reservation with a date range that conflicts with an existing reservation.
- Retrieving reservations for a specific unit.
- Retrieving all reservations within a specific date range.
- Retrieving all reservations in the system.

## Task 5: Create and Share an Unmanaged Package
Package all your components into an unmanaged package. Provide detailed instructions on how to install this package into another Salesforce sandbox environment. Include the following:

Package Creation: Steps to bundle the objects, Apex classes, triggers, and endpoints into the unmanaged package.
Installation Link: Generate a URL that can be used to install your package into another Salesforce sandbox environment.

## Submission
Package your source code in a ZIP file including:

Apex Classes
Apex Triggers (if any)
Test Classes
A FOLLOW.md file explaining:
- How to deploy your code to a Salesforce org.
- Any assumptions you made during the development.

We would really appreciate your feedback by answering the following questions? (this section isn't mandatory :D)
- How did you find the test overall?
- Did you have any issues or have difficulties completing?
- If you have any suggestions on how we can improve the test, we'd love to hear them.
