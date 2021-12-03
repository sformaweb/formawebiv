# Programación web na entorna do servidor

Os ***sitios web dinámicos\***  son sitios web que ofrecen información personalizada en resposta a solicitudes HTTP. S programación do lado do servidor, xunto con guías específicas de nivel principiante sobre como usar os marcos web Django (Python) e Express (Node.js/JavaScript) para crear aplicacións básicas.

A maioría dos principais sitios web usan algún tipo de tecnoloxía do servidor para mostrar dinámicamente os datos segundo sexa necesario. Por exemplo, imaxina cantos produtos hai dispoñibles en Amazon e imaxina cantas publicacións se escribiron en Facebook. Mostrar todos estes usando diferentes páxinas estáticas sería extremadamente ineficiente, polo que tales sitios mostran modelos estáticos (creados usando [HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML) , [CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS) e [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript) ), e despois actualizan dinámicamente os datos que se mostran dentro deses modelos cando sexa necesario, por exemplo cando quere ver un produto diferente en Amazon.

No mundo moderno do desenvolvemento web, é moi recomendable aprender sobre o desenvolvemento do servidor.

## [Vía de aprendizaxe](https://developer.mozilla.org/en-US/docs/Learn/Server-side#learning_pathway)

Empezar coa programación do servidor adoita ser máis doado que o desenvolvemento do cliente, porque os sitios web dinámicos adoitan realizar moitas operacións moi similares (recuperar datos dunha base de datos e mostralos nunha páxina, validar os datos introducidos polo usuario e gardalos). unha base de datos, comprobando os permisos dos usuarios e rexistrando usuarios, etc.) e constrúense utilizando marcos web que facilitan estas e outras operacións comúns do servidor web.

O coñecemento básico dos conceptos de programación (ou dunha determinada linguaxe de programación) é útil, pero non esencial. Do mesmo xeito, non se require experiencia en codificación do lado do cliente, pero un coñecemento básico axudarache a traballar mellor cos desenvolvedores que crean o teu "front end" web no lado do cliente.

Necesitarás entender "como funciona a web". Recomendamos que leas primeiro os seguintes temas:

- [Que é un servidor web](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server)
- [Que software necesito para crear un sitio web?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_software_do_I_need)
- [Como cargar ficheiros a un servidor web?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Upload_files_to_a_web_server)

Con esa comprensión básica, estarás preparado para avanzar nos módulos desta sección.

## [Módulos](https://developer.mozilla.org/en-US/docs/Learn/Server-side#modules)

Este tema contén os seguintes módulos. Debería comezar co primeiro módulo e, a continuación, pasar a un dos seguintes módulos, que mostran como traballar con dúas linguaxes moi populares do lado do servidor usando marcos web apropiados.

- [Primeiros pasos da programación de sitios web no servidor](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps)

  Este módulo ofrece información independente da tecnoloxía sobre a programación de sitios web no servidor, como "que é?", "¿En que se diferencia da programación do cliente?" e "por que é útil?". Este módulo tamén describe algúns dos marcos web do servidor máis populares e ofrece orientación sobre como seleccionar o mellor para o teu sitio. Por último, ofrécese unha introdución á seguridade do servidor web.

- [Django Web Framework (Python)](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django)

  Django é un marco web do servidor moi popular e con todas as funcións, escrito en Python. O módulo explica por que Django é un marco de servidor web tan bo, como configurar un ambiente de desenvolvemento e como realizar tarefas comúns con el.

- [Express Web Framework (Node.js/JavaScript)](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs)

  Express é un marco web popular, escrito en JavaScript e aloxado no entorno de execución node.js. O módulo explica algúns dos principais beneficios deste marco, como configurar o seu ambiente de desenvolvemento e como realizar tarefas comúns de desenvolvemento e implantación web.

## [Ver tamén](https://developer.mozilla.org/en-US/docs/Learn/Server-side#see_also)

- [Servidor de nodos sen marco](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Node_server_without_framework)

  Este artigo ofrece un servidor de ficheiros estático sinxelo construído con Node.js puro, para aqueles de vostedes que non queiran usar un marco.

- [Configurando correctamente os tipos MIME do servidor](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Configuring_server_MIME_types)

  Configurar o seu servidor para enviar os [tipos MIME](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) correctos (tamén coñecidos como tipos de medios ou tipos de contido) aos navegadores é importante para que os navegadores poidan procesar e mostrar correctamente o contido. Tamén é importante evitar que o contido malicioso se faga pasar por contido benigno.