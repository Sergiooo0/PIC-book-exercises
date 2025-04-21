# Gateway Device Application (Connected Devices)

## Lab Module 10

Be sure to implement all the PIOT-GDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Mi implementación recibe de manera asíncrona la infromación procedente del CDA y procesa de manera adecuada. Se centra principalmente en los sensores de humedad. Si el valor de estos sensores se sale de un rango normal durante un tiempo determinado, activa los humificadores del CDA

How does your implementation work?

Para que la comunicación funcione de manera asíncrona, se usa MqttAsyncClient, en lugar del MqttClient normal y se adapta la clase MqttClientConnector; además de añadirle la posibilidad de usar encripatación en la comunicación. También, se añaden clases que implementan IMqttMessageListener para que actúen de listenners en las suscripciones. Estas comprueban que el mensaje sea correcto y se lo mandan a la función que corresponda de del DeviceDataManager. En el caso de sensores de humedad del CDA, el DeviceDataManager comprobará si el valor de sale de un rango o no. Dependiendo del caso, mediante la instancia de la clase MqttClientConnect enviará un ActuatorData con la información (comando de apagar o encender y el valor) de el estado en el que debe de estar el humidificador del CDA.

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
