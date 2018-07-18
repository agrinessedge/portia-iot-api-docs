Portia-IoT v0.1
================================

Todas a definições deste documento estão associadas aos seguintes namespaces:

**portia:portia.agrinessedge.com/ontology/v1/**

# 1. Portia 

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
|2         |config                   |Parametrização de dispositivos (profiles)            |
|3         |rpc                      |                                                    |
|4         |event                    |                                                    |

##  1.1.3 Definições compartilhadas entre pacotes

### 1.1.3.1. Códigos de Unidades de Medida 

|**Código**|**Rótulo/Símbolo**       |**Descrição Resumida**                                      |**Categoria**                     |
|:--------:|:-----------------------:|:----------------------------------------------------------:|:--------------------------------:|
|0         |unidades                 |Medida sem unidade específica                               |--                                |
|1         |ºC                       |Grau Celsius, medida de temperatura                         |Sistema Internacional de Unidades |
|2         |%                        |Porcentagem, medida de razão com base 100                   |--                                |
|3         |ppm                      |Parte por milhão, medida de concentração com base 1.000.000 |--                                |
|4         |L                        |Litro, medida de volume                                     |Sistema Internacional de Unidades |
|5         |g                        |Grama, medida de massa                                      |Sistema Internacional de Unidades |
|6         |s                        |Segundo, medida de tempo                                    |Sistema Internacional de Unidades |
|7         |L/min                    |Litros por minuto, medida de volume (capacidade) por tempo  |Sistema Internacional de Unidades |
|8         |dBm                      |Potência absoluta mediante relação logaritimica. Nível de potência em decibéis |--             |
|9         |B                        |Byte, medida computacional                                  |--                                |
|10        |deviation                |Desvio em relação a algum valor base                        |--                                |
|11        |JSONObject               |Objeto com composição de valores                            |--                                |
|12        |ms                       |Milissegundo, medida de tempo                               |Sistema Internacional de Unidades |
|13        |V                        |Tensão elétrica, diferença de potencial elétrico            |Sistema Internacional de Unidades |
|14        |Pa                       |Unidade padrão de pressão e tensão                          |Sistema Internacional de Unidades |
|15        |Kg                       |Kilograma, medida de massa                                  |Sistema Internacional de Unidades |
|16        |dias                     |Dia, medida de tempo                                        |--                                |

### 1.1.3.1. Códigos de Coisas/Dispositivos

|**Cód.**|**Rótulo/Símbolo**  |**Sensor**                                |**Descrição Resumida**                              |**Categoria**            |
|:------:|:------------------:|:----------------------------------------:|:--------------------------------------------------:|:-----------------------:|
|0       |Sem especificação   |--                                        |--                                                  |--                       |
|1       |SondaTU_v1          |[DHT22](https://goo.gl/RQ5Saz)            |Sensor de temperatura e umidade do ar DHT22         |Passivo                  |
|2       |SondaAirQ_v1        |[MQ135](https://goo.gl/nPMY3j)            |Sensor de detecção de gases nocivos MQ135           |Passivo                  |
|3       |HubHydro_v1         |PortiaVirtualSensors0                     |Tratamento de dados de temperatura e fluxo da água  |Complexo Ativo           |
|4       |SondaLoadCell_v1    |[HX711](http://goo.gl/DLHKmD)             |Amplificador de célula de carga HX711               |Ativo                    | 
|5       |HubCycleCounter_v1  |--                                        |Tratamento de dados de acionamento elétrico         |Complexo Ativo           |
|6       |VirtualHubSmaai5    |--                                        |Sonda Virtual que faz a extração de dados de Smaai5 |Complexo Ativo           |
|7       |SondaHydroEDN15-100 |[DN15-v100](http://goo.gl/mEFakc)         |Hidrometro Elster DN15-v100 3/4                     |Passivo                  |
|8       |SondaHydroQMS_v1    |[YF-S201](https://goo.gl/qpqKs1)          |Hidrometro paralelo YF-S201                         |Passivo                  |
|9       |SondaHydroTemp_v1   |[DS18B20](http://goo.gl/FiYWXh)           |Sensor de temperatura da água DS18B20               |Passivo                  |
|10      |FarmBrain_v1        |PortiaVirtualSensors0                     |Equipamento responsável por envio de dados          |Complexo Ativo           |
|11      |HubUniversal_v1     |PortiaVirtualSensors0                     |Tratamento de dados genéricos                       |Complexo Ativo           |
|12      |VirtualHubSmaai3    |--                                        |Sonda que faz a extração de dados de Smaai3         |Complexo Passivo         |
|13      |VirtualHubSmaai4    |--                                        |Sonda que faz a extração de dados de Smaai4         |Complexo Passivo         |
|14      |MiniFarmBrain_v1    |--                                        |Equipamento responsável por envio de dados          |Complexo Ativo           |
|15      |SondaSmaaiT         |[Sonda T](https://bit.ly/2JDKwRQ)         |Sensor Smaai de temperatura                         |Passivo                  |
|16      |SondaSmaaiTU        |[Sonda TU](https://bit.ly/2JDKwRQ)        |Sensor Smaai de temperatura e umidade do ar         |Passivo                  |
|17      |SmaaiExhaustor      |[Exaustor](https://bit.ly/2HONoWq)        |Placa Smaai de relês para exaustores                |Passivo                  |
|18      |SmaaiNebulizer      |[Nebulizador](https://bit.ly/2HONoWq)     |Placa Smaai de relês para nebulizadores             |Passivo                  |
|19      |SmaaiHeater         |[Aquecedor](https://bit.ly/2HONoWq)       |Placa Smaai de relês para aquecedores               |Passivo                  |
|20      |SmaaiDimmer         |[Dimmer](https://bit.ly/2yhtLHc)          |Dimmer Smaai                                        |Passivo                  |
|21      |SondaSmaaiPE        |[Sonda PE](https://bit.ly/2JDKwRQ)        |Sensor Smaai de pressão estática                    |Passivo                  |
|22      |SondaSmaaiH2O       |[Sonda H2O](https://bit.ly/2JDKwRQ)       |Sensor Smaai de consumo de água                     |Passivo                  |
|23      |SondaSmaaiCO2       |[Sonda CO2](https://bit.ly/2JDKwRQ)       |Sensor Smaai de concentração de CO2                 |Passivo                  |
|24      |SondaSmaaiU         |[Sonda U](https://bit.ly/2JDKwRQ)         |Sensor Smaai de umidade do ar                       |Passivo                  |
|25      |SmaaiSmartScale     |[SmartScale](https://bit.ly/2I2Ip4I)      |Sensor Smaai para pesagem de aves                   |Passivo                  |
|26      |SmaaiSiloWeight     |[SiloWeight](https://bit.ly/2M2PMvb)      |Sensor Smaai para pesagem de silos                  |Passivo                  |
|27      |VirtualHub_V1       |--                                        |Hub Virtual para equipamentos como o Smaai5         |Complexo Ativo           |
|28      |VirtualHubAmbientte |--                                        |Sonda que faz a extração de dados de Ambientte      |Complexo Ativo           |

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

|**Código**|**Rótulo/Símbolo**       |**Descrição Resumida**                                |**Categoria**     |
|:--------:|:-----------------------:|:----------------------------------------------------:|:----------------:|
|0         |--                       |Não Especificada                                      |Não Especificada  |
|1         |temperaturaPontual       |Temperatura pontual                                   |Ambiente          |
|2         |temperaturaMedia         |Temperatura média                                     |Ambiente          |
|3         |umidadePontual           |Umidade pontual                                       |Ambiente          |
|4         |umidadeMedia             |Umidade média                                         |Ambiente          |
|5         |concentracaoPontual      |Concentração de gases nocivos pontual                 |Ambiente          |
|6         |concentracaoMedia        |Concentração de gases nocivos média                   |Ambiente          |
|7         |fluxoAcumulado           |Fluxo de água acumulado                               |Consumo           |
|8         |fluxoPontual             |Fluxo de água pontual                                 |Consumo           |
|9         |temperaturaAguaPontual   |Temperatura da água pontual                           |Ambiente          |
|10        |pesoPontual              |Peso pontual                                          |Indivíduo         |
|11        |pesoMedio                |Peso médio                                            |Grupos Indivíduos |
|12        |estadoDispositivo        |Estado de um dispositivo                              |Equipamento       |
|13        |concentracaoCO2Pontual   |Concentração de CO2 pontual                           |Ambiente          |
|14        |numeroCiclos             |Quantidade de vezes que um dispositivo foi ligado     |Consumo           |
|15        |uptime                   |Tempo de uptime                                       |Equipamento       |
|16        |rssi                     |Received signal strength indicator                    |Equipamento       |
|17        |memoriaLivre             |Memória RAM livre                                     |Equipamento       |
|18        |discoLivre               |Memória em disco livre                                |Equipamento       |
|19        |cargaSistema             |Carga associada ao equipamento                        |Equipamento       |
|20        |tamanhoArquivo           |Tamanho de um arquivo                                 |Equipamento       |
|21        |tempoMomentaneo          |Timestamp relativo a um momento                       |Equipamento       |
|22        |perfil                   |Perfil com descrição do equipamento                   |Equipamento       |
|23        |alimentacaoDispositivo   |Tensão elétrica de alimentação                        |Equipamento       |
|24        |pressaoPontual           |Pressão pontual                                       |Ambiente          |
|25        |pressaoMedia             |Pressão média                                         |Ambiente          |
|26        |modelo                   |Descrição de versão de ontologia, software e hardware |Equipamento       |
|27        |diaLote                  |Dia corrente do lote                                  |Lote              |

##    1.3. Config  (portia:config)
 
Em desenvolvimento.
