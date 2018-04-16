## TP#01 - Fases de la traducción y Errores  
**Usuario GitHub:** *jasanchezutn*  
**Legajo:** *129.462-3*  
**Apellido y Nombre:** *Sánchez, Javier*  
  
### Hello2  
Se ejecutó la siguiente línea: **gcc hello2.c -E -o hello2.i**  
Al compilador gcc se le pasaron como argumentos:  
El archivo fuente *hello2.c*  
El parámetro *-E* para realizar solamente el preprocesamiento del archivo.  
El parámetro *-o* para volcar la salida en el archivo *hello2.i* y no mostrarla por stdout.  
  
Como resultado, se observó que en el procesamiento se reemplaza el llamado al archivo cabecera por su contenido y
los comentarios por espacio. Tampoco se detectanron los errores presentes de sintaxis y de vocabulario.  
  
### Hello3  
Se ejecutó la siguiente línea: **gcc hello3.c -E -o hello3.i**  
Al compilador gcc se le pasaron como argumentos:  
El archivo fuente *hello3.c*  
El parámetro *-E* para realizar solamente el preprocesamiento del archivo.  
El parámetro *-o* para volcar la salida en el archivo *hello3.i* y no mostrarla por stdout.  
  
En la primer linea, se declara el prototipo de la función printf, en lugar de hacer referencia a todo el archivo de cabecera stdio.h  
Al no llamar a ningún archivo de cabecera, genera que el archivo fuente tenga el mismo contenido antes y despues de ser preprocesado.  
  
El compilar el archivo, se crea el documento *hello3.s*, pero la compilación arroja error por no finalizar la función *main*.  
*El error de que la función prontf no se encuentra definida no lo arroja*  
  
### Hello4  
Se corrigieron los errores del archivo *hello3.c*, salvandose con el nombre *hello4.c*  
Se ejecutó la línea **gcc -S hello4.c -W** para compilar el archivo fuente, teniendo en cuenta los warning y se corroboró que el mismo no presente inconvenientes.  
Se observó que el nuevo archivo *hello4.s* contiene información sobre el archivo fuente, la salida que genera, el código assembler del archivo asociado y la versión del compilador con el que fue compilado.  
Se realizó el ensamblado del archivo assembler mediante el comando: **gcc -c hello4.s**  
Se realizó el linkeo del archivo objeto *hello4.o* mediante el comando **gcc hello4.o -o hello4.out**  
  
### Hello7  
Se preproceso, compiló, ensamblo, y linkeo el archivo fuente *hello7.c*.  
En la compilación, se generó un warning que indica que la función printf no se encuentra declarada en el archivo preprocesado.  
Más allá de esto, el mismo funciona debido a que el compilador detecta que es una de las funciones propias del lenguaje.  