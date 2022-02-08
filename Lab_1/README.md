# Lab 1: The Secret Life of Passive Components - Measuring "Parasitic" Properties of Passive Components with a VNA

*Author: Arjun Dhawan*

*Lab Partner: Zachary Hoffman*

## **Abstract**
---
A Vector Network Analyzer is used to investigate and characterize the parasitic properties of passive components such as resistors, capacitors, and inductors. We compare spice simulations of these components to the actual measurements we see in lab.


## **Introduction**
---
In the study of passive components such as resistors, capacitors, and inductors, we are intially taught of their ideal behaviors. This allows us to get better intuition for circuits as a whole and understand basic circuits without the need for maxwells equations. However, when using these passive components in a real live setting, all of these components have *parasitic* properties when if not considered, can affect the performance of a circuit. 

To represent these *parasitic* properties with our conventional lumped circuit model, we add additional components so the readings we see in the real world are representative. 

The following schematics are of a realistic resistor, capacitor, and inductor represented with *lumped* circuit elements: 

- **Schematic of a Realistic Resistor**
![Schematic of a Realistic Resistor](pics/realistic_resistor.png)

- **Schematic of a Realistic Capacitor**
![Schematic of a Realistic Capacitor](pics/realistic_capacitor.png)

- **Schematic of a Realistic Inductor**
![Scheamtic of a Realistic Inductor](pics/realistic_inductor.png)

## **Experimental Setup**
---
To verify any measurements we take on the VNA of these components, we will first simulate the capacitor and inductor with parasitic values before we take measurements of these components on a VNA. Within LTSpice, the parasitic values are entered in the advanced settings for each of the components.

### **LTSpice Inductor Circuit**

![LTSpice Inductor](pics/ltspice_parasitic_capacitor.png)

### **LTSpice Capacitor Circuit**

![LTSpice Capacitor](pics/ltspice_parasitic_inductor.png)

### **Physical Experiment Setup**
For the physical experimental setup, a NanoVNA was used to measure the impedences on the RF board as well as of through hole components. Additionally, to ensure accurate readings, a SOLT calibration was conducted each time a cable was changed and each time the frequency range changed. This setup allowed us to measure the s-parameters of various components and get a better idea of how the VNA is a useful tool. 

![RF Demo Board](pics/rf_demo_board.jpeg)

## **Measurements and Results**
---
Below are the measurements and results for the lab.

### **LT Spice Results**
___
The LTSpice simulation results for the parasitic inductor and capacitor are below: 

#### **LTSpice Inductor**
![LT Spice Inductor](pics/ltspice_parasitic_inductor_v_i_graph.png)

#### **LTSpice Capacitor**
![LT Spice Capacitor](pics/ltspice_parasitic_capacitor_v_i_graph.png)

For the capacitor, we see a notch frequency at around 20MHz and for the inductor, we see a notch frequency at around 500MHz.

### **Copper Clad Setup Results**
___

#### **Mica Capacitor on Copper Clad Results**
![Mica Capacitor](pics/Mica_cap_analyzed_through_VNA.png)

#### **Inductor on Copper Clad Results**
![Inductor Copper Clad](pics/inductor_analyzed_in_series_with_a_resistor_maybe.png)

### **RF Demo Board Results**
___
#### **SOLT Calibration**
___
The below shows the results from the SOLT calibration. As expected after calibration, a short appears as a dot on the left side of the VNA graph, an open circuit appears as a dot on the right side of the VNA graph, and the load and through appear at the center of the VNA graph. 

- **S**hort
![1_LPF_30MHz](pics/13_short.png)

- **O**pen
![1_LPF_30MHz](pics/14_open.png)

- **L**oad
![1_LPF_30MHz](pics/15_load.png)

- **T**hru
![1_LPF_30MHz](pics/16_thru.png)

#### **Devices Simulated in LTSpice**
___
Below are the s-parameters for the capacitor and inductor which were simulated in LTSpice
- Capacitor
![1_LPF_30MHz](pics/7_cap.png)

- Inductor
![1_LPF_30MHz](pics/8_inductor.png)

#### **Remaining RF Demo Board Circuits:**
___
The remaining circuits on the RF demo board are analyzed throught the VNA. As seen below, the VNA graphs are the very similar to the RF board. 
- LPF 30MHz
![1_LPF_30MHz](pics/1_LPF_30MHz.png)

- HPF 100MHz
![2_LPF_30MHz](pics/2_HPF_100MHz.png)

- BPF 433MHz
![1_LPF_30MHz](pics/3_BPF_433MHz.png)

- BSF 6.5MHz
![1_LPF_30MHz](pics/4_BSF_6_5_MHz.png)

- 33 $\Omega$ SWR = 1.5
![1_LPF_30MHz](pics/5_33_ohm_swr.png)

- 75 $\Omega$ SWR = 1.5
![1_LPF_30MHz](pics/6_75_ohm_swr.png)

- Capacitor in Parallel with a device
![1_LPF_30MHz](pics/9_cap_device.png)

- Capacitor in series with an inductor
![1_LPF_30MHz](pics/10_cap_inductor.png)

- Capacitor in series with a device and inductor in parallel
![1_LPF_30MHz](pics/11_cap_parallel_inductor_resistor.png)

- Device in paralle with an indictor and capacitor in series
![1_LPF_30MHz](pics/12_parallel_series_cap_inductor_device.png)

- -5dB Attenuator
![1_LPF_30MHz](pics/17_att_neg_5.png)

- -10dB Attenuator
![1_LPF_30MHz](pics/18_att_neg_10.png)



## Discussion
---
From the above VNA graphs it is very evident that passive components have parasitic properities that can be seen in their S-parameters.

Looking at the inductor and capacitor SMD and copper clad setup VNA graphs, we can see that the lines drawn by the VNA go beyond the real plane into the capacitive and inductive regions respectively. This indiciates the presence of parasitic properties. 

Additionally, when capturing the s-parameters of the mica capicator in the copper clad setup, we see a resonant frequency of about 60MHz while in the LTSpice simulation of the same setup, we see a resonant frequency of 20MHz. This is indicative of parasitic properities that need to be characterized on a per device basis. 

## Summary/Conclusions
---
In conclusion, we have learned to use VNAs effectively to measure the s-parameters of various components. By going through this process, we have learned how to calibrate the VNAs using the SOLT method, how to display data from the VNA both on a laptop and on the VNA itself, and have been able to understand the parasitic properties of passive components. It is painfully obvious from this analysis that passive components have parasitic properties that cannot be ignored. We can simulate this fairly accurately using lumped circuit models, however, we still need to analyze physical components to understand their exact properties as depending on the experimental setup, the properties will vary. 