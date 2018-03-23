Portia-IoT v0.1
================================

Todas a definições deste documento estão associadas aos seguintes namespaces:

**portia:portia.agrinessedge.com/ontology/v1/**


# 1. Introdução 

##  1.1. Portia Package (portia:package)

### 1.1.1. Portia Package data model

    “package”:{
          "header": {
                      "code":                     "integer",
                      "username":                 "String[16]",
                      "server_timestamp":         "timestamp",
          },
          
          "body":{
                      ...
          }
     }



###  1.1.2. Tipos de Pacote Portia

|**Código**|**Rótulo**               |**Objetivo**                                        |
|:--------:|:-----------------------:|:--------------------------------------------------:|
|1         |dimension                |Descrever os fenômenos observados.                  |
|2         |config                   |Parametrizção de dispositivos (profiles)            |
|3         |rpc                      |                                                    |
|4         |event                    |                                                    |

##  1.2. Definições compartilhadas entre pacotes

### 1.2.1. Códigos de Unidades de Medida 


|**Código**|**Rótulo/Símbolo**       |**Descrição Resumida**                                      |**Categoria**                    |
|:--------:|:-----------------------:|:----------------------------------------------------------:|:-------------------------------:|
|0         |unidades                 |Medida sem unidade específica                               |--                               |
|1         |ºC                       |Grau Celsius, medida de temperatura                         |Sistema Internacional de Unidades|
|2         |%                        |Porcentagem, medida de razão com base 100                   |--                               |
|3         |ppm                      |Parte por milhão, medida de concentração com base 1.000.000 |--                               |
|4         |L                        |Litro, medida  de volume                                    |Sistema Internacional de Unidades| 
|5         |g                        |Grama, medida de massa                                      |Sistema Internacional de Unidades|
|6         |s                        |Segundo, medida de tempo                                    |Sistema Internacional de Unidades|
|7         |L/min                    |Litros por minuto, medida de volume (capacidade) por tempo  |Sistema Internacional de Unidades|
|8         |dBm                      |Potência absoluta mediante relação logaritimica. Nível de potência em decibéis  | |


### 1.2.2. Códigos de Coisas/Dispositivos


|**Cód.**|**Rótulo/Símbolo**  |**Sensor**                        |**Descrição Resumida**                                      |**Categoria**            |
|:------:|:------------------:|:--------------------------------:|:----------------------------------------------------------:|:-----------------------:|
|0       |Sem especificação   |--                                |--                                                          |--                       |
|1       |SondaTU1            |[DHT22](https://goo.gl/RQ5Saz)    |Sensor de temperatura e umidade do ar DHT22                 |Passivo                  |
|2       |SondaAirQ1          |[MQ135](https://goo.gl/nPMY3j)    |Sensor de detecção de gases nocivos MQ135                   |Passivo                  |
|3       |HubHydro1           |PortiaVirtualSensors0             |Tratamento de dados de temperatura e fluxo da água          |Complexo ativo           |
|4       |SondaLoadCell1      |[HX711](http://goo.gl/DLHKmD)     |Amplificador de célula de carga HX711                       |Ativo                    | 
|5       |HubCycleCounter1    |--                                |Tratamento de dados de acionamento elétrico                 |Complexo ativo           |
|6       |VirtualHubSmaai1    |--                                |Sonda Virtual que faz a extração de dados de Ismaais        |Complexo ativo           |
|7       |SondaHydroEDN15-100 |[DN15-v100](http://goo.gl/mEFakc) |Hidrometro Elster DN15-v100 3/4                             |Passivo                  |
|8       |SondaHydroQMS       |[YF-S201](https://goo.gl/qpqKs1)  |Hidrometro paralelo YF-S201                                 |Passivo                  |
|9       |SondaHydroTempV1    |[DS18B20](http://goo.gl/FiYWXh)   |Sensor de temperatura da água DS18B20                       |Passivo                  |

##   1.2. Portia Package Dimension (portia:dimension)

###  1.2.1. Portia Package Dimension data model

    “package”:{
          "header": {
                      "code":                     "integer",
                      "username":                 "String[16]",
                      "server_timestamp":         "timestamp"
          },
          
          "body":{
                      "dimension_device_hash":    "String[16]",
                      "dimension_port_id":        "integer",
                      "dimension_sensor_id":      "integer"          
                      "dimension_code":           "integer",
                      "dimension_value":          "float",
                      "dimension_value_string":   "String",
                      "dimension_unity_code":     "integer",
                      "dimension_thing_code":     "integer",               
                      "dimension_timestamp":      "timestamp"
          }
     }



###    1.2.2 Códigos de Dimensões 

|**Código**|**Rótulo/Símbolo**       |**Descrição Resumida**                              |**Categoria**     |
|:--------:|:-----------------------:|:--------------------------------------------------:|:----------------:|
|0         |--                       |Não Especificada                                    |Não Especificada  |
|1         |temperaturaPontual       |Temperatura pontual                                 |Ambiente          |
|2         |temperaturaMedia         |Temperatura média                                   |Ambiente          |
|3         |umidadePontual           |Umidade pontual                                     |Ambiente          |
|4         |umidadeMedia             |Umidade média                                       |Ambiente          |
|5         |concentracaoPontual      |Concentração de gases nocivos pontual               |Ambiente          |
|6         |concentracaoMedia        |Concentração de gases nocivos média                 |Ambiente          |
|7         |fluxoAcumulado           |Fluxo de água acumulado                             |Consumo           |
|8         |fluxoPontual             |Fluxo de água pontual                               |Consumo           |
|9         |temperaturaAguaPontual   |Temperatura da água pontual                         |Ambiente          |
|10        |pesoPontual              |Peso da espécie sendo monitorada pontual            |Condição Animal   |
|11        |pesoMedio                |Peso médio da espécie sendo monitorada              |Condição Animal   |
|12        |estadoDispositivo        |Estado de um dispositivo                            |Equipamento       |
|13        |concentracaoco2          |Concentração de CO2                                 |Ambiente          |
|14        |numeroCiclos             |Quantidade de vezes que um dispositivo foi ligado   |Consumo           |
|15        |uptime                   |Tempo de uptime do sistema                          |Equipamento       |
|16        |rssi                     |Received signal strength indicator                  |Equipamento       |
|17        |freememory               |Memória Livre                                       |Equipamento       |
|18        |usedmemory               |Memória Utilizada                                   |Equipamento       |





##    1.3. Config  (portia:config)
 
Em desenvolvimento.






