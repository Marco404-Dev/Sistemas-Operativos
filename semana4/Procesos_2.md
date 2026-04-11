# Gestión de procesos — Explicación detallada

Basado en tu PDF de la semana 4 sobre **gestión de procesos**. El material define proceso, sus estados, sus operaciones, el PCB y los niveles de ejecución. :contentReference[oaicite:0]{index=0}

---

## 1. ¿Qué es un programa y qué es un proceso?

En la diapositiva se diferencia así:

- **Programa**: archivo con instrucciones, algo **estático**.
- **Proceso**: un **programa en ejecución**, algo **dinámico**. :contentReference[oaicite:1]{index=1}

### Ejemplo fácil
Piensa en esto:

- **Programa** = la receta de una torta escrita en papel.
- **Proceso** = cuando ya estás cocinando la torta en la cocina.

La receta sola no hace nada.  
Recién cuando alguien la ejecuta, hay acción.  
Eso mismo pasa con el programa: guardado en disco no “trabaja”; cuando se ejecuta, se convierte en proceso.

### Ejemplo en la computadora
- Tienes instalado **Google Chrome** → eso es un programa.
- Lo abres y navegas por internet → eso ya es un proceso.
- Si abres dos ventanas o varias pestañas, pueden existir varios procesos relacionados.

---

## 2. ¿Por qué el sistema operativo se preocupa por los procesos?

Porque casi todo lo que usas en la computadora se ejecuta como proceso:

- el navegador
- Spotify
- Word
- el antivirus
- el sistema mismo

Tu PDF dice que el sistema operativo administra procesos y recursos, y por eso necesita información del estado actual de cada proceso y recurso del sistema. :contentReference[oaicite:2]{index=2}

### ¿Qué recursos usan?
Un proceso puede necesitar:

- CPU
- memoria RAM
- archivos
- teclado
- mouse
- pantalla
- impresora
- red

### Ejemplo
Supón que estás:
- escuchando música,
- descargando un archivo,
- escribiendo en Word.

Todo eso compite por recursos.  
El sistema operativo decide:

- cuál proceso usa la CPU primero,
- cuánta memoria recibe,
- quién espera,
- quién sigue ejecutándose.

---

## 3. CPU, multiprogramación y multiprocesador

Tu PDF explica que la **CPU** es un recurso importante y limitado. También habla de **multiprogramación** y **multiprocesador**. :contentReference[oaicite:3]{index=3}

### A) Multiprogramación
La CPU va cambiando rápidamente entre procesos, dándole a cada uno un pequeño tiempo.  
Eso produce una sensación de que todo ocurre a la vez, pero en realidad va alternando. Tu material lo llama **pseudo-paralelismo**. :contentReference[oaicite:4]{index=4}

### Ejemplo
Tú ves:
- música sonando,
- video cargando,
- documento abierto.

Parece que todo ocurre al mismo tiempo.  
Pero si tienes una sola CPU o un solo núcleo trabajando sobre ciertos procesos, muchas veces la CPU va saltando entre tareas muy rápido.

Es como un profesor atendiendo a 5 alumnos:
1. escucha a uno 10 segundos,
2. luego a otro,
3. luego a otro,
4. y vuelve al primero.

Parece atención simultánea, pero no lo es realmente.

### B) Multiprocesador
Aquí sí existen varios CPU o varios núcleos ejecutando varias tareas al mismo tiempo. :contentReference[oaicite:5]{index=5}

### Ejemplo
Si tu PC tiene varios núcleos:
- un núcleo puede atender el navegador,
- otro la música,
- otro una actualización,
- otro una videollamada.

Aquí ya hay paralelismo real.

---

## 4. Un proceso no es solo “el programa”: también tiene contexto

Tu PDF dice que un proceso consta básicamente de:

- **programa**
- **contexto** :contentReference[oaicite:6]{index=6}

### ¿Qué significa “contexto”?
Es toda la información que le permite al sistema operativo saber:

- en qué parte del programa iba,
- qué datos tenía,
- qué recursos estaba usando,
- si estaba listo, esperando o ejecutándose.

### Ejemplo
Imagina que estás resolviendo un examen y el profesor te dice:
“guarda todo, luego continúas”.

Para poder seguir después, necesitas saber:
- en qué pregunta estabas,
- qué respuesta ibas escribiendo,
- cuánto tiempo te quedaba.

Ese “punto exacto” donde te quedaste es parecido al **contexto** del proceso.

---

## 5. ¿Qué guarda un proceso en memoria?

En la diapositiva del mapa de memoria se muestra que cuando se crea un proceso, el sistema operativo reserva espacio para almacenar su información, como texto, instrucciones, datos y pila. :contentReference[oaicite:7]{index=7}

Normalmente un proceso tiene zonas como:

- **código o texto**: instrucciones del programa
- **datos**: variables globales e inicializadas
- **heap**: memoria dinámica
- **stack o pila**: llamadas a funciones y variables locales

### Ejemplo sencillo
Supón un programa de calculadora:

- el código de sumar/restar está en la parte de instrucciones,
- los números actuales que estás usando están en datos,
- si el programa pide memoria extra, eso va al heap,
- si llamas funciones, eso usa la pila.

---

## 6. ¿Cuándo se crea un proceso?

Tu material menciona varios casos de creación de procesos: al inicio del sistema, por interacción del usuario, por llamada del sistema y por trabajos por lotes. :contentReference[oaicite:8]{index=8}

Vamos uno por uno.

### A) Inicio del sistema
Cuando prendes la computadora, el sistema operativo crea procesos necesarios para que todo funcione.

### Ejemplo
- servicios del sistema,
- gestor de red,
- interfaz gráfica,
- procesos del sistema.

### B) Cuando el usuario inicia uno
Tú haces clic en una aplicación o escribes un comando.

### Ejemplo
Abres Firefox → se crea el proceso de Firefox.

### C) Cuando un proceso crea otro
Tu PDF menciona en Linux `fork()` y `exec()`, y en Windows `CreateProcess`. :contentReference[oaicite:9]{index=9}

### Ejemplo
Abres una terminal y escribes un comando:
- la terminal ya es un proceso,
- ese proceso lanza otro para ejecutar el comando.

### D) Trabajo por lotes
Sucede cuando se ejecuta una serie de tareas automáticamente.

### Ejemplo
Un servidor que cada noche:
- genera reportes,
- limpia archivos,
- hace copias de seguridad.

---

## 7. PID y PPID

Tu PDF explica:

- **PID**: identificador único del proceso.
- **PPID**: identificador del proceso padre. :contentReference[oaicite:10]{index=10}

### Ejemplo
Supón esto:

- La terminal tiene PID 2000
- Desde la terminal ejecutas `python`
- Entonces `python` podría tener PID 2500
- Su **PPID** sería 2000, porque fue creado por la terminal

### Idea clave
- **Padre** = proceso que crea a otro
- **Hijo** = proceso creado

Es como una relación de origen.

---

## 8. ¿Qué es el administrador de procesos?

Tu PDF dice que es el módulo del sistema operativo que administra la ejecución de programas de usuario o del sistema, y que para esto mantiene una **tabla de procesos**. Cada entrada se conoce como **PCB**. :contentReference[oaicite:11]{index=11}

### En palabras simples
Es como el encargado del tráfico de todos los procesos.

Debe saber:
- cuáles existen,
- cuáles están esperando,
- cuáles usan CPU,
- cuáles ya terminaron.

---

## 9. ¿Qué es el PCB?

El **PCB (Process Control Block)** o **Bloque de Control del Proceso** es una estructura de datos que guarda la información importante de cada proceso. Tu PDF lo define así y enumera varios campos, como estado, contador de programa, registros, prioridad, PID, proceso padre e información de memoria y archivos. :contentReference[oaicite:12]{index=12}

### Piensa en el PCB como una “ficha” del proceso

Así como en un colegio cada alumno tiene una ficha con sus datos, cada proceso tiene su PCB.

### ¿Qué guarda esa ficha?
Tu material menciona, entre otros:

- estado del proceso
- contador del programa
- registros de CPU
- prioridad
- ID del proceso
- proceso padre
- tiempo de CPU usado
- información de memoria
- archivos abiertos
- información de E/S :contentReference[oaicite:13]{index=13}

---

## 10. Explicación simple de los datos más importantes del PCB

### A) Estado del proceso
Indica en qué situación está.

Ejemplo:
- listo
- ejecutando
- esperando
- terminado

### B) Contador del programa
Apunta a la siguiente instrucción que debe ejecutarse. Tu PDF lo dice explícitamente. :contentReference[oaicite:14]{index=14}

### Ejemplo
Si el programa iba por la instrucción 120, el sistema debe recordar eso.  
Si no lo recuerda, luego no sabrá desde dónde continuar.

### C) Registros de CPU
Guardan información interna necesaria mientras el proceso se ejecuta. El PDF indica que deben respaldarse y restaurarse cuando hay cambio de estado. :contentReference[oaicite:15]{index=15}

### Ejemplo
Si la CPU estaba trabajando con ciertos valores y cambia a otro proceso, esos datos del primero deben guardarse.  
Cuando vuelva, se restauran y continúa como si nada hubiera pasado.

### D) Prioridad
Sirve para ayudar a decidir qué proceso atender primero.

### Ejemplo
Un proceso crítico del sistema puede tener más prioridad que una aplicación secundaria.

### E) Información de memoria
Dice qué partes de memoria está usando el proceso.

### F) Archivos y dispositivos
Indica qué archivos tiene abiertos o qué dispositivos usa.

### Ejemplo
Si Word tiene abierto `tarea.docx`, eso debe quedar registrado.

---

## 11. ¿Por qué el PCB es tan importante?

Porque sin el PCB el sistema operativo no podría organizar bien los procesos.

### Ejemplo muy claro
Supón que tienes 3 procesos:

- navegador
- música
- editor de texto

La CPU atiende al navegador 1 instante, luego a música, luego a Word.

Para que eso funcione, el sistema operativo debe guardar para cada uno:

- dónde se quedó,
- cuánto llevaba ejecutado,
- qué recursos usa,
- cuál es su estado.

Todo eso se apoya en el PCB.

---

## 12. Estados de un proceso

Tu PDF presenta estos estados:

- **Nuevo**
- **Listo**
- **En ejecución**
- **En espera**
- **Terminado** :contentReference[oaicite:16]{index=16}

Voy a explicarlos como una historia.

### A) Nuevo
El proceso recién fue creado, pero todavía no entra a competir por CPU.

### Ejemplo
Das doble clic en un programa.  
El sistema recién lo está preparando.

### B) Listo
El proceso ya puede ejecutarse, pero está esperando turno de CPU.

### Ejemplo
Hay varios procesos listos y la CPU solo puede atender uno a la vez.  
Entonces algunos esperan su turno.

### C) En ejecución
La CPU ya está ejecutando sus instrucciones.

### Ejemplo
Tu navegador está procesando una página en este instante.

### D) En espera o bloqueado
El proceso no puede seguir hasta que ocurra un evento, por ejemplo una operación de E/S. El PDF pone precisamente ese ejemplo. :contentReference[oaicite:17]{index=17}

### Ejemplo
Guardas un archivo en el disco.  
Mientras el disco responde, el proceso puede quedar esperando.

### E) Terminado
El proceso ya acabó y el sistema libera sus recursos. :contentReference[oaicite:18]{index=18}

### Ejemplo
Cierras una aplicación y el proceso termina.

---

## 13. Ejemplo completo de los estados

Imagina que abres **VLC** para ver un video:

### 1. Nuevo
Haces doble clic sobre el programa.

### 2. Listo
El sistema ya lo creó y está esperando CPU.

### 3. En ejecución
La CPU atiende a VLC y comienza a cargar la interfaz.

### 4. En espera
VLC necesita leer el video del disco. Mientras espera esa lectura, queda en espera.

### 5. Listo otra vez
Cuando el disco responde, vuelve a estar listo.

### 6. En ejecución
La CPU sigue procesando la reproducción del video.

### 7. Terminado
Cierras VLC y el proceso finaliza.

---

## 14. Transiciones entre estados

Tu PDF menciona estas transiciones:

- **Despachar**
- **Expiración de tiempo**
- **Bloquear**
- **Despertar** :contentReference[oaicite:19]{index=19}

### A) Despachar
Pasar de **listo** a **ejecución**.

### Ejemplo
El planificador dice:
“ahora le toca a este proceso”.

### B) Expiración de tiempo
Pasa de **ejecución** a **listo** porque se le acabó su turno.

### Ejemplo
El sistema le dio 20 ms de CPU.  
Se acabó ese tiempo y debe ceder el procesador.

### C) Bloquear
Pasa de **ejecución** a **espera**.

### Ejemplo
Pidió leer del disco o esperar red.

### D) Despertar
Pasa de **espera** a **listo**.

### Ejemplo
Ya llegó el dato del disco o terminó la operación de entrada/salida.

---

## 15. Operaciones que se pueden hacer con un proceso

Tu PDF enumera estas operaciones:

- crear y destruir
- suspender y reanudar
- cambiar prioridad
- bloquear y desbloquear
- planificar
- comunicación entre procesos :contentReference[oaicite:20]{index=20}

### Veamos una por una

### A) Crear
Se genera un nuevo proceso.

Ejemplo:
abres una app.

### B) Destruir
Se elimina del sistema. El PDF comenta que puede complicarse cuando tiene procesos hijos. :contentReference[oaicite:21]{index=21}

Ejemplo:
cierras una app o el sistema la finaliza.

### C) Suspender
El proceso queda detenido temporalmente.

Ejemplo:
una aplicación queda pausada por un momento.

### D) Reanudar
El proceso continúa desde donde se quedó. El PDF lo dice así. :contentReference[oaicite:22]{index=22}

Ejemplo:
reanudas una tarea pausada.

### E) Cambiar prioridad
Se modifica la importancia relativa del proceso.

Ejemplo:
el sistema puede subir prioridad a una tarea urgente.

### F) Bloquear / desbloquear
Se detiene por esperar algo, luego vuelve a estar disponible.

### G) Planificar
Asignarle CPU.

### H) Comunicación entre procesos
Dos procesos pueden intercambiar información.

### Ejemplo
Un proceso descarga datos y otro los muestra en pantalla.

---

## 16. Crear un proceso: ¿qué hace el sistema operativo?

Tu PDF indica que crear un proceso implica varias acciones:

- buscarle identificador
- insertarlo en la tabla de procesos
- determinar prioridad inicial
- implementar su PCB
- asignarle recursos iniciales :contentReference[oaicite:23]{index=23}

### Ejemplo paso a paso
Abres una calculadora.

El sistema operativo hace algo parecido a esto:

1. Le asigna un PID.
2. Crea su PCB.
3. La registra en la tabla de procesos.
4. Le reserva memoria.
5. Le da recursos iniciales.
6. La deja lista para ejecución.

---

## 17. Destruir un proceso

Tu material explica que destruir un proceso es eliminarlo del sistema y borrarlo de tablas o listas del sistema. :contentReference[oaicite:24]{index=24}

### Ejemplo
Cierras el bloc de notas:
- se libera memoria,
- se cierran archivos abiertos,
- se quita de la tabla de procesos.

### Caso especial: procesos hijos
A veces un padre crea hijos.  
Entonces al destruir el padre, depende del sistema qué pasa con los hijos. El PDF menciona que en algunos sistemas se destruyen automáticamente y en otros no. :contentReference[oaicite:25]{index=25}

---

## 18. Foreground y Background

Tu PDF diferencia:

- **Background**: segundo plano, el proceso corre sin interactuar con una terminal interactiva.
- **Foreground**: primer plano, los procesos son interactivos. :contentReference[oaicite:26]{index=26}

### Foreground
Está “al frente”, interactuando contigo.

### Ejemplo
Abres una app y tú la usas directamente.

### Background
Corre detrás, sin molestarte.

### Ejemplo
- actualizador del sistema
- servicio de impresión
- antivirus
- copia de seguridad

En Linux, muchos procesos en segundo plano son servicios o demonios.

---

## 19. Runlevels o niveles de ejecución

Tu PDF muestra los runlevels clásicos:

- **0** apagado
- **1** monousuario
- **2** multiusuario sin red
- **3** multiusuario con red y sin gráfico
- **4** no se usa
- **5** multiusuario con entorno gráfico y red
- **6** reinicio :contentReference[oaicite:27]{index=27}

### ¿Qué significa esto?
Es el modo en el que arranca el sistema.

### Ejemplos simples
- **Runlevel 0**: apagar
- **Runlevel 1**: modo mantenimiento, solo administrador
- **Runlevel 3**: sistema multiusuario con red, pero solo texto
- **Runlevel 5**: sistema normal con entorno gráfico
- **Runlevel 6**: reiniciar

---

## 20. Systemd y targets

Tu PDF también dice que en sistemas modernos como RHEL/CentOS 7+ se reemplaza Init por **systemd**, que es el primer proceso creado por el kernel y tiene **PID = 1**. Además, usa **targets** en lugar de runlevels. :contentReference[oaicite:28]{index=28}

### En simple
Antes se usaban mucho los runlevels clásicos.  
Ahora, en muchos Linux modernos, se trabaja con **targets**.

### Ejemplo
- `multi-user.target` → parecido a modo texto multiusuario
- `graphical.target` → modo gráfico

El PDF también menciona estos comandos:

- `systemctl get-default`
- `systemctl set-default multi-user.target`
- `systemctl isolate multi-user.target` :contentReference[oaicite:29]{index=29}

---

## 21. Resumen con una analogía completa

Imagina una universidad:

- **Programa** = el plan de estudios impreso
- **Proceso** = un curso dictándose en este momento
- **CPU** = el profesor que atiende
- **PCB** = la ficha administrativa del curso
- **Listo** = curso esperando aula/profesor
- **En ejecución** = curso en clase
- **En espera** = curso pausado porque falta proyector
- **Terminado** = curso finalizado
- **PID** = código único del curso
- **PPID** = curso que originó otra actividad relacionada

Esta analogía no es perfecta, pero ayuda bastante.

---

## 22. Lo más importante que debes recordar

### Idea 1
**Programa no es lo mismo que proceso**.  
Programa = archivo.  
Proceso = programa ejecutándose.

### Idea 2
El sistema operativo **administra procesos** todo el tiempo.

### Idea 3
Cada proceso tiene una **ficha de control** llamada **PCB**.

### Idea 4
Un proceso cambia de estado:

`nuevo → listo → ejecución → espera → listo → ejecución → terminado`

### Idea 5
La CPU no alcanza para todos al mismo tiempo, por eso el sistema operativo organiza turnos.

---

## 23. Mini ejemplo final integrando todo

Supón que abres WhatsApp Web en el navegador:

1. El navegador ya era un proceso.
2. Abres una nueva pestaña: el sistema crea o usa procesos asociados.
3. Se le asigna PID.
4. Se crea su PCB.
5. Pasa a listo.
6. Luego a ejecución.
7. Si espera datos de internet, pasa a espera.
8. Cuando llegan, vuelve a listo.
9. La CPU lo atiende otra vez.
10. Cuando cierras el navegador, termina y libera recursos.

---

## 24. Frase corta para examen

**Un proceso es un programa en ejecución administrado por el sistema operativo, el cual controla su estado, recursos, memoria y planificación mediante estructuras como el PCB.**
