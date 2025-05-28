# Gateway Device Application (Connected Devices)

## Lab Module 12 - Semester Project - GDA Components

Be sure to implement all the PIOT-GDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

La implementación del GDA permite gestionar múltiples dispositivos CDA simultáneamente, identificándolos de forma única y manteniendo sus datos completamente separados. Para ello, el GDA ahora genera un topic distinto en el cloud para cada CDA, basándose en su identificador individual. De esta forma, se evita la mezcla de información entre dispositivos y se garantiza una trazabilidad clara de los datos generados por cada uno. Además, el GDA es responsable de almacenar estos datos en el cloud y de tomar decisiones en función de ciertos valores, como la detección de vibraciones críticas, que podrían indicar una avería en el sistema.

How does your implementation work?

El GDA escucha y recibe los mensajes enviados por cada CDA, identificándolos a través del ID que incluyen en el payload (locationID en el formato JSON). Cuando se detecta un nuevo mensaje, el GDA construye dinámicamente un topic específico en función del locationID del dispositivo remitente y publica los datos en la nube bajo dicho topic. Esto permite mantener los datos separados por origen. Asimismo, el GDA analiza en tiempo real la magnitud de la aceleración recibida desde cada CDA (obtenida por estos a partir de la IMU). Si la magnitud supera un umbral predefinido, el GDA envía una instrucción al CDA correspondiente para que active su actuador, indicando una vibración anormal. Esto convierte al GDA en un componente central en la lógica de supervisión y respuesta del sistema.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/Sergiooo0/PIC-java-components/tree/labmodule12

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

- part04/CloudCLientConnectorTest
- No hay tests específicos para esta parte. Lo que se ha hecho es ejecutar distintos CDAs y el GDA, comprobando que cada CDA envía sus datos al GDA y que este los almacena en el cloud con el topic correspondiente a su ID.
- 

EOF.
