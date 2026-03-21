## Semana 4: Procesos y red

En esta semana aprenderás a ver qué está corriendo en el sistema y cómo revisar la red.

### 1. `ps`

Sirve para ver procesos en ejecución.

#### Ejemplo

```bash
ps
```

#### ¿Qué es un proceso?

Un proceso es un programa que se está ejecutando.

#### Más útil

```bash
ps aux
```

Muestra muchos procesos del sistema.

#### Explicación sencilla

Es como ver una lista de los programas que están funcionando.

---

### 2. `top`

Sirve para ver procesos en tiempo real.

#### Ejemplo

```bash
top
```

#### ¿Qué muestra?

- uso de CPU
- uso de memoria
- procesos activos
- información del sistema en vivo

#### Para salir

Presiona:

```bash
q
```

#### Explicación sencilla

Es como el Administrador de tareas de Windows, pero en la terminal.

---

### 3. `kill`

Sirve para detener un proceso usando su PID.

PID significa: **Process ID**, o sea, el número del proceso.

#### Ejemplo

```bash
kill 1234
```

Eso intenta cerrar el proceso con PID `1234`.

#### Forma más fuerte

```bash
kill -9 1234
```

Eso lo obliga a cerrarse.

#### Importante

No uses `-9` a cada rato.  
Primero prueba con `kill` normal.

#### Explicación sencilla

Es como cerrar un programa usando su número interno.

---

### 4. `ping`

Sirve para comprobar si hay conexión con otra máquina o con internet.

#### Ejemplo

```bash
ping google.com
```

#### Otro ejemplo

```bash
ping 8.8.8.8
```

#### Para detenerlo

Presiona:

```bash
Ctrl + C
```

#### Explicación sencilla

Es como preguntarle a otra máquina:

**“¿Estás ahí?”**

Si responde, hay conexión.

---

### 5. `ip`

Sirve para ver información de red de tu sistema.

#### Ejemplo útil

```bash
ip a
```

Muestra direcciones IP e interfaces de red.

#### Otro ejemplo

```bash
ip route
```

Muestra rutas de red.

#### Explicación sencilla

Es como revisar cómo está conectada tu computadora a la red.

---

### 6. `ss`

Sirve para ver puertos y conexiones de red.

#### Ejemplo

```bash
ss
```

#### Más útil

```bash
ss -tuln
```

#### ¿Qué muestra?

- puertos TCP
- puertos UDP
- qué servicios están escuchando
- conexiones de red

#### Explicación sencilla

Te permite ver qué programas están usando la red o esperando conexiones.

---

## ¿Qué practicarás?

- ver procesos
- monitorear el sistema en vivo
- ver tu IP
- comprobar conexión
- revisar puertos abiertos

---

## Resumen de la Semana 4

- `ps` → muestra procesos
- `top` → muestra procesos en tiempo real
- `kill` → cierra procesos
- `ping` → prueba conexión
- `ip` → muestra información de red
- `ss` → muestra puertos y conexiones
