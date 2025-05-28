# Constrained Device Application (Connected Devices)

## Lab Module 12 - Semester Project - CDA Components

Be sure to implement all the PIOT-CDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

La implementación del CDA permite ejecutar múltiples instancias de forma paralela, cada una con un ID único, lo que permite su identificación individual por parte del GDA. Cada CDA simula o emula un dispositivo que recoge datos del entorno, como la aceleración en los tres ejes, y los envía periódicamente al GDA. Además, puede recibir instrucciones desde el GDA, como activar un actuador en caso de detectar una vibración excesiva. La pantalla LED se utiliza para mostrar alertas visuales al usuario cuando se detectan estas condiciones críticas.

How does your implementation work?

Para lograr la ejecución simultánea, el CDA puede lanzarse con un parámetro que especifica su ID (--id <nuevo_id>). Si no se proporciona, usa el ID por defecto del archivo Piot.config. Esta ID se incluye en todos los mensajes enviados al GDA, permitiendo su identificación. El CDA obtiene datos de aceleración de los ejes x, y, z a través de la IMU emulada o simulada, calcula la magnitud total de la aceleración y la envía al GDA. En caso de recibir una instrucción de activación del actuador (por vibración crítica), el CDA muestra una alerta en la pantalla LED. Las instancias adicionales del CDA, que no pueden usar SenseHAT directamente, funcionan con una simulación del hardware, pero siguen siendo funcionales en cuanto a generación de datos y respuesta a mensajes.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/Sergiooo0/PIC-python-components/tree/labmodule12


### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- Los tests creados en la carpeta /tests/partFinal son los que se han ejecutado.
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

EOF.
