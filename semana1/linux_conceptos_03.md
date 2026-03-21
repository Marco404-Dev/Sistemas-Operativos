# Ruta de aprendizaje Linux

## Semana 3: Usuarios, permisos y paquetes

En esta semana aprenderás a entender **quién eres dentro del sistema**, qué puedes hacer, qué cosas necesitan permisos especiales y cómo instalar programas en Ubuntu.

### 1. `whoami`

Significa **who am I**.  
Sirve para mostrar **el nombre del usuario actual** con el que estás trabajando.

#### Ejemplo

```bash
whoami
```

#### Posible salida

```bash
marco
```

#### Explicación sencilla

Es como preguntarle a Linux:

**“¿Quién soy dentro del sistema?”**

---

### 2. `sudo`

Sirve para ejecutar un comando con permisos de administrador.

#### Ejemplo

```bash
sudo apt update
```

#### ¿Qué pasa cuando lo usas?

Linux te pedirá tu contraseña.

#### Importante

Cuando escribes la contraseña, no se ve nada en pantalla.  
No aparecen puntitos ni estrellas, pero sí se está escribiendo.

#### Explicación sencilla

Es como decirle al sistema:

**“Haz esto como administrador.”**

---

### 3. `chmod`

Sirve para cambiar permisos de archivos o carpetas.

En Linux, los permisos más importantes son:

- `r` = read = leer
- `w` = write = escribir
- `x` = execute = ejecutar

#### Ejemplo sencillo

```bash
chmod +x script.sh
```

Esto le da permiso de ejecución al archivo `script.sh`.

Ahora se podría ejecutar así:

```bash
./script.sh
```

#### Otro ejemplo

```bash
chmod 644 nota.txt
```

#### ¿Qué significa `644`?

- el dueño puede leer y escribir
- los demás solo pueden leer

#### Explicación sencilla

Es como decidir:

- quién puede abrir un archivo
- quién puede modificarlo
- quién puede ejecutarlo

---

### 4. `apt update`

Sirve para actualizar la lista de paquetes disponibles en Ubuntu.

#### Ejemplo

```bash
sudo apt update
```

#### Importante

Este comando no instala nada.  
Solo actualiza el catálogo de programas disponibles.

#### Explicación sencilla

Es como refrescar una tienda para ver qué programas hay disponibles.

---

### 5. `apt install`

Sirve para instalar programas en Ubuntu.

#### Ejemplo

```bash
sudo apt install nmap
```

Esto instala el programa `nmap`.

#### Otro ejemplo

```bash
sudo apt install tree
```

Esto instala `tree`.

#### Explicación sencilla

Es como descargar e instalar una aplicación desde la tienda oficial de Ubuntu.

---

## Resumen de la Semana 3

- `whoami` → muestra qué usuario eres
- `sudo` → ejecuta como administrador
- `chmod` → cambia permisos
- `apt update` → actualiza la lista de programas
- `apt install` → instala programas
