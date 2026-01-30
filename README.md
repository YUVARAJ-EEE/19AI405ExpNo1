<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: YUVARAJ M </h3>
<h3>Register Number: 212224050062 </h3>


<h3>AIM:</h3>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
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
<H3>PROGRAM:</H3>

```
import random

class MedicineAgent:
    FEVER_THRESHOLD = 98.5

    def __init__(self):
        self.rooms = ["Room 1", "Room 2"]
        self.environment = {
            room: round(random.uniform(97.0, 101.0), 1)
            for room in self.rooms
        }
        self.agent_location = "Room 1"
        self.performance_score = 0

    def move_to(self, room):
        if self.agent_location != room:
            print(f"\nMoving from {self.agent_location} to {room}...")
            self.agent_location = room
            self.performance_score -= 1

    def check_temperature(self, room):
        temp = self.environment[room]
        print(f"Checking {room}... Patient temperature: {temp}°F")
        return temp

    def treat_patient(self, room):
        print(f"Treating patient in {room}...")
        self.performance_score += 1

    def run(self):
        print("Medicine Prescribing Agent Simulation Started\n")

        for room in self.rooms:
            self.move_to(room)
            temp = self.check_temperature(room)

            if temp > self.FEVER_THRESHOLD:
                self.treat_patient(room)
            else:
                print(f"No treatment needed in {room}.\n")

        print("\nSimulation Complete!")
        print(f"Final Performance Score: {self.performance_score}")
        print("Environment State:", self.environment)


# Run the agent
agent = MedicineAgent()
agent.run()
```

<H3>OUTPUT:</H3>
<img width="767" height="462" alt="Screenshot 2026-01-30 084436" src="https://github.com/user-attachments/assets/3a77c10a-841b-495b-85b6-41223ca5f89c" />

<H3>RESULT:</H3>
<p>Thus the AI agent is developed successfully.<p>
