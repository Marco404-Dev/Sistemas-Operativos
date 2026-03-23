# Semana 9: Procesos en segundo plano en Linux

Aquí aprenderás a hacer algo muy útil en Linux: ejecutar tareas sin quedarte “pegado” esperando en la terminal.

## Los comandos clave de esta semana son:

- `jobs`
- `&`
- `bg`
- `fg`
- `nohup`

## ¿Qué aprenderás en esta semana?

Vas a aprender a responder preguntas como estas:

- ¿Cómo ejecuto un programa sin bloquear mi terminal?
- ¿Cómo mando un proceso al fondo?
- ¿Cómo recupero un proceso que dejé en segundo plano?
- ¿Cómo dejo un proceso corriendo aunque cierre la terminal?

## Idea principal de la semana

Normalmente, cuando ejecutas un comando en Linux, la terminal queda ocupada hasta que ese comando termine.

Por ejemplo:

```bash
ping google.com
```

Ese comando sigue funcionando y la terminal queda ocupada.  
No puedes usarla cómodamente hasta detenerlo con `Ctrl + C`.

Pero a veces quieres:

- que siga ejecutándose
- y tú seguir usando la terminal

Ahí entran los procesos en segundo plano.

## 1. `&`

### ¿Qué hace?

Sirve para ejecutar un comando en segundo plano desde el inicio.

### Ejemplo básico

```bash
gedit &
```

### ¿Qué pasa?

- se abre `gedit`
- pero tu terminal no queda bloqueada
- puedes seguir escribiendo otros comandos

### Otro ejemplo

```bash
firefox &
```

Abre Firefox en segundo plano y la terminal sigue libre.

### Explicación fácil

El `&` significa algo como:

> “ejecuta esto, pero déjame seguir usando la terminal.”

## 2. `jobs`

### ¿Qué hace?

Muestra los trabajos que tienes corriendo en segundo plano o suspendidos en esa terminal.

### Ejemplo

```bash
jobs
```

### Posible salida

```text
[1]+  Running                 gedit &
```

Eso significa:

- trabajo número 1
- está corriendo
- el comando fue `gedit`

### Explicación fácil

`jobs` es como mirar la lista de tareas que dejaste abiertas en esa terminal.

## 3. `Ctrl + Z`

Aunque no es un comando escrito, es muy importante en esta semana.

### ¿Qué hace?

Suspende el proceso actual.

### Ejemplo

Supón que escribes:

```bash
ping google.com
```

Como se queda ejecutando, presionas:

```text
Ctrl + Z
```

Entonces Linux lo pausa.

### Posible salida

```text
[1]+  Stopped                 ping google.com
```

Ahora el proceso ya no está ocupando activamente la terminal.

### Explicación fácil

`Ctrl + Z` es como poner un programa en pausa.

## 4. `bg`

### ¿Qué hace?

Toma un proceso suspendido y lo manda a ejecutarse en segundo plano.

### Ejemplo

Si hiciste esto:

```bash
ping google.com
```

y luego:

```text
Ctrl + Z
```

puedes escribir:

```bash
bg
```

Entonces el proceso continúa, pero ahora en segundo plano.

### Posible salida

```text
[1]+ ping google.com &
```

### Explicación fácil

`bg` significa:

> “sigue trabajando, pero allá atrás.”

## 5. `fg`

### ¿Qué hace?

Trae un proceso en segundo plano otra vez al primer plano.

### Ejemplo

```bash
fg
```

Entonces el proceso vuelve a ocupar tu terminal.

### Si tienes varios trabajos

Puedes indicar cuál quieres traer:

```bash
fg %1
```

Eso trae el trabajo número 1.

### Explicación fácil

`fg` significa:

> “ven otra vez al frente.”

## 6. `nohup`

### ¿Qué hace?

Permite ejecutar un proceso para que siga corriendo incluso si cierras la terminal.

Esto es muy útil cuando quieres dejar algo trabajando por bastante tiempo.

### Ejemplo básico

```bash
nohup ping google.com &
```

### ¿Qué pasa?

- el proceso se ejecuta en segundo plano
- si cierras la terminal, puede seguir corriendo
- normalmente guarda salida en un archivo llamado `nohup.out`

### Explicación fácil

`nohup` significa algo como:

> “no te detengas aunque cierre esta terminal.”

## Diferencia importante entre `&` y `nohup`

### `&`

Manda el proceso al fondo, pero normalmente depende de la terminal actual.

### `nohup`

Hace que el proceso pueda seguir incluso si cierras la terminal.

### Ejemplo comparativo

#### Solo segundo plano

```bash
gedit &
```

#### Segundo plano y resistente al cierre de terminal

```bash
nohup python3 script.py &
```

## Ejemplos sencillos de uso real

### Caso 1: abrir un programa sin bloquear la terminal

```bash
gedit &
```

### Caso 2: ver los trabajos actuales

```bash
jobs
```

### Caso 3: pausar un proceso actual

Ejecutas algo:

```bash
ping google.com
```

Luego presionas:

```text
Ctrl + Z
```

### Caso 4: mandarlo al fondo

```bash
bg
```

### Caso 5: traerlo otra vez

```bash
fg
```

### Caso 6: dejar un proceso corriendo aunque cierres terminal

```bash
nohup ping google.com &
```

## Flujo típico para entenderlo mejor

Haz de cuenta que ejecutas:

```bash
ping google.com
```

La terminal queda ocupada.

Entonces haces:

```text
Ctrl + Z
```

Ahora está suspendido.

Luego escribes:

```bash
bg
```

Ahora sigue ejecutándose, pero en segundo plano.

Si quieres verlo otra vez al frente:

```bash
fg
```

## Práctica guiada de Semana 9

Haz esto paso a paso.

### Paso 1: abre un proceso largo

```bash
ping 8.8.8.8
```

Eso empezará a enviar paquetes continuamente.

### Paso 2: suspéndelo

Presiona:

```text
Ctrl + Z
```

Ahora debería aparecer algo como:

```text
[1]+  Stopped                 ping 8.8.8.8
```

### Paso 3: revisa los trabajos

```bash
jobs
```

Deberías ver el trabajo suspendido.

### Paso 4: mándalo al fondo

```bash
bg
```

Ahora el proceso seguirá ejecutándose en segundo plano.

### Paso 5: revisa otra vez

```bash
jobs
```

Ahora debería aparecer como `Running`.

### Paso 6: tráelo al frente

```bash
fg
```

Ahora vuelve a ocupar la terminal.

### Paso 7: deténlo completamente

Presiona:

```text
Ctrl + C
```

Eso sí lo termina.

## Práctica con `nohup`

Prueba esto:

```bash
nohup ping 8.8.8.8 &
```

Luego:

```bash
jobs
```

Y también puedes ver el archivo de salida:

```bash
cat nohup.out
```

## Diferencia entre detener, suspender y mandar al fondo

### `Ctrl + C`

Termina el proceso.

### `Ctrl + Z`

Lo suspende, lo pausa.

### `bg`

Lo reanuda en segundo plano.

### `fg`

Lo trae de vuelta al frente.

## Resumen rápido de la Semana 9

- `&` → ejecuta un comando en segundo plano
- `jobs` → muestra trabajos actuales
- `Ctrl + Z` → suspende el trabajo actual
- `bg` → reanuda un trabajo en segundo plano
- `fg` → trae un trabajo al primer plano
- `nohup` → deja un proceso corriendo aunque cierres la terminal

## Resumen todavía más fácil

### `&`

Hazlo atrás.

### `jobs`

¿Qué tengo corriendo?

### `Ctrl + Z`

Pausa.

### `bg`

Sigue atrás.

### `fg`

Vuelve al frente.

### `nohup`

Sigue aunque cierre la terminal.
