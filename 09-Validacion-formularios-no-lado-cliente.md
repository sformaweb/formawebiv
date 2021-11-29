# Validación de formularios no lado do cliente

Antes de enviar datos ao servidor, é importante asegurarse de que todos os controis de formulario necesarios estean cubertos no formato correcto. Isto denomínase **validación do formulario no lado do cliente** e axuda a garantir que os datos enviados coincidan cos requisitos establecidos nos distintos controis do formulario. Este artigo lévache a través de conceptos básicos e exemplos de validación de formularios no lado do cliente.

| Requisitos previos: | Alfabetización informática, unha comprensión razoable de [HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML) , [CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS) e [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript) . |
| :------------------ | ------------------------------------------------------------ |
| Obxectivo:          | Para comprender que é a validación de formularios no lado do cliente, por que é importante e como aplicar varias técnicas para implementala. |

A validación do cliente é unha comprobación inicial e unha característica importante dunha boa experiencia de usuario; ao capturar datos non válidos no lado do cliente, o usuario pode solucionalo inmediatamente. Se chega ao servidor e despois é rexeitado, un atraso notable é causado por unha viaxe de ida e volta ao servidor e despois de volta ao lado do cliente para dicirlle ao usuario que corrixa os seus datos.

Non obstante, a validación do cliente *non debe considerarse* unha medida de seguridade exhaustiva. As túas aplicacións sempre deberían realizar comprobacións de seguranza en calquera dato enviado por formulario no *lado* do *servidor* **, así** como no lado do cliente, porque a validación do lado do cliente é demasiado fácil de ignorar, polo que os usuarios maliciosos poden enviar facilmente datos incorrectos ao teu servidor. . Lea [Seguridade do sitio web](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security) para ter unha idea do que *podería* pasar; implementar a validación do servidor está algo máis aló do alcance deste módulo, pero debes telo presente.

## [Que é a validación de formularios?](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#what_is_form_validation)

Vai a calquera sitio popular cun formulario de rexistro e notarás que proporcionan comentarios cando non introduzas os teus datos no formato que esperan. Recibirás mensaxes como:

- "Este campo é obrigatorio" (non podes deixar este campo en branco).
- "Introduce o teu número de teléfono no formato xxx-xxxx" (requírese un formato de datos específico para que se considere válido).
- "Introduce un enderezo de correo electrónico válido" (os datos que introduciu non están no formato correcto).
- "O teu contrasinal debe ter entre 8 e 30 caracteres e conter unha letra maiúscula, un símbolo e un número". (Requírese un formato de datos moi específico para os seus datos).

Isto chámase **validación de formularios** . Cando introduza os datos, o navegador e/ou o servidor web comprobarán que os datos están no formato correcto e dentro das restricións establecidas pola aplicación. A validación realizada no navegador chámase validación do **lado do cliente** , mentres que a validación realizada no servidor chámase validación do **lado do servidor** . Neste capítulo centrámonos na validación do cliente.

Se a información está formateada correctamente, a aplicación permite que os datos sexan enviados ao servidor e (normalmente) gardados nunha base de datos; se a información non está formateada correctamente, envíalle ao usuario unha mensaxe de erro que explica o que hai que corrixir e permítelle tentalo de novo.

Queremos que o enchido de formularios web sexa o máis sinxelo posible. Entón, por que insistimos en validar os nosos formularios? Hai tres razóns principais:

- **Queremos obter os datos correctos, no formato correcto.** As nosas aplicacións non funcionarán correctamente se os datos dos nosos usuarios se almacenan nun formato incorrecto, son incorrectos ou se omiten por completo.

- **Queremos protexer os datos dos nosos usuarios** . Forzar aos nosos usuarios a introducir contrasinais seguros fai que sexa máis fácil protexer a información da súa conta.

- Queremos protexernos

   . Hai moitas formas en que os usuarios malintencionados poden usar mal os formularios non protexidos para danar a aplicación (consulta 

  Seguridade do sitio web

   ).

  **Aviso::** Nunca confíe nos datos pasados ao seu servidor desde o cliente. Aínda que o teu formulario estea validando correctamente e evitando a entrada incorrecta no lado do cliente, un usuario malintencionado aínda pode alterar a solicitude de rede.

## [Diferentes tipos de validación do cliente](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#different_types_of_client-side_validation)

Hai dous tipos diferentes de validación do cliente que atoparás na web:

- **A validación de formularios integrada** usa funcións de validación de formularios HTML5, que comentamos en moitos lugares ao longo deste módulo. Esta validación xeralmente non require moito JavaScript. A validación de formularios integrada ten un mellor rendemento que JavaScript, pero non é tan personalizable como a validación de JavaScript.
- **A** validación de **JavaScript** está codificada mediante JavaScript. Esta validación é totalmente personalizable, pero cómpre creala toda (ou usar unha biblioteca).

## [Usando a validación integrada do formulario](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#using_built-in_form_validation)

Unha das características máis significativas dos [controis de formulario HTML5](https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML5_input_types) é a posibilidade de validar a maioría dos datos dos usuarios sen depender de JavaScript. Isto faise usando atributos de validación nos elementos do formulario. Vimos moitos destes a principios do curso, pero para recapitular:

- [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/required): Especifica se hai que cubrir un campo de formulario antes de poder enviar o formulario.
- [`minlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/minlength)e [`maxlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/maxlength): Especifica a lonxitude mínima e máxima dos datos textuais (cadeas)
- [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/min)e [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/max): Especifica os valores mínimos e máximos dos tipos de entrada numérica
- `type`: Especifica se os datos deben ser un número, un enderezo de correo electrónico ou algún outro tipo de predefinido específico.
- [`pattern`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern): Especifica unha [expresión regular](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) que define un patrón que deben seguir os datos introducidos.

Se os datos introducidos nun campo de formulario seguen todas as regras especificadas polos atributos anteriores, considérase válido. Se non, considérase non válido.

Cando un elemento é válido, son verdadeiras as seguintes cousas:

- O elemento coincide coa [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)pseudo-clase CSS, que lle permite aplicar un estilo específico a elementos válidos.
- Se o usuario tenta enviar os datos, o navegador enviará o formulario, sempre que non haxa outra cousa que o impida (por exemplo, JavaScript).

Cando un elemento non é válido, son verdadeiras as seguintes cousas:

- O elemento coincide coa [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudo-clase CSS e, ás veces, con outras pseudo-clases da IU (por exemplo, [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)) dependendo do erro, o que lle permite aplicar un estilo específico a elementos non válidos.
- Se o usuario tenta enviar os datos, o navegador bloqueará o formulario e mostrará unha mensaxe de erro.

**Nota:** Existen varios erros que han impedir que o formulario para enviar, incluíndo un [`badInput`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/badInput), [`patternMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch), [`rangeOverflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeOverflow)ou [`rangeUnderflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow), [`stepMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/stepMismatch), [`tooLong`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooLong)ou [`tooShort`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooShort), [`typeMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch), `valueMissing`ou un `customError`.

## [Exemplos de validación de formularios integrados](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#built-in_form_validation_examples)

Nesta sección, probaremos algúns dos atributos que comentamos anteriormente.

### [Arquivo de inicio sinxelo](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#simple_start_file)

Comecemos cun exemplo sinxelo: unha entrada que che permite escoller se prefires un plátano ou unha cereixa. Este exemplo implica un texto sinxelo [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)cun asociado [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)e un submit [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button). Busca o código fonte en GitHub en [fruit-start.html](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/fruit-start.html) e un exemplo en directo a continuación.

```
<form>
  <label for="choose">Would you prefer a banana or cherry?</label>
  <input id="choose" name="i_like">
  <button>Submit</button>
</form>
```

Copiar ao portapapeis

```
input:invalid {
  border: 2px dashed red;
}

input:valid {
  border: 2px solid black;
}
```

Copiar ao portapapeis

<iframe class="sample-code-frame" title="Exemplo sinxelo de ficheiro de inicio" id="frame_Simple_start_file" width="100%" height="80" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/Forms/Form_validation/_sample_.Simple_start_file.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 963.75px; max-width: 100%;"></iframe>

Para comezar, fai unha copia `fruit-start.html`nun novo directorio do teu disco duro.

### [O atributo necesario](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#the_required_attribute)

A función de validación HTML5 máis sinxela é o [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/required)atributo. Para facer unha entrada obrigatoria, engade este atributo ao elemento. Cando se define este atributo, o elemento coincide coa [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required)pseudo-clase da IU e o formulario non se enviará, mostrando unha mensaxe de erro ao enviar cando a entrada está baleira. Mentres estea baleira, a entrada tamén se considerará non válida, coincidindo coa [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudo-clase da IU.

Engade un `required`atributo á túa entrada, como se mostra a continuación.

```
<form>
  <label for="choose">Would you prefer a banana or cherry? (required)</label>
  <input id="choose" name="i_like" required>
  <button>Submit</button>
</form>
```

Copiar ao portapapeis

Teña en conta o CSS que se inclúe no ficheiro de exemplo:

```
input:invalid {
  border: 2px dashed red;
}

input:invalid:required {
  background-image: linear-gradient(to right, pink, lightgreen);
}

input:valid {
  border: 2px solid black;
}
```

Copiar ao portapapeis

Este CSS fai que a entrada teña un bordo vermello discontinuo cando non é válido e un bordo negro sólido máis sutil cando é válido. Tamén engadimos un degradado de fondo cando a entrada é necesaria *e* non é válida. Proba o novo comportamento no seguinte exemplo:

<iframe class="sample-code-frame" title="A mostra do atributo requirido" id="frame_The_required_attribute" width="100%" height="80" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/Forms/Form_validation/_sample_.The_required_attribute.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 963.75px; max-width: 100%;"></iframe>

**Nota:** Podes atopar este exemplo en directo en GitHub como[froita-validación.html](https://mdn.github.io/learning-area/html/forms/form-validation/fruit-required.html) (ver tamén o [código fonte](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/fruit-required.html).)

Proba a enviar o formulario sen valor. Teña en conta como se enfoca a entrada non válida, aparece unha mensaxe de erro predeterminada ("Encha este campo") e impide o envío do formulario.

A presenza do `required`atributo en calquera elemento que admita este atributo significa que o elemento coincide coa [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required)pseudoclase se ten un valor ou non. Se non [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)ten valor, `input`coincidirá coa [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudoclase.

**Nota:** Para unha boa experiencia de usuario, indíquelle cando se requiren os campos do formulario. Non só é unha boa experiencia de usuario, é obrigada polas directrices de [accesibilidade](https://developer.mozilla.org/en-US/docs/Learn/Accessibility) WCAG . Ademais, só esixe que os usuarios introduzan os datos que realmente necesitas: por exemplo, por que realmente precisas saber o sexo ou o título de alguén?

### [Validación contra unha expresión regular](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#validating_against_a_regular_expression)

Outra característica de validación útil é o [`pattern`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern)atributo, que espera unha [Expresión regular](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) como valor. Unha expresión regular (regex) é un patrón que se pode usar para facer coincidir combinacións de caracteres en cadeas de texto, polo que as expresións regulares son ideais para a validación de formularios e serven para outros usos en JavaScript.

As expresións regulares son bastante complexas e non pretendemos ensinalas exhaustivamente neste artigo. A continuación móstranse algúns exemplos para facerche unha idea básica de como funcionan.

- `a`— Coincide cun carácter que é `a`(non `b`, non `aa`, etc.).
- `abc`— Coincidencias `a`, seguido de `b`, seguido de `c`.
- `ab?c`—Coincidencias `a`, seguidas opcionalmente dunha única `b`, seguida de `c`. ( `ac`ou `abc`)
- `ab*c`—Coincidencias `a`, seguidas opcionalmente de calquera número de `b`s, seguido de `c`. ( `ac`, `abc`, `abbbbbc`, etc.).
- `a|b`— Coincide cun carácter que é `a`ou `b`.
- `abc|xyz`— Coincide exactamente `abc`ou exactamente `xyz`(pero non `abcxyz` ou `a`ou `y`, etc.).

Hai moitas máis posibilidades que non cubrimos aquí. Para obter unha lista completa e moitos exemplos, consulta a nosa documentación de [expresións regulares](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) .

Imos implementar un exemplo. Actualiza o teu HTML para engadir un [`pattern`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern)atributo como este:

```
<form>
  <label for="choose">Would you prefer a banana or a cherry?</label>
  <input id="choose" name="i_like" required pattern="[Bb]anana|[Cc]herry">
  <button>Submit</button>
</form>
```

Copiar ao portapapeis

Isto ofrécenos a seguinte actualización: próbaa:

<iframe class="sample-code-frame" title="Validación contra unha mostra de expresión regular" id="frame_Validating_against_a_regular_expression" width="100%" height="80" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/Forms/Form_validation/_sample_.Validating_against_a_regular_expression.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 963.75px; max-width: 100%;"></iframe>

**Nota:** Podes atopar este exemplo en directo en GitHub como[patrón-fruta.html](https://mdn.github.io/learning-area/html/forms/form-validation/fruit-pattern.html) (ver tamén o [código fonte](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/fruit-pattern.html).)

Neste exemplo, o [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)elemento acepta un dos catro valores posibles: as cadeas "banana", "Banana", "cherry" ou "Cherry". As expresións regulares distinguen entre maiúsculas e minúsculas, pero admitimos versións en maiúsculas e minúsculas utilizando un patrón "Aa" adicional aniñado entre corchetes.

Neste punto, proba a cambiar o valor dentro do [`pattern`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern)atributo para igualar algúns dos exemplos que viches anteriormente e mira como iso afecta aos valores que podes introducir para que o valor de entrada sexa válido. Proba a escribir algunha das túas e mira como vai. Fainos relacionados coas froitas sempre que sexa posible para que os teus exemplos teñan sentido!

Se un valor non baleiro de [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)non coincide co patrón da expresión regular, o `input`coincidirá coa [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudoclase.

**Nota:** Algúns [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)tipos de elementos non necesitan un [`pattern`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern)atributo para validarse contra unha expresión regular. Especificar o `email`tipo, por exemplo, valida o valor de entrada contra un patrón de enderezo de correo electrónico ben formado ou un patrón que coincida cunha lista de enderezos de correo electrónico separados por comas se ten o [`multiple`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/multiple)atributo.

**Nota:** O [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)elemento non soporta o [`pattern`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern)atributo.

### [Limitar a lonxitude das túas entradas](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#constraining_the_length_of_your_entries)

Pode restrinxir a lonxitude de caracteres de todos os campos de texto creados mediante [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)ou [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)mediante os atributos [`minlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/minlength)e [`maxlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/maxlength). Un campo non é válido se ten un valor e ese valor ten menos caracteres que o [`minlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/minlength)valor ou máis que o [`maxlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/maxlength)valor.

Os navegadores moitas veces non permiten que o usuario escriba un valor máis longo do esperado nos campos de texto. Unha experiencia de usuario mellor que usar só `maxlength`é proporcionar tamén comentarios sobre o reconto de caracteres dun xeito accesible e permitirlles editar o seu contido ata o tamaño. Un exemplo diso é o límite de caracteres que se ve en Twitter ao chío. JavaScript, incluído[solucións empregando `maxlength`](https://github.com/mimo84/bootstrap-maxlength), pódese usar para proporcionar isto

### [Limitación dos valores das súas entradas](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#constraining_the_values_of_your_entries)

Para os campos numéricos (por exemplo, [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/number)), os atributos [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/min)e [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/max)pódense utilizar para proporcionar un intervalo de valores válidos. Se o campo contén un valor fóra deste intervalo, non será válido.

Vexamos outro exemplo. Crea unha nova copia do[fruit-start.html](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/fruit-start.html) arquivo.

Agora elimina o contido do `<body>`elemento e substitúeo polo seguinte:

```
<form>
  <div>
    <label for="choose">Would you prefer a banana or a cherry?</label>
    <input type="text" id="choose" name="i_like" required minlength="6" maxlength="6">
  </div>
  <div>
    <label for="number">How many would you like?</label>
    <input type="number" id="number" name="amount" value="1" min="1" max="10">
  </div>
  <div>
    <button>Submit</button>
  </div>
</form>
```

Copiar ao portapapeis

- Aquí veredes que lle demos ao `text`campo a `minlength`e `maxlength`de seis, que ten a mesma lonxitude que o plátano e a cereixa.
- Tamén lle demos ao `number`campo a `min`un e a `max`de dez. Os números introducidos fóra deste intervalo mostraranse como non válidos; os usuarios non poderán utilizar as frechas de incremento/decremento para mover o valor fóra deste intervalo. Se o usuario introduce manualmente un número fóra deste intervalo, os datos non son válidos. O número non é necesario, polo que se elimina o valor, seguirá sendo un valor válido.

Este é o exemplo en directo:

<iframe class="sample-code-frame" title="Limitación dos valores da mostra das súas entradas" id="frame_Constraining_the_values_of_your_entries" width="100%" height="100" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/Forms/Form_validation/_sample_.Constraining_the_values_of_your_entries.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 963.75px; max-width: 100%;"></iframe>

**Nota:** Podes atopar este exemplo en directo en GitHub como[lonxitude da froita.html](https://mdn.github.io/learning-area/html/forms/form-validation/fruit-length.html) (ver tamén o [código fonte](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/fruit-length.html).)

**Nota:** `<input type="number">` (e outros tipos, como `range`e `date`) tamén poden tomar un [`step`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/step)atributo, que especifica en que incremento subirá ou baixará o valor cando se utilicen os controis de entrada (como os botóns numéricos arriba e abaixo). No exemplo anterior non incluímos un `step`atributo, polo que o valor predeterminado é `1`. Isto significa que os flotadores, como 3.2, tamén se mostrarán como non válidos.

### [Exemplo completo](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#full_example)

Aquí tes un exemplo completo para mostrar o uso das funcións de validación integradas de HTML. Primeiro, algo de HTML:

```
<form>
  <p>
    <fieldset>
      <legend>Do you have a driver's license?<abbr title="This field is mandatory" aria-label="required">*</abbr></legend>
      <!-- While only one radio button in a same-named group can be selected at a time,
           and therefore only one radio button in a same-named group having the "required"
           attribute suffices in making a selection a requirement -->
      <input type="radio" required name="driver" id="r1" value="yes"><label for="r1">Yes</label>
      <input type="radio" required name="driver" id="r2" value="no"><label for="r2">No</label>
    </fieldset>
  </p>
  <p>
    <label for="n1">How old are you?</label>
    <!-- The pattern attribute can act as a fallback for browsers which
         don't implement the number input type but support the pattern attribute.
         Please note that browsers that support the pattern attribute will make it
         fail silently when used with a number field.
         Its usage here acts only as a fallback -->
    <input type="number" min="12" max="120" step="1" id="n1" name="age"
           pattern="\d+">
  </p>
  <p>
    <label for="t1">What's your favorite fruit?<abbr title="This field is mandatory" aria-label="required">*</abbr></label>
    <input type="text" id="t1" name="fruit" list="l1" required
           pattern="[Bb]anana|[Cc]herry|[Aa]pple|[Ss]trawberry|[Ll]emon|[Oo]range">
    <datalist id="l1">
      <option>Banana</option>
      <option>Cherry</option>
      <option>Apple</option>
      <option>Strawberry</option>
      <option>Lemon</option>
      <option>Orange</option>
    </datalist>
  </p>
  <p>
    <label for="t2">What's your e-mail address?</label>
    <input type="email" id="t2" name="email">
  </p>
  <p>
    <label for="t3">Leave a short message</label>
    <textarea id="t3" name="msg" maxlength="140" rows="5"></textarea>
  </p>
  <p>
    <button>Submit</button>
  </p>
</form>
```

Copiar ao portapapeis

E agora algúns CSS para estilizar o HTML:

```
form {
  font: 1em sans-serif;
  max-width: 320px;
}

p > label {
  display: block;
}

input[type="text"],
input[type="email"],
input[type="number"],
textarea,
fieldset {
  width : 100%;
  border: 1px solid #333;
  box-sizing: border-box;
}

input:invalid {
  box-shadow: 0 0 5px 1px red;
}

input:focus:invalid {
  box-shadow: none;
}
```

Copiar ao portapapeis

Isto é o seguinte:

<iframe class="sample-code-frame" title="Exemplo completo de mostra" id="frame_Full_example" width="100%" height="420" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/Forms/Form_validation/_sample_.Full_example.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 963.75px; max-width: 100%;"></iframe>

Consulte [Atributos relacionados coa validación](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Constraint_validation#validation-related_attributes) para obter unha lista completa de atributos que se poden usar para limitar os valores de entrada e os tipos de entrada que os admiten.

**Nota:** Podes atopar este exemplo en directo en GitHub como[full-example.html](https://mdn.github.io/learning-area/html/forms/form-validation/full-example.html) (ver tamén o [código fonte](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/full-example.html).)

## [Validación de formularios usando JavaScript](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#validating_forms_using_javascript)

Debes usar JavaScript se queres controlar o aspecto das mensaxes de erro nativas ou tratar con navegadores legados que non admiten a validación de formularios integrada en HTML. Nesta sección veremos as diferentes formas de facelo.

### [A API de validación de restricións](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#the_constraint_validation_api)

A maioría dos navegadores admiten a [API de validación de restricións](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation) , que consta dun conxunto de métodos e propiedades dispoñibles nas seguintes interfaces DOM de elementos de formulario:

- [`HTMLButtonElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement)(representa un [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)elemento)
- [`HTMLFieldSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement)(representa un [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset)elemento)
- [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)(representa un [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)elemento)
- [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)(representa un [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output)elemento)
- [`HTMLSelectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)(representa un [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)elemento)
- [`HTMLTextAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)(representa un [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)elemento)

A API de validación de restricións fai que as seguintes propiedades estean dispoñibles nos elementos anteriores.

- `validationMessage`: Devolve unha mensaxe localizada que describe as restricións de validación que o control non cumpre (se as hai). Se o control non é un candidato para a validación de restricións ( `willValidate`is `false`) ou o valor do elemento satisface as súas restricións (é válido), isto devolverá unha cadea baleira.

- ```
  validity
  ```

  : Devolve un 

  ```
  ValidityState
  ```

  obxecto que contén varias propiedades que describen o estado de validez do elemento. Podes atopar todos os detalles de todas as propiedades dispoñibles na 

  `ValidityState`

  páxina de referencia; a continuación enuméranse algunhas das máis comúns:

  - [`patternMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch): Devolve `true`se o valor non coincide co especificado [`pattern`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-pattern)e `false`se coincide. Se é verdadeiro, o elemento coincide coa [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudoclase CSS.
  - [`tooLong`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooLong): Devolve `true`se o valor é maior que a lonxitude máxima especificada polo [`maxlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-maxlength)atributo, ou `false`se é menor ou igual ao máximo. Se é verdadeiro, o elemento coincide coa [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudoclase CSS.
  - [`tooShort`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooShort): Devolve `true`se o valor é máis curto que a lonxitude mínima especificada polo [`minlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-minlength)atributo, ou `false`se é maior ou igual ao mínimo. Se é verdadeiro, o elemento coincide coa [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudoclase CSS.
  - [`rangeOverflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeOverflow): Devolve `true`se o valor é maior que o máximo especificado polo [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max)atributo, ou `false`se é menor ou igual ao máximo. Se é verdadeiro, o elemento coincide coas pseudoclases [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)e [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)CSS.
  - [`rangeUnderflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow): Devolve `true`se o valor é menor que o mínimo especificado polo [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min)atributo, ou `false`se é maior ou igual ao mínimo. Se é verdadeiro, o elemento coincide coas pseudoclases [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)e [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)CSS.
  - [`typeMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch): Devolve `true`se o valor non está na sintaxe requirida (cando [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type)é `email`ou `url`), ou `false`se a sintaxe é correcta. Se `true`, o elemento coincide coa [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudo-clase CSS.
  - `valid`: Devolve `true`se o elemento cumpre todas as súas restricións de validación e, polo tanto, considérase válido, ou `false`se falla algunha restrición. Se é verdadeiro, o elemento coincide coa [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)pseudoclase CSS; a [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudo-clase CSS en caso contrario.
  - `valueMissing`: Devolve `true`se o elemento ten un [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-required)atributo, pero ningún valor, ou `false`non. Se é verdadeiro, o elemento coincide coa [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudoclase CSS.

- `willValidate`: Devolve `true`se o elemento será validado cando se envíe o formulario; `false`en caso contrario.

A API de validación de restricións tamén ofrece os seguintes métodos nos elementos anteriores e no [`form`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)elemento.

- `checkValidity()`: Devolve `true`se o valor do elemento non ten problemas de validez; `false`en caso contrario. Se o elemento non é válido, este método tamén desencadea un [`invalid`evento](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event) no elemento.
- `reportValidity()`: Informa campos non válidos mediante eventos. Útil en combinación con `preventDefault()`nun `onSubmit`controlador de eventos
- `setCustomValidity(message)`: Engade unha mensaxe de erro personalizada ao elemento; se establece unha mensaxe de erro personalizada, o elemento considérase non válido e móstrase o erro especificado. Isto permíteche utilizar código JavaScript para establecer un fallo de validación distinto dos que ofrecen as restricións de validación estándar de HTML5. A mensaxe móstrase ao usuario ao informar do problema.

#### Implementación dunha mensaxe de erro personalizada

Como viches anteriormente nos exemplos de restricións de validación HTML5, cada vez que un usuario tenta enviar un formulario non válido, o navegador mostra unha mensaxe de erro. A forma en que se mostra esta mensaxe depende do navegador.

Estas mensaxes automatizadas teñen dous inconvenientes:

- Non hai unha forma estándar de cambiar a súa aparencia con CSS.
- Dependen da configuración rexional do navegador, o que significa que pode ter unha páxina nun idioma pero unha mensaxe de erro mostrada noutro idioma, como se ve na seguinte captura de pantalla de Firefox.

![Exemplo de mensaxe de erro con Firefox en francés nunha páxina en inglés](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation/error-firefox-win7.png)

Personalizar estas mensaxes de erro é un dos casos de uso máis comúns da [API de validación de restricións](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation) . Imos traballar cun exemplo sinxelo de como facelo.

Comezaremos cun HTML sinxelo (non dubide en poñer isto nun ficheiro HTML en branco; use unha copia nova de [fruit-start.html](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/fruit-start.html) como base, se queres):

```
<form>
  <label for="mail">I would like you to provide me with an e-mail address:</label>
  <input type="email" id="mail" name="mail">
  <button>Submit</button>
</form>
```

Copiar ao portapapeis

E engade o seguinte JavaScript á páxina:

```
const email = document.getElementById("mail");

email.addEventListener("input", function (event) {
  if (email.validity.typeMismatch) {
    email.setCustomValidity("I am expecting an e-mail address!");
  } else {
    email.setCustomValidity("");
  }
});
```

Copiar ao portapapeis

Aquí almacenamos unha referencia á entrada de correo electrónico e, a continuación, engadímoslle un detector de eventos que executa o código contido cada vez que se cambia o valor dentro da entrada.

Dentro do código contido, comprobamos se a `validity.typeMismatch`propiedade da entrada de correo electrónico devolve `true`, o que significa que o valor contido non coincide co patrón dun enderezo de correo electrónico ben formado. Se é así, chamamos ao `setCustomValidity()`método cunha mensaxe personalizada. Isto fai que a entrada non sexa válida, polo que cando tentas enviar o formulario, o envío falla e móstrase a mensaxe de erro personalizada.

Se a `validity.typeMismatch`propiedade devolve `false`, chamamos ao `setCustomValidity()`método unha cadea baleira. Isto fai que a entrada sexa válida, polo que o formulario enviarase.

Podes probalo a continuación:

<iframe width="100%" height="80" src="https://mdn.github.io/learning-area/html/forms/form-validation/custom-error-message.html" loading="lazy" style="box-sizing: border-box; max-width: 100%; border: 0px;"></iframe>

**Nota:** Podes atopar este exemplo en directo en GitHub como[custom-error-message.html](https://mdn.github.io/learning-area/html/forms/form-validation/custom-error-message.html) (ver tamén o [código fonte](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/custom-error-message.html).)

#### Un exemplo máis detallado

Agora que vimos un exemplo moi sinxelo, vexamos como podemos usar esta API para crear unha validación personalizada un pouco máis complexa.

En primeiro lugar, o HTML. De novo, non dubides en construír isto xunto connosco:

```
<form novalidate>
  <p>
    <label for="mail">
      <span>Please enter an email address:</span>
      <input type="email" id="mail" name="mail" required minlength="8">
      <span class="error" aria-live="polite"></span>
    </label>
  </p>
  <button>Submit</button>
</form>
```

Copiar ao portapapeis

Este sinxelo formulario usa o [`novalidate`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/novalidate)atributo para desactivar a validación automática do navegador; isto permite que o noso script asuma o control da validación. Non obstante, isto non desactiva o soporte para a API de validación de restricións nin a aplicación de pseudoclases CSS como [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid), etc. Isto significa que aínda que o navegador non verifica automaticamente a validez do formulario antes de enviar os seus datos, aínda pode faino ti mesmo e diseña o formulario en consecuencia.

A nosa entrada para validar é un [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email), que é `required`, e ten un `minlength`de 8 caracteres. Comprobamos estes usando o noso propio código e mostramos unha mensaxe de erro personalizada para cada un.

Pretendemos mostrar as mensaxes de erro dentro dun `<span>`elemento. O [`aria-live`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Live_Regions)atributo defínese en que `<span>`para asegurarse de que a nosa mensaxe de erro personalizada presentarase a todos, incluíndo el pode ler para os usuarios lector de pantalla.

**Nota:** un punto clave aquí é que establecer o `novalidate`atributo no formulario é o que impide que o formulario mostre as súas propias burbullas de mensaxes de erro e permítenos mostrar as mensaxes de erro personalizadas no DOM dalgún xeito que elixamos.

Agora vai nalgún CSS básico para mellorar lixeiramente o aspecto do formulario e proporcionar comentarios visuales cando os datos de entrada non son válidos:

```
body {
  font: 1em sans-serif;
  width: 200px;
  padding: 0;
  margin : 0 auto;
}

p * {
  display: block;
}

input[type=email]{
  -webkit-appearance: none;
  appearance: none;

  width: 100%;
  border: 1px solid #333;
  margin: 0;

  font-family: inherit;
  font-size: 90%;

  box-sizing: border-box;
}

/* This is our style for the invalid fields */
input:invalid{
  border-color: #900;
  background-color: #FDD;
}

input:focus:invalid {
  outline: none;
}

/* This is the style of our error messages */
.error {
  width  : 100%;
  padding: 0;

  font-size: 80%;
  color: white;
  background-color: #900;
  border-radius: 0 0 5px 5px;

  box-sizing: border-box;
}

.error.active {
  padding: 0.3em;
}
```

Copiar ao portapapeis

Agora vexamos o JavaScript que implementa a validación de erros personalizado.

```
// There are many ways to pick a DOM node; here we get the form itself and the email
// input box, as well as the span element into which we will place the error message.
const form  = document.getElementsByTagName('form')[0];

const email = document.getElementById('mail');
const emailError = document.querySelector('#mail + span.error');

email.addEventListener('input', function (event) {
  // Each time the user types something, we check if the
  // form fields are valid.

  if (email.validity.valid) {
    // In case there is an error message visible, if the field
    // is valid, we remove the error message.
    emailError.textContent = ''; // Reset the content of the message
    emailError.className = 'error'; // Reset the visual state of the message
  } else {
    // If there is still an error, show the correct error
    showError();
  }
});

form.addEventListener('submit', function (event) {
  // if the email field is valid, we let the form submit

  if(!email.validity.valid) {
    // If it isn't, we display an appropriate error message
    showError();
    // Then we prevent the form from being sent by canceling the event
    event.preventDefault();
  }
});

function showError() {
  if(email.validity.valueMissing) {
    // If the field is empty,
    // display the following error message.
    emailError.textContent = 'You need to enter an e-mail address.';
  } else if(email.validity.typeMismatch) {
    // If the field doesn't contain an email address,
    // display the following error message.
    emailError.textContent = 'Entered value needs to be an e-mail address.';
  } else if(email.validity.tooShort) {
    // If the data is too short,
    // display the following error message.
    emailError.textContent = `Email should be at least ${ email.minLength } characters; you entered ${ email.value.length }.`;
  }

  // Set the styling appropriately
  emailError.className = 'error active';
}
```

Copiar ao portapapeis

Os comentarios explican as cousas bastante ben, pero brevemente:

- Cada vez que cambiamos o valor da entrada, comprobamos se contén datos válidos. Se é así, eliminamos calquera mensaxe de erro que se mostra. Se os datos non son válidos, corremos `showError()`para mostrar o erro axeitado.
- Cada vez que intentamos enviar o formulario, comprobamos de novo se os datos son válidos. Se é así, deixamos que se envíe o formulario. Se non é así, corremos `showError()`para mostrar o erro apropiado e deixamos de enviar o formulario con [`preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault).
- A `showError()`función usa varias propiedades do `validity`obxecto da entrada para determinar cal é o erro e, a continuación, mostra unha mensaxe de erro segundo corresponda.

Aquí está o resultado en directo:

<iframe width="100%" height="150" src="https://mdn.github.io/learning-area/html/forms/form-validation/detailed-custom-validation.html" loading="lazy" style="box-sizing: border-box; max-width: 100%; border: 0px;"></iframe>

**Nota:** Podes atopar este exemplo en directo en GitHub como[validación-personalizada-detallada.html](https://mdn.github.io/learning-area/html/forms/form-validation/detailed-custom-validation.html) (ver tamén o [código fonte](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/detailed-custom-validation.html).)

A API de validación de restricións ofrécelle unha poderosa ferramenta para xestionar a validación de formularios, o que lle permite ter un enorme control sobre a interface de usuario por riba do que pode facer só con HTML e CSS.

**Nota: para** obter máis información, consulte a nosa [guía de validación de restricións](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Constraint_validation) e a referencia da [API de validación de restricións](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation) .

### [Validando formularios sen unha API integrada](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#validating_forms_without_a_built-in_api)

Nalgúns casos, como a compatibilidade do navegador herdado ou [os controis personalizados](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls) , non poderás ou non quererás utilizar a API de validación de restricións. Aínda podes usar JavaScript para validar o teu formulario, pero só tes que escribir o teu.

Para validar un formulario, fai algunhas preguntas:

- Que tipo de validación debo realizar?

  Debe determinar como validar os seus datos: operacións de cadea, conversión de tipos, expresións regulares, etc. É cousa túa.

- Que debo facer se o formulario non se valida?

  Esta é claramente unha cuestión de IU. Ten que decidir como se comportará o formulario. O formulario envía os datos igualmente? Deberías resaltar os campos que teñen erro? Deberías mostrar mensaxes de erro?

- Como podo axudar ao usuario a corrixir datos non válidos?

  Co fin de reducir a frustración do usuario, é moi importante proporcionar tanta información útil como sexa posible para orientalo na corrección das súas entradas. Deberías ofrecer suxestións por adiantado para que saiban o que se espera, así como mensaxes de erro claras. Se queres afondar nos requisitos da IU de validación de formularios, aquí tes algúns artigos útiles que debes ler:SmashingMagazine: [Validación de campos de formularios: o enfoque de só erros](https://uxdesign.smashingmagazine.com/2012/06/27/form-field-validation-errors-only-approach/)SmashingMagazine: [Validación de formularios web: boas prácticas e titoriais](https://www.smashingmagazine.com/2009/07/07/web-form-validation-best-practices-and-tutorials/)WebFX: [10 Consellos para optimizar a usabilidade do envío de formularios web](https://www.webfx.com/blog/web-design/10-tips-for-optimizing-web-form-submission-usability/)Unha lista aparte: [Validación en liña en formularios web](https://www.alistapart.com/articles/inline-validation-in-web-forms/)

#### Un exemplo que non usa a API de validación de restricións

Para ilustralo, a seguinte é unha versión simplificada do exemplo anterior que funciona con navegadores legados.

O HTML é case o mesmo; acabamos de eliminar as funcións de validación HTML.

```
<form>
  <p>
    <label for="mail">
        <span>Please enter an email address:</span>
        <input type="text" id="mail" name="mail">
        <span class="error" aria-live="polite"></span>
    </label>
  </p>
  <!-- Some legacy browsers need to have the `type` attribute
       explicitly set to `submit` on the `button`element -->
  <button type="submit">Submit</button>
</form>
```

Copiar ao portapapeis

Do mesmo xeito, o CSS non necesita cambiar moito; acabamos de converter a [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudoclase CSS nunha clase real e evitamos usar o selector de atributos que non funciona en Internet Explorer 6.

```
body {
  font: 1em sans-serif;
  width: 200px;
  padding: 0;
  margin : 0 auto;
}

form {
  max-width: 200px;
}

p * {
  display: block;
}

input.mail {
  -webkit-appearance: none;

  width: 100%;
  border: 1px solid #333;
  margin: 0;

  font-family: inherit;
  font-size: 90%;

  box-sizing: border-box;
}

/* This is our style for the invalid fields */
input.invalid{
  border-color: #900;
  background-color: #FDD;
}

input:focus.invalid {
  outline: none;
}

/* This is the style of our error messages */
.error {
  width  : 100%;
  padding: 0;

  font-size: 80%;
  color: white;
  background-color: #900;
  border-radius: 0 0 5px 5px;
  box-sizing: border-box;
}

.error.active {
  padding: 0.3em;
}
```

Copiar ao portapapeis

Os grandes cambios están no código JavaScript, que ten que facer moito máis pesado.

```
// There are fewer ways to pick a DOM node with legacy browsers
const form  = document.getElementsByTagName('form')[0];
const email = document.getElementById('mail');

// The following is a trick to reach the next sibling Element node in the DOM
// This is dangerous because you can easily build an infinite loop.
// In modern browsers, you should prefer using element.nextElementSibling
let error = email;
while ((error = error.nextSibling).nodeType != 1);

// As per the HTML5 Specification
const emailRegExp = /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/;

// Many legacy browsers do not support the addEventListener method.
// Here is a simple way to handle this; it's far from the only one.
function addEvent(element, event, callback) {
  let previousEventCallBack = element["on"+event];
  element["on"+event] = function (e) {
    const output = callback(e);

    // A callback that returns `false` stops the callback chain
    // and interrupts the execution of the event callback.
    if (output === false) return false;

    if (typeof previousEventCallBack === 'function') {
      output = previousEventCallBack(e);
      if(output === false) return false;
    }
  }
};

// Now we can rebuild our validation constraint
// Because we do not rely on CSS pseudo-class, we have to
// explicitly set the valid/invalid class on our email field
addEvent(window, "load", function () {
  // Here, we test if the field is empty (remember, the field is not required)
  // If it is not, we check if its content is a well-formed e-mail address.
  const test = email.value.length === 0 || emailRegExp.test(email.value);

  email.className = test ? "valid" : "invalid";
});

// This defines what happens when the user types in the field
addEvent(email, "input", function () {
  const test = email.value.length === 0 || emailRegExp.test(email.value);
  if (test) {
    email.className = "valid";
    error.textContent = "";
    error.className = "error";
  } else {
    email.className = "invalid";
  }
});

// This defines what happens when the user tries to submit the data
addEvent(form, "submit", function () {
  const test = email.value.length === 0 || emailRegExp.test(email.value);

  if (!test) {
    email.className = "invalid";
    error.textContent = "I expect an e-mail, darling!";
    error.className = "error active";

    // Some legacy browsers do not support the event.preventDefault() method
    return false;
  } else {
    email.className = "valid";
    error.textContent = "";
    error.className = "error";
  }
});
```

Copiar ao portapapeis

O resultado é así:

<iframe class="sample-code-frame" title="Un exemplo que non usa a mostra da API de validación de restricións" id="frame_An_example_that_doesnt_use_the_constraint_validation_API" width="100%" height="130" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/Forms/Form_validation/_sample_.An_example_that_doesnt_use_the_constraint_validation_API.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 963.75px; max-width: 100%;"></iframe>

Como podes ver, non é tan difícil construír un sistema de validación por conta propia. A parte difícil é facelo o suficientemente xenérico para usar tanto multiplataforma como en calquera formulario que poidas crear. Hai moitas bibliotecas dispoñibles para realizar a validación de formularios, como[Validar.js](https://rickharrison.github.io/validate.js/).

## [Pon a proba as túas habilidades!](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#test_your_skills!)

Chegaches ao final deste artigo, pero recordas a información máis importante? Podes atopar outras probas para verificar que conservaches esta información antes de seguir adiante. Consulta [Proba as túas habilidades: validación de formularios](https://developer.mozilla.org/en-US/docs/Learn/Forms/Test_your_skills:_Form_validation) .

## [Resumo](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#summary)

A validación do formulario no lado do cliente ás veces require JavaScript se queres personalizar o estilo e as mensaxes de erro, pero *sempre* esixe que penses coidadosamente no usuario. Lembre sempre de axudar aos seus usuarios a corrixir os datos que proporcionan. Para iso, asegúrate de:

- Mostra mensaxes de erro explícitas.
- Sexa permisivo sobre o formato de entrada.
- Sinala exactamente onde se produce o erro, especialmente en formularios grandes.

Unha vez comprobado que o formulario está cuberto correctamente, pódese enviar o formulario. A continuación trataremos o [envío de datos do formulario](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data) .

_____

***ref:*** https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation



FORMAWEB

NOV 2021