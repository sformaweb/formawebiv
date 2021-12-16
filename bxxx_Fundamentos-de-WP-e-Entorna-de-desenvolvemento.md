# Fundamentos de WP

*ref.: https://knowthecode.io/labs/introduction-wordpress-web-development/*

> Para crear sitios web personalizados con Wordpress se debe dominar os tipos de publicacións, taxonomías, campos personalizados, ganchos de eventos, secuenciación e moito máis.

Wordpress ( en adiante WP) domina case o 35% do mercado de sitios publicados en internet. Pero hai que dicir que WP non é a única solución. O primeiro que deberiamos analizar é que necesidades vai a ter o noso sitio -ou o do noso cliente- e non implementar WP por defecto senón só se esa é a mellor solución posible.

Existen portais creados con WP que ben poderían funcionar nalgún modelo de sitio estático - Gatsby, Heroku, Jekill, 11th, Next, Jigsaw, Sculpin…- con resultados de efectividade e funcionamento tanto ou mellores que na plataforma de Automatic. 

Se a mellor solución posible é WP, entón desenvolveremos WP.

WP naceu coma unha plataforma de publicación de blog ou de bitácora - hoxe en día hai mellores solucións tamén para isto- para rapidamente evolucionar cara un CMS -sistema de xestión de contidos- de *interminables* prestacións grazas a innumerable cantidade de complementos, e tamén gazas a súa arquitectura, que facilita a creación de solucións altamente personalizables.

Así, se o que queremos é crear un portal onde o propietario poida engadir, cambiar ou eliminar contido de forma áxil e dinámica a solución podería ser perfectamente WP.

Para o cliente/propietario o importante vai ser a facilidade de uso. Para o deseñador/programador do sitio o importante é crear un sitio que lle dea tódalas facilidades ao propietario pero procurando que as accións deste non acaben por desmantelar ou danar a funcionalidade do sitio.

Por experiencia podo dicir que moitas veces acabo asumindo roles de edición e mantemento que perfectamente ben podería(n) desenvolver o(s) meu(s) cliente(s), pero que por precaución - ou despois dalgún susto - acabo por realizar eu para así evitar que un asunto menor acabe por converterse nun traballo de horas ou días.

A clave está nas dúas partes das que se compón calquera portal WP:

- o **frontend**, ou parte pública, que é o que calquera usuario pode ver do sitio a través do seu navegador.
- o **backend**, ou administración do sitio, que é onde o deseñador/programador configura as prestacións, aspecto e funcionalidades que vai ter o sitio.

Mentres no frontal amosamos os artigos, fotos, produtos, etc. que o cliente quere poñer a visto do público, na traseira ou administración editamos as publicacións, engadimos fotos, cambiámolos prezos dos produtos, controlamos o stock dos mesmos ou realizamos as tarefas de actualización e mantemento do portal.

Cando un usuario introduce a dirección do noso sitio web no seu navegador ou preme nunha ligazón caro o noso sitio se desencadea unha secuencia de sucesos:

- O navegador envía a dirección web. Esta é a solicitude que recibirá o servidor web.
- O enderezo web é único ao igual que o noso enderezo ou número de teléfono móbil. Ese enderezo web mapéase a un servidor de nomes e os servidores de nomes mapéanse aos servidores físicos onde se hospeda o sitio web, é dicir, onde se almacenan os arquivos. 
- A solicitude chama ao noso sitio, a unha paxina concreta do sitio: unha URI ou URL é única en si mesma, inda que no caso de WP estea composta por informaci ón compilada dende varios sitios. Basicamente toda a información do sitio está contida nunha base de datos, así que trala solicitude o primeiro que acontece é que o noso WP debe consultar a base de datos en relación coa URl concreta que o cliente solicitou e recoller e ordenar toda a información vinculada e devolvela para que se lle poida amosar da maneira máis rápida e segundo a configuración establecida previamente:  modelo ou tema, folla de estilos, tipos de fontes, textos e imaxes asociadas a esa URL especifica,... e dependendo da configuración do noso CMS máis cousas: resposta adecuada ao perfil do usuario, idioma,… ou recursos aloxados en distintos servidores web.

Un problema recorrente para os deseñadores é que con demasiada frecuencia o backend ten bastante máis complexidade da recomendable. Coa aspiración de espremer ao máximo as potencialidades de WP e/ou de darlle todo canto precise ao cliente, se acumulan complementos e máis complementos na traseira do sitio sen reparar nas consecuencias que isto vai ter no funcionamento xeral do sitio.

Moitas veces as solucións adoptadas, a conta de máis complementos que veñen a completar o manexo da cache, a minificación ou o o servicio diferido dos recursos implicados non son sempre a mellor solución. Pero aí están.

Despois de que o noso servidor localice o ID da publicación solicitada e despois de reunir tódolos elementos e recursos implicados na súa  visualización é cando se da resposta a solicitude do usuario e se lle devolve un documento html completo.

Moitas cousas suceden por detrás da escena antes de que o usuario reciba súa resposta. Parece moito para o pouco que en xeral se tarda en visualizar a páxina solicitada. Pero así acontece. E da capacidade do servidor, a arquitectura e a calidade da configuración xeral do sitio esa resposta pode ser moi rápida ou non tanto.

## Os arquivos dun sitio web

WP basea a súa arquitectura nun grupo variado de arquivos de guíón, fundamentalmente `php`; pero tamén en outros arquivos como poden ser follas de estilo `css` ou arquivos de guíon `javascript`.

Con este paquete se xestiona tanto a publicación como as consultas ao servidor e a confección das respostas que se verten ao navegador do usuario en formato `html`.

Grazas a está estrutura case todo o que sucede con WP acontece no servidor, de aí que a hora de planear un sitio web con WP o servicio de aloxamento sexa tamén unha variable a ter moi en conta.

…

https://knowthecode.io

# Entorno de desenvolvemento

*ref: https://knowthecode.io/labs/local-development-environment-setup-windows*

> Un entorno de desenvolvemento web local é fundamental cara a posibilidade de producir proxectos de software de alta calidade e ben probados. Este ambiente debería ser:
>
> - doado de usar.
> - fácil de replicar
> - rápido e áxil

Como pois configurar un entorno de desenvolvemento web local. Incluíndo, por suposto, control de versións con Git, aplicacións de axuda, xestores de paquetes (Composer, Node e npm), corredor de tarefas con Gulp, un servidor web local - replica do que imos a empregar no entorno real-, e claro está un editor de código profesional.

## Os compoñentes implicados

Un contorno de desenvolvemento local constaría dos seguintes compoñentes:

- Control de versións
- Un servidor web local
- Xestores de paquetes
- Corredor de tarefas
- Entorno de probas e depuración
- IDE profesional
- *Sniffers* para revisar e avisar de posibles inconsistencias e/ou problemas de codificación estándar. (Sniffer, del inglés sniff: olfatear, rastrear, puede entenderse como un programa con la capacidad de observar el flujo de datos en tránsito por una red, y obtener información de éste; está diseñado para analizar los paquetes de datos que pasan por la red y no están destinados para él)

   

## Entorno de desenvolvemento local en Windows

- [Git](https://git-scm.com/download/win)

  - control de versións
  - historial
  - traballas con outros

  ![Configurar Git](./assets/config_git.png)

- SSH - conexión segura cos nosos repositorios de Github  (SSH (o Secure SHell) es el nombre de un protocolo y del programa que lo implementa cuya principal función es el acceso remoto a un servidor por medio de un canal seguro en el que toda la información está cifrada.)

- Localhost - servidor local

- Editor de texto & IDE

- Aplicacións de axuda

- Composer(PHP)

  - Manexar dependencias
  - Automatización do fluxo de traballo

- Node & npm

  - Manexo de dependencias
  - Automatización do fluxo de traballo

- Gulp

O fluxo de traballo é algo persoal, así que na personalización dos recursos enumerados está parte da clave da súa eficiencia. 

Iso si, por moi persoal que sexan os teus desenvolvementos é importante documentalo todo. Nunca sabes cando deberás volver sobre os teus paso ou replicar algunha tarefa. Algo que está moi claro no momento que o facemos pódese volver indescifrable tan só unhas horas máis tarde. Se comentas e documentas o teu código tamén será máis fácil de compartir co teu equipo ou de revisar cando sexa preciso.

### Configurar Git

Descargar e instalar Git e configurar o noso usuario/correo-e de referencia.

#### Crear un .gitignore global

ref: https://docs.github.com/en/github/getting-started-with-github/getting-started-with-git/ignoring-files

O usual é crear un arquivo ``.gitignore`` para un determinado repositorio ou proxecto.

- Crear un arquivo``.gitignore``  para o teu repositorio.

```shell
$ touch .gitignore
```

Pero tamén podemos crear un para tódolos repositorios na nosa computadora:

- Configurar Git para usar un arquivo de exclusión para tódolos repositorios na nosa computadora ``~/.gitignore_global``.

```shell
$ git config --global core.excludesfile ~/.gitignore_global
```

Para obter un exemplo do arquivo *.gitignore*, se poden consultar "[Algunhas configuracións comúns .gitignore](https://gist.github.com/octocat/9257657)" no repositorio Octocat.

Se queremos ignorar un arquivo que xa está rexistrado, debemos deixar de rastrexar o arquivo antes de engadir unha regra para ignoralo. Dende o terminal, desmarcámolo arquivo.

```shell
$ git rm --cached FILENAME
```

Tamén podemos [excluír arquivos locais sen crear un arquivo *.gitignore*](https://docs.github.com/en/github/getting-started-with-github/getting-started-with-git/ignoring-files#excluding-local-files-without-creating-a-gitignore-file)

Se non queremos crear un arquivo *.gitignore* e compartilo con outras persoas, podemos crear regras que non estean comprometidas co repositorio: dentro da raíz do noso repositorio imos a  *.git/info/exclude*  e aí establecémolas regras que queiramos aplicar.

##### [Para saber máis](https://docs.github.com/en/github/getting-started-with-github/getting-started-with-git/ignoring-files#further-reading)

- [Ignoring files](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#_ignoring) no libro Pro Git.
- [.gitignore](https://git-scm.com/docs/gitignore) nas paxinas de axuda de Git
- [Colección de modelos de *.gitignore*](https://github.com/github/gitignore) no repositorio github/gitignore
- No sitio [gitignore.io](https://www.gitignore.io/)  

#### Conectarse a GitHub con SSH

Si no estás seguro de si xa tes unha clave SSH, comproba as [claves existentes](https://docs.github.com/es/articles/checking-for-existing-ssh-keys).

1. Abre Git Bash.

2. Ingresa `ls -al ~/.ssh` para ver si hai claves SSH presentes:

   ```shell
   $ ls -al ~/.ssh
   ```

Si inda no tes unha clave SSH, debes [xerar unha nova clave SSH](https://docs.github.com/es/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key). 

Si non queres volver a ingresar o teu contrasinal cada vez que usas a túa clave SSH, podes [agregar a túa clave a SSH agent](https://docs.github.com/es/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent), que xestionara as túas claves SSH e lembrará o teu contrasinal.

##### [Xerar unha nova clave SSH](https://docs.github.com/es/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#about-ssh-key-generation)

1. Abre Git Bash.

2. Pega o seguinte comando - substitúe a dirección co teu correo electrónico en GitHub-.

   ```shell
   $ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```

   Así creas unha nova clave SSH usando o correo-e como etiqueta.

   ```shell
   > Generating public/private rsa key pair.
   ```

3. Cando se indique "Ingresar un arquivo onde gardar a clave", preme Intro. Así aceptarás a localización predeterminada para este arquivo.

   ```shell
   > Enter a file in which to save the key (/c/Users/you/.ssh/id_rsa):[Press enter]
   ```

4. Onde se indica, escribe un contrasinal seguro. Para obter máis información, consulta "[Traballar con frases de contrasinal da clave SSH](https://docs.github.com/es/articles/working-with-ssh-key-passphrases)".

   ```shell
   > Enter passphrase (empty for no passphrase): [Type a passphrase]
   > Enter same passphrase again: [Type passphrase again]
   ```

#### [Agregar a clave SSH ao ssh-agent](https://docs.github.com/es/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key)

Antes de agregar unha nova clave SSH ao ssh-agent para xestionar as túas claves, debes ter [comprobado as claves SSH existentes](https://docs.github.com/es/articles/checking-for-existing-ssh-keys) e [ter xerado unha nova clave SSH](https://docs.github.com/es/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key).

**Si dispós de [GitHub Desktop](https://desktop.github.com/), podes empregalo para clonar repositorios e non manenxar claves SSH.**

#### [Para saber máis](https://docs.github.com/es/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent)

- "[Acerca de SSH](https://docs.github.com/es/articles/about-ssh)"
- Máis información en "[Traballar con frases de contrasinal da clave SSH](https://docs.github.com/es/articles/working-with-ssh-key-passphrases)"
- "[Autorizar unha clave SSH para usar có inicio de sesión único de SAML](https://docs.github.com/es/articles/authorizing-an-ssh-key-for-use-with-saml-single-sign-on)"

![Xerar clave SSH](assets/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent.png)

*ref: https://docs.github.com/es/github/authenticating-to-github/connecting-to-github-with-ssh*

### Servidor local

Son moitas as alternativas dispoñibles para instalar o teu servidor local dende as *vellas glorias* coma Xamp, Mamp, EasyPHP, até ás máis recentes Laragon, DevKinsta ou Local Flywheel (a miña favorita ultimamente). 

Podes empregar tamén Virtual Box e Vagrant (que me foron moi útiles no seu momento), ou o entorno WSL de Windows. Ou coma non o grande Docker. Inda que con calquera deles terás que pelexarte algo máis coa configuración da máquina e do entorno de depuración.

### Xestores de paquetes

Cando un proxecto depende dun paquete/módulo/biblioteca - é dicir, dalgún software externo-, un xestor de paquetes carga dito paquete así como cada unha das súas dependencias no noso proxecto local. Por exemplo, imaxinemos que imos precisar [Carbon](https://github.com/briannesbitt/Carbon) para o proxecto. Se ollámolo [arquivo composer.json](https://github.com/briannesbitt/Carbon/blob/master/composer.json#l19) de Carbon, vemos que este depende do paquete de PHP e do paquete de tradución de Symfony na versión de produción, asemade da versión de desenvolvemento de PHPUnit. Cando especificamos Carbon como unha dependencia do noso proxecto, Composer - o xestor de paquetes de PHP- cargará Carbon e asemade cada unha das dependencias de Carbon, co que o noso proxecto progresará sen faltas.

Outro beneficio de usar un xestor de paquetes é xestiónalas actualizacións. Cun simple comando, poderemos actualizar todos os paquetes do proxecto e asegurarnos de ter tódolos arquivos nas súas versións máis recentes.

Evidentemente, asemade de ser un método eficaz e eficiente para xestionar dependencias, un xestor de paquetes aforra tempo.

Así, como parte dun entorno de desenvolvemento local é recomendable ter instalados:

- **Composer**: para xestionar as dependencias PHP
- **Node Package Manager (npm)**: para xestionar os paquetes e as dependencias JavaScript
- (Gulp/)**Bower**: para xestionar as dependencias do desenvolvemento frontend.

---

ref: https://knowthecode.io/labs/local-development-environment-setup-windows/install-configure-git



DEC 2021
