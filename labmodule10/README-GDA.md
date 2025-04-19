# Gateway Device Application (Connected Devices)

## Lab Module 10

Be sure to implement all the PIOT-GDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Mi implementación recibe de manera asíncrona la infromación procedente del CDA y procesa de manera adecuada. Se centra principalmente en los sensores de humedad. Si el valor de estos sensores se sale de un rango normal durante un tiempo determinado, activa los humificadores del CDA

How does your implementation work?

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

-DeviceDataManagerWithCommsTest

- Ejecutar la aplicación del GDA y del CDA e interactuar con el slider de humedad de SenseHat. Deberíamos ver eventos de actuador.
Tanto el GDA como el CDA usan redis para almacenar datos. Para que no de error, dos opciones:

O poner enableRedis a false en el piotCOnfig de python y a false el enablePersistenceClient en el piotConfig de java.

O ejecutar redis-server en terminal.
- 

EOF.
