# Constrained Device Application (Connected Devices)

## Lab Module 10

Be sure to implement all the PIOT-CDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

Ahora el cliente MQTT cuenta con métodos de encriptación para ser más segura la conexión con el broker. Además, se suscribe a un topic para las actuadores y actualizada sus actuadores en base a lo que mande el GDA en ese topic. En este caso, se hace especificamente con el humidificador.

How does your implementation work?

La encripatación se hace aprovechando la función tls_set del mqttCLient y con un archivo de certificado, en base al cual se cifran los datos. Para los actuadores, el mqttClient recibe la información del topic al que se suscribe, el deviceDataManager "escucha" el json recibido; con DataUtils lo transforma de nuevo a un ActuatorData y usa la clase ActuatorDataManager para modificar el humificador acorde con lo que dicte el GDA.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: 


### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- 
- 
- 

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- MqttClientConnectorTest
- DeviceDataManagerCallbackTest 
- DeviceDataManagerIntegrationTest
- DeviceDataManagerWithCommosTest
- DeviceDataManagerWithMqttClientOnly

EOF.
