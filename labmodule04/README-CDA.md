# Constrained Device Application (Connected Devices)

## Lab Module 04

Be sure to implement all the PIOT-CDA-* issues (requirements).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Sustituye los sensores y actuadores simulador por emulados como si el sistema contara con un dispositivo real. Además, se puede mostrar la rasberry pi emulada y varia los valores de los sensores. Se muestra por la pantalla de la placa un mensaje cuando se encienden o apagan los actuadores y se muestra los valores de los actuadores.

How does your implementation work?
Para la emulación se usa SenseHat, que además de emular, permite desplegar una interfaz para graficar la placa y alterar los valores de los sensores. Por cada sensor del módulo anterior, se crea una nueva clase que haga lo mismo pero en lugar de obtener datos de sensores simulados, obtendrá datos de SenseHat. Lo mismo para los actuadores, pero en lugar de imprimir por pantalla los cambios de estado, se muestran en la pantalla de SenseHat. Finalmente, se habilitan los SensorManager y ActuatorManager para que administren los sensores y actuadores de la placa SenseHat en caso de que esté configurado en el archivo PiotConfig.props como True.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/Sergiooo0/PIC-python-components/tree/lab04


### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- emulated/SenseHatEmulatorQuickTest.py
- emulated/HumidityEmulatorTaskTest.py
- emulated/PressureEmulatorTaskTest.py
- emulated/TemperatureEmulatorTaskTest.py
- emulated/HumidifierEmulatorTaskTest.py
- emulated/HvacEmulatorTaskTest.py
- emulated/LedDisplayEmulatorTaskTest.py
- emulated/SensorEmulatorManagerTest.py
- emulated/ActuatorEmulatorManagerTest.py

EOF.
