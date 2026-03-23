# Semana 12: Scripts básicos en Bash

Aquí empiezas a pasar de usar comandos sueltos a automatizar tareas con archivos `.sh`. Bash puede ejecutar comandos desde la entrada estándar o desde un archivo, y justamente por eso sirve tanto como intérprete interactivo como lenguaje de scripts.

## Los temas base de esta semana son estos:

- `#!/bin/bash`
- `echo`
- `read`
- variables
- `if`
- `for`
- `while`

## ¿Qué aprenderás en esta semana?

Vas a aprender a hacer cosas como estas:

- crear un archivo que ejecute varios comandos de una vez
- guardar datos en variables
- pedir datos al usuario
- tomar decisiones con `if`
- repetir acciones con `for`
- repetir acciones con `while`

## En una frase

Esta semana trata de hacer mini programas en Bash. Bash scripting se usa justamente para automatizar tareas y agrupar comandos para ejecutarlos desde un archivo.

---

## 1. ¿Qué es un script?

Un script es un archivo de texto que contiene comandos de Bash.

Por ejemplo, en vez de escribir esto uno por uno:

```bash
pwd
ls
date
```

puedes guardarlo en un archivo y ejecutarlo todo junto.

---

## 2. La primera línea: `#!/bin/bash`

Casi todos los scripts empiezan así:

```bash
#!/bin/bash
```

Eso se llama **shebang** y le dice al sistema que use Bash para ejecutar ese archivo. Bash puede ser invocado con un archivo de comandos, y cuando corre un script, `$0` toma el nombre de ese archivo.

---

## 3. Tu primer script

Crea un archivo:

```bash
nano hola.sh
```

Y escribe esto:

```bash
#!/bin/bash
echo "Hola"
echo "Estoy aprendiendo Bash"
```

Guarda y sal.

Luego dale permiso de ejecución:

```bash
chmod +x hola.sh
```

Y ejecútalo:

```bash
./hola.sh
```

### ¿Qué hace?

- imprime `Hola`
- luego imprime `Estoy aprendiendo Bash`

---

## 4. `echo`

`echo` sirve para mostrar texto en pantalla.

### Ejemplo

```bash
echo "Hola mundo"
```

### Salida

```text
Hola mundo
```

Dentro de scripts se usa muchísimo para mostrar mensajes.

---

## 5. Variables

Una variable guarda un valor.

### Ejemplo

```bash
nombre="Marco"
echo "$nombre"
```

### Salida

```text
Marco
```

En Bash, una variable puede asignarse con `nombre=valor`, y para usarla se expande con `$nombre` o formas más explícitas como `${nombre}`.

### Importante

En Bash no debes poner espacios al asignar:

```bash
nombre="Marco"
```

No así:

```bash
nombre = "Marco"
```

Eso estaría mal.

---

## 6. `read`

`read` sirve para leer algo que escribe el usuario.

### Ejemplo

```bash
#!/bin/bash
echo "¿Cómo te llamas?"
read nombre
echo "Hola, $nombre"
```

### ¿Qué pasa?

- el script pregunta tu nombre
- tú escribes algo
- ese dato se guarda en la variable `nombre`
- luego lo muestra

---

## 7. Script completo con variable y `read`

```bash
#!/bin/bash
echo "Ingresa tu nombre:"
read nombre
echo "Bienvenido, $nombre"
```

Si escribes:

```text
Ana
```

el resultado será:

```text
Bienvenido, Ana
```

---

## 8. `if`

`if` sirve para tomar decisiones.

### Estructura básica

```bash
if [ condición ]
then
    comandos
fi
```

Bash tiene construcciones condicionales y expresiones condicionales con `[` y `[[ ... ]]` para evaluar condiciones.

### Ejemplo simple

```bash
#!/bin/bash
edad=18

if [ $edad -ge 18 ]
then
    echo "Eres mayor de edad"
fi
```

### ¿Qué significa `-ge`?

Significa **greater or equal**, o sea, **mayor o igual que**.

---

## 9. `if` con `else`

```bash
#!/bin/bash
echo "Ingresa tu edad:"
read edad

if [ $edad -ge 18 ]
then
    echo "Eres mayor de edad"
else
    echo "Eres menor de edad"
fi
```

### ¿Qué hace?

- pide tu edad
- si es 18 o más, muestra un mensaje
- si no, muestra el otro

---

## 10. `for`

`for` sirve para repetir algo varias veces.

### Ejemplo

```bash
#!/bin/bash
for i in 1 2 3
do
    echo "Número: $i"
done
```

### Salida

```text
Número: 1
Número: 2
Número: 3
```

### Explicación fácil

`for` es como decir:

> “haz esto para cada elemento de esta lista”

---

## 11. `while`

`while` sirve para repetir mientras una condición sea verdadera.

### Ejemplo

```bash
#!/bin/bash
contador=1

while [ $contador -le 3 ]
do
    echo "Vuelta $contador"
    contador=$((contador + 1))
done
```

Bash permite evaluar aritmética con expansión aritmética como `$(( ... ))`.

### Salida

```text
Vuelta 1
Vuelta 2
Vuelta 3
```

### Explicación fácil

`while` significa:

> “mientras esto sea cierto, sigue”

---

## 12. `for` vs `while`

### `for`

Lo usas cuando ya sabes cuántas veces o con qué elementos trabajarás.

```bash
for i in 1 2 3
do
    echo $i
done
```

### `while`

Lo usas cuando quieres repetir mientras se cumpla una condición.

```bash
while [ $x -lt 5 ]
do
    ...
done
```

---

## 13. Variables especiales útiles

En scripts también existen parámetros especiales como `$0`, que representa el nombre del shell o del script, y Bash define varios parámetros especiales para trabajar con argumentos y ejecución del script.

### Ejemplo con `$0`

```bash
#!/bin/bash
echo "Este script se llama $0"
```

Si el archivo se llama `prueba.sh`, mostrará algo como:

```text
Este script se llama ./prueba.sh
```

---

## 14. Cómo ejecutar un script

Hay dos formas comunes:

### Forma 1

Darle permiso y ejecutarlo:

```bash
chmod +x script.sh
./script.sh
```

### Forma 2

Ejecutarlo directamente con Bash:

```bash
bash script.sh
```

---

## 15. Ejemplos sencillos de scripts útiles

### A. Script que muestra información

```bash
#!/bin/bash
echo "Tu usuario es:"
whoami
echo "Tu carpeta actual es:"
pwd
echo "Contenido:"
ls
```

### B. Script que crea una carpeta

```bash
#!/bin/bash
echo "Creando carpeta..."
mkdir prueba_bash
echo "Hecho"
```

### C. Script que saluda

```bash
#!/bin/bash
echo "¿Cómo te llamas?"
read nombre
echo "Hola, $nombre"
```

### D. Script con decisión

```bash
#!/bin/bash
echo "Ingresa un número:"
read num

if [ $num -gt 0 ]
then
    echo "Es positivo"
else
    echo "Es cero o negativo"
fi
```

### E. Script con repetición

```bash
#!/bin/bash
for archivo in *.txt
do
    echo "Archivo encontrado: $archivo"
done
```

---

## 16. Práctica guiada de Semana 12

Haz esto paso por paso.

### Paso 1: crea un script

```bash
nano saludo.sh
```

Pega esto:

```bash
#!/bin/bash
echo "Hola"
echo "¿Cómo te llamas?"
read nombre
echo "Mucho gusto, $nombre"
```

### Paso 2: dale permiso

```bash
chmod +x saludo.sh
```

### Paso 3: ejecútalo

```bash
./saludo.sh
```

### Paso 4: crea otro con `if`

```bash
nano edad.sh
```

Pega esto:

```bash
#!/bin/bash
echo "Ingresa tu edad:"
read edad

if [ $edad -ge 18 ]
then
    echo "Eres mayor de edad"
else
    echo "Eres menor de edad"
fi
```

Ejecuta:

```bash
chmod +x edad.sh
./edad.sh
```

### Paso 5: crea uno con `for`

```bash
nano repetir.sh
```

Pega esto:

```bash
#!/bin/bash
for i in 1 2 3 4 5
do
    echo "Repetición número $i"
done
```

Ejecuta:

```bash
chmod +x repetir.sh
./repetir.sh
```

---

## 17. Errores comunes

### Error 1: olvidar el permiso de ejecución

Si haces:

```bash
./script.sh
```

y no tiene permiso, fallará.

### Solución

```bash
chmod +x script.sh
```

### Error 2: poner espacios al asignar variables

Incorrecto:

```bash
nombre = "Ana"
```

Correcto:

```bash
nombre="Ana"
```

### Error 3: olvidar cerrar estructuras

Si abres un `if`, debes cerrar con `fi`.

Si abres un `for` o `while`, debes cerrar con `done`.

### Error 4: olvidar el `$` al usar la variable

Si haces:

```bash
echo nombre
```

imprime literalmente `nombre`.

Debes hacer:

```bash
echo "$nombre"
```

---

## 18. Qué deberías dominar al terminar esta semana

Al final de la Semana 12 deberías poder:

- crear un archivo `.sh`
- ejecutarlo
- usar `echo`
- guardar datos en variables
- usar `read`
- hacer decisiones con `if`
- repetir con `for`
- repetir con `while`

Eso ya te da base real de automatización en Linux. Bash se usa justamente para agrupar comandos, automatizar tareas y construir scripts reutilizables.

---

## Resumen rápido de la Semana 12

- `#!/bin/bash` → indica que el script usará Bash
- `echo` → muestra texto
- `read` → lee datos del usuario
- `variable="valor"` → guarda información
- `if` → toma decisiones
- `for` → repite por lista
- `while` → repite mientras se cumpla una condición

## En una sola frase

La Semana 12 te enseña a crear scripts básicos en Bash para automatizar tareas, pedir datos, tomar decisiones y repetir acciones.
