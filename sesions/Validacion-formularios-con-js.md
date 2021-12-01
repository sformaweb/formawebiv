## Validación de formularios

_**.ref:**_ https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation

Vaia por diante que esta validación do lado do cliente *non debe considerarse* unha medida de seguridade completa. So unha medida pantalla máis que podemos sumar as estratexias globais de seguridade do noso sitio.

Antes de enviar datos ao servidor, é importante asegurarse de que todos os controis de formulario necesarios estean cubertos no formato correcto. Isto denomínase **validación do formulario no lado do cliente** e axuda a garantir que os datos enviados coincidan cos requisitos establecidos nos distintos controis do formulario.

En resumo a **validación de formularios** consiste en comentarios presentados ao usuario cando este non introduce os datos no formato correcto ou esperado. 

Cando se introduzan os datos, o navegador e/ou o servidor web comprobarán que os datos están no formato correcto e dentro das restricións establecidas pola aplicación. A validación realizada no navegador chámase validación do **lado do cliente**, e a validación realizada no servidor chámase validación do **lado do servidor**.

Vexamos que estratexias seguir para a validación do lado do cliente.

### Obxectivos da validación de formularios:

- **Obter datos correctos, no formato correcto.** As túas aplicacións non funcionarán correctamente se os datos dos teus usuarios se almacenan nun formato incorrecto, son incorrectos ou omitidos por completo.

- **Protexer os datos dos usuarios** . Forzar aos teus usuarios a introducir contrasinais seguras fai que sexa máis fácil protexer a información da súa conta.

- **Protexernos**: Hai moitas formas nas que os usuarios con malas intencións poden usar de xeito inadecuado os formularios non protexidos para danar a túa aplicación (consulta [Seguridade do sitio web](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security)).

  :warning: **Aviso:** Nunca confíes - a cegas- nos datos pasados ao teu servidor desde o cliente. Aínda que o teu formulario estea validando correctamente e evitando a entrada incorrecta no lado do cliente, un usuario malintencionado aínda pode alterar a solicitude de rede.

### Tipos de validación do lado do cliente:

- **validación de formularios integrada**: usa funcións de validación de formularios  propia de HTML5. A validación de formularios integrada ten un mellor rendemento que JavaScript, pero non é tan personalizable como a validación con JavaScript.

  Os [controis de formulario nativos de HTML5](https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML5_input_types) ofrecen a posibilidade de validar a maioría dos datos dun formulario sen depender de JavaScript. A validación faise usando atributos de validación nos elementos do formulario. Os atributos de validación son:

  - [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/required): Especifica se hai que cubrir un campo do formulario antes de poder envialo.
  - [`minlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/minlength)e [`maxlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/maxlength): Especifica a lonxitude mínima e máxima dos datos textuais (cadeas).
  - [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/min)e [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/max): Especifica os valores mínimos e máximos dos tipos de entrada numérica.
  - `type`: Especifica se os datos deben ser un número, un enderezo de correo electrónico ou algún outro tipo predefinido específico.
  - [`pattern`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern): Especifica unha [expresión regular](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) que define un patrón que deben seguir os datos introducidos.

  Se os datos introducidos nun campo de formulario seguen todas as regras especificadas polos atributos anteriores, considérase válido. Se non, considérase non válido.

  Un elemento é válido cando:

  - O elemento coincide coa pseudo-clase CSS  [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid), que che permite aplicar un estilo específico aos elementos válidos.

  Daquela, cando o usuario tenta enviar datos, o navegador enviará o formulario - se non hai outra cousa que o impida (por exemplo, JavaScript).

  Cando un elemento non é válido, son verdadeiras as seguintes cousas:

  - O elemento coincide coa pseudo-clase CSS [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)  ( e, ás veces, con outras pseudo-clases da IU como [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)), o que permite aplicarlle un estilo específico aos elementos non válidos.

  Se o usuario tenta enviar os datos, o navegador bloqueará o formulario e mostrará unha mensaxe de erro.

  Exemplo completo para mostrar o uso das funcións de validación integradas de HTML:

  ```html
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

  E agora algúns CSS para estilizar o HTML:

  ```css
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

  

- **Validación co emprego de JavaScript**: É totalmente personalizable, pero cómpre creala *a man* (ou usar unha librería). Debes usar JavaScript se queres controlar o aspecto das mensaxes de erro nativas ou tratar con navegadores que non admiten a validación de formularios integrada en HTML.

  A maioría dos navegadores admiten a [API de validación de restricións](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation) , que consta dun conxunto de métodos e propiedades dispoñibles nas seguintes interfaces DOM de elementos de formulario:

  - [`HTMLButtonElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement)(representa un elemento [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button))
  - [ `HTMLFieldSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement)(representa un elemento [`<fieldset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset))
  - [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)(representa un elemento [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input))
  - [`HTMLOutputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)(representa un elemento [`<output>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output))
  - [`HTMLSelectElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)(representa un elemento [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select))
  - [`HTMLTextAreaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)(representa un elemento [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea))

  A API de validación de restricións fai que as seguintes propiedades estean dispoñibles nos elementos anteriores.

  - `validationMessage`: Devolve unha mensaxe localizada que describe as restricións de validación que o control non cumpre (se as hai). Se o control non é candidato para a validación de restricións ( `willValidate` e `false`) ou o valor do elemento satisface as súas restricións (é válido), isto devolverá unha cadea baleira.

  - `validity`: Devolve un obxecto `ValidityState` que contén varias propiedades que describen o estado de validez do elemento. Podes atopar todos os detalles de todas as propiedades dispoñibles na páxina de referencia de `ValidityState` ; a continuación enuméranse algunhas das máis comúns:
    - [`patternMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch): Devolve `true`se o valor non coincide co especificado [`pattern`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-pattern) e `false` se coincide. Se é verdadeiro, o elemento coincide coa pseudoclase CSS [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid).
    - [`tooLong`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooLong): Devolve `true` se o valor é maior que a lonxitude máxima especificada polo atributo [`maxlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-maxlength), ou `false`se é menor ou igual ao máximo. Se é verdadeiro, o elemento coincide coa pseudoclase CSS [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid).
    - [`tooShort`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooShort): Devolve `true` se o valor é máis curto que a lonxitude mínima especificada polo atributo  [`minlength`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-minlength), ou `false `se é maior ou igual ao mínimo. Se é verdadeiro, o elemento coincide coa pseudoclase CSS  [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid).
    - [`rangeOverflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeOverflow): Devolve `true` se o valor é maior que o máximo especificado polo atributo  [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max), ou `false` se é menor ou igual ao máximo. Se é verdadeiro, o elemento coincide coas pseudoclases CSS [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)e [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range).
    - [`rangeUnderflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow): Devolve `true` se o valor é menor que o mínimo especificado polo atributo [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min), ou `false` se é maior ou igual ao mínimo. Se é verdadeiro, o elemento coincide coas pseudoclases CSS [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)e [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range).
    - [`typeMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch): Devolve `true` se o valor non está na sintaxe requirida (cando [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-type)é `email`ou `url`), ou `false` se a sintaxe é correcta. Se `true`, o elemento coincide coa pseudoclase CSS [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid).
    - `valid`: Devolve `true ` se o elemento cumpre todas as súas restricións de validación e, polo tanto, considérase válido, ou `false` se falla algunha restrición. Se é verdadeiro, o elemento coincide coa pseudoclase CSS  [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid); a pseudoclase CSS [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) en caso contrario.
    - `valueMissing`: Devolve `true ` se o elemento ten un atributo [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-required), pero ningún valor, ou `false` non. Se é verdadeiro, o elemento coincide coa pseudoclase CSS [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid).

  - `willValidate`: Devolve `true` se o elemento será validado cando se envíe o formulario; `false`en caso contrario.

  A API de validación de restricións tamén ofrece os seguintes métodos nos elementos anteriores e no elemento [`form`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form).

  - `checkValidity()`: Devolve `true` se o valor do elemento non ten problemas de validez; `false` en caso contrario. Se o elemento non é válido, este método tamén desencadea un [evento `invalid`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event) no elemento.
  - `reportValidity()`: Informa de campos non válidos mediante eventos. Útil en combinación con `preventDefault()` nun controlador de eventos `onSubmit`
  - `setCustomValidity(message)`: Engade unha mensaxe de erro personalizada ao elemento; se establece unha mensaxe de erro personalizada, o elemento considérase non válido e móstrase o erro especificado. Isto permíteche usar código JavaScript para establecer un fallo de validación distinto dos que ofrecen as restricións de validación estándar de HTML5. A mensaxe móstrase ao usuario ao informar do problema.

  ###### Implementación dunha mensaxe de erro personalizada

  Como viches anteriormente nos exemplos de restricións de validación HTML5, cada vez que un usuario tenta enviar un formulario non válido, o navegador mostra unha mensaxe de erro. A forma en que se mostra esta mensaxe depende do navegador.

  Estas mensaxes automatizadas teñen dous inconvenientes:

  - Non hai unha forma estándar de cambiar a súa aparencia con CSS.
  - Dependen da configuración rexional do navegador, o que significa que pode ter unha páxina nun idioma pero unha mensaxe de erro mostrada noutro idioma, como se ve na seguinte captura de pantalla de Firefox.

  ![Exemplo de mensaxe de erro con Firefox en francés nunha páxina en inglés](C:\laragon\www\fiv\sesions\proximo\assets\error-firefox-win7.png)

  Personalizar estas mensaxes de erro é un dos casos de uso máis comúns da [API de validación de restricións](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation) . Imos traballar cun exemplo sinxelo de como facelo.

  Comezaremos cun HTML sinxelo (non dubide en poñer isto nun arquivo HTML en branco; use unha copia nova de [fruit-start.html](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/fruit-start.html) como base, se queres):

  ```html
  <form>
    <label for="mail">I would like you to provide me with an e-mail address:</label>
    <input type="email" id="mail" name="mail">
    <button>Submit</button>
  </form>
  ```

  E engade o seguinte JavaScript á páxina:

  ```javascript
  const email = document.getElementById("mail");
  
  email.addEventListener("input", function (event) {
    if (email.validity.typeMismatch) {
      email.setCustomValidity("I am expecting an e-mail address!");
    } else {
      email.setCustomValidity("");
    }
  });
  ```

  Aquí almacenamos unha referencia á entrada de correo electrónico e, a continuación, engadímoslle un detector de eventos que executa o código contido cada vez que se cambia o valor dentro da entrada.

  Dentro do código contido, comprobamos se a propiedade `validity.typeMismatch` da entrada de correo electrónico devolve `true`, o que significa que o valor contido non coincide co patrón dun enderezo de correo electrónico ben formado. Se é así, chamamos ao `setCustomValidity()`método cunha mensaxe personalizada. Isto fai que a entrada non sexa válida, polo que cando tentas enviar o formulario, o envío falla e móstrase a mensaxe de erro personalizada.

  Se a propiedade  `validity.typeMismatch` devolve `false`, chamamos ao método `setCustomValidity()` cunha cadea baleira. Isto fai que a entrada sexa válida, polo que o formulario enviarase.

  Podes atopar este exemplo en directo en GitHub como[validación-personalizada-detallada.html](https://mdn.github.io/learning-area/html/forms/form-validation/detailed-custom-validation.html) (ver tamén o [código fonte](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/detailed-custom-validation.html).)

  **Para** obter máis información, consulte a nosa [guía de validación de restricións](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Constraint_validation) e a referencia da [API de validación de restricións](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation) 

  ###### [Validando formularios sen unha API integrada](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#validating_forms_without_a_built-in_api)

  Nalgúns casos, como a compatibilidade do navegador herdado ou [os controis personalizados](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls) , non poderás ou non quererás utilizar a API de validación de restricións. Aínda podes usar JavaScript para validar o teu formulario, pero só tes que escribir o teu.

  Que tipo de validación debo realizar?

  Debe determinar como validar os seus datos: operacións de cadea, conversión de tipos, expresións regulares, etc. É cousa túa.

  Que debo facer se o formulario non se valida?

  Esta é claramente unha cuestión de IU. Ten que decidir como se comportará o formulario. O formulario envía os datos igualmente? Deberías resaltar os campos que teñen erro? Deberías mostrar mensaxes de erro?

  Como podo axudar ao usuario a corrixir datos non válidos?

  Co fin de reducir a frustración do usuario, é moi importante proporcionar tanta información útil como sexa posible para guialo na corrección das súas entradas. Deberías ofrecer suxestións por adiantado para que saiban o que se espera, así como mensaxes de erro claras. Se queres afondar nos requisitos da IU de validación de formularios, aquí tes algúns artigos útiles que debes ler:

  - SmashingMagazine: [Validación de campos de formularios: o enfoque de só erros](https://uxdesign.smashingmagazine.com/2012/06/27/form-field-validation-errors-only-approach/)
  - SmashingMagazine: [Validación de formularios web: boas prácticas e titoriais](https://www.smashingmagazine.com/2009/07/07/web-form-validation-best-practices-and-tutorials/)
  - WebFX: [10 Consellos para optimizar a usabilidade do envío de formularios web](https://www.webfx.com/blog/web-design/10-tips-for-optimizing-web-form-submission-usability/)
  - Unha lista aparte: [Validación en liña en formularios web](https://www.alistapart.com/articles/inline-validation-in-web-forms/)

a seguinte é unha versión simplificada do exemplo anterior que funciona con navegadores legados.

O HTML é case o mesmo; acabamos de eliminar as funcións de validación HTML.

```html
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

Do mesmo xeito, o CSS non necesita cambiar moito; acabamos de converter a [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)pseudoclase CSS nunha clase real e evitamos usar o selector de atributos que non funciona en Internet Explorer 6.

```css
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

Os grandes cambios están no código JavaScript, que ten que facer moito máis pesado.

```javascript
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

Xa ves que non é tan difícil construír un sistema de validación pola túa conta. A parte difícil é facer un sistema o suficientemente xenérico como para poder usalo tanto en diferentes plataformas como en calquera formulario que poidas crear. 

Para acelerar este proceso tamen podes botar man das moitas librarías dispoñibles para realizar a validación de formularios, coma por exemplo [Validate.js](https://rickharrison.github.io/validate.js/).

NOV 2021