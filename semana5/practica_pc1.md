# Cuestionario teórico — Semanas 1, 2 y 3

---

# Semana 1 — Introducción a los Sistemas Operativos

## 1. ¿Qué es un recurso en sistemas operativos?
**Respuesta:**  
Un recurso es cualquier elemento que un programa necesita para poder funcionar. Los principales recursos son la CPU, la memoria RAM, el disco y los dispositivos de entrada y salida como teclado, mouse, pantalla e impresora.

---

## 2. ¿Qué es un proceso?
**Respuesta:**  
Un proceso es un programa en ejecución. A diferencia de un programa guardado en disco, el proceso ya está funcionando y usando recursos del sistema.

---

## 3. ¿Cuál es la diferencia entre programa y proceso?
**Respuesta:**  
Un programa es un conjunto de instrucciones guardadas, es decir, algo estático. Un proceso es ese programa cuando ya se está ejecutando, por eso es algo dinámico.

---

## 4. ¿Qué es un sistema operativo?
**Respuesta:**  
El sistema operativo es el software encargado de administrar los recursos de la computadora y permitir que los programas se ejecuten correctamente.

---

## 5. ¿Cuál es la función principal del sistema operativo?
**Respuesta:**  
La función principal del sistema operativo es controlar, organizar y repartir los recursos de la computadora entre los procesos que los necesitan.

---

## 6. ¿Cómo se relacionan proceso, recurso y sistema operativo?
**Respuesta:**  
El proceso solicita recursos para funcionar, los recursos son los elementos disponibles del sistema, y el sistema operativo decide cómo, cuándo y cuánto de esos recursos se asigna a cada proceso.

---

## 7. ¿Por qué se dice que el sistema operativo es un administrador?
**Respuesta:**  
Porque organiza el uso de la CPU, la memoria, el disco y los dispositivos, evitando desorden y conflictos entre varios procesos al mismo tiempo.

---

## 8. ¿Qué es el hardware?
**Respuesta:**  
El hardware es la parte física de la computadora. Incluye componentes como el procesador, la RAM, el disco duro, el monitor y el teclado.

---

## 9. ¿Por qué los recursos se consideran limitados?
**Respuesta:**  
Porque la computadora no tiene capacidad infinita. La CPU solo puede atender ciertas tareas por vez, la RAM tiene un tamaño limitado y los dispositivos también deben compartirse entre varios procesos.

---

## 10. Da un ejemplo de cómo actúa el sistema operativo al abrir varias aplicaciones.
**Respuesta:**  
Si se abren Chrome, Word y Spotify al mismo tiempo, los tres procesos quieren usar CPU, RAM y disco. El sistema operativo reparte esos recursos para que todos funcionen sin interferirse.

---

# Semana 2 — Funcionamiento del sistema de cómputo

Basado en tu material de semana 2 sobre sistema de cómputo, bootstrap, interrupciones, DMA, memoria, almacenamiento y funciones del SO. :contentReference

## 1. ¿Qué es un sistema de cómputo?
**Respuesta:**  
Es el conjunto de hardware y software que permite procesar información. Sus componentes principales incluyen CPU, memoria, dispositivos de entrada/salida y almacenamiento. 

---

## 2. ¿Cuál es el flujo básico de funcionamiento de un sistema de cómputo?
**Respuesta:**  
El flujo básico es: entrada, procesamiento, salida y almacenamiento. Primero ingresa información, luego la CPU la procesa, después se muestra un resultado y finalmente puede guardarse. 

---

## 3. ¿Qué es el bootstrap?
**Respuesta:**  
El bootstrap es el proceso de arranque de la computadora mediante el cual se inicia el sistema operativo. Comienza cuando se enciende el equipo y termina cuando el sistema operativo toma el control. 

---

## 4. ¿Qué ocurre cuando se enciende una computadora?
**Respuesta:**  
Se enciende el equipo, se ejecuta BIOS o UEFI, se busca el bootloader, se carga el sistema operativo en memoria y finalmente el sistema operativo toma el control del sistema. 

---

## 5. ¿Qué es la entrada/salida (E/S)?
**Respuesta:**  
La E/S es la forma en que la computadora se comunica con el exterior mediante dispositivos. La entrada introduce datos al sistema y la salida muestra o entrega resultados. 

---

## 6. ¿Qué es una interrupción?
**Respuesta:**  
Una interrupción es una señal que un dispositivo envía al procesador para avisarle que necesita atención. Gracias a esto, la CPU puede atender eventos importantes sin estar preguntando constantemente a cada dispositivo. 

---

## 7. ¿Por qué son importantes las interrupciones?
**Respuesta:**  
Son importantes porque hacen más eficiente la comunicación entre hardware y CPU. En vez de revisar continuamente si ocurrió algo, la CPU es avisada justo cuando un dispositivo necesita atención. 

---

## 8. ¿Qué es DMA?
**Respuesta:**  
DMA, o acceso directo a memoria, es un mecanismo que permite transferir datos entre dispositivos y memoria sin que la CPU intervenga en cada paso del proceso. 

---

## 9. ¿Qué ventaja tiene DMA frente a una transferencia normal?
**Respuesta:**  
Reduce la carga del procesador y mejora la velocidad de transferencia, porque la CPU no tiene que encargarse de mover cada parte de los datos manualmente. 

---

## 10. ¿Qué diferencia hay entre RAM y disco?
**Respuesta:**  
La RAM es la memoria principal donde se cargan programas y sistema operativo para ejecutarse; es rápida y volátil. El disco es almacenamiento más permanente y conserva la información aunque la computadora se apague. 

---

# Semana 3 — Estructura del sistema operativo

Basado en tu material de semana 3 sobre tipos de SO, componentes, kernel, shell, bootstrap y runlevels.

## 1. ¿Qué es un sistema operativo según su estructura general?
**Respuesta:**  
Es el programa principal que administra la computadora y sirve de puente entre el usuario, los programas y el hardware. 

---

## 2. ¿Cuáles son algunos tipos de sistemas operativos?
**Respuesta:**  
Entre los tipos principales están los sistemas operativos de mainframe, de servidor, de escritorio, de tiempo real y distribuidos. 

---

## 3. ¿Qué es un sistema operativo de tiempo real?
**Respuesta:**  
Es un sistema operativo diseñado para responder dentro de un tiempo exacto o muy controlado. Se usa en situaciones donde responder tarde puede causar fallos graves. 

---

## 4. ¿Qué es un sistema operativo distribuido?
**Respuesta:**  
Es un sistema formado por varias máquinas o procesadores, pero que se presenta al usuario como si fuera un solo sistema. 
---

## 5. ¿Cuáles son los componentes principales de un sistema operativo?
**Respuesta:**  
Entre sus componentes están la gestión de procesos, gestión de memoria, gestión de archivos, gestión de dispositivos de entrada/salida, el kernel y la interfaz de usuario o shell.

---

## 6. ¿Qué es el kernel?
**Respuesta:**  
El kernel es el núcleo del sistema operativo. Es la parte central que controla procesos, memoria, hardware y operaciones de entrada/salida. 

---

## 7. ¿Por qué el kernel se considera la parte más importante del sistema operativo?
**Respuesta:**  
Porque realiza el control interno del sistema y permite el acceso seguro al hardware. Sin el kernel, los programas no podrían usar correctamente los recursos de la computadora. 

---

## 8. ¿Qué es el shell?
**Respuesta:**  
El shell es la interfaz que permite al usuario comunicarse con el sistema operativo. Puede ser de texto o gráfica. 

---

## 9. ¿Cuál es la diferencia entre CLI y GUI?
**Respuesta:**  
CLI es una interfaz de línea de comandos donde el usuario escribe instrucciones. GUI es una interfaz gráfica donde el usuario interactúa con ventanas, botones, íconos y menús.

---

## 10. ¿Qué son los runlevels?
**Respuesta:**  
Los runlevels son niveles o modos de ejecución del sistema, especialmente en Linux, que indican cómo arranca o en qué modo funciona, por ejemplo apagado, monousuario, multiusuario o modo gráfico. 

---
