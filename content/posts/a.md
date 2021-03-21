---
title: "Optointerruptor"
date: 2020-01-01T11:50:08-06:00
draft: true
toc: false
images:
tags:
  - untagged
---

Ya vimos como leer sensores digitales, ahora haremos una práctica bastante simple que será la base para hacer muchos proyectos, el cual es saber manejar y leer los datos que nos manda un optointerruptor, **estos se usan en las cajas del supermercado en la banda transportadora que al bloquear la señal se detiene pero si es una señal limpia avanza la banda o también para tener un conteo se personas u objetos**, abajo se muestra el código, material y explicación de la práctica.

## Material 
> - Arduino
> - LED 5mm 
> - Resistencias de 220 Ohm's
> - Diodo emisor de 5mm IR
> - Resistencia de 10 kOhm's
> - Fototransistor 
> - Protoboard
> - Jumpers

## Circuito
![circuito](https://www.abc.com.py/resizer/nKvQnZP_HuQ0MBkXukxSVfSXhTE=/fit-in/770x495/smart/arc-anglerfish-arc2-prod-abccolor.s3.amazonaws.com/public/BGNZLHYCWVDOXLJSDEGHWC52OM.jpg)

## Código
```c
#define LED 2
#define Opto 3

int Opto_lee;

void setup() {
  pinMode(LED, OUTPUT);
  pinMode(Opto, INPUT);
}
void loop() {
  Opto_lee = digitalRead(Opto);
   if (Opto_lee == 1) {
     digitalWrite(LED, HIGH);
   } 
   else {
    digitalWrite(LED, LOW);
   }
}
```

## Explicación
Muy bien, el funcionamiento es muy simple, definimos dos pines, el **led** y el **optointerruptor** al led lo ponemos como ``OUTPUT`` y para el optointerruptor lo ponemos como ``INPUT``, también creamos una variable del tipo entero que almacenará el valor enviado por el fototransistor al **pin 3**, después en el ``loop()`` hacemos nuestro programa de ejecución, usando ``digitalRead()`` leemos el valor del pin 3 y lo almacenamos en la variable ``Opto_lee``, después con un ``if()`` hacemos una comparación lógica, si el valor digital es **1 enciende el led** usando ``digitalWrite()``, en caso de que sea un valor **distinto a 1** permanecerá apagado. Como vimos este es el funcionamiento de un optointerruptor que nos servirá para hacer muchos proyectos, desde una banda transportadora hasta un seguidor de líneas.

