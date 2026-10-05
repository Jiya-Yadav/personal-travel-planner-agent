# Personal Travel Planner Agent

A simple **Personal Travel Planner Agent** built with **Google Agent Development Kit (ADK)**.

## Assignment Requirements Covered

The agent can:

- Understand a user's destination, duration, budget, and interests.
- Recommend places to visit.
- Create a day-wise itinerary.
- Estimate the trip budget in Indian Rupees.
- Adjust suggestions when the requested budget is tight.
- Provide a final, easy-to-read travel plan.
- Use an ADK custom Python tool for budget calculation.

## Project Files

```text
personal_travel_planner_agent/
├── travel_planner/
│   ├── __init__.py
│   └── agent.py
├── requirements.txt
└── README.md
```

## Prerequisites

- Python 3.11 or newer
- A Gemini API key
- Internet connection
- Google ADK

Google's current ADK documentation recommends Python 3.11+ and supports running an agent locally through the ADK playground.

## Step 1 — Open the project

Open this folder in VS Code.

Open the VS Code terminal:

```powershell
cd path\to\personal_travel_planner_agent
```

## Step 2 — Create a virtual environment

Windows:

```powershell
python -m venv .venv
.venv\Scripts\activate
```

## Step 3 — Install dependencies

```powershell
pip install -r requirements.txt
```

If `pip` does not work:

```powershell
python -m pip install -r requirements.txt
```

## Step 4 — Add your Gemini API key

For a quick local demo, set the environment variable in PowerShell:

```text
GOOGLE_API_KEY="YOUR_API_KEY_HERE"
```

Replace `YOUR_API_KEY_HERE` with your Gemini API key. For the cleanest setup, create a file named `.env` inside the `travel_planner` folder and put that line in it. Do not submit the `.env` file.

Do NOT put the real API key inside `agent.py`, `README.md`, or your submitted files.

## Step 5 — Run the ADK playground

From the **parent folder** of `travel_planner`, run:

```powershell
adk web
```

Open the local URL shown in the terminal (normally `http://localhost:8000`), then select `travel_planner`.

For Windows, if the web server gives a reload/subprocess error, try:

```powershell
adk web --no-reload
```

If your instructor specifically asks you to use the newer Agents CLI workflow, the official local playground command is:

```powershell
agents-cli playground
```

## Example Input

```text
I want to visit Jaipur for 3 days with a budget of ₹15,000.
I like history and local food.
```

## Example Conversation 1 — Jaipur

**User:**

I want to visit Jaipur for 3 days with a budget of ₹15,000. I like history and local food.

**Agent:**

Creates a 3-day Jaipur plan focused on forts, palaces, heritage areas and local food,
while keeping accommodation, food, local transport and activities within an
approximately ₹15,000 budget.

A typical structure is:

- Day 1: City Palace / Jantar Mantar / Hawa Mahal area + local food
- Day 2: Amber Fort / Jaigarh or nearby heritage site + Rajasthani dinner
- Day 3: Albert Hall / local market + final food experience

The agent also provides an estimated budget breakdown and practical tips.

## Example Conversation 2 — Delhi

**User:**

Plan a 2-day Delhi trip for me. My budget is ₹8,000 and I love history and street food.

**Agent:**

The agent identifies the 2-day duration, ₹8,000 budget and the history + street-food
preferences, then creates a budget-conscious itinerary with places such as Red Fort,
India Gate, Humayun's Tomb or Qutub Minar, together with suitable local food
experiences.

It provides an estimated budget and a final Day 1 / Day 2 plan.

## Example Conversation 3 — Goa

**User:**

I want a 4-day Goa trip under ₹20,000. I like beaches, sunsets and local food.
Keep it relaxed.

**Agent:**

The agent prioritizes beaches, sunset locations, relaxed sightseeing and local food.
It creates a 4-day itinerary and estimates accommodation, food, local transport and
activities. It also avoids packing too many activities into one day.

## How the Agent Works

```text
User Travel Request
        |
        v
Understand Requirements
(destination, days, budget, interests)
        |
        v
Personalized Planning
        |
        +------> Place Recommendations
        |
        +------> Day-wise Itinerary
        |
        +------> Budget Tool
        |
        v
Final Travel Plan
```

## Custom Tool

The project includes:

`estimate_budget()`

This is an ADK tool implemented as a normal Python function.

It calculates:

```text
Accommodation
+ Food
+ Local Transport
+ Activities
= Estimated Total Trip Cost
```

The ADK agent can decide when this tool is useful and incorporate its result into
the final travel plan.

## Limitations

This is a simple educational agent. It does not use live hotel/flight booking APIs,
live maps, or live attraction opening hours. Therefore, all prices and schedules
should be treated as approximate unless separately verified.

## What to Show in the Screenshot / Video

For the assignment demonstration:

1. Show VS Code with `agent.py`.
2. Show the terminal command:

```powershell
adk web
```

3. Open the ADK local playground.
4. Enter:

```text
I want to visit Jaipur for 3 days with a budget of ₹15,000.
I like history and local food.
```

5. Show the generated itinerary and budget.
6. Optionally run the Delhi and Goa examples as additional demonstrations.

## Short Viva Explanation

**What did you build?**

I built a Personal Travel Planner Agent using Google ADK. It understands a user's
destination, trip duration, budget and interests, then generates a personalized
day-wise itinerary with recommendations and an estimated budget.

**Why is it an agent?**

The LLM is given a specific planning objective and can use a custom budget-estimation
tool as part of completing the user's request.

**What is the tool?**

`estimate_budget()` is a Python function registered with the ADK agent. It calculates
the approximate accommodation, food, transport and activity costs.

**What is the main limitation?**

The current version does not use live travel APIs, so prices and schedules are
estimates rather than real-time information.
