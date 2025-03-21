# Gateway Device Application (Connected Devices)

## Lab Module 05

Be sure to implement all the PIOT-GDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Mi implementación notifica el porcentaje de uso de disco, cpu y memoria usada por el dispositivo. También, tiene la capacidad de suscribirse al topic de las mediciones del CDA, obtener los JSON de las mediciones y transformarlos a un formato adecuado para procesarlos.

How does your implementation work?
Para tratar la información del rendimiento del sistema, de los sensores y actuadores del CDA, se crearon clases respectivas para almacenar en memoria RAM las últimas mediciones. Además, se añade una nueva clase (SystemDiskUtilTask) para obtener el porcentaje de espacio usado. Para transformar los datos en formato JSON provenientes del CDA en sus respectivas clases, se ha creado una clase DataUtil. Esta DataUtil, se utiliza en la clase RedisPersistenceAdapter, encargada de conectarse con el servidor Redis y suscribirse al topic donde el CDA publica las mediciones. Para integrar el funcionamiento de la clase redis y la encargada de obtener el rendimiento del sistema (disco , cpu y memoria usados), se encapsulan en la clase DeviceDataManager, usada directamente por el GDA.

En el PiotConfig se ga puesto a true la propiedad enableSystemPerformance para que los test de GatewayDeviceManager y DeviceDataManager debugen el porcentae de uso de disco, cpu y memoria usada.
También en el SystemPerformanceManager, se ha mejorada la finalización del scheduled executor para garantizar que el thread se detenga.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/Sergiooo0/PIC-java-components/tree/labmodule05


### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- ./data/ActuatorDataTest
- ./data/SensorDataTest
- ./data/SystemPerformanceDataTest
- ./data/SystemStateDataTest
- /data/DataUtilTest
- 

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- DeviceDataManagerNoCommsTest
- GatewayDeviceManagerTest
- part01/integration/system/SystemPerformanceManagerTest
- /data/DataIntegrationTest
Para los siguientes tests, se debe ejecutar en consola el comando redis-server previamente.
- /connection/PersistenceClientAdapterTest 
- /app/DeviceDataManagerNoCommsTest 
- part01/integration/app/GatewayDeviceAppTest 

Para ver el funcionamiento completo de la implementación, se debe de ejecutar en primer lugar el comando redis-server, luego ejecutar el ConstrainedDeviceApp.py y, mientras este último está ejecutándose, ejecutar el test GatewayDeviceAppTest. Así se podrá comprobar la comunicación a través de Redis.

EOF.
