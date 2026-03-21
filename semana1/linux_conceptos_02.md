## Semana 2: Manejo de archivos

En esta semana aprenderás a copiar, mover, borrar, leer y editar archivos.

### 1. `cp`

Significa **copy**.  
Sirve para copiar archivos o carpetas.

#### Ejemplo

```bash
cp nota.txt copia_nota.txt
```

Esto copia `nota.txt` y crea `copia_nota.txt`.

#### Copiar a otra carpeta

```bash
cp nota.txt Documentos/
```

#### Copiar carpetas

```bash
cp -r carpeta1 carpeta2
```

#### Explicación sencilla

Es como hacer una fotocopia.

---

### 2. `mv`

Significa **move**.  
Sirve para mover archivos o también renombrarlos.

#### Mover

```bash
mv nota.txt Documentos/
```

#### Renombrar

```bash
mv nota.txt apuntes.txt
```

#### Explicación sencilla

Sirve para:

- cambiar un archivo de lugar
- cambiarle el nombre

---

### 3. `rm`

Significa **remove**.  
Sirve para borrar archivos.

#### Ejemplo

```bash
rm nota.txt
```

#### Para borrar carpetas

```bash
rm -r carpeta1
```

#### Importante

Debes tener cuidado, porque `rm` borra directamente.

#### Explicación sencilla

Es como un borrador fuerte.

---

### 4. `cat`

Sirve para mostrar el contenido de un archivo.

#### Ejemplo

```bash
cat nota.txt
```

#### Explicación sencilla

Es como abrir rápidamente un archivo y leer lo que tiene dentro.

---

### 5. `less`

Sirve para leer archivos largos por partes.

#### Ejemplo

```bash
less nota.txt
```

#### Para salir

Presiona:

```bash
q
```

#### Explicación sencilla

Es como leer una hoja larga poco a poco.

---

### 6. `nano`

Es un editor de texto en la terminal.

#### Ejemplo

```bash
nano nota.txt
```

#### Para guardar

```bash
Ctrl + O
Enter
```

#### Para salir

```bash
Ctrl + X
```

#### Explicación sencilla

Es como usar un bloc de notas dentro de Linux.

---

## Resumen de la Semana 2

- `cp` → copia archivos o carpetas
- `mv` → mueve o renombra
- `rm` → borra
- `cat` → muestra el contenido
- `less` → permite leer por partes
- `nano` → edita texto
