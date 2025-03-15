# Constrained Device Application (Connected Devices)

## Lab Module 04

Be sure to implement all the PIOT-CDA-* issues (requirements).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

How does your implementation work?
Tuve que cambiar en .venv/lib/python3.12/site-packages/pisense/anim.py" la línea 167:
    width, height = draw.textbbox(text, f, spacing=1)
Y lo sustituí por:
    bbox = draw.textbbox((0, 0), text, font=f, spacing=1)
    width, height = bbox[2] - bbox[0], bbox[3] - bbox[1]

Debido a que en la librería Pillow (PIL) version 10.0+, textsize() se sustituyó por textbbox(), pero pinsense usa el anterior.


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

- 
- 
- 

EOF.
