Portia API v3.2.1
=================

## 1. Packages

### 1.1. Portia Dimensions Package

```javascript
{
  “package”:{
    "header": {
      "device_channel_code":      "integer",
      "device_channel_id":        "String[16]",
      "userspace":                "String[20]",
      "server_timestamp":         "timestamp"
    },

    "body":{
      "device_edge_id":           "String[16]",
      "device_port_id":           "integer",
      "device_sensor_id":         "integer",     
      "dimension_code":           "integer",
      "dimension_unity_code":     "integer",
      "dimension_thing_code":     "integer",  
      "dimension_value":          "float",             
      "dimension_timestamp":      "timestamp"
    }
  }
}
```

## 2. Codes

### 2.1. Measurement Unit Codes

|**Code** |**Label / Symbol** |**Summarized Description**                                  |**Category**                  |
|:-------:|:-----------------:|:-----------------------------------------------------------|:----------------------------:|
|0        |units              |Measurement without a specific unit                         |Not Specified                 |
|1        |ºC                 |Degree Celsius, temperature measurement                     |International System of Units |
|2        |%                  |Percentage, ratio expressed as a fraction of 100            |--                            |
|3        |ppm                |Parts-per-million, measurement of concentration             |--                            |
|4        |L                  |Liter, volume measurement                                   |International System of Units |
|5        |g                  |Gram, mass measurement                                      |International System of Units |
|6        |s                  |Second, time measurement                                    |International System of Units |
|7        |L/min              |Liters per minute, measurement of volume per time           |International System of Units |
|8        |dBm                |Decibel-milliwatts, measurement of power ratio by milliwatt |--                            |
|9        |B                  |Byte, computational measurement                             |--                            |
|10       |deviation          |Deviation of a base value                                   |--                            |
|11       |JSONObject         |Object that is a composition of values                      |--                            |
|12       |ms                 |Milliseconds, time measurement                              |International System of Units |
|13       |V                  |Voltage, measurement of an electric potential difference    |International System of Units |
|14       |Pa                 |Pascal, measurement of pressure and stress                  |International System of Units |
|15       |kg                 |Kilogram, measurement of mass                               |International System of Units |
|16       |days               |Day, time measurement                                       |--                            |

### 2.2. Thing / Device Codes

|**Code** |**Label / Symbol**  |**Sensor**                           |**Summarized Description**                              |**Category**    |
|:-------:|:------------------:|:-----------------------------------:|:-------------------------------------------------------|:--------------:|
|0        |--                  |--                                   |Not specified                                           |Not Specified   |
|1        |ProbeTU_v1          |[DHT22](https://goo.gl/RQ5Saz)       |Temperature and air umidity probe                       |Passive         |
|2        |ProbeAirQ_v1        |[MQ135](https://goo.gl/nPMY3j)       |Harmful gases detection probe                           |Passive         |
|3        |HubHydro_v1         |PortiaVirtualSensors0                |Agriness Edge's Hydro hub                               |Active Complex  |
|4        |ProbeLoadCell_v1    |[HX711](http://goo.gl/DLHKmD)        |Charge cell amplifier                                   |Active          | 
|5        |HubCycleCounter_v1  |--                                   |Agriness Edge's Cycle Counter hub (deprecated)          |Active Complex  |
|6        |HubSmaai5           |--                                   |Inobram's Smaai 5 hub                                   |Active Complex  |
|7        |ProbeHydroEDN15-100 |[DN15-v100](http://goo.gl/mEFakc)    |3/4 Hydrometer                                          |Passive         |
|8        |ProbeHydroQMS_v1    |[YF-S201](https://goo.gl/qpqKs1)     |Parallel Hydrometer                                     |Passive         |
|9        |ProbeHydroTemp_v1   |[DS18B20](http://goo.gl/FiYWXh)      |Water temperature probe                                 |Passive         |
|10       |Gateway_v0          |PortiaVirtualSensors0                |Agriness Edge's Gateway version 0                       |Active Complex  |
|11       |HubUniversal_v1     |PortiaVirtualSensors0                |Agriness Edge's Universal hub                           |Active Complex  |
|12       |HubSmaai3           |--                                   |Inobram's Smaai 3 hub                                   |Passive Complex |
|13       |HubSmaai4           |--                                   |Inobram's Smaai 4 hub                                   |Passive Complex |
|14       |Gateway_v1          |--                                   |Agriness Edge's Gateway version 1                       |Active Complex  |
|15       |ProbeSmaaiT         |[Probe T](https://bit.ly/2JDKwRQ)    |Inobram's temperature probe                             |Passive         |
|16       |ProbeSmaaiTU        |[Probe TU](https://bit.ly/2JDKwRQ)   |Inobram's temperature and air umidity probe             |Passive         |
|17       |SmaaiExhaustor      |[Exhaustor](https://bit.ly/2HONoWq)  |Inobram's exhaustor relay board                         |Passive         |
|18       |SmaaiNebulizer      |[Nebulizer](https://bit.ly/2HONoWq)  |Inobram's nebulizer relay board                         |Passive         |
|19       |SmaaiHeater         |[Heater](https://bit.ly/2HONoWq)     |Inobram's heater relay board                            |Passive         |
|20       |SmaaiDimmer         |[Dimmer](https://bit.ly/2yhtLHc)     |Inobram's dimmer                                        |Passive         |
|21       |ProbeSmaaiPE        |[Probe PE](https://bit.ly/2JDKwRQ)   |Inobram's static pressure probe                         |Passive         |
|22       |ProbeSmaaiH2O       |[Probe H2O](https://bit.ly/2JDKwRQ)  |Inobram's water consumption probe                       |Passive         |
|23       |ProbeSmaaiCO2       |[Probe CO2](https://bit.ly/2JDKwRQ)  |Inobram's CO2 concentration probe                       |Passive         |
|24       |ProbeSmaaiU         |[Probe U](https://bit.ly/2JDKwRQ)    |Inobram's air umidity probe                             |Passive         |
|25       |SmaaiSmartScale     |[SmartScale](https://bit.ly/2I2Ip4I) |Inobram's hen weight scale probe                        |Passive         |
|26       |SmaaiSiloWeight     |[SiloWeight](https://bit.ly/2M2PMvb) |Inobram's silo weight scale probe                       |Passive         |
|27       |VirtualGateway_v0   |--                                   |Agriness Edge's Virtual Gateway version 0               |Active Complex  |
|28       |HubAmbientte        |--                                   |Inobram's Ambientte hub                                 |Active Complex  |
|29       |HubBluetooth_v1     |PortiaVirtualSensors0                |Agriness Edge's Bluetooth hub                           |Active Complex  |
|30       |ProbeTruTestS2      |[S2 TRU-TEST](https://goo.gl/piukBW) |S2 Tru-Test's weight scale with bluetooth communication |Active Complex  |

## 2.3. Dimension Codes

|**Code** |**Label / Symbol**    |**Summarized Description**                     |**Category**  |
|:-------:|:--------------------:|:----------------------------------------------|:------------:|
|0        |--                    |Not specified                                  |Not Specified |
|1        |pointTemperature      |Point temperature                              |Environment   |
|2        |averageTemperature    |Average temperature                            |Environment   |
|3        |pointUmidity          |Point umidity                                  |Environment   |
|4        |averageUmidity        |Average umidity                                |Environment   |
|5        |pointConcentration    |Point harmful gases concentration              |Environment   |
|6        |averageConcentration  |Average harmful gases concentration            |Environment   |
|7        |cumulativeFlow        |Cumulative flow                                |Consumption   |
|8        |pointFlow             |Point flow                                     |Consumption   |
|9        |pointWaterTemperature |Point water temperature (deprecated)           |Environment   |
|10       |pointWeight           |Point weight                                   |Individual    |
|11       |averageWeight         |Average weight                                 |Group         |
|12       |deviceStatus          |Status of a device                             |Equipment     |
|13       |pointCO2Concentration |Point CO2 gas concentration                    |Environment   |
|14       |numberCycles          |Number of times that a device was turned on    |Consumption   |
|15       |uptime                |Device uptime                                  |Equipment     |
|16       |rssi                  |Received signal strength indicator             |Equipment     |
|17       |freeMemory            |Free RAM memory                                |Equipment     |
|18       |freeDisk              |Free disk memory                               |Equipment     |
|19       |systemLoad            |CPU load of a device                           |Equipment     |
|20       |fileSize              |File size                                      |Equipment     |
|21       |momentaryTime         |A specific moment timestamp                    |Equipment     |
|22       |profile               |Profile of a device                            |Equipment     |
|23       |devicePower           |Voltage powering a device                      |Equipment     |
|24       |pointPressure         |Point pressure                                 |Environment   |
|25       |averagePressure       |Average pressure                               |Environment   |
|26       |model                 |Description of ontology, software and hardware |Equipment     |
|27       |lotDay                |Current day of a lot                           |Lot           |

# 3. Specifications

### Labels:
* '*': Rule applies to any value
* '@': Default value for the query, each operation (SELECT, SUMMARY, ...) can have its own default values
* '#': Null value, uses parameter on the query if there is one

## 3.1. Default

|**Axiom**      |**Dimension Code**          |**From** |**To** |**Lower Bound** |**Upper Bound** |**Number of Packages** |
|:-------------:|:--------------------------:|:-------:|:-----:|:--------------:|:--------------:|:---------------------:|
| edge_axiom_v1 | 1 (pointTemperature)       | @       | @     | 0              | 60             | #                     |
| edge_axiom_v1 | 3 (pointUmidity)           | @       | @     | 0              | 100            | #                     |
| edge_axiom_v1 | 5 (pointConcentration)     | @       | @     | 0              | 4000           | #                     |
| edge_axiom_v1 | 7 (cumulativeFlow)         | @       | @     | 0              | 100000         | #                     |
| edge_axiom_v1 | 8 (pointFlow)              | @       | @     | 0              | 300            | #                     |
| edge_axiom_v1 | 12 (deviceStatus)          | @       | @     | 0              | 1              | #                     |
| edge_axiom_v1 | 13 (pointCO2Concentration) | @       | @     | 0              | 4000           | #                     |
| edge_axiom_v1 | 15 (uptime)                | @       | @     | 0              | #              | #                     |
| edge_axiom_v1 | 17 (freeMemory)            | @       | @     | 0              | 100            | #                     |
| edge_axiom_v1 | 18 (freeDisk)              | @       | @     | 0              | 100            | #                     |
| edge_axiom_v1 | 19 (systemLoad)            | @       | @     | 0              | #              | #                     |
| edge_axiom_v1 | 20 (fileSize)              | @       | @     | 0              | #              | #                     |
| edge_axiom_v1 | 23 (devicePower)           | @       | @     | 0              | #              | #                     |
| edge_axiom_v1 | 27 (lotDay)                | @       | @     | 1              | #              | #                     |
| edge_axiom_v1 | *                          | @       | @     | #              | #              | #                     |

## 3.2. Raw

|**Axiom**      |**Dimension Code** |**From** |**To** |
|:-------------:|:-----------------:|:-------:|:-----:|
| time_axiom_v1 | *                 | @       | @     |