# Clase de la semana 2: Sistemas Operativos y gestión de procesos

Hoy la idea principal es entender qué hace un sistema operativo y cómo se comunica con el hardware de la computadora.

La presentación dice que en esta semana se trabaja:

- la estructura de los sistemas de cómputo
- el arranque o **bootstrap**
- las interrupciones
- el **DMA**
- el almacenamiento
- la memoria principal
- los discos
- las funciones del sistema operativo

---

## 1) ¿Qué es un sistema de cómputo?

Un sistema de cómputo es el conjunto de **hardware** y **software** que permite procesar información.

Sus componentes principales son:

- la **CPU**
- la **memoria RAM**
- los dispositivos de **entrada/salida**
- los dispositivos de **almacenamiento**

El flujo básico es:

**entrada → procesamiento → salida → almacenamiento**

### Explícalo fácil

Imagina que la computadora es como una pequeña oficina:

- **Entrada:** lo que tú le das a la computadora.  
  Ejemplo: escribir con el teclado, mover el mouse.
- **Procesamiento:** la computadora “piensa” qué hacer.  
  Eso lo hace principalmente la **CPU**.
- **Salida:** la respuesta que te muestra.  
  Ejemplo: algo aparece en la pantalla o se escucha sonido.
- **Almacenamiento:** guardar la información.  
  Ejemplo: un archivo en el disco.

### Ejemplo cotidiano

Tú escribes en Word:

- presionas teclas → **entrada**
- la CPU procesa lo que escribes → **procesamiento**
- el texto aparece en pantalla → **salida**
- el archivo se guarda en tu disco → **almacenamiento**

---

## 2) ¿Qué es el sistema operativo?

El sistema operativo es el software que administra los recursos del sistema.

La diapositiva indica que sus funciones principales son:

- administrar hardware
- ejecutar programas
- gestionar memoria
- gestionar archivos
- administrar dispositivos

### Dicho más simple

El sistema operativo es como el **administrador general** de la computadora.

Sin sistema operativo:

- el teclado no sabría cómo enviar datos
- los programas no podrían ejecutarse bien
- la memoria no estaría organizada
- los archivos serían un caos

### Ejemplo

Cuando abres Chrome, escuchas música y descargas un archivo al mismo tiempo, el sistema operativo está organizando todo eso para que no se choquen entre sí.

---

## 3) ¿Qué es el Bootstrap o arranque?

La presentación define el proceso de arranque (**Bootstrap**) como el proceso mediante el cual una computadora inicia su sistema operativo.

Sus etapas son:

1. encendido del equipo
2. se ejecuta **BIOS** o **UEFI**
3. se localiza el **bootloader**
4. se carga el sistema operativo en memoria
5. el sistema operativo toma el control

### Explícalo fácil

Cuando tú presionas el botón de encendido, la computadora todavía no está “lista”.

Primero necesita:

- revisar que sus partes funcionen
- buscar el sistema operativo
- arrancarlo

### Ejemplo sencillo

Piensa en esto como cuando abres una tienda:

1. enciendes las luces
2. revisas que todo esté bien
3. abres la puerta
4. preparas la caja
5. recién comienzas a atender

Eso mismo hace la computadora: primero se prepara y luego entrega el control al sistema operativo.

---

## 4) Entrada y salida (E/S)

La clase también habla de la estructura de **entrada/salida**.

Los dispositivos de entrada/salida permiten que el sistema interactúe con el exterior.

### Ejemplos

- **Entrada:** teclado, mouse, escáner
- **Salida:** monitor, impresora, altavoces
- **Entrada/Salida:** disco duro, USB, red

### Explícalo fácil

La computadora no vive sola; necesita comunicarse contigo y con otros dispositivos.

- **Entrada** = lo que entra a la computadora
- **Salida** = lo que sale de la computadora
- **Entrada/Salida** = dispositivos que hacen ambas cosas

### Ejemplo

Un USB puede recibir archivos y también entregar archivos.  
Por eso cuenta como **entrada/salida**.

---

## 5) ¿Qué son las interrupciones?

La presentación dice que una **interrupción** es una señal que envía un dispositivo al procesador para indicar que necesita atención.

También pone el ejemplo de presionar una tecla:

- el teclado envía una interrupción
- el CPU detiene temporalmente lo que está haciendo
- atiende la solicitud

Además menciona tipos de interrupciones:

- hardware
- software
- temporizador

### Explícalo fácil

Una interrupción es como decirle al procesador:

**“¡Oye! Detente un momento, necesito que atiendas esto.”**

### Ejemplo de la vida real

Imagina que estás haciendo tu tarea y alguien toca la puerta.

Tú:

1. pausas lo que haces
2. abres
3. atiendes
4. luego vuelves a tu tarea

Eso hace el CPU con una interrupción:

1. estaba haciendo una tarea
2. llega una señal
3. se detiene un momento
4. atiende esa señal
5. regresa a lo anterior

### Ejemplo en la computadora

Cuando presionas una tecla:

- el teclado avisa
- el CPU atiende esa acción
- el sistema muestra la letra en pantalla

### ¿Por qué son importantes?

Porque sin interrupciones, la CPU tendría que estar preguntando a cada rato:

- “¿teclado, me escribiste algo?”
- “mouse, ¿te moviste?”
- “impresora, ¿terminaste?”

Eso sería más lento.

Con interrupciones, el dispositivo avisa solo cuando lo necesita.  
Esa es la gracia del mecanismo.

---

## 6) ¿Qué es DMA?

La clase explica que **DMA (Direct Memory Access)** permite que los dispositivos transfieran datos directamente a la memoria sin usar constantemente la CPU.

### Beneficios

- reducir carga del procesador
- mejorar la velocidad de transferencia

### Funcionamiento

1. la CPU inicia la transferencia
2. el controlador DMA toma el control
3. los datos pasan entre dispositivo y memoria
4. al final DMA notifica al CPU

### Explícalo fácil

DMA sirve para que la CPU no tenga que encargarse de mover todos los datos paso por paso.

### Ejemplo sencillo

Imagínate que la CPU es el jefe de una oficina.

**Sin DMA:**

- el jefe tendría que cargar caja por caja personalmente

**Con DMA:**

- el jefe solo dice: “trasladen estas cajas”
- otro encargado las mueve
- al final le avisan: “ya terminamos”

Eso ahorra tiempo y deja libre al jefe para otras tareas.

### Ejemplo en computadora

Si copias un archivo grande desde un disco a la memoria, DMA ayuda a que esa transferencia sea más rápida y que la CPU no se desgaste atendiendo cada pequeño movimiento de datos.

---

## 7) Estructura de almacenamiento

La diapositiva dice que el almacenamiento se organiza **jerárquicamente**.

### Niveles

- **Registros CPU** – muy alta velocidad
- **Caché** – alta
- **RAM** – media
- **Disco SSD/HDD** – baja
- **Cintas magnéticas** – muy baja

### Explícalo fácil

No toda la memoria de la computadora es igual.

Algunas son:

- más rápidas
- más lentas
- más pequeñas
- más grandes

### Idea clave

- Mientras más cerca está de la CPU, normalmente es más rápida.
- Mientras más lejos y más usada para guardar mucho, suele ser más lenta.

### Ejemplo para entenderlo

Piensa en un estudiante:

- **Registros:** lo que tienes “en la cabeza” en este instante
- **Caché:** lo que tienes súper a la mano
- **RAM:** cuaderno abierto en tu mesa
- **Disco:** tus apuntes guardados en mochila o laptop
- **Cinta:** archivos antiguos guardados por mucho tiempo

La computadora usa esa jerarquía para trabajar de forma eficiente.

---

## 8) Memoria principal (RAM)

La clase define la **memoria principal (RAM)** como el lugar donde el sistema operativo y los programas se cargan para ejecutarse.

### Características

- volátil
- alta velocidad
- acceso directo por CPU

### Explícalo fácil

La RAM es el espacio de trabajo temporal de la computadora.

### ¿Qué significa volátil?

Que cuando apagas la computadora, lo que estaba ahí se pierde.

### Ejemplo

Abres Chrome, Word y Spotify.

Esos programas se cargan en la **RAM** para poder ejecutarse.

Si la RAM se llena, la computadora puede ponerse lenta.

---

## 9) Discos magnéticos

La diapositiva indica que los discos magnéticos almacenan información mediante campos magnéticos.

### Ejemplos

- discos duros (**HDD**)
- disquetes

También menciona componentes como:

- platos
- cabezal de lectura
- motor

### Explícalo fácil

Son dispositivos que guardan información de forma permanente usando magnetismo.

### Ejemplo

Tu computadora puede guardar fotos, videos, documentos y programas en un HDD.

Aunque apagues la máquina, esos datos siguen ahí.  
Esa es una diferencia importante con la RAM.

---

## 10) Administración de procesos

La presentación dice que un **proceso** es un programa en ejecución.

El sistema operativo:

- crea procesos
- planifica procesos
- termina procesos

### Ejemplos

- navegador
- Word
- reproductor

### Explícalo fácil

Un programa guardado en disco no es lo mismo que un proceso.

- **Programa:** archivo guardado
- **Proceso:** programa funcionando en este momento

### Ejemplo

- Chrome instalado en tu PC es un **programa**
- Chrome abierto ahora mismo, usando RAM y CPU, es un **proceso**

### ¿Qué hace el sistema operativo aquí?

Decide:

- cuál proceso se ejecuta primero
- cuánto tiempo usa la CPU
- cuándo se pausa
- cuándo termina

Eso se llama **administrar procesos**.

---

## 11) Administración de memoria

La clase indica que el sistema operativo decide:

- qué programa usa memoria
- cuánto espacio usa
- cuándo liberar memoria

Y menciona que, si la RAM es insuficiente, se usa **memoria virtual**.

### Explícalo fácil

La memoria no es infinita.  
Entonces el sistema operativo tiene que repartirla.

### Ejemplo

Si abres demasiados programas al mismo tiempo:

- uno usa parte de la RAM
- otro usa otra parte
- si no alcanza, el sistema busca apoyarse en memoria virtual

Es como acomodar personas en un salón pequeño: si ya no hay espacio, toca reorganizar.

---

## 12) Sistema de archivos

La presentación explica que el sistema operativo organiza los archivos en **directorios**.

### Sus funciones incluyen

- crear archivos
- eliminar archivos
- organizar carpetas
- controlar permisos

### Explícalo fácil

Esto es básicamente el orden de tus documentos.

### Ejemplo

Tienes carpetas como:

- **Documentos**
- **Programas**
- **Imágenes**

Eso no aparece por magia.  
El sistema operativo organiza todo eso para que puedas encontrar tus archivos.

---

## 13) Estructura de sistemas operativos

La clase menciona varias formas de organizar un sistema operativo:

- estructura simple
- en capas
- modular
- máquinas virtuales
- entre otras

### Ejemplos

- **Estructura simple:** como MS-DOS
- **En capas:** como UNIX
- **Modular:** como Solaris
- **Máquinas virtuales:** entornos casi independientes sobre el hardware

### Explícalo fácil

Esto significa que no todos los sistemas operativos están construidos igual.  
Cada uno tiene una manera de organizar sus partes internas.

### Ejemplo sencillo

Es como construir una casa:

- una casa puede ser muy simple
- otra puede tener pisos bien separados
- otra puede tener piezas que se agregan cuando se necesiten

Así también se diseñan los sistemas operativos.

---

## 14) Linux, Windows y OS/2

La presentación caracteriza:

### Linux
- código abierto
- seguro
- muy usado en servidores

### Windows
- interfaz gráfica amigable
- muy usado en computadoras personales
- amplio soporte de software

### OS/2
- desarrollado por IBM
- multitarea
- estable
- usado en entornos empresariales en el pasado

### Explícalo fácil

Cada sistema operativo tiene su estilo y su uso más común.

- **Linux** suele usarse mucho en servidores y ambientes técnicos.
- **Windows** es muy común en laptops y PCs personales.
- **OS/2** fue importante antes en empresas, aunque hoy ya no es tan común.

---

## 15) Servicios del sistema operativo

La clase dice que los sistemas operativos brindan servicios a los programas.

### Los principales son

- ejecución de programas
- manejo de archivos
- comunicación entre procesos
- detección de errores
- seguridad del sistema

### Explícalo fácil

El sistema operativo no solo “enciende la PC”.  
También presta servicios para que los programas funcionen bien.

### Ejemplo

Cuando abres un programa:

- el SO permite ejecutarlo
- le da acceso a archivos
- controla errores
- protege el sistema
- ayuda a que se comunique con otros procesos si es necesario

---

# Resumen final como si cerráramos la clase

La semana 2 trata de entender que la computadora no funciona sola: necesita un sistema operativo que organice el hardware, la memoria, los archivos, los procesos y la comunicación con los dispositivos.

También se aprende:

- cómo arranca la computadora (**bootstrap**)
- cómo los dispositivos llaman la atención del CPU mediante **interrupciones**
- cómo **DMA** ayuda a transferir datos más rápido sin sobrecargar al procesador

## En una frase

Esta clase te enseña cómo la computadora arranca, cómo se comunica con sus dispositivos y cómo el sistema operativo organiza todo para que los programas funcionen correctamente.
