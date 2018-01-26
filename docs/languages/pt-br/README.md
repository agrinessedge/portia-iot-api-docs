Portia
======

Bem-vindo à documentação do *Read the Docs Template's* !
==================================================

Introdução 
-----------

### Portia Package

#### Dimension 

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

### Config 

#### Dimension v 0.1

##### Códigos de Dimensões 


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

##### Códigos de Unidades de Medida 


|**Código**|**Rótulo/Símbolo**       |**Descrição Resumida**                                      |**Categoria**                    |
|:--------:|:-----------------------:|:----------------------------------------------------------:|:-------------------------------:|
|0         |unidades                 |Medida sem unidade específica                               |--                               |
|1         |ºC                       |Grau Celsius, medida de temperatura                         |Sistema Internacional de Unidades|
|2         |%                        |Porcentagem, medida de razão com base 100                   |--                               |
|3         |ppm                      |Parte por milhão, medida de concentração com base 1000000   |--                               |
|4         |L                        |Litro, medida  de volume                                    |Sistema Internacional de Unidades| 
|5         |g                        |Grama, medida de massa                                      |Sistema Internacional de Unidades|
|6         |s                        |Segundo, medida de tempo                                    |Sistema Internacional de Unidades|
|7         |L/min                    |Litros por minuto, medida de volume (capacidade) por tempo  |Sistema Internacional de Unidades|


#### Códigos de Coisas v_0.1


|**Código**|**Rótulo/Símbolo**        |**Descrição Resumida**                                      |**Categoria**            |
|:--------:|:------------------------:|:----------------------------------------------------------:|:-----------------------:|
|0         |'Coisa' sem especificação |--                                                          |--                       |
|1         |AirTU                     |Sensor de temperatura e umidade                             |Passivo                  |
|2         |AirGases                  |Sensor de detecção de gases nocivos                         |Passivo                  |
|3         |Hydro                     |Tratamento de dados de temperatura e fluxo da água          |Ativo                    |
|4         |LoadCell                  |Amplificador de célula de carga                             |Complexo ativo           | 
|5         |Cycle                     |Tratamento de dados de acionamento elétrico                 |Complexo ativo           |



<!--
# Laranja Sync

## Unidades de Medida

| ID  | Label       | Descrição                                             |
|-----|:-----------:|:-----------------------------------------------------:|
| 1   | -           | Medida sem unidade específica                         |
| 2   | ºc          | Temperatura em graus celsius                          |
| 3   | %           | Percentual                                            |
| 4   | -           | Timestamp                                             |
| 5   | Pa          | Pressão - Pascal                                      |
| 6   | ppm         | Gás - ppm                                             |
| 7   | -           | Boolean (aceita apenas verdadeiro [<=0] ou falso[>0]  |
| 8   | dias        | Contador de dias                                      |
| 9   | Kg          | Peso em kilogramas                                    |
| 11  | segundos    | Tempo em segundos                                     |
| 12  | m/s         | Velocidade em metros por segundo                      |
| 13  | g           | Gramas                      |


## Dimensões

| ID  | Label                   | Descrição                                                                         |
|-----|:-----------------------:|:---------------------------------------------------------------------------------:|
| 1   | -                       | Não especificada                                                                  |
| 2   | temperaturaMedia        | Temperatura Média Ambiente                                                        |
| 3   | temperaturaPontual      | Temperatura Pontual                                                               |
| 4   | temperaturaDesejada     | Temperatura média ideal para o ambiente                                           |
| 5   | temperaturaDiff         | Diferença entre a temperatura atual e a temperatura média ideal para o ambiente   |
| 6   | umidadeMedia            | Umidade Média Ambiente                                                            |
| 7   | umidadePontual          | Umidade Pontual                                                                   |
| 8   | diaLote                 | Contador de dias desde o início de um lote                                        |
| 9   | pressaoMedia            | Pressão media                                                                     |
| 10  | volumeMedio             | Volume Medio                                                                      |
| 11  | volumePontual           | Volume Pontual                                                                      |
| 12  | diaInicioLote           | Data de início de um lote                                                         |
| 13  | pesoPontual  l          | Peso pontual                                     |
| 14  | pesoDesejado            | Peso determinado como desejado para o fim do lote                                 |
| 15  | volumePercReservatorio  | Volume médio restante de reservatórios                                            |
| 16  | ventilacao              | Determina a porcentagem de exaustores que serao acionados                         |
| 17  | velocidadeVento         | Velocidade do vento dentro do aviário exercida pelos exaustores                   |
| 18  | sensacaoTermica         | Temperatura sentida dentro do ambiente                                            |
| 19  | temperaturaExterna      | Temperatura exterior ao ambiente                                                  |
| 20  | umidadeExterna          | Umidade exterior ao ambiente                                                      |
| 21  | volumePercSilo          | Volume médio restante dos silos                                                   |
| 22  | anomaliasLeves          | Número de anomalias leves no sistema (Advisories)                                 |
| 23  | anomaliasModeradas      | Número de anomalias moderadas no sistema (Escalating)                             |
| 24  | anomaliasSeveras        | Número de anomalias severas no sistema (Severe)                                   |
| 25  | grauConforto            | Grau de conforto dos animais                                                      |
| 26  | eficiencia              | A eficiência do ambiente                                                          |
| 27  | estadoDispositivo       | Estado de um dipositivo (on/off)                                                   |

## Sujeitos

| ID  | Label           | Descrição                                         |
|-----|:---------------:|:-------------------------------------------------:|
| 1   | system          | O sistema como um todo                            |
| 2   | user            | O usuário do sistema                              |
| 3   | rule            | Regras do sistema                                 |
| 4   | sensor          | Referente a tudo o que é monitorado no aviário    |

## Canais

| ID  | Label           | Descrição                                             |
|-----|:---------------:|:-----------------------------------------------------:|
| 1   | localSystem     | Para decisões tomadas no código                       |
| 2   | localGui        | Para decisões tomadas por usuários na interface local |
| 3   | remoteSystem    | Para decisões tomadas remotamente                     |
| 3   | remoteGui       | Para decisões tomadas por usuários remotamente        |

## Ações

| ID  | Label           | Descrição                                 |
|-----|:---------------:|:-----------------------------------------:|
| 1   | actuation       | Atuação de sensores                       |
| 2   | restart         | Reinício de equipamentos                  |
| 3   | shutdown        | Desligamento de equipamentos              |
| 4   | register        | Registra novos sensores                   |
| 5   | update          | Atualiza sensores                         |

## Thing Codes

| ID  | Label           | Descrição                                 |
|-----|:---------------:|:-----------------------------------------:|
| 1   | dht22           | DHT22                      |
| 2   | dht11           | DHT11                      |
| 3   | dht12           | DHT12                      |
| 4   | hx711           | HX711                      |
| 5   | tc              | TC                         |
| 6   | mq135           | MQ135                      |

## Kaa 

Adopted ports (kaa-sandbox):

```
sudo iptables -I INPUT -p tcp -m tcp --dport **8080** -j ACCEPT # Admin UI
sudo iptables -I INPUT -p tcp -m tcp --dport **9888** -j ACCEPT
sudo iptables -I INPUT -p tcp -m tcp --dport **9889** -j ACCEPT
sudo iptables -I INPUT -p tcp -m tcp --dport **9997** -j ACCEPT
sudo iptables -I INPUT -p tcp -m tcp --dport **9999** -j ACCEPT
```
-->
