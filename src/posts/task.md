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
## Sensor de luz
```c
#define UMBRAL 30
#define VELOCIDAD 75

task main(){
 SetSensorLight(IN_2);
 OnFwd(OUT_AC,VELOCIDAD);
 while(true){
  if(Sensor(IN_2) < UMBRAL)
  {
    OnRev(OUT_C,VELOCIDAD);
    Wait(500);
    until(Sensor(IN_2) >= UMBRAL);
    OnFwd(OUT_AC,VELOCIDAD);
  }
 }
}