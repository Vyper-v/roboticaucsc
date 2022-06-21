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

## Modo de uso

1. Al abrir el archivo `BrixcCC.exe`
2. Conectar por usb el robot NXT
3. Seleccionar puerto `usb`
4. Seleccionar tipo de brick `NXT`
5. Seleccionar Firmware `Standard`
6. Crear un archivo nuevo con `Ctrl+N`
7. Compilar con `F5`

## Primer Hola Mundo
Presiona `Ctrl+N` para crear un nuevo archivo y escribe lo siguiente:

```c
task main() {
   OnFwd(OUT_A,50)
   return 0;
}
```

###  `OnFwd(byte outputs,char pwr)`
Hace funcionar los motores hacia adelante.

Configure las salidas para invertir la dirección y enciéndalas.

La función `OnFwd` recibe como parametros:

 - `outputs` : Puerto de salida. Puedes encontrar los puertos disponibles [aqui](http://bricxcc.sourceforge.net/nbc/nxcdoc/nxcapi/group___output_port_constants.html)
 - `pwr` : Potencia a la que el de salida tendrá, con un rango de `0 - 100`. Puede ser negativa para tener dirección reversa.

###  `OnRev(byte outputs,char pwr)`
Hace funcionar los motores hacia atrás.


Configure las salidas para invertir la dirección y enciéndalas.

La función `OnRev` recibe como parametros:

 - `outputs` : Puerto de salida. Puedes encontrar los puertos disponibles [aqui](http://bricxcc.sourceforge.net/nbc/nxcdoc/nxcapi/group___output_port_constants.html)
 - `pwr` : Potencia a la que el de salida tendrá, con un rango de `0 - 100`. Puede ser negativa para tener dirección reversa.

### Ejemplo
```c
task main() {
   OnFwd(OUT_A,50)
   return 0;
}
```

```c
#define SPEED_FWD 75
#define SPEED_REV 60
#define WAIT_TIME 500
#define DEGREES -90

task main(){
     SetSensor(IN_1,SENSOR_TOUCH);
     //OnFwd(OUT_A,SPEED_FWD);
     //Wait(WAIT_TIME);
     //OnRev(OUT_A,SPEED_REV);
     until(SENSOR_1 == true);
     RotateMotor(OUT_A,SPEED_FWD,DEGREES);
}
```