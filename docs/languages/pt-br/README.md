Portia Read the Docs Template's
================================

> Bem-vindo à documentação do *Read the Docs Template* !


# 1. Introdução 

##   1.1. Portia Package

###    1.1.1. Dimension 

    “package”:{
          "header": {
               "package_code":   "integer",
               "username":       "String[16]",
               "device_hash":    "String[8]",
               "port_id":        "integer",
               "sensor_id":      "integer"
          },
          "body":{
               "dimension_code": "integer",
               "value":          "float",
               "unity_code":     "float",
               "thing_code":     "integer",               
               "timestamp":      "timestamp"
          }
     }

###    1.1.2. Config 
 
> Ainda não documentado. 

##   1.2. Dimension (v_0.1)

###    1.2.1. Códigos de Dimensões 


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
|13        |--                       |--                                                  |--                |
|14        |numeroCiclos             |Quantidade de vezes que um dispositivo foi ligado   |Consumo           |

###    1.2.2. Códigos de Unidades de Medida 


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


###    1.2.3. Códigos de Coisas 


|**Código**|**Rótulo/Símbolo**        |**Descrição Resumida**                                      |**Categoria**            |
|:--------:|:------------------------:|:----------------------------------------------------------:|:-----------------------:|
|0         |'Coisa' sem especificação |--                                                          |--                       |
|1         |SondaTU1                  |Sensor de temperatura e umidade do ar DHT22                 |Passivo                  |
|2         |SondaAirQ1                |Sensor de detecção de gases nocivos MQ135                   |Passivo                  |
|3         |HubHydro1                 |Tratamento de dados de temperatura e fluxo da água          |Complexo ativo           |
|4         |SondaLoadCell1            |Amplificador de célula de carga                             |Ativo                    | 
|5         |HubCycleCounter1          |Tratamento de dados de acionamento elétrico                 |Complexo ativo           |
|6         |VirtualHubSmaai1          |Sonda Virtual que faz a extração de dados de Ismaais        |Complexo ativo           |
|7         |SondaHydroEDN15-100       |Hidrometro Elster DN15-v100 3/4                             |Passivo            |
|8         |SondaHydroQMS             |Hidrometro Chinese                                          |Passivo            |
|9         |SondaHydroTempV1          |Sensor de temperatura da água DS18B20                       |Passivo            |



