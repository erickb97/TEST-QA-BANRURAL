##Hallazgos Erick Barillas : 
####Primero: 
**Uncaught TypeError: guessSubmit.addeventListener is not a function**: 
 Indica que existe un error en la linea 87 - > *guesssubmit.addeventlistener('click', checkguess);*
 Esto es porque la función addeventlistener no es reconocida ya que esta mal escrita
 **Corrección**: guessSubmit.addEventListener('click', checkGuess);
####  Segundo: 
**Uncaught TypeError: Cannot set properties of null (setting 'textContent')**
El interprete reconoce valores nulos en la propiedad 
**Corrección**: const lowOrHi = document.querySelector('.lowOrHi');, Se agrega la referencia a la clase agregando el punto " . " en ('.lowOrHi');
#### Tercero: 
**Uncaught TypeError: resetButton.addeventListener is not a function at setGameOver** 
Esto es porque la función addeventlistener no es reconocida ya que esta mal escrita. 
**Correcion: **resetButton.addEventListener('click', resetGame);
#### Cuarto: 
**Error en la logica de programación ** 
else if(guessCount === ATTEMPS) El Programa solo se ejecuta 5 veces y se detiene ya que se pasa una variable constante. 
**Correción:** else if(userGuess == randomNumber), Se cambia la variable que evalua la entrada del usuario y se cambia el operador por el de iguaalción, con esto ya se puede comparar si es igual el numero ingresado con el numero random, se omite la variable ATTEMPS. 

#### Quinto: 
**Error en la variable iterador**  
if(userGuess === randomNumber) la variable que se evalua no es el iterador (de 1 a 10)
**Correción:** if(guessCount > 9) Se cambia la variable y se delimita a 10 iteraciones 

#### Sexto :
**Error en el numero random**
let randomNumber = Math.random() * 10; el numero random genera contiene decimales por lo que el numero entero ingresado no será igual. 
**Corrección:** let randomNumber = Math.round(Math.random()*100);
#### Septimo: 
Se cambia de color las áreas de texto donde se produce la impresión del mensaje por el color brindado en el requerimiento. 
**Corrección: **
lastResult.style.backgroundColor = 'green';
lastResult.style.backgroundColor = 'red';

#### Octavo: 
Se corrige el color de la fuente y el fondo de la classe lowOrHi

**Correcion:**

      .lowOrHi {
        color: white;
        padding: 3px;
      }
lowOrHi.style.backgroundColor = 'black'

#### Noveno
Se agrega una condicional para delimitar que el numero ingresado por el usuario este entre el rango de 1 y 100. 

	if (userGuess > 0 && userGuess <101) {
	Codigo
	}
	else{
      lastResult.textContent = 'Ingrese un numero entre 1 y 100';
      lastResult.style.backgroundColor = 'red';
      setGameOver()
    }