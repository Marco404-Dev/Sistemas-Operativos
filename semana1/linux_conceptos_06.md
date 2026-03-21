## Semana 6: Empaquetado y compresión

### ¿Qué aprenderás en esta semana?

Vas a aprender a responder preguntas como estas:

- ¿Cómo junto muchos archivos en uno?
- ¿Cómo comprimo una carpeta?
- ¿Cómo abro un archivo comprimido?
- ¿Qué diferencia hay entre empaquetar y comprimir?

---

### Idea importante antes de empezar

Hay dos conceptos que suelen confundirse:

#### 1. Empaquetar

Es juntar varios archivos en uno solo.

Ejemplo:

- tienes 10 archivos
- los conviertes en 1 solo archivo grande

Eso no siempre reduce el tamaño.

#### 2. Comprimir

Es hacer que ocupe menos espacio.

Ejemplo:

- un archivo pesa mucho
- se comprime para que pese menos

#### Ejemplo fácil

Piensa así:

- **empaquetar** = meter varias hojas en una sola carpeta
- **comprimir** = apretar esa carpeta para que ocupe menos espacio

---

### 1. `tar`

#### ¿Qué hace?

Sirve para empaquetar varios archivos o carpetas en uno solo.

Muy usado en Linux.

#### Ejemplo básico

```bash
tar -cvf respaldo.tar carpeta/
```

#### ¿Qué significa?

- `tar` → comando
- `-c` → create = crear
- `-v` → verbose = mostrar lo que va haciendo
- `-f` → file = indicar el nombre del archivo
- `respaldo.tar` → nombre del archivo empaquetado
- `carpeta/` → lo que quieres guardar dentro

#### Resultado

Se crea un archivo llamado:

```bash
respaldo.tar
```

Ese archivo contiene todo lo que había dentro de `carpeta/`.

#### Explicación fácil

Es como meter una carpeta completa dentro de una caja.

#### Extraer un `.tar`

```bash
tar -xvf respaldo.tar
```

#### ¿Qué significa?

- `-x` → extract = extraer
- `-v` → mostrar lo que hace
- `-f` → archivo

Esto saca todo lo que estaba dentro del `.tar`.

#### Explicación fácil

Es como abrir la caja y sacar lo que guardaste.

---

### 2. `zip`

#### ¿Qué hace?

Sirve para comprimir archivos o carpetas en formato `.zip`.

Este formato es muy común porque también se usa en Windows.

#### Ejemplo básico con un archivo

```bash
zip archivo.zip nota.txt
```

Esto crea un archivo comprimido llamado `archivo.zip` que contiene `nota.txt`.

#### Ejemplo con varios archivos

```bash
zip varios.zip a.txt b.txt c.txt
```

Eso junta y comprime esos tres archivos.

#### Comprimir una carpeta

Para carpetas suele usarse `-r`:

```bash
zip -r proyecto.zip proyecto/
```

#### ¿Qué hace?

- `-r` → recursive = incluir todo lo que hay dentro de la carpeta

#### Explicación fácil

Es como crear un archivo comprimido para enviarlo por correo o guardarlo mejor.

---

### 3. `unzip`

#### ¿Qué hace?

Sirve para descomprimir archivos `.zip`.

#### Ejemplo básico

```bash
unzip archivo.zip
```

Esto extrae el contenido de `archivo.zip`.

#### Explicación fácil

Es como abrir un archivo comprimido y sacar lo que tiene dentro.

---

### 4. `gzip`

#### ¿Qué hace?

Sirve para comprimir un archivo individual.

**Ojo:** normalmente `gzip` comprime un archivo, no una carpeta completa.

#### Ejemplo básico

```bash
gzip texto.txt
```

#### ¿Qué pasa?

`texto.txt` se convierte en:

```bash
texto.txt.gz
```

#### Importante

Después de comprimir, el archivo original normalmente desaparece y queda el comprimido.

#### Explicación fácil

Es como agarrar un archivo y hacerlo más pequeño.

---

### 5. `gunzip`

#### ¿Qué hace?

Sirve para descomprimir archivos `.gz`.

#### Ejemplo

```bash
gunzip texto.txt.gz
```

#### ¿Qué pasa?

Regresa al archivo original:

```bash
texto.txt
```

#### Explicación fácil

Es como deshacer la compresión de `gzip`.

---

### Diferencia importante: `tar`, `zip` y `gzip`

Esto es clave para no confundirte.

#### `tar`

- junta varios archivos o carpetas
- normalmente empaqueta
- no siempre comprime por sí solo

#### `zip`

- empaqueta y comprime
- muy común para compartir archivos

#### `gzip`

- comprime un archivo individual
- muy usado en Linux

---

### Combinación muy común: `tar + gzip`

En Linux es muy común ver archivos como:

```bash
archivo.tar.gz
```

Eso significa:

- primero se empaquetó con `tar`
- luego se comprimió con `gzip`

#### Crear un `.tar.gz`

```bash
tar -czvf respaldo.tar.gz carpeta/
```

#### ¿Qué significa?

- `-c` → crear
- `-z` → usar gzip
- `-v` → mostrar proceso
- `-f` → nombre del archivo

Esto crea un archivo comprimido y empaquetado al mismo tiempo.

#### Extraer un `.tar.gz`

```bash
tar -xzvf respaldo.tar.gz
```

#### ¿Qué significa?

- `-x` → extraer
- `-z` → descomprimir con gzip
- `-v` → mostrar proceso
- `-f` → archivo

#### Explicación fácil

Es como:

- meter varios archivos en una caja
- cerrar la caja
- y además aplastarla para que ocupe menos espacio

---

### Ejemplos sencillos

#### Caso 1: quiero guardar una carpeta completa

```bash
tar -cvf tareas.tar tareas/
```

#### Caso 2: quiero abrir ese archivo

```bash
tar -xvf tareas.tar
```

#### Caso 3: quiero hacer un zip

```bash
zip -r tareas.zip tareas/
```

#### Caso 4: quiero abrir un zip

```bash
unzip tareas.zip
```

#### Caso 5: quiero comprimir solo un archivo

```bash
gzip notas.txt
```

#### Caso 6: quiero recuperarlo

```bash
gunzip notas.txt.gz
```

---

### Práctica guiada de Semana 6

Haz esto paso por paso.

#### Paso 1: crea una carpeta de práctica

```bash
mkdir semana6
cd semana6
mkdir proyecto
touch proyecto/a.txt proyecto/b.txt proyecto/c.txt
ls proyecto
```

#### Paso 2: empaqueta la carpeta con `tar`

```bash
tar -cvf proyecto.tar proyecto/
```

Luego verifica:

```bash
ls
```

Deberías ver `proyecto.tar`.

#### Paso 3: extrae el `.tar`

```bash
tar -xvf proyecto.tar
```

#### Paso 4: crea un `.zip`

```bash
zip -r proyecto.zip proyecto/
```

Luego revisa:

```bash
ls
```

#### Paso 5: descomprime el `.zip`

```bash
unzip proyecto.zip
```

#### Paso 6: comprime un archivo con `gzip`

```bash
gzip proyecto/a.txt
```

Luego revisa:

```bash
ls proyecto
```

Ahora deberías ver algo como:

```bash
a.txt.gz
b.txt
c.txt
```

#### Paso 7: descomprime con `gunzip`

```bash
gunzip proyecto/a.txt.gz
```

Luego revisa otra vez:

```bash
ls proyecto
```

---

## Resumen rápido de la Semana 6

- `tar` → empaqueta archivos o carpetas
- `tar -xvf` → extrae un `.tar`
- `zip` → comprime en formato `.zip`
- `unzip` → descomprime `.zip`
- `gzip` → comprime un archivo
- `gunzip` → descomprime un `.gz`

---

## Resumen todavía más fácil

### `tar`

Junta muchas cosas en un solo archivo.

### `zip`

Junta y comprime.

### `gzip`

Comprime un archivo individual.

### `unzip` y `gunzip`

Descomprimen.

---

## Mini comparación para no olvidarte

### Si quieres guardar una carpeta completa

Usa:

```bash
tar -cvf archivo.tar carpeta/
```

### Si quieres comprimir algo en formato conocido

Usa:

```bash
zip -r archivo.zip carpeta/
```

### Si quieres comprimir un solo archivo rápido

Usa:

```bash
gzip archivo.txt
```
