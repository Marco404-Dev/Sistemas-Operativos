# Resumen de las semanas 1, 2 y 3 — Sistemas Operativos

Este resumen está pensado para estudiar teoría para la **PC1**, con los conceptos clave y sus definiciones.

---

# 1. Idea general de las 3 semanas

Las tres semanas se conectan así:

- **Semana 1:** aprendes qué administra el sistema operativo.
- **Semana 2:** aprendes cómo funciona la computadora al arrancar y cómo se comunica con dispositivos y memoria.
- **Semana 3:** aprendes cómo está estructurado el sistema operativo internamente.

En otras palabras:

- primero entiendes **los conceptos básicos**
- luego entiendes **cómo funciona el sistema**
- finalmente entiendes **sus partes principales**

---

# 2. Semana 1 — Introducción a los sistemas operativos

## 2.1. Recurso
Un **recurso** es cualquier elemento que un programa necesita para funcionar.

### Ejemplos
- CPU
- memoria RAM
- disco
- teclado
- mouse
- pantalla
- impresora

---

## 2.2. Programa
Un **programa** es un conjunto de instrucciones guardadas.  
Todavía no se está ejecutando.

### Ejemplo
Google Chrome instalado en tu computadora.

---

## 2.3. Proceso
Un **proceso** es un **programa en ejecución**.

### Ejemplo
Google Chrome abierto y funcionando en este momento.

---

## 2.4. Diferencia entre programa y proceso

- **Programa** = instrucciones guardadas
- **Proceso** = programa que ya se está ejecutando

---

## 2.5. Sistema operativo
El **sistema operativo** es el software encargado de **administrar los recursos** de la computadora y permitir que los programas funcionen correctamente.

### Idea importante
El sistema operativo:
- no es hardware
- no es un proceso cualquiera
- es el software que controla y organiza el uso de los recursos

---

## 2.6. Relación entre proceso, recurso y sistema operativo

La relación es esta:

- el **proceso** solicita recursos
- los **recursos** son limitados
- el **sistema operativo** decide cómo repartirlos

### Ejemplo
Si tienes abiertos:
- Chrome
- Word
- Spotify

los tres son procesos que quieren usar:
- CPU
- RAM
- disco

El sistema operativo se encarga de repartir esos recursos.

---

## 2.7. Hardware
El **hardware** es la parte física de la computadora.

### Ejemplos
- procesador
- memoria RAM
- disco duro
- teclado
- monitor

---

# 3. Semana 2 — Funcionamiento del sistema de cómputo

## 3.1. Sistema de cómputo
Un **sistema de cómputo** es el conjunto de **hardware y software** que permite procesar información. :contentReference[oaicite:0]{index=0}

---

## 3.2. Flujo básico del sistema
El flujo básico es:

**entrada → procesamiento → salida → almacenamiento** :contentReference[oaicite:1]{index=1}

### Explicación
- **Entrada:** información que entra a la computadora
- **Procesamiento:** trabajo que realiza la CPU
- **Salida:** respuesta que muestra la computadora
- **Almacenamiento:** guardado de información

### Ejemplo
Cuando escribes en Word:
- teclas → entrada
- CPU procesa → procesamiento
- aparece texto en pantalla → salida
- guardas el archivo → almacenamiento

---

## 3.3. Entrada
La **entrada** es la información que entra al sistema.

### Ejemplos
- teclado
- mouse
- micrófono
- escáner

---

## 3.4. Salida
La **salida** es la información que sale del sistema.

### Ejemplos
- monitor
- impresora
- parlantes

---

## 3.5. Entrada/Salida (E/S)
La **E/S** es la comunicación entre la computadora y el exterior mediante dispositivos. 

### Ejemplos
- teclado
- mouse
- monitor
- impresora
- disco
- USB

---

## 3.6. Bootstrap
El **bootstrap** es el proceso de arranque mediante el cual la computadora inicia su sistema operativo. 

### Pasos generales del arranque
1. se enciende la computadora
2. se ejecuta BIOS o UEFI
3. se revisa el hardware
4. se busca el dispositivo de arranque
5. se carga el bootloader
6. se carga el sistema operativo en memoria
7. el sistema operativo toma el control

---

## 3.7. BIOS
El **BIOS** es el firmware que se ejecuta primero al encender la computadora y realiza una revisión inicial del hardware. :contentReference[oaicite:4]{index=4}

---

## 3.8. POST
El **POST** (*Power On Self Test*) es la prueba inicial del hardware que realiza el BIOS para verificar si los componentes básicos funcionan correctamente. :contentReference[oaicite:5]{index=5}

---

## 3.9. MBR
El **MBR** (*Master Boot Record*) es una parte inicial del disco que contiene información necesaria para continuar el arranque del sistema. :contentReference[oaicite:6]{index=6}

---

## 3.10. Bootloader
El **bootloader** o gestor de arranque es el programa que permite seguir el proceso de arranque y cargar el sistema operativo.  
Un ejemplo es **GRUB**. :contentReference[oaicite:7]{index=7}

---

## 3.11. Interrupción
Una **interrupción** es una señal que un dispositivo envía al procesador para indicar que necesita atención. :contentReference[oaicite:8]{index=8}

### Ejemplo
Cuando presionas una tecla:
- el teclado envía una interrupción
- la CPU atiende ese evento
- luego continúa con lo que estaba haciendo

### Importancia
Gracias a las interrupciones, la CPU no necesita estar preguntando a cada rato si algún dispositivo necesita algo.

---

## 3.12. DMA
**DMA** (*Direct Memory Access*) es un mecanismo que permite transferir datos entre un dispositivo y la memoria sin que la CPU intervenga en cada paso. :contentReference[oaicite:9]{index=9}

### Ventajas
- reduce la carga de la CPU
- mejora la velocidad de transferencia

### Idea simple
La CPU solo inicia la operación, el DMA mueve los datos y al final avisa que terminó.

---

## 3.13. Estructura de almacenamiento
El almacenamiento en la computadora se organiza de forma jerárquica. :contentReference[oaicite:10]{index=10}

### Niveles
- registros
- caché
- RAM
- disco SSD/HDD
- cintas magnéticas

### Idea clave
Mientras más cerca está de la CPU, normalmente es más rápido.

---

## 3.14. Memoria principal o RAM
La **RAM** es la memoria donde se cargan el sistema operativo y los programas para ejecutarse. 

### Características
- es rápida
- es temporal
- es volátil

---

## 3.15. Memoria volátil
La **memoria volátil** es la que pierde su contenido cuando la computadora se apaga.

---

## 3.16. Almacenamiento
El **almacenamiento** es el medio donde se guardan datos de forma más permanente.

### Ejemplos
- HDD
- SSD
- USB
- cintas magnéticas

---

## 3.17. Disco magnético
Un **disco magnético** es un dispositivo de almacenamiento que guarda datos mediante campos magnéticos, como los HDD. :contentReference[oaicite:12]{index=12}

---

## 3.18. Administración de procesos
Es la función del sistema operativo que:
- crea procesos
- planifica procesos
- controla procesos
- termina procesos 

---

## 3.19. Administración de memoria
Es la función del sistema operativo que decide:
- qué programa usa memoria
- cuánto espacio usa
- cuándo se libera memoria 

---

## 3.20. Sistema de archivos
El sistema de archivos es la organización que usa el sistema operativo para manejar archivos y directorios. 

### Funciones
- crear archivos
- eliminar archivos
- organizar carpetas
- controlar permisos

---

# 4. Semana 3 — Estructura del sistema operativo

## 4.1. Tipos de sistemas operativos
Los sistemas operativos pueden clasificarse en varios tipos. :contentReference[oaicite:16]{index=16}

### Principales
- de mainframe
- de servidor
- de escritorio
- de tiempo real
- distribuidos

---

## 4.2. Sistemas operativos de mainframe
Están diseñados para procesar muchos trabajos y muchas operaciones al mismo tiempo. :contentReference[oaicite:17]{index=17}

### Ejemplo
Sistemas grandes de bancos o empresas.

---

## 4.3. Sistemas operativos de servidor
Atienden a muchos usuarios a través de la red y comparten recursos. :contentReference[oaicite:18]{index=18}

### Ejemplos
- Linux
- FreeBSD
- Solaris

---

## 4.4. Sistemas operativos de escritorio
Son los usados en computadoras personales y laptops. :contentReference[oaicite:19]{index=19}

### Ejemplos
- Windows
- Linux
- macOS

---

## 4.5. Sistemas operativos de tiempo real
Son sistemas que deben responder dentro de un tiempo exacto o muy controlado. :contentReference[oaicite:20]{index=20}

### Ejemplos
- control industrial
- sistemas militares
- equipos médicos
- control de aviones

---

## 4.6. Sistemas operativos distribuidos
Son sistemas formados por varias máquinas o procesadores, pero que se presentan al usuario como si fueran uno solo. :contentReference[oaicite:21]{index=21}

---

## 4.7. Componentes del sistema operativo
Entre los componentes principales del sistema operativo están: :contentReference[oaicite:22]{index=22}

- kernel
- shell o interfaz de usuario
- gestión de procesos
- gestión de memoria
- gestión de archivos
- gestión de dispositivos de E/S

---

## 4.8. Kernel
El **kernel** o núcleo es la parte central del sistema operativo.  
Se encarga de controlar:
- procesos
- memoria
- hardware
- entrada/salida :contentReference[oaicite:23]{index=23}

### Idea importante
Es la parte interna más importante del sistema.

---

## 4.9. Modo privilegiado
El **modo privilegiado** es el modo de ejecución en el que trabaja el kernel, con permisos especiales para controlar el hardware y proteger el sistema. :contentReference[oaicite:24]{index=24}

---

## 4.10. Abstracción del hardware
La **abstracción del hardware** consiste en ocultar la complejidad real del hardware y ofrecer una forma más simple de usarlo. :contentReference[oaicite:25]{index=25}

### Ejemplo
Tú guardas un archivo sin preocuparte por cómo trabaja físicamente el disco.

---

## 4.11. Shell
El **shell** es la interfaz que permite al usuario comunicarse con el sistema operativo. :contentReference[oaicite:26]{index=26}

---

## 4.12. CLI
**CLI** (*Command Line Interface*) es la interfaz de línea de comandos, donde el usuario escribe instrucciones. :contentReference[oaicite:27]{index=27}

### Ejemplos
- `ls`
- `cd`
- `pwd`

---

## 4.13. GUI
**GUI** (*Graphical User Interface*) es la interfaz gráfica de usuario, basada en ventanas, íconos, menús y botones. :contentReference[oaicite:28]{index=28}

---

## 4.14. Diferencia entre kernel y shell

- **Kernel** = parte interna que controla recursos y hardware
- **Shell** = interfaz con la que el usuario le da órdenes al sistema

---

## 4.15. Servicios del sistema operativo
El sistema operativo brinda servicios a los programas. 

### Ejemplos de servicios
- ejecución de programas
- manejo de archivos
- comunicación entre procesos
- operaciones de E/S
- seguridad
- detección de errores

---

## 4.16. Multiprogramación
La **multiprogramación** es la capacidad del sistema operativo de manejar varios programas aparentemente al mismo tiempo, alternando rápidamente el uso de la CPU. :contentReference[oaicite:30]{index=30}

---

## 4.17. Runlevels
Los **runlevels** son niveles o modos de ejecución del sistema, especialmente en Linux, que indican cómo arranca o funciona. :contentReference[oaicite:31]{index=31}

### Niveles clásicos
- **0** = apagado
- **1** = monousuario
- **2** = multiusuario sin red
- **3** = multiusuario con red y sin entorno gráfico
- **4** = no usado
- **5** = multiusuario con entorno gráfico
- **6** = reinicio

---

# 5. Cómo se conecta todo

La relación general es esta:

- el **usuario** usa un programa
- el programa al ejecutarse se convierte en **proceso**
- el proceso necesita **recursos**
- el **sistema operativo** administra esos recursos
- el **kernel** hace el control interno
- el **shell** permite la comunicación entre usuario y sistema
- todo comienza con el **bootstrap**, cuando la computadora arranca

---

# 6. Conceptos clave que más pueden venir en teoría

## Diferencias que debes saber
- programa vs proceso
- hardware vs software
- RAM vs disco
- kernel vs shell
- interrupción vs DMA

---

## Definiciones que debes memorizar
- recurso
- programa
- proceso
- sistema operativo
- hardware
- sistema de cómputo
- E/S
- bootstrap
- BIOS
- POST
- MBR
- bootloader
- interrupción
- DMA
- RAM
- almacenamiento
- kernel
- shell
- CLI
- GUI
- multiprogramación
- runlevels

---

# 7. Lo que más puede venir en la PC1

## Preguntas típicas
- ¿Qué es un sistema operativo?
- ¿Qué es un proceso?
- ¿Cuál es la diferencia entre programa y proceso?
- ¿Qué son los recursos?
- ¿Qué hace el sistema operativo con los recursos?
- ¿Qué es el bootstrap?
- ¿Qué ocurre cuando encendemos una computadora?
- ¿Qué son las interrupciones?
- ¿Qué ventaja tiene DMA?
- ¿Qué es el kernel?
- ¿Qué es el shell?
- ¿Cuál es la diferencia entre CLI y GUI?
- ¿Qué diferencia hay entre RAM y disco?
- ¿Qué son los runlevels?
- ¿Cuáles son los componentes del sistema operativo?

---

# 8. Mini resumen final para memorizar

## Semana 1
Se aprende que el sistema operativo administra recursos y que los procesos son programas en ejecución.

## Semana 2
Se aprende cómo funciona el sistema de cómputo, cómo arranca la computadora y cómo se comunica con dispositivos, memoria y almacenamiento. :contentReference[oaicite:32]{index=32}

## Semana 3
Se aprende cómo está estructurado el sistema operativo internamente, especialmente kernel, shell, tipos de SO y runlevels. :contentReference[oaicite:33]{index=33}

---

# 9. Frase final de repaso

El **sistema operativo** es el software que administra los recursos de la computadora, controla procesos, memoria, archivos y dispositivos, permite la comunicación con el usuario mediante el shell y realiza el control interno mediante el kernel.
