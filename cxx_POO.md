# Programación orientada a obxectos: Linguaxes, Metodoloxías e Ferramentas

> Proceso de desenvolvemento de aplicaciones software

## 1

*O software se encadra entre os artefactos máis complexos que son capaces de desenvolver as persoas, e xa que no ten límites físicos, polo seu carácter virtual, as súas dimensións se poden imaxinar ilimitadas. O obxectivo dun proceso de desenvolvemento web é a formalización das actividades relacionadas co desenvolvemento dun sitio en toda a súa complexidade, que van dende as estratexias de comunicación formal ás metodoloxías de desenvolvemento de software ou programación. Moitos proxectos que se crean, acabanse tarde, costan moito máis do inicialmente estimado ou acaban abandoados a medio facer . Máis, por que acontece isto?.*

### Proceso de desenvolvemento de aplicacións software.

Un proceso de desenvolvemento de software é a secuencia de actividades que deben ser seguidas por un equipo de traballadores para xerar un conxunto coherente: o programa ou sistema ideado. A tarefa vai ser tan complexa como complexo sexa o obxectivo final que se persegue. 

O obxectivo básico do proceso é facer predecible o traballo que se require: 

- Predecir os custes.
- Manter un nivel de calidade
- Predecir o tempo de desenvolvemento

## 2

*A adopción por parte dunha empresa dun proceso de desenvolvemento contrastado, lle permite producir aplicacións software con prazos e custes predecibles e con calidade constante. Existen marcos de desenvolvemento baseados en criterios xenéricos, e que cada empresa debe configurar e refinar conforme as características da empresa e do produto que se vai a desenvolver.*

### Natureza das aplicacións software

Os intereses e obxectivos dun programa son múltiples e variadamente complexos. E non existe un proceso de desenvolvemento universal que poida aplicarse indistintamente a todos. O proceso de desenvolvemento debe configurarse conforme a natureza do produto e a experiencia da empresa.

Tipos de aplicacións:

- **Aplicacións monoprocesadoras**: Se executan nun só computador. Non se comunican con outras aplicacións. Ex. Procesador de texto.
- **Aplicacións embebidas**: Se executan nun entorno computarizado especial. Require codiseño hardware/software. Ex: Teléfono móbil.
- **Aplicacións de tempo real**: Teñen entre as súas especificacións requerimentos temporais. E natureza reactiva. Ex: Software de radar.
- **Aplicacións distribuidas**: Se executan en múltiples procesadores. Requiren intercomunicación a través da rede. Ex: Aplicacións de/na rede.



## 3

*A razón básica pola que se require dispor dun proceso de desenvolvemento é mellorar a seguridade do traballo eliminando riscos innecesarios e conseguir un produto da máxima calidade.*


### Obxectivos dun proceso de desenvolvemento

Proporcionar unha guía de execución do proxecto que defina para os técnicos a secuencia de tarefas que se requiren e os produtos que se deben xerar. 

Específicamente un proceso de desenvolvemento debe conseguir:

* Proporcionar un módelo de desenvolvemento do proxecto no que quede definido o que cada traballador que interven debe realizar e os produtos que debe xerar ao longo do tempo que se adique ao proxecto.

Os obxectivos de adoptar unha metodoloxía para o proceso de desenvolvemento son:

* Mellorar a calidade do produto:
  * Disminuir o número de defectos que se producen e que deben ser correxidos.
  * Disminuir a severidade dos defectos residuais que poden permanecer no produto final. 
  * Mellorar a reusabilidade, de forma que gran parte do traballo que se realiza poida ser reutilizado en próximos proxectos.
  * Mellorar a estabilidade do proceso de forma que se minimicen as reelaboracións do produto. 
  * Xerar un produto que sexa de fácil mantemento posterior.
* Mellorar a predicibilidade do proxecto:
  * Cantidade de esforzo humano e de recursos que requirirá.
  * Disminuir os prazos de desenvolvemento e chegada ao mercado.

- Xerar ao longo do desenvolvemento a información axeitada e diferenciada para que os diferentes responsables do proxecto poidan facer un seguimento de forma efectiva.

## 4

### Elementos básicos dun proxecto.

*Os elementos básicos dun proceso de desenvolvemento de software é definir os papeles que xogan os traballadores, as actividades que desenvolven e os produtos que deben xerarse. Nun plan de desenvolvemento cada traballador debe ter definido o seu papel, o que define as actividades que debe realizar e os produtos que debe xerar. As actividades son as tarefas que deben realizar os traballadores para cumplir a súas obligacións. Nun primeiro nivel, estas actividades son concebidas como fases do proceso (especificación, análise, ..), mentres que nun nivel máis avanzado se especifican en tarefas máis concretas (crear certos diagramas, escribir código,..).  Cada actividad debe ter sempre como principal obxectivo xerar certos produtos ben definidos e especificados. Os produtos son os documentos ou información que debe ser creada como resultado da actividade que se desenvolva. O produto último é o sistema que se desenvolve, pero nas fases intermedias deben xerarse unha ampla gama de documentos intermedios. ~~Os procesos deben estar condicionados polo tipo de produto que se desenvolva e pola tradición e experiencia da empresa que lo desarrolla.~~*

## POO

A **Programación Orientada a Obxectos (POO)** é un dos paradigmas máis utilizados polas persoas que se adican ao sector informático.  

## **As principais características da programación orientada a obxectos**

É importante señalar que **a POO pode variar segundo o programador**. Xa que non se trata tanto dun modelo diferente de escribir código, senon dunha forma diferente de concebir a programación.

Se trata dun modelo de **programación** máis aberto, que favorece a **estructuración ordenada** dos proxectos. Se require dunha certa formación previa, pero na práctica aporta ventaxas polas que esta metodología favorece o desenvolvemento produtivo. A organización do código se realiza en distintas clases que, posteriormente, poderán concretarse en obxectos.

O *módulo* foi unha primera aproximación á programación con reaproveitamento, pero POO vai un paso máis alá. A POO permite que as aplicacións que se desenvolvan sexan cada vez máis complexas sin que iso supoña desbotar código. A filosofía da POO invita a reutilizalo, de maneira que progresar non supoña renunciar.

Algunhas cousas que interesa entender cando nos aproximamos a esta metodoloxia de desenvolvemento son:

### **1. Distinción entre clase e obxecto**

A **distinción entre clase e obcxecto** é unha das claves deste tipo de programación que a fai única. Si non logramos entender esta parte, resultará complicado saber cómo funciona este tipo de programación.

En primeiro lugar, a clase se referirá á **matriz xenérica**, á cal se aplicarán determinadas **categorías** para que poidase afinar. Feito isto, nos referiremos aos **obxectos**, que supoñen a **concreción** desta matriz. Por exemplo, o concepto "animal" sería unha clase, mentres que "gato" é un obxecto. Isto permite aportar orden, o que sempre é de agradecer, grazas á capacidade de **abstracción** que podemos despregar nas clases.

A idea principal é que, a partir da clase, se poden crear instancias dun obxecto tantas veces como se queira e ali onde consideremos preciso. A POO é unha metodología moi útil para programar sobretodo cando se trata cunha gran cantidade de datos á que hai que dar forma.

 

### **2. Reutiliza o código e evita a súa duplicación**

A duplicación de código é un dos problemas recorrentes no desenvolvemento de software e aplicacións, tamén na web. Sobre todo pola perda de tempo que implica.

POO manexa un **principio de herdanza** que fai que exista unha **jerarquización entre as clases** que empregamos. O resultado práctico diso é que **se reducen** expoñencialmente as **veces que tes que reescribir** un mesmo código. Como **o código se pode reutilizar** gracias ao principio de herdanza, **evitamos a súa duplicación**. O que se traduce tamén nun aforro de tempo.

 

### 3. Encapsula la información

O concepto de encapsulación da información é clave se queres ser meticuloso, p.ex., na **privacidade** do tratamento de calquera tipo de datos. 

A POO o que consegue é que **toda a información dun obxecto esté dentro del mesmo.** En consecuencia, o acceso desde fora se fai prácticamente imposible para os non programadores. O resultado práctico é que **se gaña en seguridade**.

 

### **4. Polimorfismo**

O **polimorfismo** permite **deseñar obxectos para compartir comportamentos**. Polo tanto, é unha boa forma de que se poida proporcionar orde. O efecto que se consigue é que podes **procesar os obxectos de distintas maneiras**.

O **polimorfismo**, aínda que é unha das avantaxes da POO, é tamén unha arma de dobre fio. O motivo é que **abre campos a dúas formas e adaptacións**. Básicamente podemos falar da **anulación de método** e a **sobrecarga de método**. É por iso que, cando falamos da POO, nos referimos máis ben a unha filosofía de programación, porque as adaptacións son ben diversas.

O poliformismo é, ao final, sinónimo de versatilidade. Polo tanto, esta é unha boa maneira de adaptar a programación a aquilo que necesitas.

 

## **As avantaxas de la programación orientada a obxectos**

Destacar:

- **Reutilización do código**. Pobablemente, unha das aventaxas máis importantes: permite aforrar tempo sen perder calidade de programación. Ademáis, deste xeito poderás progresar a desenvolvementos máis complexos.
- **Evitar duplicar código**. Reutilización de código, herdanza e xerarquización, aforran tempo, evitan a dispersión e acabar perdendo tempo en axustes e correccións. 
- **Simplifica a estrutura**. A distinción entre clases e obxectos permite simplificar a estrutura e facilita a programación. E fai o traballo máis sinxelo.
- **Protección da información**. A encapsulación proporciona privacidade, o que permite que se poida traballar en equipo só coas persoas autorizadas. É unha boa forma de gañar en seguridade e evita as filtracións; ou alo menos sirve para combatelas.
- **Fácil corrección de erros**. A estruturación do código en compoñentes fácilita a localización de erros, e en consecuencia, na súa corrección.

 

ref: 

- https://desarrolloweb.com/manuales/teoria-programacion-orientada-objetos.html

___

XAN 2022