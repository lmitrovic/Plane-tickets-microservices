This is a system for selling plane tickets. A microservice architecture was used for implementation. The system contains three services. 

Service 1 is a customer service. It supports: user registration and login, profile change, credit card addition, user rank depending on the number of miles traveled. The role of the admin is to add and delete flights.

Service 2 is a flight service. It contains: flight list, flight search, adding and deleting aircraft. When the Admin deletes the flight, if at least one ticket has been sold, then a refund is made for the given flight. When refunding money, the information is propagated to service 1 and service 3 via message broker.

Service 3 is an airline ticket service. The user can buy tickets through this service. He chooses the credit card with which he wants to pay the ticket. If the capacity of the aircraft for a given flight is full, the user will be shown an error during the purchase. Depending on the rank of the user, he gets a discount on the ticket price (gold-20%,
silver-10%, bronze-0%). The user can see all the tickets he bought,
sorted by date of purchase.

Spring-boot, Maven, Apache ActiveMQ were used in this project. The Gateway API has been implemented.
