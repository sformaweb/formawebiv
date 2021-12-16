# A seguridade nun sitio web

A seguridade do sitio web require vixilancia en todos os aspectos do deseño e uso do sitio web. 

Internet é un lugar perigoso! Terás oído moitas veces como sitios web sofren ataques de denegación de servizo ou que amosan información modificada (e moitas veces daniña) nas súas páxinas de inicio. Noutros casos destacados, millóns de contrasinais, enderezos de correo electrónico e detalles de tarxetas de crédito se filtran ao dominio público, e expón as persoas usuarias do sitio web a riscos todo tipo incluídos a chantaxe ou os danos financeiros.

O propósito da seguridade do sitio web é evitar estes (ou calquera) tipos de ataques. A definición máis formal da seguridade do sitio web *é o acto/práctica de protexer os sitios web do acceso, uso, modificación, destrución ou interrupción non autorizados* .

A seguranza eficaz do sitio web require un esforzo de deseño en todo o sitio web: 

- na codificación da aplicación web, 
- na configuración do servidor web, 
- nas políticas para crear e anovar contrasinais
- e para actualizar o código do cliente. 

Aínda que todo isto pareza moito, a boa noticia é que se estás a usar un marco web do servidor, case seguro que alí se activarán "por defecto" mecanismos de defensa o suficientemente robustos e ben deseñados para evitar moitos dos posibles ataques máis comúns. Outros ataques pódense mitigar tamén a través da configuración do servidor, por exemplo activando HTTPS. 

Por outra banda, hai ferramentas de escáneo de vulnerabilidades que poden axudarche a descubrir se cometiches algún erro obvio.

## Ameazas á seguridade

- **[Cross-Site Scripting (XSS)](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security#cross-site_scripting_xss)**

  XSS é un termo usado para describir unha clase de ataques que permiten que un atacante inxecte scripts de cliente, a *través* dun sitio web, nos navegadores doutros usuarios.

  Este código inxectado chega ao noso navegador desde un suposto sitio de confianza, pero pode pode facer cousas como enviar a cookie de autorización do usuario ao atacante. Cando o atacante obtén esta cookie, pode iniciar sesión nun sitio como se fose o usuario orixinal e facer todo aquilo ao que o usuario orixe ten autorización: acceder aos detalles da súa conta incluídos datos de contacto, contrasinais ou  datos das tarxetas de crédito.

  - En función de como o sitio devolve os scripts inxectados a un navegador, [as vulnerabilidades XSS divídense en *reflectidas* e *persistentes*](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security#website_security_threats):
    - Unha **vulnerabilidade XSS *reflectida*** prodúcese cando o contido do usuario que se pasa ao servidor se devolve *inmediatamente* e *non se modifica* para mostrar no navegador. 
    - Unha **vulnerabilidade XSS *persistente*** prodúcese cando o script malicioso se *almacena* no sitio web e despois se volve a mostrar sen modificar para que outros usuarios o executen sen querelo.

Aínda que os datos `POST`ou as solicitudes `GET` son a fonte máis común de vulnerabilidades XSS, calquera dato do navegador é potencialmente vulnerable, como os datos de cookies representados polo navegador ou os arquivos de usuario que se cargan e se mostran.

A mellor defensa contra as vulnerabilidades XSS é eliminar ou desactivar calquera marcado que poida conter instrucións para executar o código. Toda HTML que inclúa elementos como `<script>`, `<object>`, `<embed>`.

O proceso de modificar os datos do usuario para que non se poidan utilizar para executar scripts ou afectar doutro xeito á execución do código do servidor coñécese como **sanitización** de entrada. Moitos marcos web desinfectan automaticamente e por defecto a entrada do usuario dos formularios HTML.

- [**Inxección SQL**](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security#sql_injection)

  As vulnerabilidades de inxección de SQL permiten aos usuarios malintencionados executar código SQL arbitrario nunha base de datos, o que permite acceder, modificar ou eliminar os datos independentemente dos permisos do usuario. Un ataque de inxección exitoso pode falsificar identidades, crear novas identidades con dereitos de administración, acceder a todos os datos do servidor ou destruír/modificar os datos para facelos inservibles.

  Os tipos de inxección de SQL inclúen a inxección de SQL baseada en erros, a inxección de SQL baseada en erros booleanos e a inxección de SQL baseada no tempo.

- [**Falsificación de solicitudes entre sitios (CSRF)**](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security#cross-site_request_forgery_csrf)

  Os ataques CSRF permiten que un usuario malintencionado execute accións utilizando as credenciais doutro usuario sen o coñecemento ou consentimento deste. (Cross-site request forgery
El CSRF es un tipo de exploit malicioso de un sitio web en el que comandos no autorizados son transmitidos por un usuario en el cual el sitio web confía.)

- [**Outras ameazas**](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security#other_threats)

  Outros ataques/vulnerabilidades comúns:

  - [Clickjacking](https://www.owasp.org/index.php/Clickjacking). un usuario malintencionado secuestra os clics destinados a un sitio visible de nivel superior e envíaos a unha páxina oculta debaixo. Esta técnica pódese usar, por exemplo, para mostrar un sitio bancario lexítimo pero capturar as credenciais de inicio de sesión nun ``<iframe>`` invisible controlado polo atacante. O clickjacking tamén se pode usar para facer que o usuario faga clic nun botón dun sitio visible, pero ao facelo realmente fai clic sen querer nun botón completamente diferente. Como defensa, tes que configurar as cabeceiras HTTP axeitadas.
  - [Denegación de servizo](https://developer.mozilla.org/en-US/docs/Glossary/Distributed_Denial_of_Service) (DoS). DoS adoita conseguirse inundando un sitio de destino con solicitudes falsas para que o acceso a un sitio sexa interrompido para os usuarios lexítimos. As solicitudes poden ser numerosas, ou poden consumir individualmente grandes cantidades de recursos (por exemplo, lecturas lentas ou carga de arquivos grandes). As defensas DoS adoitan funcionar identificando e bloqueando o tráfico "malo" mentres permiten o paso de mensaxes lexítimas. Estas defensas localízanse normalmente antes ou no servidor web (non forman parte da propia aplicación web).
  - [Percorrido do directorio](https://en.wikipedia.org/wiki/Directory_traversal_attack)(Arquivo e divulgación). Un usuario malintencionado tenta acceder a partes do sistema de arquivos do servidor web aos que non debería poder acceder. Esta vulnerabilidade prodúcese cando o usuario é capaz de pasar nomes de arquivos que inclúen caracteres de navegación do sistema de arquivos (por exemplo, `../../`). A solución é desinfectar a entrada antes de usala.
  - [Inclusión de arquivos](https://en.wikipedia.org/wiki/File_inclusion_vulnerability). Neste ataque, un usuario pode especificar un arquivo "non desexado" para a súa visualización ou execución nos datos pasados ao servidor. Cando se carga, este arquivo pode executarse no servidor web ou no lado do cliente (o que leva a un ataque XSS). A solución é desinfectar a entrada antes de usala.
  - [Inxección de comandos](https://www.owasp.org/index.php/Command_Injection). Os ataques de inxección de comandos permiten que un usuario malintencionado execute comandos arbitrarios do sistema no sistema operativo host. A solución é desinfectar a entrada do usuario antes de que poida usarse nas chamadas do sistema.

  Para obter unha lista completa das ameazas de seguridade do sitio web, consulte [Categoría: Explotacións de seguridade web](https://en.wikipedia.org/wiki/Category:Web_security_exploits) (Wikipedia) e [Categoría: Ataque](https://www.owasp.org/index.php/Category:Attack) (Abrir Proxecto de seguridade de aplicacións web).
