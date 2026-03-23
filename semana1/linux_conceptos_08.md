# Semana 7: Redirección y tuberías en Linux

Esta semana es muy importante, porque aquí Linux empieza a sentirse realmente poderoso. Ya no solo ejecutas comandos sueltos: ahora aprendes a guardar resultados, agregar texto a archivos y conectar un comando con otro.

## Los símbolos clave son estos:

- `>`
- `>>`
- `<`
- `|`

## ¿Qué aprenderás en esta semana?

Vas a aprender a hacer cosas como estas:

- guardar la salida de un comando en un archivo
- agregar más contenido a un archivo sin borrar lo anterior
- usar la salida de un comando como entrada de otro
- combinar comandos para trabajar más rápido

## Idea central de esta semana

Normalmente, cuando escribes un comando, el resultado aparece en pantalla.

Por ejemplo:

```bash
ls
```

Te muestra los archivos en la terminal.

Pero a veces no quieres verlo solo en pantalla.  
A veces quieres:

- guardarlo en un archivo
- pasarlo a otro comando
- seguir trabajando con ese resultado

Ahí entran `>`, `>>` y `|`.

## 1. `>`

### ¿Qué hace?

Sirve para guardar la salida de un comando en un archivo.

### Ejemplo básico

```bash
ls > lista.txt
```

### ¿Qué pasa aquí?

- `ls` genera una lista de archivos
- `>` toma esa salida
- `lista.txt` recibe el contenido

Entonces, en vez de mostrar el resultado en pantalla, Linux lo guarda dentro de `lista.txt`.

### Ejemplo sencillo

Supón que en tu carpeta tienes:

- `tarea.txt`
- `notas.txt`
- `foto.png`

Si haces:

```bash
ls > lista.txt
```

y luego escribes:

```bash
cat lista.txt
```

verás algo como:

```text
foto.png
notas.txt
tarea.txt
```

### Importante

`>` sobrescribe el archivo.

O sea:

- si `lista.txt` ya tenía algo
- ese contenido se borra
- y se reemplaza por el nuevo

### Explicación fácil

Es como decir:

> “No me lo muestres aquí; guárdalo en este archivo.”

## 2. `>>`

### ¿Qué hace?

Sirve para agregar la salida al final de un archivo, sin borrar lo que ya tenía.

### Ejemplo básico

```bash
echo "hola" >> lista.txt
```

Eso agrega la palabra `hola` al final de `lista.txt`.

### Diferencia entre `>` y `>>`

#### `>`

Reemplaza todo.

```bash
echo "uno" > prueba.txt
```

Contenido de `prueba.txt`:

```text
uno
```

Luego:

```bash
echo "dos" > prueba.txt
```

Ahora el archivo queda así:

```text
dos
```

Se perdió `uno`.

#### `>>`

Agrega sin borrar.

```bash
echo "uno" > prueba.txt
echo "dos" >> prueba.txt
```

Ahora queda:

```text
uno
dos
```

### Explicación fácil

- `>` = escribir desde cero
- `>>` = agregar al final

## 3. `<`

### ¿Qué hace?

Sirve para usar un archivo como entrada de un comando.

No se usa tanto al inicio como `>` o `|`, pero es bueno conocerlo.

### Ejemplo simple

```bash
sort < nombres.txt
```

### ¿Qué pasa?

- `nombres.txt` tiene contenido
- `sort` toma ese contenido como entrada
- lo ordena y lo muestra

Si `nombres.txt` contiene:

```text
Carlos
Ana
Luis
```

entonces el resultado será:

```text
Ana
Carlos
Luis
```

### Explicación fácil

Es como decir:

> “Toma este archivo como lo que vas a leer.”

## 4. `|`

### ¿Qué hace?

Se llama **pipe** o **tubería**.

Sirve para mandar la salida de un comando como entrada de otro comando.

Este es uno de los conceptos más bonitos de Linux.

### Ejemplo básico

```bash
history | grep nano
```

### ¿Qué pasa?

- `history` muestra todos los comandos usados
- `|` toma esa salida
- `grep nano` busca solo las líneas donde aparece `nano`

### Resultado posible

```text
15 nano nota.txt
22 nano tarea.txt
30 nano prueba.py
```

### Explicación fácil

Es como una tubería de agua:

- el primer comando produce algo
- ese resultado viaja por la tubería
- el segundo comando lo recibe y trabaja con eso

## Ejemplos importantes de pipes

### Ejemplo 1

```bash
ls | less
```

### ¿Qué hace?

- `ls` lista archivos
- `less` los muestra por partes

Sirve cuando hay muchos resultados.

### Ejemplo 2

```bash
cat nombres.txt | sort
```

### ¿Qué hace?

- `cat` muestra el contenido
- `sort` lo ordena

### Ejemplo 3

```bash
ps aux | less
```

### ¿Qué hace?

- muestra muchos procesos
- los pasa a `less`
- puedes leerlos poco a poco

### Ejemplo 4

```bash
ip a | grep inet
```

### ¿Qué hace?

- `ip a` muestra información de red
- `grep inet` filtra solo líneas relacionadas con direcciones IP

## Comparación importante

### Redirección `>`

Guarda la salida en un archivo.

```bash
ls > lista.txt
```

### Pipe `|`

Manda la salida a otro comando.

```bash
ls | less
```

### Diferencia fácil

- `>` = manda a archivo
- `|` = manda a otro comando

## Comando `echo`

En esta semana `echo` ayuda mucho para practicar.

### ¿Qué hace?

Muestra texto en pantalla.

```bash
echo "Hola"
```

Resultado:

```text
Hola
```

También sirve para escribir texto en archivos usando redirección.

### Ejemplo con `>`

```bash
echo "Primera línea" > notas.txt
```

Crea el archivo `notas.txt` con ese contenido.

### Ejemplo con `>>`

```bash
echo "Segunda línea" >> notas.txt
```

Agrega otra línea al final.

Luego:

```bash
cat notas.txt
```

Resultado:

```text
Primera línea
Segunda línea
```

## Casos reales de uso

### Caso 1: guardar lista de archivos

```bash
ls > archivos.txt
```

### Caso 2: guardar tu ruta actual

```bash
pwd > ubicacion.txt
```

### Caso 3: agregar una nota

```bash
echo "Estoy practicando Linux" >> notas.txt
```

### Caso 4: buscar algo en el historial

```bash
history | grep apt
```

### Caso 5: ver procesos poco a poco

```bash
ps aux | less
```

### Caso 6: ver IPs filtradas

```bash
ip a | grep inet
```

## Práctica guiada de Semana 7

Haz esto paso por paso.

### Paso 1: crea una carpeta de práctica

```bash
mkdir semana7
cd semana7
```

### Paso 2: guarda la salida de `ls` en un archivo

```bash
ls > lista.txt
cat lista.txt
```

Como la carpeta recién está creada, quizá salga vacía o solo muestre algunos archivos si ya creaste algo.

### Paso 3: escribe texto en un archivo

```bash
echo "Hola Linux" > notas.txt
cat notas.txt
```

### Paso 4: agrega más líneas

```bash
echo "Estoy aprendiendo redirección" >> notas.txt
echo "Esto no borra lo anterior" >> notas.txt
cat notas.txt
```

Ahora deberías ver:

```text
Hola Linux
Estoy aprendiendo redirección
Esto no borra lo anterior
```

### Paso 5: usa `sort` con entrada desde archivo

```bash
echo "Carlos" > nombres.txt
echo "Ana" >> nombres.txt
echo "Luis" >> nombres.txt
sort < nombres.txt
```

Resultado esperado:

```text
Ana
Carlos
Luis
```

### Paso 6: usa una tubería

```bash
cat nombres.txt | sort
```

Esto hace algo parecido, pero usando `|`.

### Paso 7: busca comandos del historial

```bash
history | grep echo
```

Esto mostrará las líneas del historial donde usaste `echo`.

### Paso 8: mira resultados largos por partes

```bash
ps aux | less
```

Para salir de `less`, presiona:

```text
q
```

## Errores comunes

### Error 1: olvidar que `>` borra lo anterior

Si haces esto:

```bash
echo "uno" > archivo.txt
echo "dos" > archivo.txt
```

el archivo quedará solo con:

```text
dos
```

Porque el segundo `>` reemplazó todo.

### Error 2: confundir `>` con `|`

No hacen lo mismo.

Esto guarda en archivo:

```bash
ls > lista.txt
```

Esto manda a otro comando:

```bash
ls | less
```

### Error 3: usar `<` sin entender que es entrada

`<` no escribe en el archivo.  
Solo le da ese archivo como entrada al comando.

## Resumen rápido de la Semana 7

- `>` → guarda salida en un archivo
- `>>` → agrega salida al final de un archivo
- `<` → usa un archivo como entrada
- `|` → conecta la salida de un comando con otro

## Resumen todavía más fácil

- `>` = escribir en archivo desde cero
- `>>` = agregar más al archivo
- `<` = leer desde un archivo
- `|` = pasar resultado a otro comando

## En una sola frase

La Semana 7 te enseña a guardar resultados, agregar contenido y conectar comandos entre sí.
