# Temperature & Humidity Sensor at Home
  * Zhixing Wang, Jeremy Yin, Xinyao Shen, Siwen Li

## 1. Introduction


### 1.1 Motivation

Air humidity refers to the humidity of the air, which is used to indicate the degree of saturation of water vapor content in the air. Studies show that the optimal range of humidity is 45 to 60 percent.

If the humidity is lower than 45%, indoor dryness will result in dry skin, throat, and respiratory tract, which is prone to asthma and other respiratory diseases.

If the humidity is above 60 percent, the human body feels sweltering. When the air humidity is higher than 80%, the high humidity will result in high body temperature, rapid heartbeat, dizziness and nausea. At the same time, high humidity leads to the growth of more mold and fungi in the indoor space.

In addition, if the air temperature is too high, but the humidity is too low, it will also affect the human digestive system. High temperature will make the human body sweat a lot, thereby losing water, saliva secretion is reduced, resulting in throat thirst; Will also accelerate the growth and reproduction of bacteria, resulting in food and water pollution; At the same time, but also easy to cause capillary dilatation, gastrointestinal discomfort, skin allergies.

### 1.2 Goals

* Improve the resolution of a commercial humidifier by using an external sensor with higher sensitivity to meet humidity goals
* Toggle a light or heat source to meet predefined temperature goals
* Verify the accuracy of native sensors in the environment
* Use other things like a basin of water to test the function of sensor


## 2. Methodology

### 2.1 Phenomena of Interest

Relative humidity-humidity ratio (specific humidity);

PMV thermal comfort Method and ASHRAE Standard 55-2020 comfortable range;

Psychrometric chart with dry-bulb temperature based on humidity ratio (temperature vs. relative humidity)

Furthermore, Center for the built environmental Thermal Comfort Tool will be applied in our project.

Humidifier in our groups will also be listed at the last.


### 2.2 Sensors Used
* DHT11

Humidity measurement range: 20 - 90%RH

Humidity measurement accuracy: ±5%RH

Temperature measurement range: 0 - 50℃

Temperature measurement accuracy: ±2℃

Power supply: DC 3.5~5.5V; PCB size: 2.0 x 2.0 cm

Communicates a 40-bit data transfer from the DATA channel containing:

    8-bit humidity integer data

    8-bit humidity decimal data

    8-bit temperature integer data

    8-bit temperature decimal data

    8-bit parity check data

![](sensor%20DHT11.png)

 <center>Figure1.picture of DHT11</center>

### 2.3 Relative humidity-Humidity ratio

The definition of humidity contains several aspects: **Absolute humidity, Relative humidity, Specific humidity (humidity ratio)**. Absolute humidity can be defined as the mass of H_2 O in certain amount of volume, which will be affected by air pressure and will also be affected by temperature if the volume is not a constant.AH is absolute humidity,$AH=\frac {m_{H_{2O}}}{V_{net}}$,unit is g/$m^3$

Relative humidity, Rh or ϕ is the ratio of partial pressure of water vapor in the mixture to the equilibrium vapor pressure of water over a flat surface of pure water at a given temperature.  $ϕ=\frac {p_(H_{2O})}{p*(H_{2O})}$ (Partial pressure means the percentage of water pressure divided by total pressure.) Once the ϕ increase, air should be wetter and if it reaches to 100%, it will reach to dew point(participation). Relative humidity will be affected by temperature. **The colder air will get lower capacity to maintain vapors**。 

Specific Humidity (humidity ratio) is the ratio of the mass of water vapor to total mass of the air parcel. Approximate formula should be $\frac {m_{H_{2O}}}{m_{air}-m_{H_{2O}}(dry air)}$, with unit kg/kg or g/kg. In our project we need also consider the transform formula for Specific Humidity and Relative humidity. It should be 

$$RH=100*\frac {ω}{ω_s} =0.263pq(exp⁡\frac {17.67(T-T_0)}{T-29.65})^{-1}$$
$$ω_s=\frac {m_{vs}}{m_d} =\frac {0.622e_s}{p}(approximation)$$, es means saturation vapor pressure(pa), it can be get from vapor pressure of water table [2].

ω means humidity ratio at certain cases,and ω_s  means saturation equilibrium humidiy ratio.

q means specific humidity same as ω(approximation),p certain case pressure(can be measured.)

### 2.4 Thermal Comfort Method (PMV)

The Predicted Mean Vote (PMV) model stands among the most recognized thermal comfort models. It was developed using principles of heat balance and experimental data collected in a controlled climate chamber under steady state conditions. 

Today, thermal comfort is defined as “that condition of mind that expresses satisfaction with the thermal environment” in the globally recognized ASHRAE 55 and ISO 7730 standards for evaluating indoor environments. To assess this condition, engineers must first determine the thermal sensation or thermal balance inhabitants of an indoor environment may feel in tangent with the thermal dissatisfaction experienced by occupants. These comfort limits can be expressed by the PMV and the PPD indices.

**Our group will use PMV method to estimate the thermal comfort with ASHRAE standard and project comfortable range into Psychrometric chart.**

### 2.5 ASHARE Standard 55-2020

Standard 55 specifies conditions for acceptable thermal environments and is intended for use in design, operation, and commissioning of buildings and other occupied spaces. Standard 55 specifies conditions for acceptable thermal environments and is intended for use in design, operation, and commissioning of buildings and other occupied spaces. [5]

In our project, the table here can be utilized to estimate an exact value (the range is based on website tool from Berkeley.)

**Table 1 presents the values from the Canadian Standards Association (CSA) International's Standard** CAN/CSA Z412-00 - "Office Ergonomics" which gives temperature and relative humidity requirements for offices in Canada. These values are based on the American Society of Heating, Refrigerating, and Air Conditioning Engineers (ASHRAE) Standard 55 - 2004 "Thermal Environmental Conditions for Human Occupancy". These values are designed to meet the needs of 80% of individuals which means a few people will feel uncomfortable even if these values are met. Additional measures may be required. ASHRAE Standard 55 recommends a range of temperature and humidity values for thermal comfort in office work. 

**The reason we use ASHRAE Standard 55 in 2020 is that there is a good website that can manipulate inputs and outputs. (Temperature, relative humidity, humidity ratio and thermal comfortable range.)**

### 2.6 Psychrometric chart (temperature vs. relative humidity)

As you can see, this chart comes from Thompson, and it is used in recent engineering program to estimate facts. **The X-axis means dry bulb temperature, Y-axis means humidity ratio, and relative humidity in parabola.** 

In next part, the thermal comfort tool is based on this chart to generate exact figure for our project.

### 2.7 Center for the built environmental Thermal Comfort Tool

The website tool contains inputs and outputs. **In our projects, the main two parts is temperature and relative humidity**. The other inputs, as **assumptions**, including **Air speed, metabolic rate, and clothing level, is related to ASHRAE Standard 55-2020 to get the range**. We use the formula to check with the humidity ratio that comes from relative humidity (which is closed to the chart in tool).

We get sensor value for temperature 24C and relative humidity for 46% and it’s out of thermal comfort range. In Figure 2., it shows the humidifier should work until the relative humidity reach 50%, which means it’s on thermal comfort range. 

In this case, the humidifier should be on working. However, according to humidifier’s shortcomings in accuracy and unity (can’t reach temperature value.), our humidifier didn’t release the vapor. 

### 2.8 Humidifier
*summary of humidifier*
The humidifier limits are based on several aspects:
1.	**Inaccuracy** 
The humidity is inaccurate because its sensor is on the circuit. In this case, it might be inaccurate. However, DHT11 in Raspberry Pi is directly connected to air which is accurate.
2.	**Unity**
The humidifier’s sensor can only get the value in relative humidity not temperature. It can not get the correct thermal comfort range to release vapor efficiently. 



### 2. Coding Progress

Our code is listed below:


