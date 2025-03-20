# Constrained Device Application (Connected Devices)

## Lab Module 03

Be sure to implement all the PIOT-CDA-* issues (requirements).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do?
Mi implementación simula los sensores de humedad, presión y temperatura, además de los actuadores de climatización y ventilación y el humidificador. También se añaden mecanismos para almacenar temporalmente los datos, manejar el procesamiento de estos datos y dirigir las solicitudes al destino apropiado. En este caso, en base a los datos del sensor de temperatura, se activa el sistema de climatización y ventilación con un valor determinado (entre 18 y 20) o se desactiva.

How does your implementation work?
En primer lugar, se crean clases para almacenar los datos de los sensores, actuadores y rendimiento del sistema. Creamos los sensores de humedad, presión y temperatura para simular su comportamiento y crear valores randomizados. Creamos también el sistema de climatización y ventilación y el humidificador. A estos actuadores se les simula los valores y el encendido/apagado mediante comandos. Para controlarlos, se añade un manager para los sensores y otro para los actuadores. El manager de los sensores tiene un scheduler para obtener los datos simulados de los sensores en segundo planom (orientado ya a obtenerlos emulados en los siguientes módulos). La información generada por los sensores, actuadores y el SystemPerformanceManager del módulo anterior se almacenan en nuevas clases respectivamente. Finalmente, el DeviceDataManager, encapsulará los tres managers anteriores para extraer sus datos, procesarlos y enviarlos al destino adecuado. En lugar de encapsular los managers en la aplicación principal, se encapsula este DeviceDataManager en el CDA (ConstrainedDeviceApp).

Se ha añadido que los sensores y actuadores simulados se instancien si la variable eneableSimulator en el archivo PiotConfig.props es True. Esto permitirá una manera más rápida y simple de desactivar la simulación cuando se tenga la capacidad de emular los dispositivos.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/Sergiooo0/PIC-python-components/tree/labModule03

### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- /data/ActuatorDataTest
- /data/SensorDataTest
- /data/SystemPerformanceDataTest
- /sim/HumiditySensorSimTaskTest
- /sim/PressureSensorSimTaskTest
- /sim/TemperatureSensorSimTaskTest
- /sim/HumidifierActuatorSimTaskTest
- /sim/HvacActuatorSimTaskTest

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- system/SensorAdapterManagerTest
- system/ActuatorAdapterManagerTest
- /app/DeviceDataManagerNoCommsTest
- part01/app/ConstrainedDeviceAppTest

EOF.
