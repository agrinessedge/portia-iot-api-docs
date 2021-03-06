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

|**Código** |**Rótulo/Símbolo** |**Descrição Resumida**                                      |**Categoria**                        |
|:---------:|:-----------------:|:-----------------------------------------------------------|:-----------------------------------:|
|0          |unidades           |Medida sem unidade específica                               |Sem Categoria                        |
|1          |°C                 |Grau Celsius, medida de temperatura                         |Sistema Internacional de Unidades    |
|2          |%                  |Porcentagem, medida de razão com base 100                   |Sem Categoria                        |
|3          |ppm                |Parte por milhão, medida de concentração com base 1.000.000 |Sem Categoria                        |
|4          |L                  |Litro, medida de volume                                     |Sistema Internacional de Unidades    |
|5          |g                  |Grama, medida de massa                                      |Sistema Internacional de Unidades    |
|6          |s                  |Segundo, medida de tempo                                    |Sistema Internacional de Unidades    |
|7          |L/min              |Litros por minuto, medida de volume (capacidade) por tempo  |Sistema Internacional de Unidades    |
|8          |dBm                |Decibel-milliwatts, nível de potência em decibéis           |Sistema Internacional de Unidades    |
|9          |B                  |Byte, medida computacional                                  |Comissão Eletrotécnica Internacional |
|10         |desvio             |Desvio em relação a algum valor base                        |Sem Categoria                        |
|11         |JSONObject         |Objeto com composição de valores                            |Sem Categoria                        |
|12         |ms                 |Milissegundo, medida de tempo                               |Sistema Internacional de Unidades    |
|13         |V                  |Tensão elétrica, diferença de potencial elétrico            |Sistema Internacional de Unidades    |
|14         |Pa                 |Pascal, unidade padrão de pressão e tensão                  |Sistema Internacional de Unidades    |
|15         |kg                 |Kilograma, medida de massa                                  |Sistema Internacional de Unidades    |
|16         |dias               |Dia, medida de tempo                                        |Sistema Internacional de Unidades    |
|17         |mV                 |Milivolts, medida de diferença de potencial elétrico        |Sistema Internacional de Unidades    |
|18         |gal                |Galões, unidade de medida de volume de líquidos             |Sistema Imperial Britânico           |
|19         |°F                 |Fahrenheit, medida de temperatura                           |Sistema Imperial Britânico           |

### 2.2. Códigos de Coisas / Dispositivos

|**Código**|**Rótulo / Símbolo** |**Sensor**                             |**Descrição Resumida**                               |**Categoria**     |
|:--------:|:-------------------:|:-------------------------------------:|:----------------------------------------------------|:----------------:|
|0         |NotSpecified         |--                                     |Sem especificação                                    |Sem Categoria     |
|1         |ProbeTU_v1           |[DHT22](https://goo.gl/RQ5Saz)         |Sensor de temperatura e umidade do ar                |Passivo           |
|2         |ProbeAirQ_v1         |[MQ135](https://goo.gl/nPMY3j)         |Sensor de detecção de gases nocivos                  |Passivo           |
|3         |HubHydro_v1          |PortiaVirtualSensors0                  |Hub Hydro da Agriness Edge                           |Complexo Ativo    |
|4         |ProbeLoadCell_v1     |[HX711](http://goo.gl/DLHKmD)          |Amplificador de célula de carga                      |Ativo             | 
|5         |HubCycleCounter_v1   |--                                     |Hub contador de ciclos da Agriness Edge (depreciado) |Complexo Ativo    |
|6         |HubSmaai5            |--                                     |Hub Smaai 5 da Inobram                               |Complexo Ativo    |
|7         |ProbeHydroEDN15-100  |[DN15-v100](http://goo.gl/mEFakc)      |Hidrômetro 3/4                                       |Passivo           |
|8         |ProbeHydroQMS_v1     |[YF-S201](https://goo.gl/qpqKs1)       |Hidrômetro paralelo                                  |Passivo           |
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
|31        |HubLogical_v0        |PortiaVirtualSensors0                  |Hub Lógico versão 0 da Agriness Edge                 |Complexo Ativo    |
|32        |SmaaiInlet           |--                                     |Placa de relês para *inlets* da Inobram              |Passivo           |
|33        |SmaaiCurtain         |--                                     |Placa de relês para cortinas da Inobram              |Passivo           |
|34        |ProbeTruTestS3       |--                                     |Balança S3 Tru-Test com comunicação via bluetooth    |Complexo Ativo    |
|35        |ProbeGsiT            |--                                     |Sensor de temperatura da GSI                         |Passivo           |
|36        |ProbeGsiU            |--                                     |Sensor de umidade do ar da GSI                       |Passivo           |
|37        |ProbeGsiH2O          |--                                     |Sensor de consumo de água da GSI                     |Passivo           |
|38        |GsiPlatformScale     |--                                     |Sensor para pesagem de aves da GSI                   |Passivo           |
|39        |GsiExhaustor         |--                                     |Placa de relês para exaustores da GSI                |Passivo           |

## 2.3. Códigos de Dimensões

|**Código** |**Rótulo/Símbolo**     |**Descrição Resumida**                                |**Categoria**     |
|:---------:|:---------------------:|:-----------------------------------------------------|:----------------:|
|0          |dimensaoAnonima        |Dimensão genérica                                     |Sem Categoria     |
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
|12         |estado                 |Estado de algo                                        |Equipamento       |
|13         |concentracaoCO2Pontual |Concentração de CO2 pontual                           |Ambiente          |
|14         |numeroCiclos           |Quantidade de vezes que um dispositivo foi ligado     |Consumo           |
|15         |tempoAcumulado         |Uptime                                                |Equipamento       |
|16         |rssi                   |Indicador de força de sinal recebido                  |Equipamento       |
|17         |memoriaLivre           |Memória RAM livre                                     |Equipamento       |
|18         |armazenamentoLivre     |Memória em disco livre                                |Equipamento       |
|19         |cargaSistema           |Carga associada ao equipamento                        |Equipamento       |
|20         |tamanhoArquivo         |Tamanho de um arquivo                                 |Equipamento       |
|21         |tempoPontual           |Um momento específico no tempo                        |Equipamento       |
|22         |perfil                 |Perfil com descrição do equipamento                   |Equipamento       |
|23         |tensaoEletricaPontual  |Tensão elétrica pontual de alimentação                |Equipamento       |
|24         |pressaoPontual         |Pressão pontual                                       |Ambiente          |
|25         |pressaoMedia           |Pressão média                                         |Ambiente          |
|26         |modelo                 |Descrição de versão de ontologia, software e hardware |Equipamento       |
|27         |diaLote                |Dia corrente do lote                                  |Lote              |
|28         |tensaoEletricaMedia    |Tensão elétrica média de alimentação                  |Equipamento       |

# 3. Fases

## 3.1. Tipo Consulta

|**Nome**       | **Parâmetros**                                                                              |
|:-------------:|:-------------------------------------------------------------------------------------------:|
| time_query    | **de (from)** (_alvo_: time, _operador_: >=); **para (to)** (_alvo_: time, _operador_: <=); |
| default_query | **limite_inferior (lower_bound)** (_alvo_: value, _operador_: >=); **limite_superior (upper_bound)** (_alvo_: value, _operador_: <=); **número_de_pacotes (number_of_packages)** (_alvo_: number_of_packages, _operador_: >=); |

# 4. Axiomas

|**Nome**       |**Fases**                   |
|:-------------:|:--------------------------:|
| time_axiom_v1 | time_query;                |
| edge_axiom_v1 | time_query; default_query; |

# 5. Especificações

### Legenda:
* '*': Regra se aplica a qualquer valor
* '@': Valor padrão para a consulta, cada operação (SELECT, SUMMARY, ...) pode ter seus próprios valores padrões
* '#': Valor nulo, usa valores passados na consulta caso existam

## 5.1. Default (Padrão)

|**Axioma**     |**Código de Dimensão**       |**De** |**Para** |**Limite Inferior** |**Limite Superior** |**Número de Pacotes** |
|:-------------:|:---------------------------:|:-----:|:-------:|:------------------:|:------------------:|:--------------------:|
| edge_axiom_v1 | 1 (temperaturaPontual)      | @     | @       | 0                  | 60                 | #                    |
| edge_axiom_v1 | 3 (umidadePontual)          | @     | @       | 0                  | 100                | #                    |
| edge_axiom_v1 | 5 (concentracaoPontual)     | @     | @       | 0                  | 4000               | #                    |
| edge_axiom_v1 | 7 (fluxoAcumulado)          | @     | @       | 0                  | 72000              | #                    |
| edge_axiom_v1 | 8 (fluxoPontual)            | @     | @       | 0                  | 55                 | #                    |
| edge_axiom_v1 | 12 (estado)                 | @     | @       | 0                  | 1                  | #                    |
| edge_axiom_v1 | 13 (concentracaoCO2Pontual) | @     | @       | 0                  | 4000               | #                    |
| edge_axiom_v1 | 15 (uptime)                 | @     | @       | 0                  | #                  | #                    |
| edge_axiom_v1 | 17 (memoriaLivre)           | @     | @       | 0                  | 100                | #                    |
| edge_axiom_v1 | 18 (armazenamentoLivre)     | @     | @       | 0                  | 100                | #                    |
| edge_axiom_v1 | 19 (cargaSistema)           | @     | @       | 0                  | #                  | #                    |
| edge_axiom_v1 | 20 (tamanhoArquivo)         | @     | @       | 0                  | #                  | #                    |
| edge_axiom_v1 | 23 (tensaoEletricaPontual)  | @     | @       | 0                  | #                  | #                    |
| edge_axiom_v1 | 27 (diaLote)                | @     | @       | 1                  | #                  | #                    |
| edge_axiom_v1 | *                           | @     | @       | #                  | #                  | #                    |

## 5.2. Raw (Crua)

|**Axioma**     |**Código de Dimensão** |**De** |**Para** |
|:-------------:|:---------------------:|:-----:|:-------:|
| time_axiom_v1 | *                     | @     | @       |

# 6. Produtos

|**Nome**       |**Código do Produto**|**Versão de SW** |**Versão de HW** |
|:-------------:|:-------------------:|:---------------:|:---------------:|
|               |1.0                  |1.2.0            |1.0              |
|               |1.0                  |1.2.1            |1.0              |
|               |1.0                  |1.3.0            |1.0              |
|               |                     |1.4.0            |2.0              |
