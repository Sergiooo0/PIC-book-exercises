# Gateway Device Application (Connected Devices)

## Lab Module 02

Be sure to implement all the PIOT-GDA-* issues.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

How does your implementation work?

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/Sergiooo0/PIC-java-components/tree/labmodule2


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

- 
- 
- 

What does your implementation do? 
La implementación realizada hace que el Gestor de rendimiento del sistema de la aplicación de puerta de enlace (GDA)
 muestre por consola de depuración la cantidad de CPU y Memoria RAM que está usando el dispositivo.

How does your implementation work?
Para alcanzar dicho funcionamiento se desarrolló una clase abstracta de la que heredan
dos subclases encargadas, respectivamente, de gestionar la CPU y la RAM.
Posteriormmente, la clase SystemPerformanceManager llama con un scheduled executor de un thread los 
métodos principales de las dos subclases e imprime por consola de depuración los resultados.



EOF.
