---
layout: layouts/post.njk
title: Primera clase - Un vistazo a NXC
date: 2022-06-21T04:50:51.884Z
---
Not eXactly C, o NXC, es un lenguaje de programacion para Lego Mindstorms NXT diseñado por John Hansen en 2006. Tiene una sintaxis parecida a C y un IDE llamado Bricx Command Center.

# Bricx Command Center

Bricx Command Center esta limitado a computadores que tienen Windows como sistema operativo.

1. Descarga el IDE en <https://sourceforge.net/projects/bricxcc>
2. Descomprime el archivo `test_release20111024.zip`
3. Abre el archivo `BrixcCC.exe`

# Modo de uso

Al abrir el archivo `BrixcCC.exe` 


```
#define SPEED_FWD 75
#define SPEED_REV 60
#define WAIT_TIME 500
#define DEGREES -90

task main(){
     SetSensor(IN_1,SENSOR_TOUCH);
     //Fwd(OUT_A,SPEED_FWD);
     //Wait(WAIT_TIME);
     //OnRev(OUT_A,SPEED_REV);
     until(SENSOR_1 == true);
     RotateMotor(OUT_A,SPEED_FWD,DEGREES);
}
```