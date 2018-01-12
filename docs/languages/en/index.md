The Portia-IoT API documentation (v1)
=====================================

## Querying Portia

### Last dimension

* **URL:** ht&#8203;tp://io.portia.supe.solutions/api/v1/device/**\<device_hash\>**/port/**\<port\>**/sensor/**\<sensor\>**/last?limit=**\<limit\>**

* **Method:** `GET`

* **Required URL Params:**
  * `device_hash=[string]`
  * `port=[integer]`
  * `sensor=[integer]`

* **Required GET Params:**
  * `limit=[integer]` [Optional, default = 1]

* **Required HEADER Params:**
  * `access_token=[string]` ['Authorization': Bearer \<access_token\>]

* **Success Response:**

  * **Code:** `200 OK`

    * **Content:** `JSON object`

* **Error Response:**

  * **Code:** `401 Unauthorized`

    * **Troubleshooting:** `Error on token authentication`

  * **Code:** `400 Bad Request`

    * **Troubleshooting:** `Error on request params`
<!--
* **Sample Call:**

  * **Javascript:**
    ```javascript
      // Access token to be sent for authentication
      let accessToken = "F894wrfDf344D-Q44fwr";

      // Ajax post request
      $.ajax({

        url: "http://io.portia.supe.solutions/api/v1/device/Bk4TFr2simTbj8vt3hww/port/1/sensor/1/last",
        type: "GET",
        dataType: "json",
        
        beforeSend: function(xhr) {
          xhr.setRequestHeader("Authorization", "Bearer " + accessToken);
        },

        success: function(response) {
          console.log(response);
        }

      });
    ```

    * **Return:** `[{"server_timestamp":1508434103038,"package_local_timestamp":1508434101,"package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":1,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":24.7,"dimension_unity_code":1,"dimension_thing_code":1}]`

  * **Python:**
    ```python
      # Library for HTTP requests
      import requests

      # Sets URL
      url = "http://io.portia.supe.solutions/api/v1/device/Bk4TFr2simTbj8vt3hww/port/1/sensor/1/last"
      accessToken = "F894wrfDf344D-Q44fwr"

      # POST with JSON 
      response = requests.get(url, headers={"Authorization", "Bearer " + accessToken})

      # Response
      response.text
    ```

    * **Return:** `[{"server_timestamp":1508434103038,"package_local_timestamp":1508434101,"package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":1,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":24.7,"dimension_unity_code":1,"dimension_thing_code":1}]`

  * **Java:**
    ```java
      StringBuilder result = new StringBuilder();

      URL url = new URL("http://io.portia.supe.solutions/api/v1/device/Bk4TsimTbj8vt3hww/port/1/sensor/1/dimension/1/last");

      HttpURLConnection conn = (HttpURLConnection) url.openConnection();
      conn.setRequestMethod("GET");

      BufferedReader rd = new BufferedReader(new InputStreamReader(conn.getInputStream()));

      String line;
      while ((line = rd.readLine()) != null) {
        result.append(line);
      }

      rd.close();

      return result.toString();
    ```

    * **Return:** `[{"server_timestamp":1508271656566,"package_local_timestamp":1508271655,"package_type_code":1,"package_username":"agrosensor","package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":2,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":23.2,"dimension_value_string":null,"dimension_unity_code":1,"dimension_thing_code":1,"dimension_thing_local_id":-1}]`
-->

### Dimensions with time intervals

* **URL:** ht&#8203;tp://io.portia.supe.solutions/api/v1/device/**\<device_hash\>**/port/**\<port\>**/sensor/**\<sensor\>**?from_timestamp=**\<from_timestamp\>**&to_timestamp=**\<to_timestamp\>**

* **Method:** `GET`

* **Required URL Params:**
  * `device_hash=[string]`
  * `port=[integer]`
  * `sensor=[integer]`

* **Required GET Params:**
  * `from_timestamp=[unsigned long]`
  * `to_timestamp=[unsigned long]` [Both optional, default = 24 hours]

* **Required HEADER Params:**
  * `access_token=[string]` ['Authorization': Bearer \<access_token\>]

* **Success Response:**

  * **Code:** `200 OK`

    * **Content:** `JSON object`

* **Error Response:**

  * **Code:** `401 Unauthorized`

    * **Troubleshooting:** `Error on token authentication`

  * **Code:** `400 Bad Request`

    * **Troubleshooting:** `Error on request params`
<!--
* **Sample Call:**

  * **Javascript:**
    ```javascript
      // Access token to be sent for authentication
      let accessToken = "F894wrfDf344D-Q44fwr";

      // Setting the intervals for the last hour
      let toTimestamp = Date.now();
      let fromTimestamp = toTimestamp - hour;

      // Sets URL
      let url = "http://io.portia.supe.solutions/api/v1/device/Bk4TsimTbj8vt3hww/port/1/sensor/1?from_timestamp=" + fromTimestamp + "&?to_timestamp=" + toTimestamp;

      // Ajax post request
      $.ajax({

        url: url,
        type: "GET",
        dataType: "json",
        
        beforeSend: function(xhr) {
          xhr.setRequestHeader("Authorization", "Bearer " + accessToken);
        },

        success: function(response) {
          console.log(response);
        }

      });
    ```

    * **Return:** `[{"server_timestamp":1508434283522,"package_local_timestamp":1508434282000,"package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":1,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":24.7,"dimension_unity_code":1,"dimension_thing_code":1},{"server_timestamp":1508434223402,"package_local_timestamp":1508434222000,"package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":1,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":24.7,"dimension_unity_code":1,"dimension_thing_code":1},{"server_timestamp":1508434163294,"package_local_timestamp":1508434162000,"package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":1,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":24.7,"dimension_unity_code":1,"dimension_thing_code":1},{"server_timestamp":1508434103038,"package_local_timestamp":1508434101000,"package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":1,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":24.7,"dimension_unity_code":1,"dimension_thing_code":1},{"server_timestamp":1508434042957,"package_local_timestamp":1508434041000,"package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":1,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":24.7,"dimension_unity_code":1,"dimension_thing_code":1}]`

  * **Python:**
    ```python
      # Library for HTTP requests
      import requests

      # Setting the intervals for the last hour
      toTimestamp = 1508330591;
      fromTimestamp = 1508330591;

      # Sets URL
      url = "http://io.portia.supe.solutions/api/v1/device/Bk4TsimTbj8vt3hww/port/1/sensor/1?from_timestamp=" + fromTimestamp + "&?to_timestamp=" + toTimestamp;
      accessToken = "F894wrfDf344D-Q44fwr"

      # POST with JSON 
      response = requests.get(url, headers={"Authorization", "Bearer " + accessToken})

      # Response
      response.text
    ```

    * **Return:** `[{"server_timestamp":1508434283522,"package_local_timestamp":1508434282000,"package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":1,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":24.7,"dimension_unity_code":1,"dimension_thing_code":1},{"server_timestamp":1508434223402,"package_local_timestamp":1508434222000,"package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":1,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":24.7,"dimension_unity_code":1,"dimension_thing_code":1}]`

  * **Java:**
    ```java
      StringBuilder result = new StringBuilder();

      URL url = new URL("http://io.portia.supe.solutions/api/v1/device/Bk4TsimTbj8vt3hww/port/1/sensor/1/dimension/1/from/1508330521/to/1508330591");

      HttpURLConnection conn = (HttpURLConnection) url.openConnection();
      conn.setRequestMethod("GET");

      BufferedReader rd = new BufferedReader(new InputStreamReader(conn.getInputStream()));

      String line;
      while ((line = rd.readLine()) != null) {
        result.append(line);
      }

      rd.close();

      return result.toString();
    ```

    * **Return:** `[{"server_timestamp":1508271656566,"package_local_timestamp":1508271655,"package_type_code":1,"package_username":"agrosensor","package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":2,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":23.2,"dimension_value_string":null,"dimension_unity_code":1,"dimension_thing_code":1,"dimension_thing_local_id":-1}, {"server_timestamp":1508271656566,"package_local_timestamp":1508271655,"package_type_code":1,"package_username":"agrosensor","package_device_hash":"Bk4TsimTbj8vt3hww","dimension_port_id":2,"dimension_sensor_id":1,"dimension_code":1,"dimension_value":23.2,"dimension_value_string":null,"dimension_unity_code":1,"dimension_thing_code":1,"dimension_thing_local_id":-1}]`
-->

### Get devices

* **URL:** ht&#8203;tp://io.portia.supe.solutions/api/v1/devices/all

* **Method:** `GET`

* **Required HEADER Params:**
  * `access_token=[string]` ['Authorization': Bearer \<access_token\>]

* **Success Response:**

  * **Code:** `200 OK`

    * **Content:** `JSON object`

* **Error Response:**

  * **Code:** `401 Unauthorized`

    * **Troubleshooting:** `Error on token authentication`
<!--
* **Sample Call:**

  * **Javascript:**
    ```javascript
      // Access token to be sent for authentication
      let accessToken = "F894wrfDf344D-Q44fwr";

      // Ajax post request
      $.ajax({

        url: "http://io.portia.supe.solutions/api/v1/devices/all",
        type: "GET",
        dataType: "json",
        
        beforeSend: function(xhr) {
          xhr.setRequestHeader("Authorization", "Bearer " + accessToken);
        },

        success: function(response) {
          console.log(response);
        }

      });
    ```
    * **Return:** `["WR3432-24D22waew4", "R3wrwq32-24FwaeR4", "d3wrwq32r24Fwa566", "4333Arwq3wfw24Fwa"]`

  * **Python:**
    ```python
      # Library for HTTP requests
      import requests

      # Sets URL
      url = "http://io.portia.supe.solutions/api/v1/devices/all"
      accessToken = "F894wrfDf344D-Q44fwr"

      # POST with JSON 
      response = requests.get(url, headers={"Authorization", "Bearer " + accessToken})

      # Response
      response.text
    ```
    * **Return:** `["WR3432-24D22waew4", "R3wrwq32-24FwaeR4", "d3wrwq32r24Fwa566", "4333Arwq3wfw24Fwa"]`

  * **Java:**
    ```java
      StringBuilder result = new StringBuilder();

      URL url = new URL("http://io.portia.supe.solutions/api/v1/devices/all");

      HttpURLConnection conn = (HttpURLConnection) url.openConnection();
      conn.setRequestMethod("GET");

      BufferedReader rd = new BufferedReader(new InputStreamReader(conn.getInputStream()));

      String line;
      while ((line = rd.readLine()) != null) {
        result.append(line);
      }

      rd.close();

      return result.toString();
    ```
    * **Return:** `["WR3432-24D22waew4", "R3wrwq32-24FwaeR4", "d3wrwq32r24Fwa566", "4333Arwq3wfw24Fwa"]`
-->
<!-- ### List users devices/paths

* **URL:**  `http://io.portia.supe.solutions/api/v1/user/<username>/devices`

* **Method:**  `GET`

*  **Required POST Params:**

 * `text=[string]`
 * `similarity=[float]` [between 0 and 1]
 * `ontology=[ontologyID]` [see ontology IDs]
   

* **Success Response:**

  * **Code:** 200 <br />
  * **Content:** JSON object <br />

* **Error Responses:**

  * **Code:** `415 Unsupported Media Type` <br />
  * **Troubleshooting:** Check parameters


  * **Code:**  `404 NOT FOUND`  <br />
  * **Troubleshooting:**  Ontology ID not found

  * **Sample Call:**

  * **Code:** 
    ```javascript
      $.ajax({
        url: "http://ontomatch.lis.ic.unicamp.br/api/rest/resource",
        dataType: "json",
        type : "POST",
        data: { text: "chest pain", similariy: 0.8, ontology:"hfo" },
        success : function(r) {
          console.log(r);
        }
      });
    ```

    * **Return:**  `{"uri":"http://bmi.utah.edu/ontologies/hfontology/C0008031","label":"Chest Pain","similarity":1.0}`

### Based on a given similarity threshold (/api/rest/resources)


* **URL:**    `/api/rest/resource`

* **Method:**  `POST`
  
*  **Required POST Params:**

   * `text=[string]`
   * `n=[float]` [the service will return the **n** most similar entities]
   * `ontology=[ontologyID]` [see ontology IDs]
     

* **Success Response:**

  * **Code:** 200 <br />
  * **Content:** JSON array <br />

 
* **Error Responses:**

  * **Code:** `415 Unsupported Media Type` <br />
    **Troubleshooting:** Check parameters


  * **Code:**  `404 NOT FOUND`  <br />
    **Troubleshooting:**  Ontology ID not found

* **Sample Call:**
  
    * **Code:** 
  ```javascript
    $.ajax({
      url: "http://ontomatch.lis.ic.unicamp.br/api/rest/resources",
      dataType: "json",
      type : "POST",
      data: { text: "chest pain", n: 5, ontology:"hfo" },
      success : function(r) {
        console.log(r);
      }
    });
  ```

    * **Return:**  

    ```json
    [
    {"uri":"http://bmi.utah.edu/ontologies/hfontology/C0008031","label":"Chest Pain","similarity":1.0},
    {"uri":"http://bmi.utah.edu/ontologies/hfontology/C0030193","label":"Pain","similarity":0.7071067690849304},
    {"uri":"http://bmi.utah.edu/ontologies/hfontology/C0000737","label":"Abdominal Pain","similarity":0.5}
    ]
    ``` 
-->