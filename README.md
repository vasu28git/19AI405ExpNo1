## ExpNo 1 :Developing AI Agent with PEAS Description
## Name: VASU VIGNESHWARAN P
## Register Number: 212224220119


## AIM:
To find the PEAS description for the given AI problem and develop an AI agent.

## Theory:
Medicine prescribing agent:
Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.

## PEAS DESCRIPTION:
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

## DESIGN STEPS
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

## Coding:
```
import random
class HealthAgent:
    def __init__(self,data):
        self.data = data

    def monitor_health(self):
        current_state = self.sensors.get_state()
        action = self.choose_action(current_state)
        self.actuators.perform_action(action)

    def choose_action(self, current_state):
        if current_state['heart_rate'] > 120:
            return "High heart rate detected"
        elif current_state['blood_pressure'] > 140:
            return "High blood pressure detected"
        elif current_state['temperature'] > 38:
            return "Recommend rest and monitor temperature"
        else:
            return "All fine"

class HealthSensors:
    def get_state(self):
        hr = int(input("Enter Heart Rate: "))
        bp = int(input("Enter Blood Pressure: "))
        temp = int(input("Enter Temperature: "))
        return {
            'heart_rate': hr,
            'blood_pressure': bp,
            'temperature': temp
        }

class HealthActuators:
    def perform_action(self, action):
        print(action)
        
if __name__ == "__main__":
    data = {'patient_id': int(input("Enter Patient Id: ")), 'name': input("Enter Patient Name: "), 'age': int(input("Enter Age: "))}

    health_sensors = HealthSensors()
    health_actuators = HealthActuators()

    health_agent = HealthAgent(data)

    health_agent.sensors = health_sensors
    health_agent.actuators = health_actuators

    health_agent.monitor_health()
```
## Output:
![image](https://github.com/user-attachments/assets/173e83f6-a3b4-4802-8a23-f887ecaf42d2)

## Result:
The AI Agent reads the patient vitals and detect any abnormal Heart Rate or Blood Pressure or Temperature and print the Health status.
