# Semana 10: Servicios y logs del sistema en Linux

Aquí ya entras a una parte más “de administrador”. La idea es aprender a controlar servicios, o sea, programas que el sistema mantiene corriendo en segundo plano, como red, SSH, impresión, audio, etc.

En Ubuntu moderno, el comando principal para eso es `systemctl`, que controla el gestor de servicios `systemd`. También existe `service`, que sigue siendo útil como interfaz para scripts de servicio en Ubuntu. Para revisar registros, se usa `journalctl`, que consulta el journal de `systemd-journald`.

## Los comandos clave de esta semana son estos:

- `systemctl`
- `service`
- `journalctl`

## ¿Qué aprenderás en esta semana?

Vas a aprender a responder preguntas como estas:

- ¿Cómo veo si un servicio está activo?
- ¿Cómo inicio o detengo un servicio?
- ¿Cómo hago que un servicio arranque al encender la PC?
- ¿Cómo veo errores o logs del sistema?

Todo eso entra en servicios del sistema y registros.

## Idea principal de la semana

Un servicio es un proceso que el sistema controla y supervisa. En `systemd`, un archivo que termina en `.service` describe información sobre un proceso controlado y supervisado por `systemd`. Por eso verás nombres como `ssh.service`, `NetworkManager.service` o `cron.service`.

## 1. `systemctl`

### ¿Qué hace?

`systemctl` sirve para inspeccionar y controlar el estado del sistema y del gestor de servicios `systemd`. Es el comando más importante de esta semana.

### Ver el estado de un servicio

```bash
systemctl status ssh
```

Esto te muestra si el servicio está:

- activo
- inactivo
- fallando

Y algunos datos extra, como PID y mensajes recientes. `status` es uno de los usos más comunes de `systemctl`.

### Explicación fácil

Es como preguntarle al sistema:

> “¿Este servicio está funcionando o no?”

### Iniciar un servicio

```bash
sudo systemctl start ssh
```

Esto intenta encender el servicio `ssh`. `start`, `stop` y `status` son acciones típicas que `systemd` permite hacer sobre servicios.

### Explicación fácil

Es como prender un motor.

### Detener un servicio

```bash
sudo systemctl stop ssh
```

Esto detiene el servicio.

### Explicación fácil

Es como apagar ese motor.

### Reiniciar un servicio

```bash
sudo systemctl restart ssh
```

Esto lo apaga y lo vuelve a iniciar. Reiniciar es útil cuando cambias una configuración y quieres que el servicio la vuelva a leer. `service` también contempla acciones como `start`, `stop` y reinicios.

### Explicación fácil

Es como apagar y volver a prender para que “agarre” los cambios.

### Hacer que arranque al encender la PC

```bash
sudo systemctl enable ssh
```

Con `enable`, el servicio queda configurado para iniciarse en el arranque del sistema. Los nombres de unidades o aliases pueden usarse en comandos como `enable`, `start`, `stop` y `status`.

### Lo contrario

```bash
sudo systemctl disable ssh
```

Esto evita que se inicie automáticamente al arrancar.

### Explicación fácil

- `enable` = “préndete solo al iniciar”
- `disable` = “no te prendas solo”

### Ver servicios fallando

```bash
systemctl --state=failed
```

La documentación de `systemctl` indica que al listar unidades puedes filtrar por estado, incluyendo `failed`. Eso sirve para detectar servicios que arrancaron mal o se cayeron.

### Explicación fácil

Es como pedirle al sistema:

> “Muéstrame lo que está roto.”

## 2. `service`

### ¿Qué hace?

`service` es una herramienta de Ubuntu para ejecutar scripts de servicio de tipo System V en `/etc/init.d/`. Sus comandos mínimos suelen incluir `start` y `stop`, y también puede usarse para acciones como `status` o `--full-restart`, según el script.

### Ejemplo

```bash
sudo service ssh status
sudo service ssh start
sudo service ssh stop
sudo service ssh restart
```

Estos comandos hacen lo mismo que sus equivalentes más modernos con `systemctl`, pero `systemctl` es el comando central cuando trabajas con `systemd`. `service` todavía es útil porque simplifica el manejo de ciertos scripts tradicionales.

### Explicación fácil

`service` es una forma más clásica y simple de decir:

> “maneja este servicio”

## 3. `journalctl`

### ¿Qué hace?

`journalctl` sirve para consultar los logs almacenados por el journal de `systemd`, que escribe `systemd-journald`. Si lo ejecutas sin parámetros, muestra el contenido del journal accesible para tu usuario, empezando por las entradas más antiguas.

### Ver logs generales

```bash
journalctl
```

Muestra muchos mensajes del sistema: arranques, errores, servicios, kernel, etc.

### Explicación fácil

Es como abrir el cuaderno donde Linux anota lo que va pasando.

### Ver logs del arranque actual

```bash
journalctl --boot
```

La documentación de `journalctl` indica que puedes usar restricciones como `--boot` para limitar qué entradas quieres ver. Eso te ayuda a revisar solo lo ocurrido en el arranque actual.

### Explicación fácil

Es como decir:

> “Muéstrame solo lo que pasó desde que prendí la máquina.”

### Ver logs de un servicio específico

```bash
journalctl --unit=ssh
```

o también:

```bash
journalctl -u ssh
```

`journalctl` permite filtrar por unidad con `--unit=`. Así revisas solo los mensajes relacionados con un servicio concreto.

### Explicación fácil

Es como abrir el cuaderno, pero solo en la sección de un servicio.

### Seguir logs en tiempo real

```bash
journalctl -f
```

Eso te deja viendo nuevas entradas a medida que van apareciendo, parecido a seguir un log “en vivo”. `journalctl` está pensado precisamente para inspeccionar logs anteriores o ver nuevas entradas mientras se registran.

### Para salir

Presionas:

```text
Ctrl + C
```

### Explicación fácil

Es como mirar una cámara en vivo de los mensajes del sistema.

## Flujo típico de trabajo

Imagina que un servicio no funciona.

### Paso 1: ver su estado

```bash
systemctl status ssh
```

### Paso 2: si está detenido, iniciarlo

```bash
sudo systemctl start ssh
```

### Paso 3: si falla, mirar sus logs

```bash
journalctl -u ssh
```

Ese es el flujo más común: estado → acción → revisión de logs. `systemctl` controla el servicio y `journalctl` muestra el historial de mensajes relacionado con él.

## Ejemplos reales y sencillos

### Ver si SSH está activo

```bash
systemctl status ssh
```

### Iniciar SSH

```bash
sudo systemctl start ssh
```

### Hacer que SSH inicie automáticamente

```bash
sudo systemctl enable ssh
```

### Ver logs del servicio SSH

```bash
journalctl -u ssh
```

### Ver logs solo del arranque actual

```bash
journalctl --boot
```

### Seguir logs en vivo

```bash
journalctl -f
```

Todos esos usos corresponden al control de servicios con `systemctl` y a la consulta del journal con `journalctl`.

## Práctica guiada de Semana 10

Haz esto paso por paso.

### Paso 1: revisa un servicio conocido

```bash
systemctl status ssh
```

Si no tienes `ssh`, prueba con otro como `cron` o `NetworkManager`, porque `systemctl status` funciona con cualquier unidad de servicio disponible.

### Paso 2: prueba la interfaz clásica

```bash
sudo service ssh status
```

Así comparas `service` con `systemctl`. `service` sigue siendo una interfaz válida para acciones como `start`, `stop` y `status`.

### Paso 3: mira el journal general

```bash
journalctl
```

Vas a ver muchos mensajes, porque el journal recopila y almacena datos de logging del sistema.

### Paso 4: filtra por arranque

```bash
journalctl --boot
```

Así no te pierdes entre logs de otros reinicios.

### Paso 5: filtra por un servicio

```bash
journalctl -u ssh
```

Eso te deja concentrarte solo en ese servicio.

### Paso 6: sigue los logs en vivo

```bash
journalctl -f
```

Y sales con `Ctrl + C`.

## Diferencia fácil entre los tres comandos

### `systemctl`

Controla servicios y su estado.

### `service`

Forma más clásica de manejar ciertos servicios o scripts.

### `journalctl`

Lee y filtra logs del sistema.
