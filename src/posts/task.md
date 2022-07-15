---
layout: layouts/post.njk
title: Task
date: 2022-07-15T19:46:05.641Z
---
## Sensor ultrasonico
```c
#define VELOCIDAD_BUSQUEDA
#define VELOCIDAD 75
#define LIMITE 60

task main(){
SetSensorLowSpeed(IN_2);
while(true){
OnFwd(OUT_AC,VELOCIDAD_BUSQUEDA);
until(SensorUS(IN_2) < LIMITE);
RotateMotor(OUT_A,VELOCIDAD,-720);
}
}
```