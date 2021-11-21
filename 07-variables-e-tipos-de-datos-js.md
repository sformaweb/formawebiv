# Variables e tipos de datos de JavaScript

_*ref:*_ https://docs.microsoft.com/es-es/learn/modules/web-development-101-variables/

Unha linguaxe de programación consta de moitos conceptos. Podes usar  estes conceptos para crear calquera cousa, desde unha pequena aplicación  de liña de comandos ata un sistema empresarial a gran escala. Antes de crear unha aplicación, debes coñecer os aspectos básicos da linguaxe.

Un concepto fundamental importante é o das *variables*.  O código fonte pode ter desde 10 liñas ata moitos miles e pode repartirse entre centos de arquivos. As variables son referencias con  nome que che axudan a controlar os valores importantes do programa.

Existen varios tipos de valores. É posible que queiras cambiar algúns e outros non. Dependendo de que tipo de valor se utilice, debe almacenarse como ese tipo.

Neste módulo se explican os tipos de variables e o seus tipos de  datos, xunto có xeito no que se poden usar na programación con  JavaScript.

Imos ver:

- Que son as variables e por que usalas.
- Cando usar constantes.
- Como almacenar valores como tipos diferentes pode aportar claridade no código.



# Introdución ás variables

Para comprender correctamente JavaScript (a linguaxe que proporciona interactividade en Internet), primeiro debes comprender os tipos de datos e variables da linguaxe e como se crean. E inda máis importante é comprender cando, onde e como usalos.

## Interactividade

Mediante o uso de variables, poderás realizar un seguimento do estado. Quizás necesites lembrar o valor da selección dun usuario ou gardar o resultado dun cálculo. Situacións como estas exixen o uso de variables.

Os tipos de datos melloran o uso de variables ao permitirche especificar a forma e o tamaño dos datos que necesitas almacenar. Os tipos de datos poden expresarse como números, cadeas ou incluso estruturas máis complexas.

Se xa aprendiches unha linguaxe de programación antes, é posible que observes algunhas similitudes entre dita linguaxe e JavaScript, se ben a sintaxe pode ser un pouco diferente. Se é a primeira vez que aprendes unha linguaxe de programación, non te preocupes. Imos ver os conceptos básicos de JavaScript que che axudarán a desempeñarte satisfactoriamente coma desenvolvedor web.

 Suxestión: mira agora este [vídeo](https://youtu.be/JNIXfGiDWM8/) de introducción.

# Uso de variables para lembrar valores

Saber como usar correctamente variables e tipos de datos é esencial para escribir código en JavaScript. As variables almacenan valores que se poden usar e cambiar en todo o código, e os tipos de datos axudan a describir que tipo de datos se almacena nesas variables.

## Variables

Imaxina que tes un valor no código que queres lembrar para un uso futuro. Ao almacenar o valor, podes facer referencia a el máis adiante no código.

Podes crear e declarar unha variable mediante a seguinte sintaxe: `[keyword] [name]`. Coma neste exemplo dunha declaración de variable:

```js
var aVariable;
```

A palabra clave `var` indica que se desexa declarar unha variable, e `aVariable` é o nome da variable. O nome dunha variable é elixible e debe reflectir para que se usa.

## Palabra clave para traballar con variables

A palabra clave `let` foi introducida no estándar de JavaScript ECMAScript 6 (ES6). O uso de `let` proporciona o *ámbito de bloque* das variables. Recomendase usar `let` en lugar de `var` para administrar mellor o ámbito da aplicación.

JavaScript usa os diferentes tipos de ámbito, como o ámbito global e o ámbito de función, para determinar que variables están dispoñibles en que partes do código. Por exemplo, unha variable global está dispoñible dentro dunha función porque pertence ao ámbito global (o ámbito "externo"). As variables designadas coa  palabra clave `var` teñen o seu ámbito (os seus valores son visibles) dentro do corpo da función e as variables `let` teñen como ámbito o seu bloque de inclusión entre chaves. Isto significa que se usas `var`  nun bucle `for`, será visible fora do bucle `for`, o que podería provocar resultados inesperados. O uso de `let` é unha mellor opción porque só está dispoñible no bloque de inclusión (é dicir, o bucle `for`), polo que a súa dispoñibilidade podería ser máis previsible.

Para declarar una variable mediante `let`, usa a sintaxe seguinte:

```javascript
let myVariable;
```

`myVariable` foi declarada agora mediante a palabra clave `let`. Actualmente non ten un valor, pero podes darlle un.

### Asignación dun valor

Para almacenar un valor nunha variable, usa o *operador de asignación* (`=`) seguido do valor esperado:

```javascript
myVariable = 123;
```

Suxestión: O uso do operador de asignación (`=`) neste exemplo establece un valor nunha variable. Difire dunha comparación, que usa dous ou tres operadores como `==` ou `===`.

Agora a `myVariable` *asignóuselle* o valor `123`.

### Inicialización explícita

Unha *inicialización* difire dunha asignación en que se declara o valor e se lle asigna un valor. Este é un exemplo dunha inicialización:

```javascript
let myVariable = 123;
```

Unha inicialización explícita se usa no lugar dunha asignación se se desexa que unha variable conteña un *valor de inicio*. Imaxina, por exemplo, que queres que todos os xogadores dun xogo de cartas teñan fichas de póker por valor de 100 puntos antes de empezar unha partida. Para representar ese estado, poderías declaralo da seguinte forma:

```javascript
let pokerChips = 100;
```

### Cambio de variables

É posible que queiras almacenar un valor nunha variable temporalmente. Un exemplo é a suma dun cálculo.

O código seguinte mostra como se usa o operador de asignación (`=`) e como se *asigna* un valor no lado dereito do operador:

```javascript
myVariable = 321;
```

Suxestión: Próbao para practicar. Pode escribir código JavaScript directamente no explorador. Abre unha xanela do explorador e vai a **Ferramentas de desenvolvemento**. Na consola, atoparás unha solicitude. Escribe `let myVariable = 123` e, a continuación, `myVariable`. Que sucede?



As veces non queres que se cambien os valores dunha variable. Esta situación pode acontecer cando se confía nunha constante matemática, coma o valor de pi. Para satisfacer esta necesidade, JavaScript permite crear *constantes*.

## Constantes

A declaración e a inicialización dunha constante seguen os mesmos conceptos que unha variable, salvo que usa a palabra clave `const`:

```javascript
const MY_VARIABLE = 123;
```

Suxestión: Aínda que podes asignarlle a una variable constante o nome que queiras, recoméndase que poñas todas as letras en maiúsculas.

As constantes son similares ás variables, con dúas excepcións:

- *Deben ter un valor*. As constantes se deben inicializar ou se producirá un erro ao executar o código.
- *A referencia non se pode cambiar*. Se a referencia dunha constante cambia despois de inicializarse, se producirá un erro ao executar o código.

Vexamos algúns exemplos:

- A seguinte sintaxe de código para un valor simple *non* está permitida:

  ```javascript
  const PI = 3;
  PI = 4; // non permitido
  ```

- A sintaxe seguinte ten unha referencia de obxecto protexido e *no*n está permitida:

  ```javascript
  const obj = { a: 3 };
  obj = { b: 5 } // non permitido
  ```

- A sintaxe seguinte ten un valor de obxecto que non está protexido. *Está* permitida porque vai a cambiar o valor do obxecto, pero non a propia referencia.

  ```javascript
  const obj = { a: 3 };
  obj.a = 5;  // permitido
  ```

**Nota:** A presencia de `const` significa que a referencia non se pode reasignar. Sen embargo, o valor non é *inmutable* e pode cambiar, especialmente se se trata dunha construcción complexa como un obxecto.

## Comprobar  coñecementos

1. En JavaScript, podemos declarar valores coa palabra clave _______ ou _______.

```js
`let` ou `var`      ---
```

```js
`get` ou `script`
```

```js
`char` ou `log`
```

2. As constantes son as mesmas que `let` e `var` para declarar variables, salvo que...

As constantes se poden modificar.

As constantes se deben inicializar.  ---

As constantes se poden reasignar.



# Tipos de datos

As variables poden almacenar moitos tipos diferentes de valores, como números e texto. Estes valores se denominan *tipos de datos*.

Os tipos de datos son unha parte importante do desenvolvemento de software porque os desenvolvedores úsanos para tomar decisións sobre como se debe escribir o código e como debe executarse o software. Algúns tipos de datos teñen características únicas que axudan a transformar ou extraer información adicional nun valor.

Os tipos de datos tamén se denominan *primitivas de datos de JavaScript*, xa que son os tipos de datos de nivel máis baixo que proporciona a linguaxe. Hai seis tipos de datos primitivos: `string`, `number`, `bigint`, `boolean`, `undefined` e `symbol`.

Suxestión: Dedica un minuto a visualizar o que podería representar cada unha destes primitivos. Que é unha cebra? E se se executa `0`? E se se executa `true`?

## Números

Na sección anterior, o valor de `myVariable` era un tipo de datos `number`:

```
let myVariable = 123;
```

As variables poden almacenar todos os tipos de números, incluídos decimais ou números negativos. Os números tamén se poden usar con *operadores aritméticos*.

Estes son algúns tipos de operadores que podes usar ao realizar funcións aritméticas:

| Símbolo | Descrición                                              | Exemplo                          |
| :------ | :------------------------------------------------------ | :------------------------------- |
| `+`     | **Suma**: calcula a suma de dous números.               | `1 + 2 //expected answer is 3`   |
| `-`     | **Resta**: calcula a diferencia de dous números.        | `1 - 2 //expected answer is -1`  |
| `*`     | **Multiplicación**: calcula o produto de dous números.  | `1 * 2 //expected answer is 2`   |
| `/`     | **División**: calcula o cociente de dous números.       | `1 / 2 //expected answer is 0.5` |
| `%`     | **Resto**: calcula o resto da división de dous números. | `1 % 2 //expected answer is 1`   |

Suxestión: Proba unha operación aritmética na consola do explorador. Que che parecen os resultados?

## Cadeas - *String*

As cadeas son conxuntos de caracteres que residen entre comiñas simples ou dobres.

- `'This is a string'`
- `"This is also a string"`
- `let myString = 'This is a string value stored in a variable';`

Suxestión: Lembra usar comiñas ao escribir unha cadea ou JavaScript asumirá que é un nome de variable.

As cadeas son textuais e é necesario aplicarlles formato ocasionalmente.

Para *concatenar* dúas ou máis cadeas ou unilas, emprega o operador `+`:

```javascript
let myString1 = "Hello";
let myString2 = "World";

myString1 + myString2 + "!"; //HelloWorld!
myString1 + " " + myString2 + "!"; //Hello World!
myString1 + ", " + myString2 + "!"; //Hello, World!
```

Por que `1 + 1 = 2` en JavaScript, pero `'1' + '1' = 11`? Pénsao. E que pasa con `'1' + 1`?

Os *literais de modelo* son outra maneira de dar formato ás cadeas, salvo que, en lugar de comiñas, usan acentos graves. Todo o que no sexa texto sen formato debe colocarse dentro de marcadores de posición `${ }`, incluídas as variables que poden ser cadeas. Este é un exemplo:

```javascript
let myString1 = "Hello";
let myString2 = "World";

`${myString1} ${myString2}!` //Hello World!
`${myString1}, ${myString2}!` //Hello, World!
```

Podes empregar calquera método para aplicar o formato que queiras, pero os literais de modelo respectarán todos os espazos e saltos de líña.

Suxestión: Dedica un momento a pensar nos casos de uso de diferentes tipos de cadea. Cando usarías un literal de modelo en lugar dunha cadea sen formato?

## Valores booleanos

Os valores booleanos só poden ser de dous tipos: `true` ou `false`. Os valores booleanos axudan a tomar decisións sobre que liñas de código se deben executar cando se cumpran certas condicións. En moitos casos, os operadores axudan a establecer o valor dun valor booleano. A miúdo observarás que as variables se inicializan cun operador ou que os seus valores se actualizan cun operador. Este é un exemplo:

- `let myTrueBool = true`
- `let myFalseBool = false`

Unha variable se pode considerar "verdadeira" se se evalúa como un valor booleano cuxo valor é `true`. En JavaScript, [todos os valores son verdadeiros a menos que se definan como "falsos"](https://developer.mozilla.org/docs/Glossary/Truthy/).

Suxestión: Explora os problemas comúns de JavaScript. Lembra que podes escribir JavaScript directamente no explorador. Abre unha xanela do explorador e vai a **Ferramentas de desenvolvemento**. Na consola, atoparás unha solicitude. Este código se resolve como `false`: `let age = 1`; `let Age = 2`; `age == Age`. Por que crees que é así e que outros problemas comúns pode atopar?

## Comprobar coñecementos

1. Cal dos seguintes non é un tipo de datos?

Números

Arquivos ---

Valores booleanos

2. Os números e ____ son primitivas de JavaScript que controlan datos numéricos.

```js
bigint   ----
```

```js
boolean
```

```js
star
```

3. Las cadeas poden residir entre ________ simples e dobres.

corchetes

comiñas  ----

barras diagonais inversas



# Creación de código modular mediante funcións en JavaScript

As funcións son os bloques de creación de calquera aplicación que se vaia a crear. Coas funcións podes crear seccións de código con nome e reutilizables, para que sexa máis lexible e fácil de manter. Imos a explorar os conceptos básicos das funcións.

## Obxectivos de aprendizaxe

Neste módulo, aprenderás:

- Como escribir unha función básica.
- Que parámetros se proporcionan e como usalos.
- Como devolver valores dunha función.
- Como usar funcións anónimas.

## Introdución

Cando pensamos en escribir código, sempre queremos asegurarnos de que o código sexa lexible. Aínda que pareza contraditorio, o código se lee moitas máis veces das que se escribe.

A *función* é una ferramenta principal do cadro de ferramentas dun desenvolvedor para garantir que o código se pode manter. Basicamente, unha función é un bloque de código que se pode executar a petición. Este código pode realizar una tarea, como ir a otra parte de un sitio web o calcular un valor, como la suma de dos números.

En este módulo, aprenderá lo seguinte:

- Como escribir una función básica.
- Que parámetros se proporcionan y como usarlos.
- Como devolver valores de una función.
- Como usar funcións anónimas.

# Información xeral sobre as funcións

Las funcións son bloques de creación clave para escribir código. Una función é una colección reutilizable de líneas de código que hace que algo suceda dentro del programa.

Las funcións son perfectas para escenarios en los que se necesita realizar la misma tarea varias veces. En lugar de duplicar la lógica en varias ubicaciones, lo que dificulta la actualización del código más adelante, pode centralizarlo en una ubicación. De este modo, pode llamarlo siempre que necesite que la operación se realice de nuevo. Incluso pode llamar a funcións desde otras funcións.

Igual de importante é la capacidad de asignar un nome a una función. Aunque asignar un nome a una función pode parecer trivial, el nome proporciona una forma rápida de documentar una sección de código. Se podría pensar en la nomenclatura como una etiqueta en un botón. Por ejemplo, si selecciona el botón "Cancelar temporizador", dejará de correr el reloj.

## Creación y llamada a una función

Una función toma alguna entrada y luego devuelve una salida que transforma de algún modo la entrada. Por ejemplo, una función de suma pode tomar dos números enteros y luego devolver la suma de sus valores.

Las funcións están formadas por tres componentes diferentes:

- Un *cuerpo de función* é un bloque de código que se ejecuta cuando se llama a la función.
- Un *parámetro* é otro nome para la entrada que se pasa a una función.
- Por último, hay un *valor devuelto* o la salida da función.

La sintaxe de una función se muestra en el código seguinte:

JavaScriptCopiar

```javascript
function nameOfFunction(parameter) { // function definition with some input
// function body
}
```

Los parámetros y los valores devueltos son opcionales al escribir una función. Para empezar, comprobemos algunas funcións básicas que no toman ninguna entrada ni devuelven ningún valor. Si desea crear una función para mostrar un saludo en la [consola](https://developer.mozilla.org/docs/Web/API/console) de depuración del editor de código, podría tener este aspecto:

JavaScriptCopiar

```javascript
function displayGreeting() {
  console.log('Hello, world!');
}
```

La función se denomina `displayGreeting`. Al ejecutar la función, el texto "¡Hola, mundo!" se imprime en la consola.

Siempre que quiera llamar a la función o invocarla, use el nome da función seguido de un par de paréntesis (`()`). Merece la pena tener en cuenta que pode definir la función antes o después de que decida llamarla. En cualquier caso, JavaScript la encontrará por usted, siempre y cuando se encuentre dentro del ámbito de donda llama.

JavaScriptCopiar

```javascript
// calling the function
displayGreeting();
```

 Nota

Hay un tipo especial de función conocido como *método*, que ya ha estado usando. De hecho, vio un método en la demostración anterior cuando usó console.log. Lo que hace que un método sea diferente de una función é que está asociado a un objeto (*consola*, en el ejemplo); en cambio, una función é flotante libre. Oirá que muchos desenvolvedores usan estos términos indistintamente.

## Procedimientos recomendados

Al crear funcións, tenga en cuenta algúns procedimientos recomendados:

- Use nomes descriptivos que indiquen lo que pretenden hacer las funcións. Por ejemplo, el nome `displayGreeting` deja claro que el propósito da función é mostrar un saludo. Un nome como `greet`, para una función que realiza la misma tarea, é un poco ambiguo. Podría mostrar un saludo, pero también podría realizar una operación diferente.
- Use una mezcla de mayúsculas y minúsculas para combinar palabras. Para escribir combinando mayúsculas y minúsculas, mantenga la primera palabra da variable o función en minúsculas y escriba en mayúsculas cada palabra posterior. Dado que los nomes de función y variable no poden contener espacios, la combinación de mayúsculas y minúsculas facilita la lectura das palabras del código. Por ejemplo, `displayGreeting` é más fácil de leer que `displaygreeting`.
- Mantenga las funcións centradas en una tarea específica. Esto no solo facilita la reutilización de una función en un programa, sino que también facilita la depuración del código. Si tiene una incidencia con la función que no realiza la tarea que consideró que haría, sabrá que el problema está dentro de esa función.
- Use texto comentado para anotar el código y describir lo que hacen las funcións. Para mejorar la legibilidad del código, incluya en el comentario una breve descripción da tarea de cada función. Para crear comentarios, escriba una barra diagonal doble (`//`), seguida de su descripción. El comentario finaliza cuando se inicia una nueva línea.

# Parámetros de función

Completado100 XP

- 2 minutos

Para que una función sea más reutilizable, a menudo querrá pasarle información. Este tipo de entrada se denomina *parámetro*. Un parámetro, a veces también denominado "argumento", é información adicional que se envía a una función.

Supongamos que quiere cambiar la función `displayGreeting` para poder saludar a una persona específica, en lugar de imprimir solo "¡Hola, mundo!" cada vez que se llama a la función. Puede usar un parámetro para especificar el nome da persona.

Los parámetros se enumeran en la definición da función y se incluyen entre paréntesis (`()`). Puede tener varios parámetros separados por comas, como se muestra aquí:

JavaScriptCopiar

```javascript
function name(param, param2, param3) {

}
```

Puede actualizar la función `displayGreeting` para que tome el nome de una persona como entrada e imprimir un mensaje personalizado en la consola, como se muestra aquí:

JavaScriptCopiar

```javascript
// function with a parameter called name
function displayGreeting(name) { 
    // creating a new local variable that inserts the name into a string   
    const message = `Hello, ${name}!`; 
    // printing the variable to the console
    console.log(message);
}
```

Si desea llamar a la función y pasar el parámetro, é posible especificarlo entre paréntesis da seguinte forma:

JavaScriptCopiar

```javascript
displayGreeting('Christopher');
// displays "Hello, Christopher!" when run
```

## Valores predeterminados

Puede hacer que la función sea aún más flexible, añadiendo más parámetros. ¿Y qué ocurre si no quiere requerir que se especifiquen todos los valores? Si seguimos con el ejemplo de saludo, pode mantener `name`, según sea necesario (debe saber a quién está saludando), pero quiere permitir que el saludo se personalice. Si alguien no quiere personalizarlo, pode proporcionar un valor predeterminado en su lugar. Para ello, establezca el valor da misma manera que establece un valor para una variable: `parameterName = 'defaultValue'`. Por ejemplo:

JavaScriptCopiar

```javascript
function displayGreeting(name, salutation='Hello') {
  console.log(`${salutation}, ${name}`);
}
```

Al llamar a la función, pode decidir si establece un valor para el saludo, como se muestra aquí:

JavaScriptCopiar

```javascript
displayGreeting('Christopher');
// displays "Hello, Christopher"

displayGreeting('Christopher', 'Hi');
// displays "Hi, Christopher"
```

------

# Valores devueltos

Completado100 XP

- 2 minutos

Hasta este punto, las funcións que ha creado tienen salida en la [consola](https://developer.mozilla.org/docs/Web/API/console). Esto pode ser exactamente lo que busca, especialmente cuando se crean funcións que llaman a otros servicios. ¿Y qué ocurre si desea crear una función auxiliar para realizar un cálculo y después proporcionar un valor que pueda usar en otro lugar?

Para ello, use un *valor devuelto*. La función devuelve un valor devuelto y pode almacenarlo en una variable igual que pode almacenar un valor literal, como una cadena o un número.

Si una función debe devolver algo, se usa la palabra clave `return`, seguida normalmente de un valor o una referencia a lo que se devuelve. Sin embargo, también pode usar `return` por sí mismo para salir de una función.

Este é un ejemplo de una instrucción "return" que devuelve un valor:

JavaScriptCopiar

```javascript
return myVariable;
```

Aquí se muestra como usaría `return` por sí solo:

JavaScriptCopiar

```javascript
return;
```

Siguiendo con el ejemplo anterior, podría escribir una función para crear un mensaje de saludo y luego devolver el valor al autor da llamada. Tenga en cuenta que la palabra clave `return` detiene la ejecución da función y devuelve el valor especificado, si lo hay. Por lo tanto, normalmente querrá usar `return` al final da función, da seguinte manera:

JavaScriptCopiar

```javascript
function createGreetingMessage(name) {
  const message = `Hello, ${name}`;
  return message;
}
```

 Nota

No se pode acceder a las variables que defina dentro de una función desde ningún lugar fuera da función. Estas variables se denominan *variables locales*. Fuera da función, se considera que están *fuera del ámbito*.

Cuando se llama a esta función, se almacena el valor en una variable. Esto se hace da misma manera que establecería una variable en un valor estático (por ejemplo, `let name = 'Christopher'`), da seguinte manera:

JavaScriptCopiar

```javascript
let greetingMessage = createGreetingMessage('Christopher');
```

Los valores devueltos ayudan a demostrar otra razón por la que las funcións son una parte tan importante de JavaScript. Puede reutilizar la misma función con argumentos diferentes para generar varios valores devueltos.



# Ejercicio: Creación de una función

Completado100 XP

- 3 minutos

Al escribir código estará creando funcións con frecuencia. En este ejercicio creará una función para mostrar un nome en una página web. La función tomará un parámetro, el nome da persona a la que desea saludar y después devolverá el mensaje. Luego llamará a esta función para mostrar el mensaje.

 Nota

Puede encontrar el código completo de este ejercicio en la parte inferior da página.

## Creación de una página de ejemplo

Empiece por crear una nueva página en Visual Studio Code.

1. Abra una terminal o ventana de comandos de Visual Studio Code.

2. Para crear un nuevo directorio y cambiar a este, ejecute uno de los seguintes comandos:

   BashCopiar

   ```bash
   # Windows
   md functions && cd functions
   
   # macOS or Linux
   mkdir functions && cd functions
   ```

3. Para abrir el nuevo directorio en Visual Studio Code, ejecute el seguinte comando:

   BashCopiar

   ```bash
   code .
   ```

4. En el panel **Explorador,** mantenga el puntero sobre **funcións** y luego seleccione el icono **Nuevo archivo**.

   ![Captura de pantalla del panel del Explorador con el icono Nuevo archivo resaltado](https://docs.microsoft.com/es-es/learn/modules/web-development-101-functions/media/functions-create-file.png) .

5. Asigne al nuevo archivo el nome *index.html* y luego seleccione Entrar.

## Agregar el código para mostrar el mensaje

Ahora pode agregar el código para mostrar el mensaje.

1. En el archivo *index.html* cree el núcleo del archivo HTML, pegando el código HTML seguinte:

   HTMLCopiar

   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Message</title>
   </head>
   <body>
       <script>
           // TODO: Add hello code
   
           // TODO: Add setTimeout code
   
       </script>
   </body>
   </html>
   ```

    Nota

   Los comentarios `TODO` dentro da etiqueta de script son marcadores para agregar código tanto en este ejercicio como en uno próximo.

2. En el archivo *index.html*, debajo la línea comentada `//TODO: Add hello code`, cree una función, agregando el código seguinte.

   La función toma un parámetro, denominado `name`, y devuelve una cadena que dice "Hola" y el nome da persona que proporciona la entrada:

   JavaScriptCopiar

   ```javascript
   // TODO: Add hello code
   function getMessage(name) {
       return 'Hello, ' + name + '...';
   }
   ```

3. Debajo da llave de cierre (`}`) en el código que acaba de agregar, añada el código seguinte para obtener el mensaje y use `document.write` para mostrarlo en la página web.

   JavaScriptCopiar

   ```javascript
   const message = getMessage('Ornella');
   document.write(message);
   ```

4. Guarde el archivo seleccionando **Archivo** > **Guardar**.

## Visualización da página

Ya se ha creado la página. Veamos como funciona:

1. En Visual Studio Code, abra la **Paleta de comandos**, presionando Ctrl+Mayús+P (Windows) o Cmd+Mayús+P en un equipo Mac.

2. En la **Paleta de comandos**, abra [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer), escribiendo **Live Server** y luego seleccionando **Live Server: Abrir con Live Server**.

   ![Captura de pantalla da Paleta de comandos con &quot;Live Server: Abrir con Live Server&quot; resaltado.](https://docs.microsoft.com/es-es/learn/modules/web-development-101-functions/media/launch-live-server.png)

   Live Server se abre en el explorador y se muestra el mensaje "Hola, Ornella...".

   ![Captura de pantalla da ventana del explorador, en la que se muestra el mensaje &quot;Hola, Ornella...&quot;.](https://docs.microsoft.com/es-es/learn/modules/web-development-101-functions/media/hello-ornella.png)

Ahora ha creado y llamado a una función para mostrar un mensaje. Puede intentar cambiar el nome y guardar el archivo de nuevo para ver los resultados actualizados.

 Importante

Mantenga Visual Studio Code y el explorador abiertos para usarlos en una próxima unidad.

## Código completo

HTMLCopiar

```html
<!DOCTYPE html>
<html>
<head>
    <title>Message</title>
</head>
<body>
    <script>
        // TODO: Add hello code
        function getMessage(name) {
            return 'Hello, ' + name + '...';
        }
        const message = getMessage('Ornella');
        document.write(message);

        // TODO: Add setTimeout code

    </script>
</body>
</html>
```

# funcións anónimas

Completado100 XP

- 4 minutos

Como ha visto, pode llamar a una función a petición mediante su nome y pasando los parámetros adecuados. Pero, a veces, é posible que quiera permitir que otro proceso ejecute las funcións que ha creado.

Imagine la creación de una página web con varios temporizadores. Cuando finalice un temporizador, querrá ejecutar código para mostrar un mensaje. El problema é que sabe que el temporizador expirará, pero, dado que la longitud del temporizador pode cambiar, no sabe exactamente *cuándo* expirará. Por lo tanto, no sabe exactamente *cuándo* quiere que se ejecute el código. Para admitir este tipo de escenario, pode usar una *devolución de llamada*.

## Introducción a las devoluciones de llamada

Básicamente, una devolución de llamada é una manera de pasar una función a otra función como parámetro. Este parámetro se comporta da misma manera que cualquier otro parámetro, como una cadena o un número, salvo que se pode llamar a él porque é una función.

Imaginemos que un amigo suyo va a la tienda y le pide que le traiga dos helados, y lo que é más importante, que se los traiga antes de que se derritan.

En la programación, esta situación se pode representar mediante una devolución de llamada. Ha dado a su amigo un conjunto de instrucciones (ve a la tienda, pide helados). La devolución de llamada aquí sería una instrucción adicional para traerlos antes de que se derritan.

Es posible que haya seleccionado otro componente clave sobre el tiempo de ejecución: sabe que su amigo completará la tarea, pero no sabe necesariamente *cuándo*.

Las devoluciones de llamada se usan con frecuencia en una variedad de marcos y bibliotecas para indicar el código que desea ejecutar cuando algo sucede o finaliza. Usará una devolución de llamada para indicar lo que debe ocurrir cuando, por ejemplo, un usuario selecciona un botón, finaliza una operación de ejecución larga o expira un temporizador.

## Utilización de una devolución de llamada

Una devolución de llamada é una función normal y pode crearla como lo haría con cualquier función que haya escrito en el pasado. En el ejemplo `displayDone` seguinte, observará que é una función normal sin parámetros.

JavaScriptCopiar

```javascript
function displayDone() {
    console.log('Done!');
}
```

Puede pasarla a una función, que acepta una devolución de llamada como `setTimeout`. La devolución de llamada `setTimeout` é una función integrada que permite crear un temporizador. Cuando finaliza el temporizador, llama a la función que se pasa como primer parámetro. El segundo parámetro indica el número de milisegundos que se esperarán hasta que llame a la función.

Si desea establecer un tiempo de espera de 3 segundos y hacer que el código muestre "Listo" cuando haya terminado de ejecutarse, podría usar `setTimeout` da seguinte forma:

JavaScriptCopiar

```javascript
// timer value is in milliseconds
setTimeout(displayDone, 3000);
```

 Importante

Observe que `displayDone` no va seguido de un par vacío de paréntesis (`()`) cuando se pasa como un parámetro a `setTimeout`. Si escribe `setTimeout(displayDone(), 3000)`, está indicando a JavaScript que ejecute `displayDone` inmediatamente. Dado que desea pasar la función a `setTimeout` para llamar `setTimeout` cuando transcurra el temporizador, solo se usa `displayDone`.

## funcións anónimas

Aunque el código anterior é válido, este código pode crear lo que algúns desenvolvedores llaman la "contaminación del espacio de nomes". Es decir, cuando escribe código con numerosas variables, funcións y otras entidades con nomes, pode resultar confuso conocer el propósito de cada una de ellas y, a veces, pode que se quede sin nomes buenos. En nuestro ejemplo, si el único lugar `displayDone` que se usará é con `setTimeout`, no é necesario darle un nome. Puede crear una *función anónima*.

Una función anónima é una función sin nome. Las funcións anónimas se comportan da misma manera que las funcións normales y son la forma en que los desenvolvedores normalmente establecen las devoluciones de llamada.

Puede crear una función anónima con la misma sintaxe que usaría para crear una función normal, salvo que se omite el nome. Por ejemplo:

JavaScriptCopiar

```javascript
setTimeout(
    function() { // anonymous function
        console.log('Done!');
    },
    3000 // 3000 milliseconds (3 seconds)
)
```

Este código realiza exactamente la misma tarea que el código anterior con la función `displayDone`. La diferencia clave é que se crea la función insertada (es decir, dentro da llamada a `setTimeout`), sin un nome. Al hacerlo, el código se limpia un poco.

## funcións de flecha

Las funcións de *flecha* o las de *flecha gruesa*, son una forma ligeramente diferente de crear funcións anónimas. Las funcións de flecha usan el operador `=>` para indicar el inicio del cuerpo da función. Puede volver a escribir el ejemplo de función anónima anterior mediante la sintaxe de flechas gruesas:

JavaScriptCopiar

```javascript
setTimeout(
    () => { // anonymous function
        console.log('Done!');
    },
    3000 // 3000 milliseconds (3 seconds)
)
```

Este código hace exactamente lo mismo que antes. La única diferencia é el uso del operador `=>`. Verá que muchos desenvolvedores prefieren la sintaxe concisa que proporcionan las funcións de flecha.

# Ejercicio: Creación de una función anónima

Completado100 XP

- 1 minuto

En este ejercicio usará `setTimer` con una función anónima para mostrar un mensaje en una página web. Creará código que muestra el mensaje después de un retraso de 2 segundos.

Usará el mismo archivo que usó en el ejercicio anterior para completar este.

 Nota

Puede encontrar el código completo de este ejercicio en la parte inferior da página.

## Agregar el código para mostrar el mensaje

Ahora agregará el código para mostrar el mensaje, que tendrá un retraso de 2 segundos.

1. En Visual Studio Code, abra el archivo *index.html*.

2. Debajo da línea comentada `// TODO: Add setTimeout code`, agregue el código seguinte:

   JavaScriptCopiar

   ```javascript
   setTimeout(
       () => { document.write('...Hello again!')},
       2000
   );
   ```

3. Guarde el archivo seleccionando **Archivo** > **Guardar**. Live Server actualiza automáticamente la página al guardar el archivo.

## Visualización da página

Veamos los resultados.

1. Vuelva a la ventana del explorador.

   El mensaje "... ¡Hola de nuevo!" é posible que ya se muestre, porque Live Server ya habrá actualizado la ventana.

2. Actualice la ventana del explorador. Observe que se muestra el mensaje original y, después de dos segundos, se reemplaza por "... ¡Hola de nuevo!". "Hola mundo".

   ![Captura de pantalla del explorador, en la que se muestra el mensaje &quot;... ¡Hola de nuevo!&quot;.](https://docs.microsoft.com/es-es/learn/modules/web-development-101-functions/media/hello-again.png)

Ahora ha usado una función anónima para que aparezca un mensaje después de un retraso.

## Código completo

HTMLCopiar

```html
<!DOCTYPE html>
<html>
<head>
    <title>Message</title>
</head>
<body>
    <script>
        // TODO: Add hello code
        function getMessage(name) {
            return 'Hello, ' + name + '...';
        }
        const message = getMessage('Ornella');
        document.write(message);

        // TODO: Add setTimeout code
        setTimeout(
            () => { document.write('...Hello again!')},
            2000
        );
    </script>
</body>
</html>
```



## Comprobación de conocimientos

\1. 

¿Qué é un parámetro?



Un valor que devuelve una función



El nome da función



Un valor que una función acepta del autor da llamada --- 

\2. 

¿Cuál de los seguintes nomes sigue las directrices de nomenclatura para las funcións de JavaScript?



helloworld



helloWorld ----



hola_mundo



HelloWorld

\3. 

¿Qué función llama a una función una vez transcurrido un período de tiempo especificado?



setTimeout  ---



document.write



console.log

# Resumen

Completado100 XP

- 4 minutos

En este módulo ha explorado como crear funcións en JavaScript. Una función é una abstracción excelente que se pode usar cuando se necesita realizar la misma tarea varias veces y se quiere evitar duplicar el código. También ha aprendido la diferencia entre una función y un método. Estos dos tipos son funcións, pero una función é flotante libre y un método se asienta en un objeto.

Después, ha explorado parámetros y variables como elementos importantes que permiten a las funcións trabajar con datos.

Seguidamente, ha aprendido sobre las variables de devolución. Un valor devuelto son los datos que abandonan la función. Cualquier invocador de una función pode aprovechar el valor devuelto al asignarlo a una variable.

Por último, ha aprendido sobre las funcións anónimas. Una función anónima no tiene un nome, pero é una función que se pode pasar. Se usa normalmente en un contexto donde é necesario realizar una tarea que é asincrónica y finalizará en algún momento en el futuro. Los ejemplos poden ser un tiempo de espera o la captura de datos a través da red. Una vez que finaliza la tarea, se invoca la función anónima.

*****************

# Toma de decisiones con JavaScript

- 14 min.
- Módulo
- 8 Unidades

 4.7 (122)

Califíquelo

Principiante

Estudiante

Visual Studio Code

En esta lección, se tratan los conceptos básicos da toma de decisiones if/else de JavaScript. Aprenderá como comparar variables y el uso de valores booleanos, y el uso de instrucciones if/else le permiten tomar decisiones en el código.

## Objetivos de aprendizaje

En este módulo, aprenderá a:

- Revisar los valores booleanos.
- Aprender sobre los operadores de comparación.
- Explorar como se usan if y else en JavaScript.
- Descubrir como formar condiciones y tomar decisiones con operadores lógicos.

# Introducción

Completado100 XP

- 1 minuto

algúns programas que se escriben se ejecutan de arriba a abajo. A menudo, tendrá aplicaciones cuyas rutas en el código están determinadas por las diferentes condiciones que configure.

Supongamos que tiene un programa para crear un archivo de copia de seguridad de todos los archivos de un directorio. Si el archivo de copia de seguridad ya existe, no deseará volver a crearlo porque podría llevar mucho tiempo. Este escenario é un ejemplo en el que se desea poder expresar la lógica condicional para que el código se ejecute de forma diferente en función de si se cumple una condición o no.

En este módulo, aprenderá a trabajar con los diferentes operadores que pode usar para expresar lógica para crear varias rutas en los programas.

## Objetivos de aprendizaje

En este módulo, aprenderá a:

- Revisar los valores booleanos.
- Aprender sobre los operadores de comparación.
- Explorar como se usan if y else en JavaScript.
- Descubrir como formar condiciones y tomar decisiones con operadores lógicos.

## Requisitos previos

Ninguno

# Operadores lógicos

Completado100 XP

- 3 minutos

Las decisiones pueden requerir más de una comparación y se pueden combinar con operadores lógicos para generar un valor booleano.

## Operadores lógicos y valores booleanos

Hay operadores específicos que nos permiten conectar varias instrucciones booleanas. El resultado es una instrucción más compleja que en cualquier caso se evalúa como `true` o `false`. Puede usar el siguiente conjunto de operadores para construir estas comparaciones más complejas:

| Símbolo | Descripción                                                  | Ejemplo                                                      |
| :------ | :----------------------------------------------------------- | :----------------------------------------------------------- |
| `&&`    | **AND lógico**: compara dos expresiones booleanas. Devuelve true *solo* si ambos lados son true. | `(5 > 6) && (5 < 6 ) //One side is false, other is true. Returns false` |
| `||`    | **OR lógico**: compara dos expresiones booleanas. Devuelve true si al menos un lado es true. | `(5 > 6) || (5 < 6) //One side is false, other is true. Returns true` |
| `!`     | **NOT lógico**: devuelve el valor opuesto de una expresión booleana. | `!(5 > 6) // 5 is not greater than 6, but "!" will return true` |

## Condiciones y decisiones con operadores lógicos

Puede usar estos operadores complejos con ambas asignaciones, pero también con las cláusulas `if` y `else`.

### En asignaciones

Como parte de la asignación de un valor a una variable, puede usar un operador OR (`||`).

JavaScriptCopiar

```javascript
let isHoliday = true;
let isMember = true;
let hasDiscount = isHoliday || isMember;
```

Con el código anterior, se expresa si un cliente puede tener un descuento o no. Solo es necesario que una de las variables, `isMember` o `hasDiscount`, tenga un valor verdadero para que se asigne true a la variable `hasDiscount`.

### En if...else

También puede usar este tipo de operador lógico en una instrucción `if/else`. En el ejemplo de código siguiente, tiene una situación en la que hay dos portátiles, uno con descuento y otro vendido a precio completo. Mediante el uso de un operador `||`, puede construir una cláusula `if` de aspecto más complejo.

JavaScriptCopiar

```javascript
let currentMoney= 800;
let laptopPrice = 1000;
let laptopDiscountPrice = laptopPrice - (laptopPrice * .20) //Laptop price at 20 percent off

if (currentMoney >= laptopPrice || currentMoney >= laptopDiscountPrice){
    //Condition was true. Code in this block will run.
    console.log("Getting a new laptop!");
}
else {
    //Condition was true. Code in this block will run.
    console.log("Can't afford a new laptop, yet!");
}
```

 Sugerencia

¿Recuerda lo que hemos dicho sobre aprender a leer código? ¿Qué nos dice el código? ¿Va a obtener un equipo portátil nuevo? Desplácese hacia abajo para obtener la respuesta.

Sí.

## Operador de negación

Ha visto cómo puede usar una instrucción `if...else` para crear lógica condicional. Todo lo que va a una instrucción `if` se debe evaluar como true o false. Mediante el operador `!`, puede *negar* la expresión. Debería tener un aspecto similar al siguiente:

JavaScriptCopiar

```javascript
if (!condition) {
  // runs if condition is false
} else {
  // runs if condition is true
}
```

## Expresiones ternarias

El uso de `if...else` no es la única manera de expresar la lógica de decisión. También puede usar algo llamado operador *ternario*. La sintaxis tiene un aspecto similar al siguiente:

JavaScriptCopiar

```javascript
let variable = condition ? <return this if true> : <return this if false>
```

Este es un ejemplo más tangible.

JavaScriptCopiar

```javascript
let firstNumber = 20;
let secondNumber = 10
let biggestNumber = firstNumber > secondNumber ? firstNumber: secondNumber;
```

El código indica que:

Si `firstNumber` es mayor que `secondNumber`, se asigna `firstNumber` a `biggestNumber`; de lo contrario, se asigna `secondNumber`.

 Sugerencia

Tómese un minuto para leer este código varias veces. ¿Comprende cómo funcionan estos operadores?

La expresión ternaria es una forma compacta de escribir el código siguiente:

JavaScriptCopiar

```javascript
let biggestNumber;
if (firstNumber > secondNumber) {
  biggestNumber = firstNumber;
} else {
  biggestNumber = secondNumber;
}
```

 Sugerencia

Tómese un momento para reflexionar. ¿Cuál de los dos enfoques, expresiones ternarias o if/else, era más fácil de entender?



# Ejercicio: If...else

Completado100 XP

- 2 minutos

Para completar este módulo, se necesita un espacio aislado. Un [espacio aislado](https://docs.microsoft.com/en-us/learn/support/faq?pivots=sandbox) le da acceso a recursos gratuitos. La suscripción personal no se le cobrará. El espacio aislado solo se puede usar para realizar los cursos de Microsoft Learn. Está prohibido el uso con cualquier otro fin y puede dar lugar a la pérdida permanente del acceso al espacio aislado.



Activar espacio aislado

Como desarrollador junior de juegos recreativos, se le ha pedido que inicie el desarrollo de un juego de Blackjack. El Blackjack tiene algunas reglas interesantes sobre cómo calcular puntos. Se da cuenta de que es una excelente oportunidad para aplicar alguna lógica booleana que ha aprendido.

## Cálculo de una mano de naipes

En el Blackjack, el objetivo del juego es ganar a la banca. Se gana manteniendo una puntuación mayor que la banca, pero menor o igual que 21.

1. Cree un archivo llamado *blackjack.js*.

   JavaScriptCopiar

   ```javascript
   touch app.js
   code .
   ```

2. Asígnele el siguiente código de inicio:

   JavaScriptCopiar

   ```javascript
   let cardOne = 7;
   let cardTwo = 5;
   let sum = cardOne + cardTwo; // 15
   ```

   A continuación, va a agregar código que simula tomar un naipe más. Veamos qué sucede.

3. Agregue el código siguiente:

   JavaScriptCopiar

   ```javascript
   let cardThree = 7;
   sum += cardThree;
   if (sum > 21) {
     console.log('You lost');
     process.exit(1); // exit program
   }
   console.log(`You have ${sum} points`);
   ```

4. Ejecute el código.

   JavaScriptCopiar

   ```javascript
   node blackjack.js
   ```

   Verá la salida siguiente:

   ResultadosCopiar

   ```output
   You have 19 points
   ```

## Adición de un adversario

Su adversario es la banca. Recuerde las reglas. Gana si tiene una puntuación mejor que la banca o si la banca tiene más de 21. Vamos a implementar esas reglas.

1. Agregue las siguientes variables para representar los naipes de la banca.

   JavaScriptCopiar

   ```javascript
   let cardOneBank = 7;
   let cardTwoBank = 5;
   let cardThreeBank = 6;
   let cardFourBank = 4;
   ```

2. A continuación, agregue el siguiente código al final del archivo.

   JavaCopiar

   ```java
   let bankSum = cardOneBank + cardTwoBank + cardThreeBank + cardFourBank;
   if (bankSum > 21 || (sum <= 21 && sum > bankSum)) {
    console.log('You win');
   } else {
     console.log('Bank wins');
   }
   ```

3. Ejecute el código.

   JavaScriptCopiar

   ```javascript
   node blackjack.js
   ```

   Verá la salida siguiente:

   ResultadosCopiar

   ```output
   You have 19 points
   You win
   ```

Felicidades. Ha implementado correctamente algunas de las reglas del Blackjack mediante el uso de lógica y operadores booleanos.

Este es el código completo.

JavaScriptCopiar

```javascript
let cardOne = 7;
let cardTwo = 5;
let sum = cardOne + cardTwo; // 15
let cardOneBank = 7;
let cardTwoBank = 5;
let cardThreeBank = 6;
let cardFourBank = 4;

let cardThree = 7;
sum += cardThree;
if (sum > 21) {
  console.log('You lost');
}
console.log(`You have ${sum} points`);

let bankSum = cardOneBank + cardTwoBank + cardThreeBank + cardFourBank;

if (bankSum > 21 || (sum <= 21 && sum > bankSum)) {
  console.log('You win');
  process.exit(1); // exit program
} else {
  console.log('Bank wins');
}
```

------

## Siguiente unidad: Prueba de conocimientos

[Continuar](https://docs.microsoft.com/es-es/learn/modules/web-development-101-if-else/7-knowledge-check/)

# Resumen

Completado100 XP

- 1 minuto

Ahora que está familiarizado con las funcionalidades de toma de decisiones de JavaScript, puede empezar a pensar en las decisiones que deberá tomar en el código futuro que escriba.

Poder tomar decisiones en el código permite que este tenga capacidad de respuesta. También permitirá a los usuarios interactuar con los sitios web en lugar de hacer que sean una página estática.

¡Enhorabuena! Va a desarrollar su primer sitio web dinámico mediante JavaScript.





# Matrices y bucles de JavaScript

Aprenda a manipular y almacenar datos en JavaScript.

## Objetivos de aprendizaje

En este módulo, obtendrá información sobre lo siguiente:

- Qué son las matrices y para qué se usan.
- Cómo usar bucles para trabajar con matrices.
- Cómo aplicar operaciones de matriz.

# Introducción

Completado100 XP

- 1 minuto

JavaScript es una de las tecnologías principales del World Wide Web. Los desarrolladores la usan para crear contenido interactivo en sus sitios web.

Dado que JavaScript es un lenguaje de scripting del lado cliente, permite a los usuarios ejecutar código en sus dispositivos.

Imagine tener que volver a cargar una página web cada vez que cambia la información en el dispositivo, no poder comprobar si los datos tienen el formato correcto antes de enviar un formulario o no poder mover un objeto de forma interactiva en una pantalla. Sin JavaScript, estas tareas serían imposibles en la mayoría de los sitios web.

En este módulo obtendrá información del formato estructural y los usos de las matrices en JavaScript, y de cómo los bucles pueden ayudarle con tareas repetitivas que implican los datos de dichas matrices.

## Objetivos de aprendizaje

En este módulo, obtendrá información sobre lo siguiente:

- Qué son las matrices y para qué se usan.
- Cómo usar bucles para trabajar con matrices.
- Cómo aplicar operaciones de matriz.

## Requisitos previos

Ninguno

# Manipulación de matrices

200 XP

- 4 minutos

Para que los datos e información de sus sitios web sean interactivos, debe poder manipular y almacenar los datos en el código. Afortunadamente, en JavaScript se pueden almacenar varios elementos en una *matriz*. El uso de matrices le ayudará a no tener que declarar muchas variables, entre otras ventajas.

## Acerca de las matrices

Una matriz es un tipo de estructura de datos que contiene más de un elemento. Imagine un pedido de compra que contiene varios artículos o una heladería donde puede elegir entre varios sabores. En lugar de almacenar, por ejemplo, ocho sabores de helado diferentes como ocho variables diferentes, puede usar una sola matriz para almacenar esa información, como se muestra a continuación:

JavaScriptCopiar

```javascript
let iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Neapolitan"];
```

En este código, se indica una matriz al encerrar todo su contenido entre corchetes (`[]`).

### Acceso a un elemento

El contenido de una matriz se suele conocer como *elemento*. A menudo se necesita acceder a un elemento específico para leer el valor, actualizarlo o incluso quitarlo. Para acceder a un elemento específico, se usan corchetes y la posición que interesa, de la siguiente forma:

JavaScriptCopiar

```javascript
array[<number>]
```

El primer elemento de una matriz comienza por 0 y el último elemento es su longitud (número de elementos) menos 1. Es decir, si una matriz tiene tres elementos, 0 sería la primera posición y 2 su última posición. Una posición de una matriz se conoce como su *índice*. Si observa la matriz `iceCreamFlavors`, supongamos que quiere **Pistacho**. Para leer su valor, puede escribir el código siguiente:

JavaScriptCopiar

```javascript
iceCreamFlavors[3] // Pistachio
```

### Cambiar un valor

Para cambiar un valor en una matriz, debe seleccionar el índice del elemento y asignarle un nuevo valor mediante el operador de asignación de signo igual (`=`) y un valor a la derecha del operador. La heladería se ha quedado sin "Napolitano", pero no se preocupe, ha encontrado "helado de nuez":

JavaScriptCopiar

```javascript
iceCreamFlavors[4] = "Butter Pecan"; //Changes "Neapolitan" to "Butter Pecan"
```

### Añada más valores

El negocio de helados crece y quiere ofrecer más sabores. ¿Qué puede hacer? Puede usar el método `push()` para agregar más sabores. El método `push()` toma un elemento como entrada y agrega el elemento a la matriz original. Por ejemplo, para agregar "Menta con chocolate" como sabor, usaría el código siguiente:

JavaScriptCopiar

```javascript
iceCreamFlavors.push("Mint Chip");
```

### Uso de la longitud de la matriz

Imagine que alguien le pregunta, ¿cuántos sabores de helado tiene? Echa un vistazo a la trastienda y todo lo que ve es un mar de sabores que va a tardar mucho en contar. Un momento, en la matriz, existe el campo `length` que puede usar para contar todos los sabores:

JavaScriptCopiar

```javascript
iceCreamFlavors.length // 6 flavors, because you recently added "Mint Chip"
```

 Sugerencia

Use la consola del explorador para crear y manipular una matriz de su propia creación. Recuerde que puede escribir código JavaScript directamente en el explorador. Para hacerlo, abra una ventana del explorador y diríjase a "Herramientas de desarrollo". En la consola, encontrará una solicitud. Experimente con la manipulación de una matriz con índices y propiedades que acabamos de ver.

### Quitar un valor

Para quitar un valor de una matriz, puede usar `delete`. Supongamos que se ha quedado sin el sabor de "Menta con chocolate". El envase sigue ahí, pero ya no queda helado de "Menta con chocolate". El código tiene este aspecto:

JavaScriptCopiar

```javascript
let iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Neapolitan", "Mint Chip"];
delete iceCreamFlavors[iceCreamFlavors.length-1];
console.log(iceCreamFlavors[length-1]) // undefined
```

Todos los elementos siguen ahí, pero el envase, donde estaba el helado de "Menta con chocolate", está vacío. Ahora puede asignarle otro sabor, ¿cuál?

JavaScriptCopiar

```javascript
iceCreamFlavor[iceCreamFlavor.length-1] = "your choice";
```

### Quitar un elemento

A veces, no basta con quitar el valor. Debe quitar el envase también. ¿Es posible que no tenga suficiente espacio en casa? Decide comerse todo el helado de "vainilla" (probablemente se arrepentirá de ello) y tira el envase. Para esta operación, usará el método de matrices `splice()`. Toma una posición e indica los elementos que hay que quitar, como se muestra en este código:

JavaScriptCopiar

```javascript
array.splice(<position index, <number of elements to remove>)
```

Para quitar un elemento (comerse todo el helado de "vainilla" y tirar el envase), use el método `splice()`, de la siguiente forma:

JavaScriptCopiar

```javascript
iceCreamFlavor.splice(2,1); 
iceCreamFlavor // [ 'Chocolate', 'Strawberry', 'Pistachio', 'Neapolitan', 'Mint Chip' ]
```

## Comprobar los conocimientos

\1. 

Para hacer referencia a un elemento específico de una matriz, usaría



Corchetes `[]`



Un índice



Llaves `{}`

\2. 

¿Cómo se obtiene el número de elementos de una matriz?



El método "len(array)"



El tamaño de propiedad en la matriz



La propiedad de longitud en la matriz

\3. 

En JavaScript, los índices comienzan en



0



1



2



# Recorrer en iteración los elementos de una matriz mediante bucles

Completado100 XP

- 4 minutos

Tiene una matriz, ¿y ahora qué? Puede usar *bucles* para llevar a cabo iteraciones en cada elemento de la matriz. Puede realizar operaciones como imprimir cada elemento, sumarlo o buscar elementos específicos dada una condición.

## Acerca de los bucles

Los bucles permiten tareas repetitivas o *iterativas*, y pueden ahorrarle mucho tiempo y código. Una iteración puede variar en sus variables, valores y condiciones. Hay diferentes tipos de bucles en JavaScript, cada uno tiene pequeñas diferencias. Pero todos hacen básicamente lo mismo: ejecutan un bucle en los datos.

### Bucles `For`

Un bucle `for` requiere tres partes para iterar:

- **Contador**: variable que normalmente se inicializa con un número que cuenta el número de iteraciones. Este es un ejemplo:

  JavaScriptCopiar

  ```javascript
  let i = 0;
  ```

  Normalmente, este valor se usa como la primera posición a la que quiere acceder en una matriz.

- **Condición**: expresión que usa operadores de comparación para hacer que el bucle se detenga cuando `true`. Este es un ejemplo de una condición que se detiene cuando la matriz no tiene índices:

  JavaScriptCopiar

  ```javascript
  i < 10;   
  ```

  En este ejemplo, la expresión será false cuando `i` sea igual a `arry.length`. Si se está recorriendo en bucle una matriz, este es el resultado correcto. No se recomienda abordar un índice fuera de los límites de la matriz.

- **Expresión de incremento**: expresión que se ejecuta al final de cada iteración, normalmente para cambiar el valor del contador. Puede incrementar tanto como quiera por iteración, pero es habitual aumentar en una, como se muestra en este ejemplo:

  JavaScriptCopiar

  ```javascript
  i++;
  i +=2; // this would work too and increases by 2
  ```

Cuando las tres partes se usan juntas, un bucle `for` puede tener este aspecto:

JavaScriptCopiar

```javascript
for (let i = 0; i < 10; i++ ) {
  console.log(i);
}
```

 Sugerencia

Ejecute este código en una consola de explorador. ¿Qué ocurre cuando se hacen pequeños cambios en el contador, condición o expresión de incremento? ¿Puede hacer que se ejecute hacia atrás y crear una cuenta regresiva?

### Bucles `While`

A diferencia del bucle `for`, un bucle `while` requiere una condición que detendrá el bucle solo cuando la expresión del bucle `while` se evalúe como `true`.

Las condiciones de los bucles suelen basarse en otros valores, como los contadores, y deben administrarse durante el bucle.

Los valores iniciales de los contadores deben crearse fuera del bucle y cualquier expresión que cumpla una condición, incluido el cambio del contador, debe mantenerse dentro del bucle. En el ejemplo siguiente, el bucle `while` se ejecuta para 10 iteraciones.

JavaScriptCopiar

```javascript
//Counting up to 10
let i = 0;
while (i < 10) {
 console.log(i);
 i++;
}
```

 Nota

¿Por qué elegir un bucle `for` o un bucle `while`? En StackOverflow, [17 000 espectadores se hacían la misma pregunta](https://stackoverflow.com/questions/39969145/while-loops-vs-for-loops-in-javascript/), puede que le interesen algunas de las opiniones.

Las matrices se suelen usar con bucles porque la mayoría de las condiciones requieren la longitud de la matriz para detener el bucle y el índice también puede ser el valor del contador.

## Bucles y matrices

Volvamos a la lista de sabores de helado. Un cliente le ha pedido el nombre de todos los sabores antes de decidir cuál comprar. Afortunadamente, conoce los bucles `for`, así que use uno. Recuerde que ha definido una condición sobre cuándo terminar la lista, de la siguiente forma:

JavaScriptCopiar

```javascript
i < 10
```

La matriz de sabores de helado tiene una longitud arbitraria, lo que significa que puede quitar o agregar elementos en cualquier momento. Sabe que tiene seis tipos de helado, pero también puede usar el campo `length` en la matriz y fiarse de él:

JavaScriptCopiar

```javascript
let iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Neapolitan", "Mint Chip"];

for (let i = 0; i < iceCreamFlavors.length; i++) {
  console.log(iceCreamFlavors[i]);
} // Ends when all flavors are printed
```

Ahí está. Ha enumerado todos los sabores y el cliente ha elegido "Vainilla". ¿Qué sabor elegiría?

## El bucle `forEach()`

Hasta ahora, conoce los bucles `for` y `while`. Hay otro bucle en la propia matriz llamado `forEach()`. El bucle `forEach()` recorre en iteración los elementos y ofrece una manera simplificada de crear bucle, ya que no necesita un contador si lo único que quiere hacer es crear bucle. Por ejemplo:

JavaScriptCopiar

```javascript
let numbers = [1, 2, 3, 4, 5];
numbers.forEach(number => console.log(number)); // 1 2 3 4 5
```

Además, si desea acceder al índice actual, también puede hacerlo si cambia ligeramente el código anterior al que le mostramos a continuación:

JavaScriptCopiar

```javascript
numbers.forEach((number, index) => console.log(`Number ${number} ${index}`));
```

### Qué construcción de bucle usar y cuándo

Los bucles `for` y `forEach()` permiten recorrer en bucle los elementos de la matriz, pero la diferencia entre ellos es que el bucle `for` le permite salir si se cumple una condición determinada.

Observe el código siguiente:

JavaScriptCopiar

```javascript
let numbers = [1, 2, -1, 4, 5];
for(let i = 0; i< numbers.length; i++>) {
  if (numbers[i] < 0) {
    break;
  }
  console.log(numbers[i]);
}
```

Agregar `break` hace que el bucle se detenga en un elemento negativo. El bucle `forEach()` no puede hacer eso.

 Sugerencia

Experimente con bucles en una matriz propia en la consola del explorador. Si quiere un desafío, hay otras maneras de recorrer en bucle matrices que no sean los bucles `for` y `while`. Hay bucles [`forEach`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach), [`for-of`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of/) y [`map`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map/). Pruebe a reescribir el bucle de matriz mediante una de estas técnicas.



# Uso de operaciones para consultar matrices

Completado100 XP

- 4 minutos

Ha obtenido mucha información, aun así, las matrices son mucho más complejas que simplemente iterar por ellas o quitar y agregar elementos. También puede consultarlas o realizar operaciones en ellas.

## Filtrado

Puede realizar muchas operaciones útiles en una matriz. Buscar y filtrar aquello que necesita son operaciones que es probable que realice con frecuencia.

### Buscar un elemento mediante `find()`

Imagine que alguien le pregunta, ¿tiene helado de "Chocolate"? y, si lo tiene, ¿me pone uno? A ese punto, puede usar el método `find()` en la matriz, como se muestra aquí:

JavaScriptCopiar

```javascript
let iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Neapolitan", "Mint Chip"];
iceCreamFlavors.find(flavor => flavor === "Chocolate") // "Chocolate"
```

La operación `find()` ejecuta la función que proporcionó como entrada para cada elemento. Si la operación descubre el elemento que se busca, devuelve el elemento. Si no encuentra el elemento, devuelve `undefined`.

### Filtrar elementos con una propiedad común mediante `filter()`

¿Qué ocurre si el cliente dice: quiero un helado que *contenga* "Chocolate", ¿qué tiene? Debe reordenar un poco la heladería y empezar a organizar por categorías. La consulta de este cliente debe devolver "Chocolate", "Napolitano" y "Menta con chocolate" como sabores que contienen "Chocolate". Teniendo esto en cuenta, opta por almacenar la matriz de la siguiente manera:

JavaScriptCopiar

```javascript
let iceCreamFlavors = [
  { name: "Chocolate", type: "Chocolate" }, 
  { name: "Strawberry", type: "fruit"}, 
  { name: "Vanilla", type: "Vanilla"}, 
  { name: "Pistachio", type: "Nuts"}, 
  { name: "Neapolitan", type: "Chocolate"}, 
  { name: "Mint Chip", type: "Chocolate"}
];
```

Ya ha reorganizado la oferta. El cliente pide un helado que contenga chocolate y parece que quiere una bola de cada uno de los tres sabores devueltos por la consulta. El mejor método para usar en este caso es la operación `filter()`. Toma una expresión de filtro (una función) y devuelve cualquier elemento que coincida con la expresión. Para ayudar al cliente a encontrar lo que quiere, use el código siguiente:

JavaScriptCopiar

```javascript
iceCreamFlavors.filter(flavor => flavor.type === "Chocolate") // [{ name: "Chocolate", type: "Chocolate" }, { name: "Neapolitan", type: "Chocolate"}, { name: "Mint Chip", type: "Chocolate"}]
```

### Comprobación de una condición mediante `some()`

Uno de sus clientes es alérgico a las "Nueces" y primero quiere saber si alguno de los helados contiene "Nueces". Comprueba el inventario mediante el método `some()`. El método usa una función que comprueba si al menos un elemento cumple una condición.

JavaScriptCopiar

```javascript
iceCreamFlavors.some(flavor => flavor.type === "Nuts") // true
```

Dado que el helado de "Pistacho" contiene nueces, el método `some()` devuelve *true*. Ahora, el cliente quiere saber qué sabores *puede* escoger, lo que le lleva a ejecutar este código:

JavaScriptCopiar

```javascript
iceCreamFlavors.filter(flavor => flavor.type !== "Nuts") // returns everything except for Pistachio.
```

## Asignación de proyecciones

Una proyección es intentar cambiar la matriz de alguna manera. Imagine, por ejemplo, que toma la matriz original `iceCreamFlavor` y desea agregar una propiedad `price` a cada sabor. Esta situación es adecuada para un método de proyección llamado `map()`. Imagínese un día soleado y que decide que cada bola de helado que vende debe costar 1 $. Escribe código para que esto suceda, como se muestra a continuación:

JavaScriptCopiar

```javascript
let iceCreamFlavors = [
  { name: "Chocolate", type: "Chocolate" }, 
  { name: "Strawberry", type: "fruit"}, 
  { name: "Vanilla", type: "Vanilla"}, 
  { name: "Pistachio", type: "Nuts"}, 
  { name: "Neapolitan", type: "Chocolate"}, 
  { name: "Mint Chip", type: "Chocolate"}
];
iceCreamFlavors.map(flavor => {
  flavor.price = 1;
  return flavor;
}) // every item now has a new property price: 1 
```

El código pasa por cada elemento de la lista, adjunta la propiedad `price`, le proporciona el valor `1` y, a continuación, devuelve el elemento.

## Agregaciones

El negocio funciona. Hoy hace sol y ha vendido muchos helados. Los recibos de su caja están almacenados en una matriz larga, que se parece al código siguiente:

JavaScriptCopiar

```javascript
let sales = [{
 date : '2021-05-01',
 amount: 2
},
{
 date : '2021-05-01',
 amount: 1
}
// and so on...
]
```

Podría usar un bucle `for` para sumarlo todo, de la siguiente manera:

JavaScriptCopiar

```javascript
let sum = 0;
for( let i =0; i< sales.length; i++) {
  sum += sales[i].amount; 
}
```

Este código funciona, pero hay una estrategia más elegante: es decir, el método `reduce()`. El objetivo de este método es *reducir* una lista larga a un solo elemento, que podría ser un objeto o un número, por ejemplo. Para usar `reduce(),` debe proporcionarle una función que tome dos parámetros, un valor acumulado y el valor actual del bucle.

Dentro de la función, debe volver a calcular el valor acumulado mediante el valor actual. El segundo argumento de `reduce()` es el valor de inicio. Dado que en este caso quiere usar `reduce()` para calcular las ventas, la función debe actualizar el valor acumulado con el valor de lo que hay en la propiedad `amount` para cada elemento. El valor inicial debe ser `0`. Con esto en mente, el aspecto del código es el siguiente:

JavaScriptCopiar

```javascript
sales.reduce((acc, curr) => acc + curr.amount, 0);
```

Como puede ver, no se necesita una variable `sum`. Tardará un poco en acostumbrarse a esta estrategia, pero es eficaz y se puede usar en muchas situaciones.



# Operaciones de ejercicio

Completado100 XP

- 3 minutos

Como propietario de la heladería y puesto que ha adquirido algunas aptitudes de programación, ha decidido desarrollar un software para su negocio. Puede que un día convierta la heladería en una cadena.

En primer lugar, quiere codificar todo lo que sabe sobre su negocio, como los distintos helados y los precios. A continuación, quiere simular interacciones de clientes. Por último, quiere calcular los beneficios y obtener más información útil.

## Crear negocio

En primer lugar, inicie su imperio de heladerías mediante la codificación de todos los sabores de los que dispone.

1. Cree un archivo, llámelo *app.js* y agregue el siguiente contenido:

   JavaScriptCopiar

   ```javascript
   let iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Neapolitan", "Mint Chip", "Raspberry"];
   ```

2. A continuación, quiere clasificar los sabores por tipo y asignarle un precio a cada uno. Acaba por modificar el código de la siguiente manera:

   JavaScriptCopiar

   ```javascript
   let iceCreamFlavors = [
    { name: "Chocolate", type: "Chocolate", price: 2 }, 
    { name: "Strawberry", type: "Fruit", price: 1 }, 
    { name: "Vanilla", type: "Vanilla", price 2 }, 
    { name: "Pistachio", type: "Nuts", price: 1.5 }, 
    { name: "Neapolitan", type: "Chocolate", price: 2}, 
    { name: "Mint Chip", type: "Chocolate", price: 1.5 },
    { name: "Raspberry", type: "Fruit", price: 1},
   ];
   ```

   Ahora el elemento de la matriz ha pasado de cadenas a objetos. Ha realizado este cambio para anticiparse a los clientes que consultan los precios o los tipos de helado que tiene.

## Recepción de clientes

Quiere simular algunos escenarios de clientes en el código, para asegurarse de que la manera en que clasificó el inventario es lo suficientemente flexible.

1. Antes de la primera transacción de cliente, se da cuenta de que necesita una matriz `transactions`. Empieza a pensar en qué información desea guardar en cada transacción. El precio es definitivamente algo que debe guardar y probablemente también lo que compran los clientes. Agrega el código siguiente:

   JavaScriptCopiar

   ```javascript
   // { scoops: [], total: }
   let transactions = []
   ```

2. A continuación, decide codificar transacciones mediante la adición del código siguiente:

   JavaScriptCopiar

   ```javascript
   transactions.push({ scoops: ["Chocolate", "Vanilla", "Mint Chip"], total: 5.5 })
   transactions.push({ scoops: ["Raspberry", "StrawBerry"], total: 2 })
   transactions.push({ scoops: ["Vanilla", "Vanilla"], total: 4 })
   ```

   Esto simula tres interacciones de clientes. A continuación, desea analizar el resultado.

## Analizar el negocio

Cuando se tiene un negocio, los beneficios son importantes, pero no son lo único que importa. ¿Qué es aquello que se vende tanto que necesita asegurarse de que haya existencias suficientes? También, ¿qué es lo que no se vende tanto, por lo que no es necesario tener tantas existencias?

1. Para calcular las ganancias, agregue el código siguiente:

   JavaScriptCopiar

   ```javascript
   const total = transactions.reduce((acc, curr) => acc + curr.total, 0);
   console.log(`You've made ${total} $ today`); // You've made 11.5 $ today
   ```

2. Para averiguar cuánto ha vendido de cada sabor, agregue el código siguiente:

   JavaScriptCopiar

   ```javascript
   let flavorDistribution = transactions.reduce((acc, curr) => {
     curr.scoops.forEach(scoop => {
       if (!acc[scoop]) {
         acc[scoop] = 0;
       }
       acc[scoop]++;
     })
     return acc;
   }, {}) // { Chocolate: 1, Vanilla: 3, Mint Chip: 1, Raspberry: 1, StrawBerry: 1 }
   ```

   El código anterior repasa todas las transacciones. Para cada transacción, comprueba la cantidad de bolas de helado y actualiza un diccionario con la frecuencia de compra de cada sabor. Si estas ventas fueran reales, es probable que tuviera que tener más existencias de vainilla.

Enhorabuena, ha abierto una heladería. Ya sabe cómo codificar sabores y transacciones mediante matrices y objetos. También ha aprendido a hacer un resumen de sus ganancias y a identificar la cantidad de helado que ha vendido de cada sabor.



# Resumen

Completado100 XP

- 1 minuto

Ahora que conoce las matrices y bucles de JavaScript, puede empezar a pensar en formas de estructurar y organizar los datos en el código JavaScript.

Para practicar lo que ha aprendido, visite algunos de sus sitios web favoritos y tenga en cuenta los tipos de datos que usan. Por ejemplo, considere la forma en que se agregan y quitan elementos de un carro de la compra en línea, o la forma como el equipo y las existencias de un jugador se agregan y quitan en un juego basado en explorador. Tenga en cuenta por qué y cómo se usan los bucles y matrices.

A medida que adquiera más conocimientos sobre matrices y bucles, empezará a tener en cuenta estos tipos de datos y métodos de almacenamiento en los sitios web que usa cada día.

 Sugerencia

Las matrices de JavaScript tienen muchos métodos asociados que son útiles para la manipulación de datos. [Lea estos métodos](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/) y pruebe algunos de ellos (como `push`, `pop`, `slice` y `splice`) en una matriz que haya creado.









_______



# Ejercicio de variables

​				 				Completado 			 			100 XP 		

- 3 minutos

Espacio aislado activado Tiempo restante:

​			

​			 	

Ha usado 1 de los 10 espacios aislados de hoy. Mañana habrá disponibles más espacios aislados.

Como nuevo desarrollador de juegos, se le ha encargado la tarea de crear juegos recreativos para Internet. Su primera tarea consiste en  empezar a trabajar en el juego de cartas Texas Hold'em. En lugar de que  los jugadores apuesten dinero, usará puntos para representar las fichas  de póker.

## Modelado del estado del juego

Debe tomar lo que sabe de Texas Hold'em y crear variables para almacenar valores de cartas. Al hacerlo, debe pensar en los *valores de inicio* y en los valores que cambiarán con el tiempo.

Sabe que en el Texas Hold'em hay jugadores, cartas iniciales y  puntos. Intente montar una estructura de juego básica mediante  variables.

1. Cree un archivo denominado *app.js*:

   Bash

```bash
touch app.js
code .
```

Ahora debería tener un editor abierto en el shell.

Agregue el siguiente código al archivo:

JavaScript

```javascript
let startingPokerChips = 100; // points
let players = 3;
let noOfStarterCards = 2;
```

Ahora tiene tres variables para representar el estado inicial del juego.

Cree variables que representen a jugadores concretos. Agregue el código siguiente:

JavaScript

```javascript
let playerOnePoints = startingPokerChips;
let playerTwoPoints = startingPokerChips;
let playerThreePoints = startingPokerChips;
```

Ha creado los puntos de partida de tres jugadores asignándoles la variable `startingPokerChips`, que contiene el valor `100`.

Muestre una ronda del juego específica y cómo una asignación  puede representar un estado del juego. Agregue las siguientes líneas al  código:

JavaScript

1. ```javascript
   playerOnePoints -= 50;
   playerTwoPoints -=25;
   playerThreePoints +=75; 
   ```

Ha simulado correctamente una ronda del juego en la que el primer y  el segundo jugador han apostado 50 y 25 puntos respectivamente. Dado que el tercer jugador tiene una mejor mano, este termina ganando la ronda.  El juego toma los puntos del primer y el segundo jugador y los agrega al bote del tercer jugador.

## Refactorización a constantes

En este punto, tiene algunas variables que representan partes del  juego de cartas. Recuerde que tiene constantes disponibles, que son  variables que no deben cambiar su valor. Veamos qué variables se podrían prestar para representarse mejor como constantes en el código fuente.

 Sugerencia

Dedique uno o dos minutos a pensar en qué variables no deben cambiar y qué variables podrían tener valores cambiantes. A continuación,  desplácese hacia abajo para ver la solución.

1. En la parte superior del archivo, cambie el código siguiente:

   JavaScript

```javascript
let startingPokerChips = 100; // points
let players = 3;
let noOfStarterCards = 2;
```

... por este código:

JavaScript

```javascript
const STARTING_POKER_CHIPS = 100; // points
const PLAYERS = 3;
const NO_OF_STARTER_CARDS = 2;
```

Ha identificado correctamente qué variables son importantes para el  juego. También describen cómo se juega. Las fichas iniciales de un  jugador no cambiarán, incluso si el bote de un jugador determinado  cambia durante el juego. El número de jugadores también es constante, a  menos que imagine que podría recompilar el juego de forma que un jugador pueda unirse en cualquier momento. El número de cartas iniciales  siempre es dos en el Texas Hold'em. Como desarrollador de juegos, tiene  la capacidad de decidir en última instancia qué debe ser modificable y  qué debe ser constante.

 Sugerencia

Una excelente manera de pensar en las variables es convertir todas  las variables en constantes para empezar. A continuación, decida si el  valor de una variable tendrá que cambiar en el futuro. En tal caso,  cámbiela de `const` a `let`.

Asegúrese de cambiar el código dependiente, para que el código se siga compilando:

JavaScript

1. ```javascript
   let playerOnePoints = STARTING_POKER_CHIPS;
   let playerTwoPoints = STARTING_POKER_CHIPS;
   let playerThreePoints = STARTING_POKER_CHIPS;
   ```

¡Enhorabuena! Ha empezado a trabajar en una base de código de  JavaScript que implementa Texas Hold'em. Al hacerlo, ha determinado  cuáles son los valores de inicio, qué valores pueden cambiar y cómo  cambiar los valores.

------

## Siguiente unidad: Tipos de datos

# Ejercicio - Tipos de datos

​				 				Completado 			 			100 XP 		

- 3 minutos

Espacio aislado activado Tiempo restante:

​			

​			 	

Ha usado 1 de los 10 espacios aislados de hoy. Mañana habrá disponibles más espacios aislados.

Su empresa está satisfecha con el modelado anterior del Texas  Hold'em y desea ver que sigue trabajando en su implementación. Ya sabe  más sobre los tipos de datos, así que vamos a poner esos conocimientos  en práctica.

## Adición de tipos de datos

Para empezar, vamos a revisar el código siguiente que ha creado hasta ahora:

JavaScript

```javascript
const STARTING_POKER_CHIPS = 100; // points
const PLAYERS = 3;
const NO_OF_STARTER_CARDS = 2;

let playerOnePoints = STARTING_POKER_CHIPS;
let playerTwoPoints = STARTING_POKER_CHIPS;
let playerThreePoints = STARTING_POKER_CHIPS;

playerOnePoints -= 50;
playerTwoPoints -=25;
playerThreePoints +=75; 
```

Tiene ciertos aspectos del juego representados como variables, pero  carece de otros aspectos, como saber si el juego ha finalizado. Además,  sería bueno que los jugadores tuvieran nombres.

1. Después de las tres constantes, agregue el siguiente código:

   JavaScript

```javascript
let playerOneName = "Chloe";
let playerTwoName = "Jasmine";
let playerThreeName = "Jen";
```

Ahora tiene tres variables para representar los nombres de los  jugadores. Vamos a agregar texto de introducción para que se note que es un juego. Después del código siguiente:

JavaScript

```javascript
let playerOnePoints = STARTING_POKER_CHIPS;
let playerTwoPoints = STARTING_POKER_CHIPS;
let playerThreePoints = STARTING_POKER_CHIPS;
```

... agregue código para representar el inicio del juego:

JavaScript

1. ```javascript
   console.log(`Welcome to Texas Hold'em. The championship title will be awarded to one of these three players: ${playerOneName}, ${playerTwoName} and ${playerThreeName}. Each player has ${STARTING_POKER_CHIPS} in their pot. We have an exciting game ahead of us. May the best player win!`)
   ```

## Adición de una condición de fin

Una partida de Texas Hold'em puede alargarse durante muchas rondas y  normalmente finaliza cuando un jugador tiene todas las fichas y los  demás jugadores han perdido las suyas. Debe agregar código para  representar este estado. En esta situación conviene confiar en los  operadores y usar un tipo de datos booleano.

1. Agregue el código siguiente en la parte superior del archivo:

   JavaScript

```javascript
let gameHasEnded = false;
```

Ya tiene una variable para representar el final del juego. Más  adelante, deberá encontrar una manera de volver a evaluar el valor de  esta variable y determinar si se debe detener el juego y designar un  ganador.

Agregue el código siguiente para evaluar el estado del juego:

JavaScript

```javascript
gameHasEnded = ((playerOnePoints + playerTwoPoints) == 0) || // three has won
               ((playerTwoPoints + playerThreePoints) == 0) ||  // one has won
               ((playerOnePoints + playerThreePoints) == 0);  // two has won 
console.log("Game has ended: ", gameHasEnded);
```

El código completo debe ser similar al siguiente:

JavaScript

```javascript
const STARTING_POKER_CHIPS = 100; // points
const PLAYERS = 3;
const NO_OF_STARTER_CARDS = 2;
let gameHasEnded = false;

let playerOneName = "Chloe";
let playerTwoName = "Jasmine";
let playerThreeName = "Jen";

console.log(`Welcome to Texas Hold'em. The championship title will be awarded to one of these three players: ${playerOneName}, ${playerTwoName}, and ${playerThreeName}. Each player has ${STARTING_POKER_CHIPS} in their pot. We have an exciting game ahead of us. May the best player win!`);

let playerOnePoints = STARTING_POKER_CHIPS;
let playerTwoPoints = STARTING_POKER_CHIPS;
let playerThreePoints = STARTING_POKER_CHIPS;

playerOnePoints -= 50;
playerTwoPoints -=25;
playerThreePoints +=75; 

gameHasEnded = ((playerOnePoints + playerTwoPoints) == 0) || // three has one
               ((playerTwoPoints + playerThreePoints) == 0) ||  // one has won
               ((playerOnePoints + playerThreePoints) == 0);  // two has won 

console.log("Game has ended: ", gameHasEnded);
```

Para ejecutar el juego, escriba el código siguiente en el terminal:

JavaScript

```javascript
node app.js
```

Debería aparecer la salida siguiente:

Resultados

1. ```output
   Welcome to Texas Hold'em. The championship title will be awarded to one of these three players: Chloe, Jasmine, and Jen. Each player has 100 in their pot. We have an exciting game ahead of us. May the best player win!
   Game has ended: false
   ```

 Sugerencia

Pruebe a cambiar `playerOnePoints` y `playerTwoPoints` a `0` y vuelva a ejecutar la aplicación. ¿Hay alguna diferencia en el resultado?

------

## Siguiente unidad: Resumen