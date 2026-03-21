# Ruta de aprendizaje Linux

## Semana 1: Terminal y navegación

En esta primera semana aprenderás a **moverte por Linux** y a reconocer en qué lugar del sistema estás trabajando.

### 1. `pwd`

Significa **print working directory**.  
Sirve para ver **en qué carpeta te encuentras actualmente**.

#### Ejemplo

```bash
pwd
```

#### Posible salida

```bash
/home/usuario
```

#### Explicación sencilla

Es como preguntarle a Linux:

**“¿Dónde estoy ahorita?”**

---

### 2. `ls`

Sirve para listar lo que hay dentro de la carpeta actual.

#### Ejemplo

```bash
ls
```

#### Posible salida

```bash
Documentos  Descargas  Imágenes
```

#### Variantes útiles

```bash
ls -l
```

Muestra información más detallada.

```bash
ls -a
```

Muestra también archivos ocultos.

```bash
ls -la
```

Muestra todo con detalle.

#### Explicación sencilla

Es como abrir una carpeta y mirar qué contiene.

---

### 3. `cd`

Significa **change directory**.  
Sirve para cambiar de carpeta.

#### Ejemplo

```bash
cd Documentos
```

#### Ejemplos importantes

```bash
cd
```

Te lleva a tu carpeta personal.

```bash
cd ..
```

Sube una carpeta.

```bash
cd ~
```

Te lleva al inicio de tu usuario.

```bash
cd /home/usuario/Documentos
```

Te lleva a una ruta completa.

#### Explicación sencilla

Es como caminar de una habitación a otra.

---

### 4. `mkdir`

Significa **make directory**.  
Sirve para crear una carpeta.

#### Ejemplo

```bash
mkdir practica
```

#### Explicación sencilla

Es como crear una carpeta nueva en el explorador de archivos.

---

### 5. `rmdir`

Sirve para eliminar una carpeta vacía.

#### Ejemplo

```bash
rmdir practica
```

#### Importante

Solo funciona si la carpeta está vacía.

#### Explicación sencilla

Es como borrar una carpeta que no tiene nada adentro.

---

### 6. `touch`

Sirve normalmente para crear un archivo vacío.

#### Ejemplo

```bash
touch nota.txt
```

#### Explicación sencilla

Es como crear un archivo nuevo en blanco.

---

## Resumen de la Semana 1

- `pwd` → muestra dónde estás
- `ls` → muestra qué hay en la carpeta
- `cd` → te mueve entre carpetas
- `mkdir` → crea carpetas
- `rmdir` → elimina carpetas vacías
- `touch` → crea archivos vacíos
