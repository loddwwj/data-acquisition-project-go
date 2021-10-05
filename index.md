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

![avatar](https://github.com/loddwwj/loddwwj.github.io/blob/main/sensor%20DHT11.png)
