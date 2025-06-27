# QuickField_Touch_Sensor_Simulations

## 📌 Summary

This repository showcases a series of capacitive and inductive touch sensor simulations developed from scratch using **QuickField Student Edition**. The objective was to explore and analyze the behavior of electric fields, potential distributions, and capacitance in different sensor designs under real-world-inspired conditions. A total of **six distinct sensor configurations** were modeled and simulated successfully:

- Touch_Sensor_Capacitance
- Touch_Screen
- Touchless_Sensor
- Touch_Sensor_Matrix
- Inductive_Touch_Sensor
- Capacitive_Touch_Sensor_3D

Despite the limitations of the QuickField Student Edition — including the 255-node mesh cap and occasional crashes during complex geometry modeling — each example was completed with effective simulations and documented results. Troubleshooting and mesh optimization techniques were employed to work around these constraints. This project deepened the understanding of touch sensor physics and simulation practices.

---

## 🧠 Software Description: QuickField

**QuickField** is a lightweight yet powerful **Finite Element Analysis (FEA)** software used for simulating electromagnetic, electrostatic, thermal, and structural problems. It offers a user-friendly GUI that simplifies geometry creation, mesh generation, and field visualization — making it ideal for education and conceptual modeling.

### Key Features:
- 2D planar and axisymmetric simulation
- Electrostatics, magnetostatics, DC conduction, thermal analysis
- Supports custom materials and boundary conditions
- Visualization of field lines, vector plots, and equipotential maps

> **Note:** This project uses the **Student Edition**, which limits simulations to **255 mesh nodes**. Mesh simplification and careful geometry tuning were required to remain within this constraint.

🔗 [Download QuickField Student Edition](https://quickfield.com/free_student_version.htm)

# 🧪 Simulated Examples
Below are the sensor designs simulated in this project:

## Example 1: Touch Sensor Capacitance

**Description:** The touch sensor consists of two circular electrodes, a transmitting (Tx) and a receiving (Rx) ring, placed on a dielectric board. The presence of a conductive stylus in their vicinity affects the capacitance between the electrodes.

**Problem Type:** Axisymmetric problem of electrostatics.

**Geometry:**

![image](https://github.com/user-attachments/assets/d8b25f09-11c0-4f07-8ea1-419335228bdc)

![image](https://github.com/user-attachments/assets/b472d5a2-4139-466f-bf01-f60e126fdf28)

**Given:**
- **Relative Permittivity of Dielectric:** 4.7.

**Task:** Determine the capacitance of Tx and Rx electrodes as a function of the distance between the touch sensor and the stylus.

**Solution:**
- The "floating conductor" boundary condition is assigned to the stylus surface, ensuring no field inside the conductor.
- Capacitance is calculated as the ratio of stored charge (q) to the potential difference (ΔU) between Rx and Tx electrodes.
- Simulations are performed for different stylus positions. The LabelMover tool is used to automate a series of calculations.

**Results:**
- The simulation provides the electric field distribution in and around the touch sensor.
- The capacitance of the touch sensor changes as the distance between the stylus and the sensor varies.
- Electric Field Distribution: The electric field is mapped around the touch sensor to visualize how the presence of the stylus influences the field.

![image](https://github.com/user-attachments/assets/84c90708-e673-4fe6-a350-00ecf42cf794)

![image](https://github.com/user-attachments/assets/f5893a6d-47c1-4f29-947e-1e3de4c86837)

### 📊 Capacitance Results

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

