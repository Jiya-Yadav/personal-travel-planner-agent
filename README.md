# Personal Travel Planner Agent

This project is a simple travel planning agent made using Google Agent Development Kit (ADK).

The user gives details such as the destination, number of days, budget and interests. 
The agent then creates a suitable travel plan with places to visit, food suggestions 
and an approximate budget.

## Example

Input:

> I want to visit Jaipur for 3 days with a budget of ₹15,000. I like history and local food.

The agent generates a day-wise plan for Jaipur and gives an estimated cost for the trip.

## Features

- Understands the destination, duration and budget given by the user
- Takes user interests into account
- Suggests places to visit
- Creates a day-wise itinerary
- Gives an approximate budget
- Provides a final summary of the trip

## Technologies Used

- Python
- Google ADK
- Gemini API

## Project Structure

```text
personal_travel_planner_agent/
│
├── travel_planner/
│   ├── __init__.py
│   └── agent.py
│
├── Screenshots/
│   ├── Jaipur.jpeg
│   ├── Delhi.jpeg
│   └── Goa.jpeg
│
├── agent.py
├── requirements.txt
├── README.md
└── .gitignore