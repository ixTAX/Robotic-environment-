# Robotic environment 
A robotic environment used in a food store warehouse

## Top view of the robotic environment

<img width="831" height="847" alt="Screenshot 2025-07-19 193525" src="https://github.com/user-attachments/assets/aab5f458-f001-4bf4-a8d5-040aca71d4d9" />


## Side view of the robotic environment

<img width="1313" height="549" alt="Screenshot 2025-07-19 193546" src="https://github.com/user-attachments/assets/62b20349-f268-4930-b00f-8e94ef305c75" />


## Front view of the robotic environment

<img width="1203" height="579" alt="Screenshot 2025-07-19 193602" src="https://github.com/user-attachments/assets/3995120e-7969-4a17-84ef-48f69cf9d1e2" />


## Close up top view of the SCARA arm

<img width="408" height="613" alt="Screenshot 2025-07-19 193618" src="https://github.com/user-attachments/assets/c3cff3cf-098b-4579-9edd-a4939f8997d6" />


## Close up side view of the SCARA arm

<img width="1136" height="535" alt="Screenshot 2025-07-19 193632" src="https://github.com/user-attachments/assets/6a8c099c-4715-4fe3-83d2-3ed00025f191" />


## Close up 3D view of the SCARA arm

<img width="925" height="824" alt="Screenshot 2025-07-19 193715" src="https://github.com/user-attachments/assets/045e826e-5dda-449b-a3cb-f004845af6ad" />


## Execution Algorithm:

### 1- System Initialization
  - Power on and calibrate SCARA arm position.
  - Perform homing for forward and backward rail and vertical actuator.
  - Check sensor status (shelf detection, item presence, basket availability).

### 2- Item Detection
  - Scan the shelves that will be to the left side of the arm using RFID
  - Identify which item to pick from the shelves

### 3- Arm Movement
  - Slide the entire SCARA arm platform forward or backward along the rail to align with the correct shelf column.
  - Use the vertical actuator to raise or lower the SCARA arm to the correct shelf row.
  - Rotate and extend the SCARA arm toward the item.
  - Close the gripper to pick the item.

### 4- Item Placement
  - The shelves will be slightly tilted towards the arm so the items will slide close to the arm
  - The arm will take the item and will put it in the slider that will be to the right side of the arm

### 5- Item Delivery
  - The slider will direct the item into a collection basket
  - Notify workers via a light or alert when an item arrives

### 6- Loop or Standby
  - If there are more items, repeat from Step 2
  - If there are no more items then return to home position and standby

## Working Envelope

| **Component**              | **Motion Type**       | **Axis / Direction**          | **Range**                       | **Description**                                                 |
|---------------------------|-----------------------|-------------------------------|---------------------------------|-----------------------------------------------------------------|
| Sliding Platform           | Linear                | X-axis (forward/backward)     | 0 – 2.5 meters (adjustable)        | Moves SCARA arm in front of shelf columns                      |
| Vertical Actuator          | Linear                | Z-axis (up/down)              | 0 – 2 meters (from bottom to top) | Lifts or lowers SCARA arm to reach shelf levels                |
| SCARA Arm – Base Rotation | Rotation                | Left/right rotation            | ±150 degree rotation             | Rotates from left shelf to right chute area                   |
| SCARA Arm – Elbow Joint   | Rotation                | Arm extension/folding          | ±120 degree rotation             | Extends toward shelves or retracts to center                  |
| Gripper / End Effector    | Linear / Mechanical   | Open/Close                     | 50–120 mm width (adjustable)     | Picks up food items from shelf                                 |
| Slider                    | Gravity               | Inclined plane                 | 1 meter * 3.5 meters (45 degree angle)| Delivers item from gripper to collection basket               |
