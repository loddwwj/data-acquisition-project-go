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

The definition of humidity contains several aspects: Absolute humidity, Relative humidity, Specific humidity (humidity ratio). Absolute humidity can be defined as the mass of H_2 O in certain amount of volume, which will be affected by air pressure and will also be affected by temperature if the volume is not a constant.

$$ AH,_(Absolute humidity)=\frac {m_(H_2 O)}/{V_net} ,unit:g/m^3 $$ 

Relative humidity, Rh or ϕ is the ratio of partial pressure of water vapor in the mixture to the equilibrium vapor pressure of water over a flat surface of pure water at a given temperature. [1] ϕ=p_(H_2 O)/〖p*〗_(H_2 O) (partial pressure means the percentage of water pressure divided by total pressure.) Once the ϕ increase, air should be wetter and if it reaches to 100%, it will reach to dew point(participation). Relative humidity will be affected by temperature. The colder air will get lower capacity to maintain vapors. 
Specific Humidity (humidity ratio) is the ratio of the mass of water vapor to total mass of the air parcel. [1] Approximate formula should be m_(H_2 O)/(〖m_air-m〗_(H_2 O) [dry air]), with unit kg/kg or g/kg. In our project we need also consider the transform formula for Specific Humidity and Relative humidity. It should be 
	RH=100*ω/ω_s =0.263pq[exp⁡(17.67(T-T_0 )/(T-29.65)) ]^(-1)
	ω_s=m_vs/m_d =(0.622e_s)/p(approximation), es means saturation vapor pressure(pa), it can be get from vapor pressure of water table [2].
ω means humidity ratio at certain cases,and ω_s  means saturation equilibrium humidiy ratio.
q means specific humidity same as ω(approximation),p certain case pressure(can be measured.)



### 2. Coding Progress

Our code is listed below:


