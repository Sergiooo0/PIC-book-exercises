# Constrained Device Application (Connected Devices)

## Lab Module 05

Be sure to implement all the PIOT-CDA-* issues (requirements).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do?
En primer lugar, se obtiene además del porcentaje de CPU y Memoria RAM usados por el dispositivo, ahora también se obtiene el porcentaje de espacio usado. Mi implementación tiene la capacidad de coger estos datos junto los de los sensores y actuadores y transformalos en formato JSON; además de hacer el proceso contrario. En el caso de los datos de los sensores, la CDA publica el JSON en un topic del servidor Redis de forma periódica, con el objetivo de que los reciba el GDA (Gateway Device Application) y los procese.

How does your implementation work?
Por un lado, una nueva clase SystemDiskUtilTask se encarga de devolver el porcentaje de espacio usado. Por otro lado, se ha creado una clase DataUtil que con la ayuda de la librería json, implementa funciones con la capacidad de transformar los datos de los sensores, actuadores y rendimiento del sistema en formato JSON, y viciversa. Estas funciones se encargan de transformar los datos en formato JSON y de devolverlos en un formato adecuado para ser publicado en un topic del servidor Redis. Para la publicación, se crea una clase RedisPersistenceAdapter encargada de establecer la conexión con el servidor Redis, transformar los datos en formato JSON con DataUtil y publicarlos en un topic determinado. Finalmente, es el DeviceDataManager, el encargado de utilizar la clase anterior para cada vez que obtiene los datos de un sensor, publicarlo.



### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/Sergiooo0/PIC-python-components/tree/labmodule05


### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- /data/DataUtilTest
- 
- 

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- part01/integration/SystemPerformanceManagerTest
- /data/DataIntegrationTest
- part02/integration/connection/RedisClientAdapterTest (antes de ejecutar este, se debe ejecutar el comando redis-server en terminal)

EOF.
