# Semana 2: Sistemas Operativos y gestión de procesos

En esta clase se estudia cómo funciona una computadora por dentro y qué papel cumple el **sistema operativo**. La sesión incluye estos temas: estructura de los sistemas de cómputo, *bootstrap*, entrada/salida, interrupciones, DMA, almacenamiento, memoria principal, discos magnéticos, administración de procesos, memoria, archivos y servicios del sistema operativo.

---

## 1. ¿Qué es un sistema de cómputo?

Un **sistema de cómputo** es el conjunto de **hardware** y **software** que permite procesar información. Sus componentes principales son:

- CPU
- Memoria principal (RAM)
- Dispositivos de entrada/salida
- Dispositivos de almacenamiento

El flujo básico es:

**Entrada → Procesamiento → Salida → Almacenamiento**

### Explicación sencilla

Piensa en la computadora como una oficina:

- **Entrada**: lo que tú le das a la computadora.
  - Ejemplo: escribir con el teclado.
- **Procesamiento**: lo que la computadora analiza.
  - Lo hace la CPU.
- **Salida**: lo que la computadora te devuelve.
  - Ejemplo: texto en pantalla.
- **Almacenamiento**: donde se guarda la información.
  - Ejemplo: un archivo en disco.

### Ejemplo

Cuando escribes en Word:

- usas el teclado → entrada
- la CPU procesa lo escrito → procesamiento
- lo ves en la pantalla → salida
- lo guardas como archivo → almacenamiento

---

## 2. ¿Qué es el sistema operativo?

Un **sistema operativo** es el software que **administra los recursos del sistema**. Entre sus funciones principales están:

- administrar hardware
- ejecutar programas
- gestionar memoria
- gestionar archivos
- administrar dispositivos

### Explicación sencilla

El sistema operativo es como el **administrador general** de la computadora.

Él se encarga de que:

- los programas funcionen
- la memoria se reparta bien
- los archivos estén ordenados
- el teclado, mouse, pantalla y otros dispositivos trabajen correctamente

### Ejemplo

Si abres Chrome, Word y Spotify al mismo tiempo, el sistema operativo organiza todo para que los tres funcionen sin desorden.

---

## 3. ¿Qué es el Bootstrap?

El **bootstrap** o **proceso de arranque** es el proceso mediante el cual una computadora inicia su sistema operativo. Sus etapas son:

1. Se enciende el equipo.
2. Se ejecuta BIOS o UEFI.
3. Se localiza el bootloader.
4. Se carga el sistema operativo en memoria.
5. El sistema operativo toma el control.

### Explicación sencilla

Cuando presionas el botón de encendido, la computadora todavía no está lista. Primero revisa sus partes y luego busca el sistema operativo para empezar a trabajar.

### Ejemplo

Es como abrir una tienda:

1. enciendes las luces  
2. revisas que todo esté bien  
3. abres la puerta  
4. preparas la caja  
5. comienzas a atender  

La computadora hace algo parecido antes de empezar a usarse.

---

## 4. Estructura de Entrada / Salida (E/S)

Los dispositivos de entrada/salida permiten que el sistema interactúe con el exterior. Ejemplos:

- **Entrada**: teclado, mouse, escáner
- **Salida**: monitor, impresora, altavoces
- **Entrada/Salida**: disco duro, USB, red

### Explicación sencilla

La computadora necesita comunicarse contigo y con otros dispositivos.

- **Entrada** = información que entra
- **Salida** = información que sale
- **Entrada/Salida** = puede hacer ambas cosas

### Ejemplo

Un USB puede recibir archivos y también entregarlos, por eso es de entrada/salida.

---

## 5. ¿Qué son las interrupciones?

Una **interrupción** es una señal que envía un dispositivo al procesador para indicar que necesita atención. La clase también menciona tres tipos:

- hardware
- software
- temporizador

### Explicación sencilla

Una interrupción es como decirle al CPU:

**"Detente un momento, necesito que atiendas esto."**

### Ejemplo

Cuando presionas una tecla:

- el teclado envía una interrupción
- el CPU pausa lo que estaba haciendo
- atiende la solicitud del teclado
- luego sigue con lo anterior

### Ejemplo de la vida diaria

Estás haciendo tarea y alguien toca la puerta.  
Tú dejas un momento lo que haces, atiendes, y luego continúas.  
Eso mismo hace el procesador.

---

## 6. ¿Qué es DMA?

**DMA** significa **Direct Memory Access**. Permite que los dispositivos transfieran datos directamente a la memoria sin usar constantemente la CPU. Sus beneficios son:

- reduce carga del procesador
- mejora velocidad de transferencia

### Explicación sencilla

DMA ayuda a que la CPU no tenga que mover todos los datos por sí sola.

### Ejemplo

Imagina que la CPU es el jefe de una oficina.

- **Sin DMA**: el jefe mueve caja por caja.
- **Con DMA**: el jefe da la orden y otro encargado hace el traslado.

Así, la CPU queda libre para hacer otras tareas.

### Funcionamiento básico

1. La CPU inicia la transferencia.
2. El controlador DMA toma el control.
3. Los datos pasan entre dispositivo y memoria.
4. DMA avisa al CPU cuando termina.

---

## 7. Estructura de almacenamiento

El almacenamiento se organiza de forma jerárquica:

1. Registros CPU — muy alta velocidad  
2. Caché — alta  
3. RAM — media  
4. Disco SSD/HDD — baja  
5. Cintas magnéticas — muy baja  

### Explicación sencilla

No toda la memoria de la computadora es igual. Algunas partes son más rápidas y otras más lentas.

Mientras más cerca está algo de la CPU, normalmente es más rápido.

### Ejemplo

Piensa en esto:

- **Registros**: lo que tienes en la mente en este instante
- **Caché**: lo que tienes al alcance inmediato
- **RAM**: el cuaderno abierto en tu mesa
- **Disco**: tus apuntes guardados en tu mochila
- **Cintas**: archivos viejos guardados hace tiempo

---

## 8. Memoria principal (RAM)

La **RAM** es donde el sistema operativo y los programas se cargan para ejecutarse. Sus características son:

- volátil
- alta velocidad
- acceso directo por CPU

### Explicación sencilla

La RAM es el **espacio de trabajo temporal** de la computadora.

### ¿Qué significa que sea volátil?

Que cuando apagas la computadora, su contenido se pierde.

### Ejemplo

Si abres Chrome y Word, ambos se cargan en la RAM para poder funcionar.

---

## 9. Discos magnéticos

Los **discos magnéticos** almacenan información mediante campos magnéticos. Ejemplos:

- discos duros (HDD)
- disquetes

Componentes:

- platos
- cabezal de lectura
- motor

### Explicación sencilla

Sirven para guardar información de forma permanente.

### Ejemplo

Tus fotos, videos y documentos pueden quedarse guardados en un HDD incluso si apagas la computadora.

---

## 10. Administración de procesos

Un **proceso** es un **programa en ejecución**. El sistema operativo se encarga de:

- crear procesos
- planificar procesos
- terminar procesos

### Explicación sencilla

No es lo mismo un programa guardado que un programa funcionando.

- **Programa**: está instalado
- **Proceso**: está ejecutándose ahora

### Ejemplo

Chrome instalado en tu computadora es un programa.  
Chrome abierto y funcionando en este momento es un proceso.

---

## 11. Administración de memoria

El sistema operativo decide:

- qué programa usa memoria
- cuánto espacio usa
- cuándo liberar memoria

Si la RAM es insuficiente, se usa **memoria virtual**.

### Explicación sencilla

La memoria no alcanza para todo, así que el sistema operativo la reparte entre los programas.

### Ejemplo

Si abres muchos programas a la vez, la RAM puede llenarse y el sistema empieza a apoyarse en memoria virtual.

---

## 12. Sistema de archivos

El sistema operativo organiza los archivos en directorios. Sus funciones incluyen:

- crear archivos
- eliminar archivos
- organizar carpetas
- controlar permisos

### Explicación sencilla

Esto es lo que hace posible que tus documentos estén ordenados en carpetas.

### Ejemplo

Cuando ves carpetas como:

- Documentos
- Programas
- Imágenes

eso forma parte del sistema de archivos.

---

## 13. Estructura de sistemas operativos

La clase menciona varias formas de organizar un sistema operativo:

- estructura simple
- estructura en capas
- estructura modular
- máquinas virtuales
- estructura monolítica
- micronúcleo
- núcleo híbrido
- exonúcleo

### Explicación sencilla

No todos los sistemas operativos están construidos igual.  
Cada uno organiza sus partes internas de una manera distinta.

### Ejemplo

Es como construir una casa:

- una puede ser muy simple
- otra puede estar dividida por pisos
- otra puede tener partes que se agregan según necesidad

---

## 14. Linux, Windows y OS/2

La clase presenta ejemplos de sistemas operativos:

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

---

## 15. Servicios del sistema operativo

Los sistemas operativos brindan servicios a los programas. Entre los principales están:

- ejecución de programas
- manejo de archivos
- comunicación entre procesos
- detección de errores
- seguridad del sistema

### Explicación sencilla

El sistema operativo no solo "enciende" la computadora. También ayuda a que los programas funcionen de forma segura y ordenada.

---

## Resumen final

La semana 2 trata de entender cómo una computadora arranca, cómo se comunica con sus dispositivos y cómo el sistema operativo organiza todo para que los programas puedan funcionar correctamente. También introduce conceptos importantes como **interrupciones**, **DMA**, **RAM**, **almacenamiento** y **procesos**.

## Idea más corta para memorizar

**El sistema operativo es el encargado de administrar la computadora: controla el hardware, la memoria, los archivos, los procesos y la comunicación con los dispositivos.**
