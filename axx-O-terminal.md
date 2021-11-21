# A terminal ou liña de comandos

A terminal é unha interface de texto para executar programas baseados en texto. Se estás a executar calquera ferramenta para o desenvolvemento web, hai unha posibilidade case garantida de que teñas que abrir a liña de comandos e executar algúns comandos para usar as ferramentas que escolliches (a miúdo verás ferramentas deste tipo denominadas **ferramentas CLI**: ferramentas da interface de liña de comandos).

**Pódense usar un gran número de ferramentas escribindo comandos na liña de comandos**; moitas veñen preinstaladas no teu sistema e outras moitas pódense instalar desde os rexistros de paquetes. Os rexistros de paquetes son como tendas de aplicacións, pero (principalmente) para ferramentas e software baseados na liña de comandos.

Unha das maiores críticas á liña de comandos é que carece de experiencia du usuario. Ver a liña de comandos por primeira vez pode ser unha experiencia desalentadora: unha pantalla en branco e un cursor intermitente, con moi pouca axuda obvia dispoñible sobre o que facer.

Visto así as consolas están lonxe de ser entornas acolledoras, pero pódense facer moitas cousas con elas. Un pouco de orientación e práctica, pode facer que usalos sexa máis fácil! 

### De onde veu a terminal?

A terminal ten a súa orixe nos anos 1950 e 1960 e a súa forma orixinal realmente non se parece ao que usamos hoxe (o que é de agradecer). Podes ler un pouco da historia na entrada da Wikipedia para [Terminal informático](https://en.wikipedia.org/wiki/Computer_terminal).

Desde entón, a terminal segue sendo unha característica constante de todos os sistemas operativos: desde máquinas de escritorio, ata servidores escondidos na nube, microordenadores como o Raspberry PI Zero e ata teléfonos móbiles. Ofrece acceso directo ao sistema de arquivos subxacente do ordenador e ás funcións de baixo nivel e, polo tanto, é incriblemente útil para realizar tarefas complexas rapidamente, se se sabe o que se está a facer :eye:.

Tamén é útil para a automatización, por exemplo, para escribir un comando para actualizar os títulos de centos de arquivos ao instante, digamos de "ch01-xxxx.png" a "ch02-xxxx.png". Se actualizaches os nomes dos arquivos usando a túa aplicación GUI (Graphic User Interface) do buscador ou do explorador, levaríache moito tempo.

De todos os xeitos, a terminal non desaparecerá pronto.

### Como é a terminal

A continuación podes ver algúns dos diferentes tipos de programas que hai dispoñibles para chegar a unha terminal.

As seguintes imaxes mostran as solicitudes de comando dispoñibles en Windows: hai unha boa variedade de opcións desde o programa "cmd" ata "powershell", que se poden executar desde o menú de inicio. Ou empregando a `tecla de Windows+r`  escribir o nome do programa e executar.

![Executar a liña de comandos](./assets/executar-cmd.png)

![Unha xanela de liña cmd de Windows de vanilla e unha xanela de Powershell de Windows](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/win-terminals.png)

E a continuación, podes ver a aplicación da terminal de macOS.

![Un terminal básico de vainilla mac](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/mac-terminal.png)

### Como accedes aa terminal?

Hoxe por hoxe, moitos desenvolvedores están a usar ferramentas baseadas en Unix (por exemplo, a terminal e as ferramentas ás que se pode acceder a través dela). Moitos titoriais e ferramentas que existen na web hoxe admiten (e, por desgraza, asumen) sistemas baseados en Unix, pero non te preocupes: están dispoñibles na maioría dos sistemas. Nesta sección, imos ver como acceder a terminal no sistema escollido.

#### Linux/Unix

Como se indicou anteriormente, os sistemas Linux/Unix teñen un terminal dispoñible de forma predeterminada, que aparece entre as súas Aplicacións.

#### macOS

macOS ten un sistema chamado Darwin que se atopa debaixo da interface gráfica de usuario. Darwin é un sistema tipo Unix, que proporciona a terminal e acceso ás ferramentas de baixo nivel. macOS Darwin ten sobre todo unha paridade con Unix, o suficientemente boa como para non causarnos ningunha preocupación mentres traballamos.

A terminal está dispoñible en macOS en Aplicacións/Utilidades/Terminal.

#### Windows

Do mesmo xeito que con outras ferramentas de programación, usar a terminal (ou a liña de comandos) en Windows non foi tradicionalmente tan sinxelo nin tan simple coma noutros sistemas operativos. Pero as cousas están mellorando.

Windows tivo tradicionalmente o seu propio programa do tipo terminal chamado **cmd **("o símbolo do sistema") durante moito tempo, pero este definitivamente non ten paridade cos comandos de Unix, pois é equivalente ao antigo estilo de Windows DOS.

Existen programas mellores que poden ofrecer unha experiencia de terminal en Windows, como Powershell ([mira aquí para atopar instaladores](https://github.com/PowerShell/PowerShell)), e Gitbash (que vén como parte do conxunto de ferramentas de [git para Windows](https://gitforwindows.org/) )

Non obstante, a mellor opción para Windows na actualidade é o subsistema Windows para Linux (WSL): unha capa de compatibilidade para executar sistemas operativos Linux directamente desde Windows 10, que lle permite executar un "terminal verdadeiro" directamente en Windows, sen necesidade de unha máquina virtual.

Isto pódese instalar directamente desde a tenda de Windows gratuitamente. Podes atopar toda a documentación que necesitas no [Subsistema de Windows para documentación de Linux](https://docs.microsoft.com/en-us/windows/wsl).

![unha captura de pantalla do subsistema de Windows para a documentación de Linux](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/wsl.png)

En canto á opción a elixir en Windows, recomendámosche encarecidamente que intentes instalar o WSL. Podes seguir co símbolo do sistema predeterminado ( `cmd`) e moitas ferramentas funcionarán ben, pero todo será máis fácil se tes unha mellor paridade coas ferramentas Unix.

#### Nota lateral: cal é a diferenza entre unha liña de comandos e unha terminal?

Xeralmente atoparás estes dous termos usados indistintamente. Tecnicamente, un terminal é un software que se inicia e se conecta a un shell. Un shell é o teu ambiente de sesión e a sesión de seu (onde poden personalizarse cousas como o aviso e os atallos). A liña de comandos é a liña literal onde se introducen comandos e o cursor parpadea.

### *Teño* que usar a terminal si ou si?

Aínda que hai unha gran cantidade de ferramentas dispoñibles desde a liña de comandos, se estás a usar ferramentas como [Visual Studio Code](https://code.visualstudio.com/) tamén dispós dunha grande cantidade de extensións que se poden usar coma proxy para usar comandos de terminal sen necesidadd de usar a terminal directamente. Non obstante, non atoparás unha extensión de editor de código para todo o que queiras facer; e ao final terás que adquirir certa experiencia ca terminal.

## Comandos básicos da terminal incorporada

Vexamos algúns comandos da terminal! 

Unha vez aberta, estas son algunhas das cousas que poderás facer desde o inicio, seguidas da ferramenta ou comando  nomes das a empregar en cada caso:

- Navegar polo sistema de arquivos do teu ordenador e tarefas básicas como crear, copiar, renomear e eliminar arquivos o/ou cartafoles:

  - Moverse pola estrutura de directorios: `cd`

    ```cd meuproxecto```

  - Crear directorios: `mkdir`

    ```mkdir meuproxecto```

  - Crea arquivos: `touch`

    ```touch meuproxecto```

  - Copiar arquivos: `cp`

    ```cp index.html```

  - Mover arquivos: `mv`

  - Elimina arquivos ou directorios: `rm`

- Descargar arquivos dende unha URL específica: `curl`

- Buscar fragmentos de texto dentro de corpos de texto máis grandes: `grep`

- Ver o contido dun arquivo páxina por páxina: `less`,`cat`

- Manipula e transforma fluxos de texto (por exemplo, cambiando todas as instancias de `<div>` nun arquivo HTML a `<article>`): `awk`, `tr`,`sed`

**Nota:** hai unha serie de bos tutoriais na web que afondan máis na liña de comandos para a web. Esta é só unha breve introdución.

Vexamos usar algunhas destas ferramentas na liña de comandos. Antes de continuar, abre o teu programa de terminal.

### Navegar polo arbore de directorios dende a liña de comandos

Cando visites a liña de comandos, inevitablemente terás que navegar a un directorio particular para "facer algo". Todos os sistemas operativos (asumindo unha configuración predeterminada) lanzarán o seu programa de terminal no teu directorio "home" e, a partir de aí, é probable que queiras ir a outro lugar diferente.

O comando  `cd` permíteche cambiar de directorio. Tecnicamente, `cd` non é un programa senón un comando integrado. Isto significa que o teu sistema operativo ofréceo por defecto e non podes eliminalo, nin accidentalmente - menos mal!-. Non tes que preocuparte demasiado por se o comando que estás a usar é integrado ou non, pero ten en conta que os comandos integrados son os mesmos en todos os sistemas baseados en Unix.

Para cambiar de directorio, escribe `cd` no teu terminal, seguido do directorio ao que queres moverte. Asumindo que o directorio está dentro do teu directorio de inicio, podes utilizalo `cd Desktop`(ver as capturas de pantalla a continuación).

![resultados do comando cd Desktop que se executa nunha variedade de terminais de Windows: a localización da terminal móvese ao escritorio](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/win-terminals-cd.png)

Proba a escribir isto na terminal do teu sistema:

```bash
cd Desktop
```

Se queres volver ao directorio anterior, podes usar:

```bash
cd ..
```



**Nota:** un atallo de terminal moi útil é usar a tecla TAB para autocompletar os nomes que sabes que están presentes, en lugar de ter que escribilo todo. Por exemplo, despois de escribir os dous comandos anteriores, proba a escribir `cd D` e premer TAB: debería completarse automaticamente o nome do directorio `Desktop`, sempre que estea presente no directorio actual. Ten en conta isto mentres avanzas.

Se o directorio ao que queres ir está aniñado en profundidade, debes coñecer o camiño para chegar a el. Isto adoita facerse máis sinxelo a medida que te familiarizas coa estrutura do teu sistema de arquivos, pero se non estás seguro da ruta, normalmente podes descubrilo cunha combinación do comando `ls` (ver máis abaixo) ou usando o buscador do Explorador de arquivos para ver onde está un determinado directorio, en relación a onde estás actualmente.

**Nota**: é unha boa práctica que manteñas a arbores de arquivos do teu sistema o máis organizado posible, será máis sinxelo de usar.

Por exemplo, se queres ir a un directorio chamado `src`, situado dentro dun directorio chamado `project`, situado no `Desktop`, podes escribir estes tres comandos para chegar alí desde o teu cartafol de inicio:

```bash
cd Desktop
cd project
cd src
```

Pero iso é unha perda de tempo; en vez diso, podes escribir un comando, cos diferentes elementos do camiño separados por barras inclinadas, igual que se fai cando especificas camiños para imaxes ou outros recursos en código CSS, HTML ou JavaScript:

```bash
cd Desktop/project/src
```

Teña en conta que incluír unha barra inclinada no camiño fai que este sexa absoluto, por exemplo `/Users/your-user-name/Desktop`. Omitir a barra inclinada como se fixo anteriormente fai que o camiño sexa relativo ao directorio de traballo actual. Isto é exactamente o mesmo que ves coas URL nun navegador web. Unha barra inclinada significa "na raíz do sitio web", mentres que omitir a barra significa que a "URL é relativa á páxina actual".

**Nota:** Windows usa barras invertidas \  en lugar de barras invertidas /, por exemplo `cd Desktop\project\src`, isto pode parecer raro, e se che interesa saber por que, [mira este clip de YouTube](https://www.youtube.com/watch?v=5T3IJfBfBmI) cunha explicación dun dos enxeñeiros principais de Microsoft. 

### Lista de contidos do directorio

Outro comando incorporado de Unix é `ls` (abreviatura de lista), que enumera os contidos do directorio no que estás actualmente. Ten en conta que isto non funcionará se estás a usar o indicador de comandos predeterminado de Windows ( `cmd`), o equivalente que deberás emprgear aí é: `dir`.

Proba a executar no teu terminal:

```bash
ls
```

Isto ofrécelle unha lista dos arquivos e directorios do teu directorio de traballo actual, pero a información é realmente básica: só obtén o nome de cada elemento presente, non se é un arquivo ou un directorio ou calquera outra cousa. Afortunadamente, un pequeno cambio no uso do comando pode darche moita máis información.

### Opcións dos comandos

A maioría dos comandos da terminal teñen opcións: son modificadores que engades ao final dun comando, que fan que se comporte dun xeito lixeiramente diferente. Estes normalmente consisten nun espazo despois do nome do comando, seguido dun guión, seguido dunha ou máis letras.

Por exemplo, proba isto e mira o que obtén:

```bash
ls -l
```

No caso de `ls`, a opción `-l`( *guión ele* ) *ofréce* unha lista con un arquivo ou directorio en cada liña e mostra moita máis información. Os directorios pódense identificar buscando unha letra "d" no lado esquerdo das liñas. Eses son nos que podemos `cd`entrar.

A continuación móstrase unha captura de pantalla cun terminal macOS "por defecto" na parte superior e un terminal personalizado con algunhas iconas e cores adicionais para que se vexa vivo, ambos mostrando os resultados da execución `ls -l`:

![Un terminal mac de vainilla e un terminal mac personalizado máis colorido, que mostra unha lista de arquivos - o resultado de executar o comando ls -l](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/mac-terminals-ls.png)

**Nota:** para saber exactamente que opcións ten cada comando dispoñible, podes mirar as súas [páxina de man](https://en.wikipedia.org/wiki/Man_page). Isto faise escribindo o comando `man`, seguido do nome do comando que estás a buscar, por exemplo `man ls`. Isto abrirá a páxina de manual no visor de arquivos de texto predeterminado da terminal (por exemplo,[`less`](https://en.wikipedia.org/wiki/Less_(Unix))no meu terminal), e entón deberías poder desprazarte pola páxina usando as teclas de frecha ou algún mecanismo similar. A páxina de manual enumera todas as opcións con gran detalle, o que pode ser un pouco intimidante para comezar, pero polo menos sabes que está aí se o necesitas. Unha vez que remates de mirar a páxina de manual, debes saír dela usando o comando `quit` do teu visor de texto ("q" en `less`; quizais teñas que buscar na web para atopala se non é obvio).

**Nota:** para executar un comando con varias opcións ao mesmo tempo, normalmente pode poñelas todas nunha única cadea despois do carácter de guión, por exemplo `ls -lah`, ou `ls -ltrh`. Proba a mirar a páxina de manual para `ls` e descubrir o que fan as opcións adicionais.

Agora que falamos de dous comandos fundamentais, repasa un pouco o teu directorio e mira se podes navegar dun lugar a outro.

### Crear, copiar, mover, eliminar

Existen outros comandos básicos de utilidade que probablemente acabarás usando bastante mentres traballas ca terminal. Son bastante sinxelos, polo que non os explicaremos con tanto detalle como a parella anterior.

Xoga con eles nun directorio de proba que creaches nalgún lugar para non eliminar accidentalmente nada importante, usando os comandos de exemplo que aparecen a continuación como guía:

- `mkdir`— Isto crea un novo directorio dentro do directorio actual no que estás, co nome que proporcionas despois do nome do comando. Por exemplo, `mkdir my-awesome-website` creará un novo directorio chamado `my-awesome-website`.
- `rmdir`— elimina o directorio nomeado, pero só se está baleiro. Por exemplo `rmdir my-awesome-website`, eliminará o directorio que creamos anteriormente. Se queres eliminar un directorio que non está baleiro (e tamén eliminar todo o que contén), podes usar a opción `-r` (recursivo), inda que isto pode ser algo perigoso. Asegúrate de que non hai nada que necesites dentro do directorio, xa que desaparecerá para sempre.
- `touch`— crea un novo arquivo baleiro, dentro do directorio actual. Por exemplo, `touch mdn-example.md` crea un novo arquivo baleiro chamado `mdn-example.md`.
- `mv`— move un arquivo desde a primeira localización especificada ata a segunda localización especificada, por exemplo `mv mdn-example.md mdn-example.txt`(as localizacións escríbense como rutas de arquivos). Este comando move un arquivo chamado `mdn-example.md` no directorio actual a un arquivo chamado `mdn-example.txt` tamén no directorio actual. Tecnicamente o arquivo estase movendo, pero desde unha perspectiva práctica, este comando está a renomear o arquivo.
- `cp`— similar en uso a `mv`, `cp` crea unha copia do arquivo na primeira localización especificada, na segunda localización especificada. Por exemplo, `cp mdn-example.txt mdn-example.txt.bak` crea unha copia de `mdn-example.txt` chamado `mdn-example.txt.bak`(por suposto que podes chamarlle como queiras).
- `rm`— elimina o arquivo especificado. Por exemplo, `rm mdn-example.txt` elimina un único arquivo chamado `mdn-example.txt`. Ten en conta que esta eliminación é permanente e non se pode desfacer a través da papeleira que teñas na interface de usuario do teu escritorio.

**Nota:** Moitos comandos de terminal permítenche usar asteriscos como caracteres de "comodín", que significa "calquera secuencia de caracteres". Isto permítelle executar unha operación contra un número potencialmente grande de arquivos á vez, todos eles coincidentes co patrón especificado. Como exemplo, `rm mdn-*`eliminaría todos os arquivos que comezan por `mdn-`. `rm mdn-*.bak`eliminaría todos os arquivos que comezan `mdn-`e rematan por `.bak`.

## Terminal: pódese considérar prexudicial?

Xa aludimos a isto antes, pero para que quede claro: debes ter coidado ca terminal. Os comandos sinxelos non comportan demasiado perigo, pero a medida que comezas a xuntar comandos máis complexos, cómpre pensar coidadosamente sobre o que fará o comando e probalos primeiro antes de executalos finalmente no directorio previsto.

Digamos que tiña 1000 arquivos de texto nun directorio e quería revisar todos eles e só eliminar os que teñen unha determinada subcadea dentro do nome do arquivo. Se non tes coidado, podes acabar eliminando algo importante, perdendo unha carga do teu traballo no proceso. Un bo hábito é escribir o comando do teu terminal nun editor de texto, averiguar como pensas que debería verse e, a continuación, facer unha copia de seguridade do teu directorio e probar primeiro a executalo para probalo.

Outro bo consello: se non estás cómodo probando os comandos da terminal na túa propia máquina, un lugar seguro para probalos está aquí. [Glitch.com](https://glitch.com/). Ademais de ser un gran lugar para probar código de desenvolvemento web, os proxectos tamén che dan acceso a un terminal, polo que podes executar todos estes comandos directamente nese terminal, sabendo que non romperás a túa propia máquina.

![unha dobre captura de pantalla que mostra a páxina de inicio de glitch.com e o emulador de terminal de fallos](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/glitch.png)

Un gran recurso para obter unha visión xeral rápida dos comandos específicos da terminal é [tldr.sh](https://tldr.sh/). Este é un servizo de documentación impulsado pola comunidade, similar a MDN, pero específico para os comandos da terminal.

Na seguinte sección imos aumentar un nivel (ou varias de feito) e ver como podemos conectar ferramentas na liña de comandos para ver realmente como a terminal pode ser vantaxoso sobre a interface de usuario do escritorio normal.

## Conexión de comandos xunto con *tubos*

A terminal realmente cobra importancia por si mesma cando comezas a encadear comandos usando o símbolo`|` (tubo). Vexamos un exemplo moi rápido do que isto significa.

Xa miramos `ls`, que saca o contido do directorio actual:

```bash
ls
```

Pero e se quixeramos contar rapidamente o número de arquivos e directorios dentro do directorio actual? `ls` non pode facelo por si só.

Hai outra ferramenta Unix dispoñible chamada `wc`. Isto conta o número de palabras, liñas, caracteres ou bytes do que se introduza nel. Este pode ser un arquivo de texto; o seguinte exemplo mostra o número de liñas en `myfile.txt`:

```
wc -l myfile.txt
```



Pero tamén pode contar o número de liñas de calquera saída que se lle **introduza** . Por exemplo, o seguinte comando conta o número de liñas emitidas polo comando `ls` (o que normalmente imprimiría na terminal se se executase por si só) e, no seu lugar, saíu que contan para a terminal:

```bash
ls | wc -l
```

Dado que `ls` imprime cada arquivo ou directorio na súa propia liña, iso ofrécenos un número de directorios e arquivos.

Entón, que está a pasar aquí? Unha filosofía xeral das ferramentas de liña de comandos (unix) é que imprimen texto na terminal (tamén referido a "impresión na saída estándar" ou `STDOUT`). Unha gran cantidade de comandos tamén poden ler contido da entrada de transmisión (coñecida como "entrada estándar" ou `STDIN`).

O operador de tubos pode *conectar* estas entradas e saídas xuntas, o que nos permite crear operacións cada vez máis complexas para atender ás nosas necesidades: a saída dun comando pode converterse na entrada do seguinte comando. Neste caso, `ls` normalmente imprimiría a súa saída a `STDOUT`, pero neste caso a saída`ls` está a ser canalizada a `wc`, quen toma esa saída como entrada, contando o número de liñas que contén a saída de `ls` e imprime a conta nun propio `STDOUT`.

## Un exemplo un pouco máis complexo

Primeiro tentaremos buscar o contido da páxina "fetch" de MDN mediante o comando `curl` (que se pode usar para solicitar contido dos URL), de

 `https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch`. 

Proba agora:

```bash
curl https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch
```

Non obterás unha saída porque a páxina foi redirixida (a [/Web/API/fetch](https://developer.mozilla.org/en-US/docs/Web/API/fetch) ). Necesitamos indicar de forma explícita a `curl` que siga as redireccións usando a marca de opción `-L`.

Imos tamén ollar os cabezallos que `developer.mozilla.org` devolve usando a marca de opción de `curl`, `-I`, e imprimir todas as redireccións de localización que envía á terminal, canalizando a saída de `curl` dentro `grep`(imos pedir `grep` para volver todas as liñas que conteñen a palabra ' location ').

Proba a executar o seguinte (verás que só hai unha redirección antes de chegar á páxina final):

```bash
curl https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch -L -I | grep location
```



A túa saída debería verse así ( `curl`primeiro sairá algúns contadores de descargas e similares):

```bash
location: /en-US/docs/Web/API/fetch
```



Aínda que é artificioso, poderiamos levar este resultado un pouco máis alá e transformar o `location:`contido das liñas, engadindo a orixe base ao inicio de cada unha delas para que se impriman URL completos. Para iso, engadiremos `awk` á mestura (que é unha linguaxe de programación semellante a JavaScript ou Ruby ou Python, só que moito máis antiga!).

Proba a executar isto:

```
curl https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch -L -I | grep location | awk '{ print "https://developer.mozilla.org" $2 }'
```



E a túa saída final debería ser algo así:

```
https://developer.mozilla.org/en-US/docs/Web/API/fetch
```



Ao combinar estes comandos, personalizamos a saída para mostrar os URL completos aos que está redirixindo o servidor de Mozilla cando solicitamos a URL `/docs/Web/API/WindowOrWorkerGlobalScope/fetch`. 

> Coñecer o teu sistema será útil no futuro: aprende como funcionan estas ferramentas de servizo único e como poden formar parte do teu arsenal para resolver problemas concretos.

## Engadindo potenciadores

Agora botaremos unha ollada a algúns dos comandos integrados cos que está equipado o teu sistema, e tamén como podemos instalar unha ferramenta CLI de terceiros e facer uso dela.

O amplo ecosistema de ferramentas instalables para o desenvolvemento web front-end existe na súa maioría na sé de [npm](https://www.npmjs.com/), un servizo de hospedaxe de paquetes de propiedade privada que traballa en estreita colaboración con Node.js. Isto vaise expandindo lentamente; podes esperar ver máis provedores de paquetes a medida que pase o tempo.

[Ao instalar Node.js](https://nodejs.org/en/) tamén instalas a ferramenta de liña de comandos `npm` (e unha ferramenta complementaria centrada en  `npm`  chamada ``npx`` ), que ofrece unha porta de entrada para instalar ferramentas de liña de comandos adicionais. Node.js e `npm` funcionan igual en todos os sistemas: macOS, Windows e Linux.

Instala npm, indo ao URL anterior e descargando e executando o instalador de Node.js axeitado ao teu sistema operativo. Se se te solicita, asegúrate de incluír `npm` como parte da instalación.

![o instalador node.js en Windows, que mostra a opción de incluír npm](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/npm-install-option.png)

*Aínda que xa veremos outras ferramentas, podemos ir por [Prettier](https://prettier.io/). Prettier é un formatador de código coa sona de que ten "poucas opcións". Máis menos opcións non ten porque significar máis sinxelo. Dado que as ferramentas ás veces poden saírse de control en termos de complexidade, dispor de "poucas opcións" pode resultar un claro atractivo.*

### Onde instalar as ferramentas CLI?

Antes de mergullarnos na instalación de Prettier, hai unha pregunta que responder: "onde debemos instalalo?"

Con `npm` temos a opción de instalar ferramentas globalmente - para que poidamos acceder a elas desde calquera lugar - ou localmente: xusto no cartafol do proxecto actual.

Hai pros e contras en cada sentido, e esta lista de pros e contras para a instalación global está lonxe de ser exhaustiva:

| Pros da instalación global                     | Contras da instalación global                                |
| :--------------------------------------------- | :----------------------------------------------------------- |
| Accesible na túa terminal desde calquera lugar | Pode non ser compatible coa base de código do teu proxecto   |
| Instálao só unha vez                           | Outros desenvolvedores do teu equipo non terán acceso a estas ferramentas, por exemplo, se estás compartindo a base de código a través dun VCS como git. |
| Usa menos espazo no disco                      | Relacionado co punto anterior, fai que o código do proxecto sexa máis difícil de replicar (se instalas as túas ferramentas localmente, pódense configurar como dependencias e instalar con `npm install`). |
| Sempre a mesma versión                         |                                                              |
| Semella outro comando máis de Unix             |                                                              |

Aínda que a lista de *contras* é máis curta, o impacto negativo da instalación global é potencialmente moito maior que os beneficios. 

### Instalando Prettier

Para este artigo instalaremos Prettier como unha utilidade de liña de comandos global.

Prettier é unha ferramenta de formato de código apta para desenvolvedores front-end, que se centra en linguaxes baseadas en JavaScript e engade compatibilidade con HTML, CSS, SCSS, JSON e moito máis. Paquete Prettier:

- Aforra a sobrecarga de conseguir un estilo coherente de xeito manual en todos os teus arquivos de código; Prettier pode facelo por ti automaticamente.
- Axuda aos recén chegados ao desenvolvemento web a formatear o seu código segundo as mellores prácticas.
- Instalado en calquera sistema operativo ou mesmo como parte directa das ferramentas do proxecto, asegurará que os compañeiros que traballan no teu código usen o estilo de código que estás a usar ti.
- Pódese configurar para executarse despois de gardar, mentres escribes ou mesmo antes de publicar o teu código.

Unha vez instalado NodeJS, abre a terminal e executa o seguinte comando para instalar Prettier:

```
npm install --global prettier
```



Unha vez que o comando rematou de executarse, a ferramenta Prettier agora está dispoñible na túa terminal, en calquera lugar do teu sistema de arquivos.

Executar o comando sen argumentos, como ocorre con moitos outros comandos, ofrecerá información de uso e axuda. Proba isto agora:

```bash
prettier
```



A túa saída debería verse algo así:

```bash
Usage: prettier [options] [file/glob ...]

By default, output is written to stdout.
Stdin is read if it is piped to Prettier and no files are given.

…
```



Sempre paga a pena, como mínimo, revisar a información de uso, aínda que sexa longa. Axudarache a comprender mellor como se pretende utilizar a ferramenta.

### Xogando con Prettier

Imos xogar rapidamente con Prettier, para que vexas como funciona.

Primeiro de todo, crea un novo directorio nalgún lugar do teu sistema de arquivos que sexa fácil de atopar. Quizais un directorio chamado `prettier-test` no teu cartafol de proxectos.

Agora garda o seguinte código nun arquivo novo chamado `index.js`, dentro do teu directorio de proba:

```js
const myObj = {
a:1,b:{c:2}}
function printMe(obj){console.log(obj.b.c)}
printMe(myObj)
```



Podes executar Prettier contra unha base de código só para comprobar se o noso código quere ser axustado. Usa  `cd` para ir ate o teu directorio e proba a executar este comando:

```bash
prettier --check index.js
```



Deberías obter unha saída algo así

```bash
Checking formatting...
index.js
Code style issues found in the above file(s). Forgot to run Prettier?
```



Polo tanto, hai algúns estilos de código que se poden corrixir. Sen problema. Engadir a opción `--write` ao comando Prettier solucionaraos, permitíndoche centrarte en escribir código útil.

Agora tenta executar esta versión do comando:

```bash
prettier --write index.js
```



Obterás unha saída coma esta

```bash
Checking formatting...
index.js
Code style issues fixed in the above file(s).
```



Pero o máis importante é que se miras atrás no teu arquivo JavaScript verás que foi reformateado a algo así:

```
const myObj = {
  a: 1,
  b: { c: 2 },
};
function printMe(obj) {
  console.log(obj.b.c);
}
printMe(myObj);
```



Dependendo do teu fluxo de traballo (ou do fluxo de traballo que elixas), podes converter isto nunha parte automatizada do teu proceso. A automatización é realmente onde destacan as ferramentas; a nosa preferencia persoal é o tipo de automatización que "só sucede" sen ter que configurar nada.

Con Prettier hai varias formas en que se pode conseguir a automatización e, aínda que están fóra do alcance deste artigo, hai algúns excelentes recursos en liña para axudar (algunhas das cales foron ligadas). Podes invocar Prettier:

- Antes de enviar o teu código a un repositorio git usando [Husky](https://github.com/typicode/husky).
- Sempre que premes "gardar" no teu editor de código, sexa [VSCode](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode), [Átom](https://atom.io/packages/prettier-atom), ou [SublimeText](https://packagecontrol.io/packages/JsPrettier).
- Como parte das comprobacións de integración continuas mediante ferramentas como [accións de Github](https://github.com/features/actions).

A nosa preferencia persoal é a segunda: mentres usamos, por exemplo, VS Code, Prettier activa e limpa calquera formato que teña que facer cada vez que prememos gardar. Podes atopar moita máis información sobre o uso de Prettier de diferentes xeitos na páxina [Documentación de Prettier](https://prettier.io/docs/en/).

## Outras ferramentas para xogar

Se queres xogar con algunhas ferramentas máis, aquí tes unha breve lista que é divertido de probar:

- [`bat`](https://github.com/sharkdp/bat)— Un "máis agradable" `cat`( `cat`úsase para imprimir o contido dos arquivos).
- [`prettyping`](https://denilson.sa.nom.br/prettyping/)— `ping` na liña de comandos, pero visualizado ( `ping` é unha ferramenta útil para comprobar se un servidor responde).
- [`htop`](https://hisham.hm/htop/) — Un visor de procesos, útil para cando algo está facendo que o ventilador da CPU se comporte como un motor a reacción e quere identificar o programa ofensivo.
- [`tldr`](https://tldr.sh/#installation) — dispoñible como ferramenta de liña de comandos.

Ter en conta que algunhas destas ferramentas poden necesitar ser instalalas mediante npm, como fixemos con Prettier.



___

OUT 2021



_**ref:**_  https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line