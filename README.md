<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name:  MADHUMITHA R</h3>
<h3>Register Number: 212224240082</h3>


# Vacuum Cleaner Agent

## Aim
To design and implement a simple Vacuum Cleaner Agent using Artificial Intelligence principles and evaluate its performance using the PEAS model.

---

## Theory
A vacuum cleaner agent is an intelligent agent that cleans dirty areas in its environment. The environment consists of rooms or floor locations, where each location may be clean or dirty. The agent uses sensors to detect dirt, obstacles, its current location, and battery level. Based on the sensor inputs, it decides whether to clean the current location or move to another location. If dirt is detected, the agent activates its vacuum mechanism to clean the area; otherwise, it moves to the next location. The performance of the agent is measured by increasing the performance score for every successfully cleaned location and decreasing it for every unnecessary movement or energy consumption. Thus, the vacuum cleaner agent aims to maximize cleanliness while minimizing movement and energy usage.

---

## PEAS Description

| Agent Type | Performance | Environment | Actuators | Sensors |
|------------|-------------|-------------|-----------|---------|
| Vacuum Cleaner Agent | Cleanliness of rooms, minimum time, minimum energy consumption | Rooms, floor, dirt, obstacles | Move (left, right, forward, backward), suck dirt, turn on/off | Dirt sensor, location sensor, obstacle sensor, battery level sensor |

---

## Design Steps

### Step 1: Identifying the Input
- Dirt status of the current location
- Current location
- Obstacle detection
- Battery level

### Step 2: Identifying the Output
- Move to the required location and clean the dirty area using the vacuum.

### Step 3: Developing the PEAS Description
PEAS description is developed by defining the performance measure, environment, actuators, and sensors of the vacuum cleaner agent.

### Step 4: Implementing the AI Agent
The agent detects dirty locations, moves to those locations, cleans them, avoids obstacles, and continues until all accessible areas are clean.

### Step 5: Performance Measurement
- Performance increases for every cleaned location.
- Performance decreases for every movement or unnecessary energy consumption.

---

## Python Implementation

```python
import random

# Environment (2 Rooms)
rooms = {
    "Room A": random.choice(["Clean", "Dirty"]),
    "Room B": random.choice(["Clean", "Dirty"])
}

performance = 0

print("Initial Environment")
for room, status in rooms.items():
    print(f"{room}: {status}")

print("\nVacuum Cleaner Agent Started...\n")

for room in rooms:

    print(f"Agent moved to {room}")
    performance -= 1      # Movement cost

    if rooms[room] == "Dirty":
        print("Sensor: Dirt detected.")
        print("Action: Cleaning the room...")
        rooms[room] = "Clean"
        performance += 10   # Reward for cleaning
        print("Room cleaned successfully.")
    else:
        print("Sensor: Room is already clean.")

    print(f"Current Performance: {performance}\n")

print("Final Environment")
for room, status in rooms.items():
    print(f"{room}: {status}")

print("\nFinal Performance:", performance)
```

## Output:
<img width="370" height="536" alt="image" src="https://github.com/user-attachments/assets/67c1fe09-6001-485f-aad4-b950770ad439" />
