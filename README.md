# QuickField_Touch_Sensor_Simulations

This repository showcases a series of capacitive and inductive touch sensor simulations developed from scratch using **QuickField Student Edition**. The objective was to explore and analyze the behavior of electric fields, potential distributions, and capacitance in different sensor designs under real-world-inspired conditions. A total of **six distinct sensor configurations** were modeled and simulated successfully:

- Touch_Sensor_Capacitance
- Touch_Screen
- Touchless_Sensor
- Touch_Sensor_Matrix
- Inductive_Touch_Sensor
- Capacitive_Touch_Sensor_3D

Despite the limitations of the QuickField Student Edition — including the 255-node mesh cap and occasional crashes during complex geometry modeling — each example was completed with effective simulations and documented results. Troubleshooting and mesh optimization techniques were employed to work around these constraints. This project deepened the understanding of touch sensor physics and simulation practices.



## Software Description: QuickField

**QuickField** is a lightweight yet powerful **Finite Element Analysis (FEA)** software used for simulating electromagnetic, electrostatic, thermal, and structural problems. It offers a user-friendly GUI that simplifies geometry creation, mesh generation, and field visualization — making it ideal for education and conceptual modeling.

### Key Features:
- 2D planar and axisymmetric simulation
- Electrostatics, magnetostatics, DC conduction, thermal analysis
- Supports custom materials and boundary conditions
- Visualization of field lines, vector plots, and equipotential maps

> **Note:** This project uses the **Student Edition**, which limits simulations to **255 mesh nodes**. Mesh simplification and careful geometry tuning were required to remain within this constraint.

🔗 [Download QuickField Student Edition](https://quickfield.com/free_student_version.htm)


# Simulated Examples
> Below are the detailed sensor designs and simulation case studies included in this project, each highlighting a unique configuration and analysis technique to understand touch sensing mechanisms:

## Example 1: Touch Sensor Capacitance

### Description: 
The touch sensor consists of two circular electrodes, a transmitting (Tx) and a receiving (Rx) ring, placed on a dielectric board. The presence of a conductive stylus in their vicinity affects the capacitance between the electrodes.

### Problem Type:
Axisymmetric problem of electrostatics.

### Geometry:

![image](https://github.com/user-attachments/assets/d8b25f09-11c0-4f07-8ea1-419335228bdc)

![image](https://github.com/user-attachments/assets/b472d5a2-4139-466f-bf01-f60e126fdf28)

### Given:
- **Relative Permittivity of Dielectric:** 4.7.

### Task: Determine the capacitance of Tx and Rx electrodes as a function of the distance between the touch sensor and the stylus.

### Solution:
- The "floating conductor" boundary condition is assigned to the stylus surface, ensuring no field inside the conductor.
- Capacitance is calculated as the ratio of stored charge (q) to the potential difference (ΔU) between Rx and Tx electrodes.
- Simulations are performed for different stylus positions. The LabelMover tool is used to automate a series of calculations.

### Results:
- The simulation provides the electric field distribution in and around the touch sensor.
- The capacitance of the touch sensor changes as the distance between the stylus and the sensor varies.
- Electric Field Distribution: The electric field is mapped around the touch sensor to visualize how the presence of the stylus influences the field.

![image](https://github.com/user-attachments/assets/84c90708-e673-4fe6-a350-00ecf42cf794)

![image](https://github.com/user-attachments/assets/f5893a6d-47c1-4f29-947e-1e3de4c86837)

### Capacitance Results:

The capacitance is plotted as a function of the distance between the touch sensor and the stylus, showing how it changes with variation in distance between the stylus and the dielectric. As the stylus approaches the sensor, the capacitance increases due to the closer proximity of the conductive object affecting the electric field between the Tx and Rx electrodes.

The parametric analysis automated the simulation process, allowing for the collection of capacitance values at different positions of the stylus as it moves towards the conductor. This method provided a comprehensive set of data to understand the sensor's behaviour under varying conditions.

| Step   | Contour length for distance | Stored energy for air+dielectric |
|--------|------------------------------|----------------------------------|
| 0      | 1.765                        | 3.18E-13                         |
| 1      | 1.665                        | 3.20E-13                         |
| 1_2    | 1.565                        | 3.22E-13                         |
| 1_3    | 1.465                        | 3.24E-13                         |
| 1_4    | 1.365                        | 3.28E-13                         |
| 1_5    | 1.265                        | 3.34E-13                         |
| 1_6    | 1.165                        | 3.40E-13                         |
| 1_7    | 1.065                        | 3.43E-13                         |
| 1_8    | 0.965                        | 3.52E-13                         |
| 1_9    | 0.865                        | 3.58E-13                         |
| 1_10   | 0.765                        | 3.63E-13                         |
| 1_11   | 0.665                        | 3.74E-13                         |
| 1_12   | 0.565                        | 3.66E-13                         |
| 1_13   | 0.465                        | 3.80E-13                         |
| 1_14   | 0.365                        | 4.00E-13                         |
| 1_15   | 0.265                        | 4.32E-13                         |
| 1_16   | 0.165                        | 4.85E-13                         |
| 1_17   | 0.065                        | 5.91E-13                         |



![image](https://github.com/user-attachments/assets/5582fe58-5b92-4a2a-adc4-17d947f12598)


### Problems Faced:

During the simulation process, I encountered a significant issue related to mesh creation. Specifically, I received an error indicating that the mesh limit exceeded 255 nodes, a restriction imposed by the student edition of QuickField. This limitation prevented the automatic generation of the mesh, which is essential for accurate simulation results.

To resolve this issue, I had to manually set the mesh spacing instead of relying on the automatic mesh generation feature. By adjusting the spacing parameters, I was able to create a mesh that adhered to the node limit while still maintaining the necessary level of detail for accurate simulations. This manual adjustment process was time-consuming and required careful attention to ensure that the mesh was suitable for the complex geometries involved in the simulations.

Despite this challenge, I successfully built the mesh within the constraints of the student edition and completed all simulations. This experience improved my understanding of mesh generation and the importance of customizing mesh parameters to fit specific software limitations.



###  Conclusion:

The detailed simulation and analysis of the touch sensor capacitance using QuickField provided valuable insights into the behavior of capacitive touch sensors. By modeling various positions of a conductive stylus in relation to the sensor, I was able to observe and quantify how the capacitance changes as the stylus approaches the electrodes. This change in capacitance is crucial for the effective functioning of touch sensors, as it directly impacts their sensitivity and accuracy.

The parametric analysis, facilitated by the LabelMover tool, enabled efficient automation of the simulation process, ensuring comprehensive data collection for different stylus positions. Despite challenges such as software limitations and crashes, the simulations were successfully completed, demonstrating the robustness and versatility of QuickField for electrostatic analysis.

Overall, this project enhanced my understanding of capacitive touch sensor design and analysis, providing practical experience in handling simulation tools and addressing real-world challenges. The findings from these simulations can inform the development and optimization of touch-sensitive devices, contributing to advancements in sensor technology.

---

## Example 2: Touch Sensor Capacitance

### Description:

This simulation models a simplified capacitive touchscreen, where the capacitance of the finger and human body is represented by a grounded touch area on the touchscreen surface. Electric potential is applied to electrodes at the four corners of a conductive sheet. When a conductive object with zero potential (representing a finger) touches the sheet, the currents in the electrodes vary based on the touch position.

### Problem Type:
Plane-parallel problem of DC conduction.

### Geometry:

![image](https://github.com/user-attachments/assets/25a463d9-fa62-414d-8ec6-66cb0bd6222e
![image](https://github.com/user-attachments/assets/9a832fc1-cd0a-4d40-8fc6-748bd3a8713d)


### Given
-	Electrical Conductivity of the Touchscreen: 100 S/m.
-	Electrode Voltages: +1V at A, B, C, D.
-	Finger Voltage: 0V.

### Task: 
Determine the currents in electrodes A, B, C, and D as a function of the touch position.

### Solution:
- Different touch positions are simulated by creating separate models.
- The process of creating new problems, modifying the geometry model, and measuring results is automated using LabelMover.

### Results:
-	The simulation provides the electric field distribution in the touchscreen.
-	Due to symmetry, a single chart can be used to measure the currents for all electrodes.

![image](https://github.com/user-attachments/assets/51bfb66f-4c98-4815-acf8-f8a0859402df)
 

### Parametric Analysis:
The parametric analysis of the finger at different positions on the touchscreen shows how the current through the surface of each electrode changes with the touch position. This data is critical for understanding the touchscreen's sensitivity and optimizing its design for accurate touch detection.

| Step   | Current A (A)     | Current B (A)     | Current C (A)     | Current D (A)     |
|--------|-------------------|-------------------|-------------------|-------------------|
| 0      | -0.00084149       | 0.00084124        | -0.0008275        | 0.00084439        |
| 1_3    | -0.00074891       | 0.00096417        | -0.00094646       | 0.0007468         |
| 1_4    | -0.00072411       | 0.0010046         | -0.0009839        | 0.00072278        |
| 1_7    | -0.00064809       | 0.0011023         | -0.0011025        | 0.00063639        |
| 1_8    | -0.0006112        | 0.0011783         | -0.0011247        | 0.00063621        |
| 1_9    | -0.00058514       | 0.0012078         | -0.0011594        | 0.00060921        |
| 1_10   | -0.00056423       | 0.0012745         | -0.0012086        | 0.0005874         |
| 1_11   | -0.00055845       | 0.0013216         | -0.0013165        | 0.0005565         |
| 1_12   | -0.00053811       | 0.00131           | -0.0013507        | 0.00053626        |
| 1_13   | -0.00051563       | 0.0013851         | -0.0013974        | 0.00051386        |
| 1_14   | -0.00049343       | 0.0014562         | -0.0014729        | 0.0004918         |
| 1_15   | -0.00046622       | 0.0014083         | -0.0014339        | 0.00046469        |
| 1_16   | -0.00044222       | 0.0014413         | -0.0015002        | 0.00044074        |
| 1_17   | -0.000411         | 0.0013737         | -0.00149          | 0.00040964        |
| 1_18   | -0.00037516       | 0.0012898         | -0.0013605        | 0.00037394        |


![image](https://github.com/user-attachments/assets/ae0bfb30-5e13-4d71-ba1f-b66aa58f6571)

#### 

> Variation in current due to movement of finger from one position to another, for one of the positions result is provided in below image:

![image](https://github.com/user-attachments/assets/87ada2ed-4f23-49a3-b39e-010a31be3575)


### Problems Faced:
During the simulation process, I encountered a significant issue related to mesh creation. Specifically, I received an error indicating that the mesh limit exceeded 255 nodes, a restriction imposed by the student edition of QuickField. This limitation prevented the automatic generation of the mesh, which is essential for accurate simulation results.

### Conclusion:
The simulations of the capacitive touchscreen using QuickField provided a comprehensive understanding of how touch positions affect the currents in the electrodes. By modeling the touchscreen with various touch positions, we were able to observe the variations in current through each electrode, which is vital for the functionality of the touchscreen.

The parametric analysis revealed that as the finger's position changes, the currents in the electrodes also change. This relationship is crucial for determining the precise location of the touch on the screen. The data obtained from the simulations can be used to optimize the design and improve the accuracy of touchscreens.

Despite challenges such as mesh generation limits and software crashes, the simulations were successfully completed by manually adjusting mesh parameters and using automation tools like LabelMover. This project not only enhanced my technical skills in using simulation software but also provided practical experience in problem-solving and optimizing designs within software constraints.

---

## Example 3: Touchless Sensor

Touchless sensor consists of two groups of electrodes on the sides of the rectangular dielectric frame. Tx - transmitter, with voltage applied, Rx - receivers. Rx potential depends on the position of the finger near the sensor.

### Problem Type:
3D electrostatics problem.

### Geometry:

![image](https://github.com/user-attachments/assets/d225e323-f9ee-4e4e-bfaf-f35cdf70aecb)

![image](https://github.com/user-attachments/assets/a12ad4a6-5454-4dca-a49c-91d43a566d86)

![image](https://github.com/user-attachments/assets/eefe0cb2-676a-4793-8825-741baee40ed8)

![image](https://github.com/user-attachments/assets/b527f63a-eb3f-4034-9f29-db0bdef1fbe4)

####

> Orange highlighted in below image  is Rx ( Rx left, Rx top, Rx right, Rx bottom) 

![image](https://github.com/user-attachments/assets/405785be-c338-4de8-a692-299db472c119)


> Orange highlighted in below image  is Tx .

![image](https://github.com/user-attachments/assets/2ee9506f-68da-469e-a453-59250d7f4db8)


### Given Parameters
- Relative permittivity of dielectric (ε): 4.7
- Tx voltage (V): +1V
- Rx electrodes: Floating potential

### Task
Determine the Rx electrode potentials for different finger positions relative to the sensor.

### Simulation Steps
1.	Model Construction:
   - Define the geometry with electrodes and dielectric material.
   - Position the finger at different coordinates relative to the sensor surface (simulate only the top-left quarter due to symmetry).
2.	Boundary Conditions:
   -	Apply +1V to the Tx electrode.
   -	Ground the finger.
   -	Leave Rx electrodes floating.
3.	Solver Setup:
   - Use QuickField's 3D electrostatic solver.
   - Set up the simulation to calculate potential distribution across Rx electrodes for each finger position.
5.	Post-Processing:
   - Calculate and visualize potential differences (Tx-Rx) for Rx electrodes at various finger positions.
   - Analyze the electric field distribution within the sensor.

### Results




