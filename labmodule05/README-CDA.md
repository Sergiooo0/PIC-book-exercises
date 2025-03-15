# Constrained Device Application (Connected Devices)

## Lab Module 05

Be sure to implement all the PIOT-CDA-* issues (requirements).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do?
He añadido la parte voluntario de que devuelva el porcentaje de disco usado

Por ahora Redis almacena un dato por el sensor de humedad, uno para el de temperatura y otro del sensor de presión. Cada vez que le llega uno nuevo de estos, actualiza el anterior.

How does your implementation work?
Una nueva clase SystemDiskUtilTask se encarga de devolver el porcentaje de espacio usado en la carpeta src.

No están hecho los opcionales del lab 05

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

- part02/integration/connection/RedisClientAdapterTest
- 
- 

EOF.
