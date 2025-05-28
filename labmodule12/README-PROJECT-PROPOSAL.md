# Lab Module 12 - Semester Project Proposal

## Description

Describe your idea in 1 paragraph (at least 2 or 3 sentences).

La idea del proyecto fue permitir que múltiples instancias del CDA se ejecuten de forma simultánea, cada una con un identificador único, y que el GDA las gestione sin confusión. Cada CDA recoge datos de sensores (temperatura, presión, humedad, aceleración) y envía la información al GDA, que los almacena en la nube. Además, el sistema detecta vibraciones críticas a partir de la aceleración, lo que permite actuar rápidamente para prevenir fallos.

## What - The Problem 

What problem are you trying to solve and why does it matter? Write 1 to 2 paragraphs in response.

El problema principal era que el sistema original solo permitía un único CDA en funcionamiento. Esto impedía escalar el sistema a múltiples dispositivos, ya que al compartir ID, el GDA no podía distinguir entre ellos. Además, no se aprovechaban todos los sensores disponibles para prevenir fallos mecánicos.

Resolver esto es importante porque en escenarios reales se requiere que varios dispositivos trabajen juntos y de forma coordinada. También permite aprovechar sensores como la IMU para detectar problemas antes de que se produzcan daños graves, reduciendo tiempos de parada y costos.

## Why - Who Cares? 

Why do you care about this particular problem? Write 1 to 2 paragraphs in response.

Este problema es relevante porque limita el uso del sistema en aplicaciones reales donde se necesita escalar a múltiples sensores y dispositivos. Si solo se permite un CDA, el valor práctico del sistema es muy bajo.

Además, integrar la detección de fallos por vibraciones mejora la capacidad del sistema para alertar sobre situaciones críticas, lo cual es esencial en entornos industriales donde el mantenimiento predictivo puede ahorrar tiempo y dinero.

## How - Expected Technical Approach

How do you plan to tackle this problem technically?

Include a high-level design diagram depicting your planned technical approach - it does not need to be final, but it must include the CDA, GDA, and cloud services you plan to use, as well as the protocol(s) you will use for communicating between the devices and the cloud.

Write 1 to 2 paragraphs describing your diagram.

El problema se resuelve permitiendo que cada CDA se lance con un ID único, que se pasa como parámetro. El GDA procesa los datos de todos los CDAs y los publica en la nube usando topics distintos por cada dispositivo. El GDA también analiza los datos de aceleración para detectar vibraciones anormales y, en ese caso, envía una instrucción al CDA correspondiente para activar una alerta en su pantalla LED.

La comunicación entre los dispositivos se realiza con el protocolo MQTT. El CDA se comunica con el GDA mediante MQTT y este, a su vez, publica los datos en la nube (Ubidots), también vía MQTT. El cloud puede enviar mensajes de vuelta al GDA para activar actuadores en los CDA según ciertas condiciones.

[Diagram Placeholder]

CDA → (MQTT) → GDA → (MQTT) → Cloud

Cloud → (MQTT) → GDA → (MQTT) → CDA

Este diseño permite un flujo de datos constante y controlado entre los sensores, el gateway y el servidor cloud, con separación por dispositivo gracias al uso de IDs y topics únicos.

## Results - Expected Outcomes 

If your project is successful, what outcome do you expect (e.g. what will happen if everything works)? Write 1 to 2 paragraphs describing your expected outcomes.

Si el proyecto funciona correctamente, el GDA podrá recibir datos de múltiples CDAs, identificar correctamente el origen de cada mensaje y almacenarlos en la nube sin mezclar datos. También podrá reaccionar ante valores críticos de aceleración enviando comandos de activación a los dispositivos correspondientes.

Esto dará como resultado un sistema escalable y funcional que permite monitoreo ambiental y de vibración en tiempo real, y que puede ser utilizado en entornos reales para mantenimiento preventivo y gestión inteligente de dispositivos conectados.

EOF.
