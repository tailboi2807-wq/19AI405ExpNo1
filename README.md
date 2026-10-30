<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Saravanan N</h3>
<h3>Register Number/Staff Id: TSML006</h3>


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
program:
~~~

<!DOCTYPE html>
<html>
<head>
    <title>Medicine Prescribing Agent</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            padding: 30px;
        }

        .container {
            max-width: 700px;
            margin: auto;
            background: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 0 10px gray;
        }

        h1 {
            text-align: center;
            color: blue;
        }

        pre {
            background: #222;
            color: lightgreen;
            padding: 20px;
            border-radius: 8px;
            overflow-x: auto;
            font-size: 14px;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Medicine Prescribing Agent</h1>

    <h2>Python Program</h2>

    <pre>
import random

class MedicinePrescribingAgent:

    def __init__(self):
        self.rooms = {
            "Room 1": random.uniform(97.0, 102.5),
            "Room 2": random.uniform(97.0, 102.5)
        }

        self.performance = 0
        self.current_room = random.choice(
            list(self.rooms.keys())
        )

    def sense(self):
        temperature = self.rooms[self.current_room]

        print(f"\nAgent is in {self.current_room}")
        print(f"Patient Temperature: {temperature:.1f}°F")

        return temperature

    def prescribe_medicine(self, temperature):
        if temperature > 98.5:
            print("Patient has fever.")
            print("Medicine Prescribed.")
            self.performance += 1
        else:
            print("Patient is healthy.")
            print("No medicine required.")

    def move(self):
        previous_room = self.current_room

        self.current_room = (
            "Room 2" if self.current_room == "Room 1"
            else "Room 1"
        )

        print(f"\nMoving from {previous_room} to {self.current_room}")
        self.performance -= 1

    def run(self):
        print("=== Medicine Prescribing Agent ===")

        temperature = self.sense()
        self.prescribe_medicine(temperature)

        self.move()

        temperature = self.sense()
        self.prescribe_medicine(temperature)

        print("\nFinal Performance:", self.performance)


agent = MedicinePrescribingAgent()
agent.run()
    </pre>

</div>

</body>
</html>

~~~


output:
<img width="461" height="595" alt="image" src="https://github.com/user-attachments/assets/8d95bbd9-8d1b-4e0d-b56e-fdf0d41e976d" />
