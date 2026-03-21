## Semana 5: Búsqueda y ayuda

### ¿Qué aprenderás en esta semana?

Vas a aprender a responder preguntas como estas:

- ¿Dónde está este archivo?
- ¿En qué archivo aparece esta palabra?
- ¿Cómo funciona este comando?
- ¿Qué comandos usé antes?
- ¿Dónde está instalado un programa?

O sea, esta semana trata de **búsqueda y ayuda**.

---

### 1. `find`

#### ¿Qué hace?

Sirve para buscar archivos o carpetas.

Piensa así:

**`find` = “búscame algo dentro del sistema”**

#### Ejemplo básico

```bash
find ~ -name "hola.txt"
```

#### ¿Qué significa?

- `find` → buscar
- `~` → desde tu carpeta personal
- `-name "hola.txt"` → buscar algo que se llame exactamente `hola.txt`

#### Ejemplo real

Supongamos que no recuerdas dónde guardaste un archivo llamado `tarea.txt`.

Entonces escribes:

```bash
find ~ -name "tarea.txt"
```

Y Linux te puede responder algo como:

```bash
/home/usuario/Documentos/tarea.txt
```

Eso significa que el archivo está en esa ruta.

#### Buscar todos los `.txt`

```bash
find ~ -name "*.txt"
```

Esto busca todos los archivos que terminen en `.txt`.

#### Ejemplo

Te puede mostrar:

```bash
/home/usuario/Documentos/nota.txt
/home/usuario/Descargas/lista.txt
/home/usuario/practica/hola.txt
```

#### Buscar carpetas

```bash
find ~ -type d -name "Documentos"
```

#### ¿Qué significa?

- `-type d` → buscar directorios, o sea carpetas

#### Buscar archivos solamente

```bash
find ~ -type f -name "*.py"
```

#### ¿Qué significa?

- `-type f` → buscar archivos
- `"*.py"` → que terminen en `.py`

#### Explicación fácil

`find` es como cuando en Windows usas el buscador del explorador, pero aquí lo haces por terminal.

---

### 2. `grep`

#### ¿Qué hace?

Sirve para buscar una palabra o texto dentro de un archivo.

Piensa así:

**`grep` no busca archivos por nombre, sino palabras dentro del contenido.**

#### Ejemplo básico

```bash
grep "hola" archivo.txt
```

#### ¿Qué hace?

Busca la palabra `hola` dentro de `archivo.txt`.

Si el archivo tiene esto:

```txt
hola mundo
me gusta linux
hola otra vez
```

Entonces el resultado sería:

```txt
hola mundo
hola otra vez
```

Porque te muestra las líneas donde aparece `hola`.

#### Ejemplo con mayúsculas y minúsculas

```bash
grep -i "linux" archivo.txt
```

#### ¿Qué hace `-i`?

Ignora si está en mayúscula o minúscula.

Entonces encuentra:

```txt
linux
Linux
LINUX
```

#### Ejemplo mostrando número de línea

```bash
grep -n "hola" archivo.txt
```

#### Resultado posible

```txt
1:hola mundo
3:hola otra vez
```

Eso te dice que aparece en la línea 1 y en la línea 3.

#### Buscar en varios archivos

```bash
grep "python" *.txt
```

Busca la palabra `python` en todos los archivos `.txt` de esa carpeta.

#### Explicación fácil

`grep` es como usar **Ctrl + B** o **buscar** dentro de un documento, pero desde terminal.

---

### Diferencia entre `find` y `grep`

Esto es muy importante:

- `find` busca archivos o carpetas
- `grep` busca palabras dentro de archivos

#### Ejemplo

- “quiero encontrar el archivo `nota.txt`” → `find`
- “quiero encontrar la palabra `Linux` dentro de `nota.txt`” → `grep`

---

### 3. `man`

#### ¿Qué hace?

Sirve para ver el manual de un comando.

Piensa así:

**`man` = “explícame cómo funciona este comando”**

#### Ejemplo

```bash
man ls
```

Esto abre el manual del comando `ls`.

Ahí verás:

- qué hace
- cómo se usa
- qué opciones tiene

#### Otro ejemplo

```bash
man grep
```

Te enseña toda la ayuda sobre `grep`.

#### Cómo salir de `man`

Presiona:

```bash
q
```

#### Explicación fácil

`man` es como el libro de instrucciones de Linux.

#### ¿Cuándo usarlo?

Cuando se te olvida:

- qué hace un comando
- qué opción usar
- cómo se escribe correctamente

---

### 4. `history`

#### ¿Qué hace?

Muestra los comandos que has escrito antes.

#### Ejemplo

```bash
history
```

#### Resultado posible

```bash
1  pwd
2  ls
3  cd Documentos
4  nano nota.txt
5  cat nota.txt
```

Eso significa que esos comandos los usaste anteriormente.

#### ¿Para qué sirve?

Sirve para:

- recordar comandos
- repetir algo que ya hiciste
- ver errores pasados
- aprender de lo que has practicado

#### Truco útil

Puedes combinarlo con `grep`:

```bash
history | grep nano
```

#### ¿Qué hace?

Busca en tu historial todos los comandos donde usaste `nano`.

#### Ejemplo de salida

```bash
15 nano nota.txt
22 nano tarea.txt
30 nano prueba.py
```

#### Explicación fácil

`history` es como el historial de búsqueda, pero de tus comandos.

---

### 5. `which`

#### ¿Qué hace?

Sirve para mostrar dónde está instalado un comando o programa.

#### Ejemplo

```bash
which python3
```

#### Posible salida

```bash
/usr/bin/python3
```

Eso significa que `python3` está en esa ruta.

#### Otro ejemplo

```bash
which ls
```

#### Posible salida

```bash
/usr/bin/ls
```

#### ¿Para qué sirve?

Sirve para:

- confirmar si un programa existe
- saber en qué ruta está
- entender qué ejecuta Linux cuando escribes un comando

#### Explicación fácil

Es como preguntarle al sistema:

**“Cuando escribo este comando, ¿de dónde lo estás sacando?”**

---

## Resumen rápido de la Semana 5

- `find` → busca archivos o carpetas
- `grep` → busca palabras dentro de archivos
- `man` → muestra el manual de un comando
- `history` → muestra comandos usados antes
- `which` → muestra dónde está instalado un comando
