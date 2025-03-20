# Constrained Device Application (Connected Devices)

## Lab Module 02

Be sure to implement all the PIOT-CDA-* issues (requirements).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Mi implementación desarrolla el sistema que maneja el rendimiento del dispositivo de recursos limitados. Permite obtener el porcentaje de CPU y Memoria utilizadas por el dispositivo. Este manager se puede iniciar y parar.

How does your implementation work?
Se elaboró una clase abstracta de la que heredan el manager de la CPU y el de la memoria. Se implementan los métodos abstractos (getTelemetry) de las dos clases para obtener el porcentaje de CPU y Memoria utilizando la librería psutil. Dentro de la clase SystemPerformanceManager, se crea un scheduler que reportará el porcentaje de CPU y Memoria de manera periódica y en paralelo utilizando las dos clases anteriormente mencionadas. El tiempo entre reporte y reporte viene definido por la variable pollRate. Finalmente, el SystemPerformanceManager se encapsula en la clase principal del CDA (ConstrainedDeviceApp).

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/Sergiooo0/PIC-python-components/tree/labmodule2

### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- /common/ConfigUtilTest.
- /app/ConstrainedDeviceAppTest.
- /system/SystemPerformanceManagerTest.
- /system/SystemCpuUtilTaskTest
- /system/SystemMemUtilTaskTest
- 

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- /app/ConstrainedDeviceAppTest
- /system/SystemPerformanceManagerTest
- 
EOF.
