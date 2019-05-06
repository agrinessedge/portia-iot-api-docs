Portia API v3.2.1
=================

<!--
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
-->

## 1. Pacotes

### 1.1. Pacote Portia de Dimensões

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

## 2. Códigos

### 2.1. Códigos de Unidades de Medida

|**Código** |**Rótulo/Símbolo** |**Descrição Resumida**                                      |**Categoria**                     |
|:---------:|:-----------------:|:-----------------------------------------------------------|:--------------------------------:|
|0          |unidades           |Medida sem unidade específica                               |Sem Especificação                 |
|1          |ºC                 |Grau Celsius, medida de temperatura                         |Sistema Internacional de Unidades |
|2          |%                  |Porcentagem, medida de razão com base 100                   |--                                |
|3          |ppm                |Parte por milhão, medida de concentração com base 1.000.000 |--                                |
|4          |L                  |Litro, medida de volume                                     |Sistema Internacional de Unidades |
|5          |g                  |Grama, medida de massa                                      |Sistema Internacional de Unidades |
|6          |s                  |Segundo, medida de tempo                                    |Sistema Internacional de Unidades |
|7          |L/min              |Litros por minuto, medida de volume (capacidade) por tempo  |Sistema Internacional de Unidades |
|8          |dBm                |Decibel-milliwatts, nível de potência em decibéis           |--                                |
|9          |B                  |Byte, medida computacional                                  |--                                |
|10         |desvio             |Desvio em relação a algum valor base                        |--                                |
|11         |JSONObject         |Objeto com composição de valores                            |--                                |
|12         |ms                 |Milissegundo, medida de tempo                               |Sistema Internacional de Unidades |
|13         |V                  |Tensão elétrica, diferença de potencial elétrico            |Sistema Internacional de Unidades |
|14         |Pa                 |Pascal, unidade padrão de pressão e tensão                  |Sistema Internacional de Unidades |
|15         |kg                 |Kilograma, medida de massa                                  |Sistema Internacional de Unidades |
|16         |dias               |Dia, medida de tempo                                        |--                                |

### 2.2. Códigos de Coisas / Dispositivos

|**Código**|**Rótulo / Símbolo** |**Sensor**                             |**Descrição Resumida**                               |**Categoria**     |
|:--------:|:-------------------:|:-------------------------------------:|:----------------------------------------------------|:----------------:|
|0         |--                   |--                                     |Sem especificação                                    |Sem Especificação |
|1         |ProbeTU_v1           |[DHT22](https://goo.gl/RQ5Saz)         |Sensor de temperatura e umidade do ar                |Passivo           |
|2         |ProbeAirQ_v1         |[MQ135](https://goo.gl/nPMY3j)         |Sensor de detecção de gases nocivos                  |Passivo           |
|3         |HubHydro_v1          |PortiaVirtualSensors0                  |Hub Hydro da Agriness Edge                           |Complexo Ativo    |
|4         |ProbeLoadCell_v1     |[HX711](http://goo.gl/DLHKmD)          |Amplificador de célula de carga                      |Ativo             | 
|5         |HubCycleCounter_v1   |--                                     |Hub contador de ciclos da Agriness Edge (depreciado) |Complexo Ativo    |
|6         |HubSmaai5            |--                                     |Hub Smaai 5 da Inobram                               |Complexo Ativo    |
|7         |ProbeHydroEDN15-100  |[DN15-v100](http://goo.gl/mEFakc)      |Hidrometro 3/4                                       |Passivo           |
|8         |ProbeHydroQMS_v1     |[YF-S201](https://goo.gl/qpqKs1)       |Hidrometro paralelo                                  |Passivo           |
|9         |ProbeHydroTemp_v1    |[DS18B20](http://goo.gl/FiYWXh)        |Sensor de temperatura da água                        |Passivo           |
|10        |Gateway_v0           |PortiaVirtualSensors0                  |Gateway versão 0 da Agriness Edge                    |Complexo Ativo    |
|11        |HubUniversal_v1      |PortiaVirtualSensors0                  |Hub Universal da Agriness Edge                       |Complexo Ativo    |
|12        |HubSmaai3            |--                                     |Hub Smaai 3 da Inobram                               |Complexo Passivo  |
|13        |HubSmaai4            |--                                     |Hub Smaai 4 da Inobram                               |Complexo Passivo  |
|14        |Gateway_v1           |--                                     |Gateway versão 1 da Agriness Edge                    |Complexo Ativo    |
|15        |ProbeSmaaiT          |[Sonda T](https://bit.ly/2JDKwRQ)      |Sensor de temperatura da Inobram                     |Passivo           |
|16        |ProbeSmaaiTU         |[Sonda TU](https://bit.ly/2JDKwRQ)     |Sensor de temperatura e umidade do ar da Inobram     |Passivo           |
|17        |SmaaiExhaustor       |[Exaustor](https://bit.ly/2HONoWq)     |Placa de relês para exaustores da Inobram            |Passivo           |
|18        |SmaaiNebulizer       |[Nebulizador](https://bit.ly/2HONoWq)  |Placa de relês para nebulizadores da Inobram         |Passivo           |
|19        |SmaaiHeater          |[Aquecedor](https://bit.ly/2HONoWq)    |Placa de relês para aquecedores da Inobram           |Passivo           |
|20        |SmaaiDimmer          |[Dimmer](https://bit.ly/2yhtLHc)       |Dimmer da Inobram                                    |Passivo           |
|21        |ProbeSmaaiPE         |[Sonda PE](https://bit.ly/2JDKwRQ)     |Sensor de pressão estática da Inobram                |Passivo           |
|22        |ProbeSmaaiH2O        |[Sonda H2O](https://bit.ly/2JDKwRQ)    |Sensor de consumo de água da Inobram                 |Passivo           |
|23        |ProbeSmaaiCO2        |[Sonda CO2](https://bit.ly/2JDKwRQ)    |Sensor de concentração de CO2 da Inobram             |Passivo           |
|24        |ProbeSmaaiU          |[Sonda U](https://bit.ly/2JDKwRQ)      |Sensor de umidade do ar da Inobram                   |Passivo           |
|25        |SmaaiSmartScale      |[SmartScale](https://bit.ly/2I2Ip4I)   |Sensor para pesagem de aves da Inobram               |Passivo           |
|26        |SmaaiSiloWeight      |[Peso de Silo](https://bit.ly/2M2PMvb) |Sensor para pesagem de silos da Inobram              |Passivo           |
|27        |VirtualGateway_v0    |--                                     |Gateway Virtual versão 0 da Agriness Edge            |Complexo Ativo    |
|28        |HubAmbientte         |--                                     |Hub Ambientte da Inobram                             |Complexo Ativo    |
|29        |HubBluetooth_v1      |PortiaVirtualSensors0                  |Hub Bluetooth da Agriness Edge                       |Complexo Ativo    |
|30        |ProbeTruTestS2       |[S2 TRU-TEST](https://goo.gl/piukBW)   |Balança S2 Tru-Test com comunicação via bluetooth    |Complexo Ativo    |

## 2.3. Códigos de Dimensões

|**Código** |**Rótulo/Símbolo**     |**Descrição Resumida**                                |**Categoria**     |
|:---------:|:---------------------:|:-----------------------------------------------------|:----------------:|
|0          |--                     |Sem especificação                                     |Sem Especificação |
|1          |temperaturaPontual     |Temperatura pontual                                   |Ambiente          |
|2          |temperaturaMedia       |Temperatura média                                     |Ambiente          |
|3          |umidadePontual         |Umidade pontual                                       |Ambiente          |
|4          |umidadeMedia           |Umidade média                                         |Ambiente          |
|5          |concentracaoPontual    |Concentração de gases nocivos pontual                 |Ambiente          |
|6          |concentracaoMedia      |Concentração de gases nocivos média                   |Ambiente          |
|7          |fluxoAcumulado         |Fluxo de água acumulado                               |Consumo           |
|8          |fluxoPontual           |Fluxo de água pontual                                 |Consumo           |
|9          |temperaturaAguaPontual |Temperatura da água pontual                           |Ambiente          |
|10         |pesoPontual            |Peso pontual                                          |Indivíduo         |
|11         |pesoMedio              |Peso médio                                            |Grupos Indivíduos |
|12         |estadoDispositivo      |Estado de um dispositivo                              |Equipamento       |
|13         |concentracaoCO2Pontual |Concentração de CO2 pontual                           |Ambiente          |
|14         |numeroCiclos           |Quantidade de vezes que um dispositivo foi ligado     |Consumo           |
|15         |uptime                 |Tempo de uptime                                       |Equipamento       |
|16         |rssi                   |Received signal strength indicator                    |Equipamento       |
|17         |memoriaLivre           |Memória RAM livre                                     |Equipamento       |
|18         |discoLivre             |Memória em disco livre                                |Equipamento       |
|19         |cargaSistema           |Carga associada ao equipamento                        |Equipamento       |
|20         |tamanhoArquivo         |Tamanho de um arquivo                                 |Equipamento       |
|21         |tempoMomentaneo        |Timestamp relativo a um momento                       |Equipamento       |
|22         |perfil                 |Perfil com descrição do equipamento                   |Equipamento       |
|23         |alimentacaoDispositivo |Tensão elétrica de alimentação                        |Equipamento       |
|24         |pressaoPontual         |Pressão pontual                                       |Ambiente          |
|25         |pressaoMedia           |Pressão média                                         |Ambiente          |
|26         |modelo                 |Descrição de versão de ontologia, software e hardware |Equipamento       |
|27         |diaLote                |Dia corrente do lote                                  |Lote              |