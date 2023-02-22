1. Al abrir el archivo index.html en consola encontre un error el cual mostraba el mensaje "guessSubmit.addeventListener is not a function", sabemos que esta función esta escuchando a lo que haga el usuario, el error lo muestra en la linea 87 que es donde se llama a la función "checkGuess" que es la que realiza las validaciones correspondientes. 
    Solución: le di solución a este errror corrigiendo el error de sintaxis de la función addEventListener, ya que esta es la manera correcta de utilizar esta función. 
    #El mismo error se corrigio en la linea 95

2. El número a adivinar debe pertenecer al conjunto de los enteros (e.g. 1, 2, 3...):
    
    Validando este requerimiento, imprimi en consola el numero que se estaba generando, pude percatarme que generaba el numero aleatorio decimal y unicamente de 1 a 10.

        Solución: para cumplir con este requerimiento, modifique la forma en que se genera el número aleatorio quedo de la siguiente manera --> let randomNumber = Math.round(Math.random() * 100+1);
        Se redondea el numero obtenido y "*100+1" es el valor maximo que sería 100, el +1 es para que tome en cuenta el valor maximo. 

3. El numero debe ser entero, si es diferente se debe mostrar una alerta y no aumentar los intentos:

    Solución: para poder validar que sea entero se creo la función "validar", en donde se convierte el input en tipo numerico y se utiliza la función "Number.isInteger": 
                            function validar(){
                                let x = Number(guessField.value);
                                if(Number.isInteger(x)){
                                    checkGuess();
                                }else{
                                    lowOrHi.textContent = 'El número no debe ser decimal'
                                }
                            }
    Lo corregi de esta manera, ya que no se aumentan los intentos si ingresan un dato erroneo. 

4. Me presento error al querer utilizar el valor de la variable "userGuess" que es donde se almacena lo que el usuario esta ingresando, el error no dejaba ejecutar de buena manera la funcion anterior debido a que estaba siendo tomado como tipo texto, la solución que implemente fue utilizar la funcion que convierte los datos a numeros, quedando la variable de la siguiente manera --> "let userGuess = Number(guessField.value);".

5. Otro error que observe y asi mismo corregí, es que los mensajes del juego estaban cruzados, es decir, si el usuario adivina el número mostraba el mensaje de incorrecto. 
        Solucion: unicamente se modificaron los textos, se colocaron en su lugar correspondiente. 

6. Sí el número que ingresó el jugador es mayor al número a adivinar, se debe mostrar el siguiente mensaje en color     negro: "Incorrecto! El número es mayor!", en caso que sea menor, se debe mostrar: "Incorrecto! El número es menor!".
    Solucion: mostraba un error, que era sobre lowOrhi era nulo, pero era porque se necesitaba un selector de clase por los que se corrigió colocando "." en la declaración de la variable del selector "const lowOrHi = document.querySelector('.lowOrHi');".
    Para dar el color solicitado, en la sección de Style, colocamos la clase ".lowOrhi" esto nos permitio darle el color al texto blanco y en la función colocamos el fondo negro como se solicita "lowOrHi.style.backgroundColor = 'black';".

7. Si después de 10 intentos, el usuario no adivina el número, se debe mostrarse el mensaje de color rojo: "!!!Pérdistes!!!".
    Solucion:
        Aca pues como venía el código ya se encontraba implementado, unicamente era de imrpimir los intentos. 
        Se imprime el contador de intentos dentro de la sentencia condicional. Se aumenta el contador, cuando se finalice todas las validaciones, llega a 10  y muestra el mensaje de perdiste. 
        Agregue la variable intentos, que serviria para ir imrpimiendo la cantidad de intentos que el usuario llevaba --> "const intentos = document.querySelector('.intentos');".

8. Si el usuario adivina el número antes de los 10 intentos, se debe mostrar el mensaje de color verde: "Felicitaciones! adivinaste el número!".
    Solucion:
        Aca de igual manera ya esta implementado, unicamente se le cambia el color del background al solicitado -->
        "lastResult.style.backgroundColor = 'green';".


9. Un error que encontre, para mi es relevante, creo que es necesario que todo tipo de proyecto o aplicación debe de tener comentarios, sobre que es lo que se realiza en cada sección de código, esto con el fin de que los nuevos desarrolladores tengan conocimiento de donde acudir si se presentara un problema. 



