<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: MADHUMITHA R</h3>
<h3>Register Number: 212224240082</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>
PROGRAM:

```python
import random

class MedicineAgent:
    def __init__(self):
        self.room = "Room A"

    def check_patient(self, rooms):
        temp = rooms[self.room]

        if temp > 98.5:
            print(self.room, "Patient has fever")
            print("Giving medicine")
            rooms[self.room] = 98.0
        else:
            print(self.room, "Patient is healthy")

        if self.room == "Room A":
            self.room = "Room B"
        else:
            self.room = "Room A"

        print("Moving to", self.room)
        print("-------------------")

rooms = {
    "Room A": random.uniform(97, 102),
    "Room B": random.uniform(97, 102)
}

agent = MedicineAgent()

for i in range(5):
    print("Step", i + 1)
    agent.check_patient(rooms)

    random_room = random.choice(["Room A", "Room B"])
    rooms[random_room] = random.uniform(97, 103)
    
```
OUTPUT:

<img width="380" height="631" alt="image" src="https://github.com/user-attachments/assets/83eb1c72-d090-4184-bfcc-60de7aed9c4d" />

### Result

Thus the Devoloping AI Agent with PEAS description was implementated using python programming
