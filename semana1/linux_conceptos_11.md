# Semana 11: Gestión de paquetes con APT en Ubuntu

Aquí aprenderás a buscar programas, ver información de un paquete, instalar, actualizar, eliminar y borrar completamente software en Ubuntu usando **APT**, que es la herramienta recomendada para gestionar paquetes en Ubuntu. La documentación oficial también aclara que `apt` está pensado para uso interactivo en terminal.

## Los comandos clave de esta semana son estos:

- `apt search`
- `apt show`
- `apt install`
- `apt remove`
- `apt purge`
- `apt upgrade`

## ¿Qué aprenderás en esta semana?

Vas a aprender a responder preguntas como estas:

- ¿Cómo busco un programa?
- ¿Cómo veo información de un paquete?
- ¿Cómo instalo software?
- ¿Cómo lo desinstalo?
- ¿Cómo lo borro por completo?
- ¿Cómo actualizo lo que ya tengo instalado?

En otras palabras, esta semana trata de **administrar software**. Ubuntu indica justamente que con `apt` puedes instalar software nuevo, actualizar paquetes existentes, actualizar el índice de paquetes y mejorar el sistema.

## Idea principal de la semana

En Ubuntu, la mayoría de programas se instalan desde repositorios.  
APT consulta esos repositorios y trabaja con paquetes.

Piensa así:

- **paquete** = programa listo para instalar
- **APT** = herramienta que busca, instala, actualiza y elimina esos paquetes

## 1. `apt search`

### ¿Qué hace?

Sirve para buscar paquetes por nombre o por palabra relacionada.

### Ejemplo

```bash
apt search nmap
```

Eso busca paquetes relacionados con `nmap`.

### Otro ejemplo

```bash
apt search python
```

Eso mostrará muchos paquetes que tengan relación con Python.

### Explicación fácil

Es como escribir en una tienda:

> “búscame programas relacionados con esto”

La documentación de `apt` incluye `search` entre sus comandos principales para buscar en la lista de paquetes disponibles.

## 2. `apt show`

### ¿Qué hace?

Sirve para ver información detallada de un paquete.

### Ejemplo

```bash
apt show nmap
```

### ¿Qué te puede mostrar?

Te puede enseñar cosas como:

- nombre del paquete
- versión
- tamaño
- descripción
- dependencias

### Explicación fácil

Es como abrir la ficha técnica de un programa antes de instalarlo.

La ayuda oficial de `apt` contempla `show` como el comando para mostrar información detallada de un paquete.

## 3. `apt install`

### ¿Qué hace?

Sirve para instalar un paquete.

### Ejemplo

```bash
sudo apt install nmap
```

Eso instala `nmap`.

### Otro ejemplo

```bash
sudo apt install tree
```

Eso instala `tree`.

### Explicación fácil

Es como decirle a Ubuntu:

> “instálame este programa”

Ubuntu explica que `apt` es la forma recomendada de instalar paquetes Debian en Ubuntu, y muestra `sudo apt install ...` como uso normal.

## 4. `apt remove`

### ¿Qué hace?

Sirve para desinstalar un paquete.

### Ejemplo

```bash
sudo apt remove nmap
```

Eso elimina el programa instalado.

### Pero ojo

Normalmente `remove` quita el paquete, pero puede dejar archivos de configuración.

### Explicación fácil

Es como quitar el programa, pero dejar algunos rastros de configuración.

La documentación de `apt` agrupa `remove` y `purge` como acciones de eliminación, mientras que la documentación de `dpkg` distingue que purgar va más allá y elimina también archivos de configuración conocidos por el sistema.

## 5. `apt purge`

### ¿Qué hace?

Sirve para eliminar el paquete y también sus archivos de configuración.

### Ejemplo

```bash
sudo apt purge nmap
```

### Diferencia con `remove`

- `remove` = quita el programa
- `purge` = quita el programa y su configuración registrada

### Explicación fácil

Si `remove` es “desinstalar”, `purge` es más como “bórralo por completo”.

La documentación de `dpkg` define el purgado como la eliminación del paquete junto con sus archivos de configuración, y `apt` expone `purge` como una de sus acciones de gestión de paquetes.

## 6. `apt upgrade`

### ¿Qué hace?

Sirve para actualizar los paquetes que ya tienes instalados.

### Ejemplo correcto

```bash
sudo apt update
sudo apt upgrade
```

### ¿Por qué van juntos?

Primero:

```bash
sudo apt update
```

actualiza la lista de paquetes disponibles.

Después:

```bash
sudo apt upgrade
```

instala las nuevas versiones disponibles de los paquetes ya instalados.

Ubuntu recomienda precisamente ese orden para actualizar el sistema. Además, el manual de `apt` aclara que `upgrade` instala actualizaciones disponibles de los paquetes instalados; si una actualización requiriera eliminar paquetes ya instalados, ese paquete no se actualiza con `upgrade`.

### Explicación fácil

- `apt update` = refresca el catálogo
- `apt upgrade` = actualiza lo que ya tienes

## Diferencia importante entre varios comandos

### `apt search`

Busca programas.

```bash
apt search curl
```

### `apt show`

Muestra información del paquete.

```bash
apt show curl
```

### `apt install`

Instala.

```bash
sudo apt install curl
```

### `apt remove`

Desinstala, pero puede dejar configuración.

```bash
sudo apt remove curl
```

### `apt purge`

Desinstala y borra configuración registrada.

```bash
sudo apt purge curl
```

### `apt upgrade`

Actualiza programas ya instalados.

```bash
sudo apt update
sudo apt upgrade
```

Todo eso forma parte del flujo normal de gestión de software con APT en Ubuntu.

## Casos reales de uso

### Caso 1: quiero buscar un programa

```bash
apt search nmap
```

### Caso 2: quiero ver qué hace ese paquete

```bash
apt show nmap
```

### Caso 3: quiero instalarlo

```bash
sudo apt install nmap
```

### Caso 4: ya no lo quiero

```bash
sudo apt remove nmap
```

### Caso 5: quiero borrarlo por completo

```bash
sudo apt purge nmap
```

### Caso 6: quiero actualizar mi sistema

```bash
sudo apt update
sudo apt upgrade
```

Ese flujo coincide con el uso recomendado por Ubuntu para instalar, eliminar y actualizar paquetes.

## Práctica guiada de Semana 11

Haz esto paso por paso.

### Paso 1: busca un paquete

```bash
apt search tree
```

Vas a ver resultados relacionados con `tree`.

### Paso 2: revisa su información

```bash
apt show tree
```

Así ves su descripción y datos.

### Paso 3: instálalo

```bash
sudo apt install tree
```

### Paso 4: úsalo

```bash
tree
```

Si se instaló bien, verás tus carpetas en forma de árbol.

### Paso 5: elimínalo

```bash
sudo apt remove tree
```

### Paso 6: bórralo completamente

```bash
sudo apt purge tree
```

### Paso 7: actualiza el sistema

```bash
sudo apt update
sudo apt upgrade
```

Ubuntu documenta exactamente ese patrón para mantener el sistema al día.

## Error común que debes evitar

Mucha gente cree que:

```bash
sudo apt update
```

ya actualiza los programas.

Pero no.  
`apt update` solo actualiza la lista de paquetes disponibles.  
Para instalar actualizaciones reales necesitas usar después `apt upgrade`. Eso lo aclaran tanto la documentación oficial de Ubuntu como el manual de `apt`.

## Resumen rápido de la Semana 11

- `apt search` → buscar paquetes
- `apt show` → ver información detallada
- `apt install` → instalar
- `apt remove` → desinstalar
- `apt purge` → desinstalar y borrar configuración registrada
- `apt upgrade` → actualizar paquetes instalados

## Resumen todavía más fácil

### `search`

Buscar

### `show`

Ver detalles

### `install`

Instalar

### `remove`

Quitar

### `purge`

Quitar completamente

### `upgrade`

Actualizar
