# JAMstack

**JAMstack** é unha abreviatura práctica acuñada por Mathias Biilmann, CEO de Netlify. Seu significado: JavaScript, API e Markup. Pero o que significa é moito máis do que representa.

**JAMstack se refire a unha arquitectura de desenvolvemento web** que permite aos desenvolvedores confiar nas avantaxas dos sitios web estáticos:

- mellor rendemento web
- beneficios de seguridade
e conservando os atributos dinámicos dun CMS orientado á base de datos sen a base de datos.

O enfoque JAMstack permite crear sitios totalmente dinámicos mentres que os activos reais son arquivos estáticos prerenderizados incorporados dende un CDN. 



Isto defire claramente de como funcionan as cousas nunha pila LAMP: Alí con cada solicitude do usuario, un servidor primeiro consulta unha base de datos e combina o resultado cos datos do marcado e os complementos da paxina para xerar un documento HTML no navegador.

JAMstack pola súa banda **sirve marcado preconstruido e activos optimizados de xeito máis rápido,** xa que todo está xa listo para ser servido. Non é necesario consultar a base de datos, xa que os arquivos xa están compilados e se serven ao navegador desde unha CDN.

## Logo JAMstack é estático?

Si e non.

Se ben o *produto* final dos sitios web construídos por JAMstack son arquivos estáticos, eses arquivos no están exentos de funcionalidades dinámicas, funcionalidades como formularios, comentarios, pasarelas de pago, etc., xeralmente manexadas por [API](https://study.com/academy/lesson/application-programming-interface-api-definition-example.html) de terceiros.

Estático, no caso de JAMstack, non significa **fixo**, senón máis ben libre de servidores, é dicir, o navegador non necesita a axuda de servidores para manexar as partes dinámicas. O lado dinámico das cousas se manexa con JavaScript do lado do cliente, e xeralmente se executa a través de funcións sen servidor.



## Prácticas recomendadas de JAMstack

Para desatar todo o potencial convén seguir as mellores prácticas:

- servir o proxecto desde unha rede CDN
- almacenar o código en GIT
- compilacións automatizadas e implementacións atómicas
- invalidación instantánea de caché
- e uso de ferramentas de construción modernas para axudar con todo isto.



## Crecemento da adopción do enfoque JAMstack

O crecemento deste ecosistema de desenvolvemento se veu favorecido por:

- A expansión das capacidades do navegador (Chrome, Firefox, etc.),
- O crecemento da economía de API,
- Os xeradores de sitios estáticos (SSG), 
- O crecente número de solucións CMS sin cabeza
- O inmenso uso de CDN (redes de entrega de contido) avanzadas para unha mellor distribución de contidos,



## Cales son os beneficios de JAMstack?

- **Rendemento**: O rendemento dun sitio web inflúe claramente na experiencia de usuario e, pode ser determinante cara o tráfico, a pesar dos esforzos SEO ou as estratexias SEM.

  A experiencia do usuario sempre foi difícil de rastrexar, medir e optimizar. Mais a conclusión é que os sitios web optimizados para o rendemento teñen avantaxas sobre os sitios web lentos. Poden ofrecer unha mellor experiencia de usuagulprio, e obter tamén un mellor posicionamento nas buscas, o que potencialmente equivale a máis audiencia e a maior rendibilidade. [Web Vitals](https://web.dev/vitals/#core-web-vitals)

- **Seguridade**: Sen bases de datos ou servidores dos que preocuparse. Uso de servicios de terceiros, que se ocupan do seu mantemento: ti ocupaste doutras cousas. Front-end e back-end desacoplados. Uso de API para exjecutar procesos do lado do servidor. 

  JAMstack ven con beneficios de seguridade dos que, a miúdo, outras entornas carecen. A clara separación dos servizos, e  que estes sexan mantidos, fai que sexa máis difícil atopar vulnerabilidades nas compoñentes individuais.

- **Escalado e aloxamento**: As CDN son case *infinitamente escalables*. Asemade o aloxamento de CDN para arquivos estáticos é moito máis barato que o aloxamento tradicional.

- **Mantemento**: Ao desfacerse das bases de datos, os complementos e o mantemento do aloxamento, reduciras tamén os costos operativos e de desenvolvemento.

- **Experiencia do desenvolvedor**: Vistas previas automáticas, reversión fácil (non máis copias de seguridade, *re-publicar* a versión anterior nun instante), entornas de desenvolvemento locais coa capacidade de executar e depurar funcións na nube localmente, administrar redireccións, encabezados HTTP, reescrituras a través dun só arquivo de configuración, etc.  E toda a facilidade para empregar **Github ->** [**CI/CD** ](https://bejamas.io/discovery/what-is-ci-cd/)**-> fluxo de CDN** (Netlify e Vercel dominan isto). 

- **Complexidade da API**: pode ser amedrentador encontrar unha solución perfecta entre tantas, pero iso tamén se pode dicir do ecosistema de complementos de WordPress. Unha diferencia, a API sempre que obteña os datos durante a compilación, non romperá o teu sitio web de producción. Un plugin de  WP pode.

## E as limitacións?

Como calquera outra tecnoloxía, JAMstack tamén ven con un par de limitacións:

- **Non é amigable para novizos**: necesitaras saber un poco, bastante, máis sobre desenvolvemento web.

- **Uso de datos específicos do usuario e/ou en tempo real**: algunhas cousas simplemente non se poden xerar previamente, coma os datos específicos dun usuario e/ou en tempo real (nome, avatar, datos de usuario rexistrado,…)

- **O proceso de construción**: Pode resultar un inconveniente en sitios con gran cantidade de paxinas de contidos. Un cambio calquera nunha soa paxina, dispara a reconstrucción de todo o sitio web. Algo que pode ser un problema nun sitio web con miles de paxinas.

  A solución: algunhas solucións coma [Gatsby](https://www.gatsbyjs.org/blog/2020-04-22-announcing-incremental-builds/) e/eu [NextJS](https://nextjs.org/blog/next-9-4) xa dispoñen de compilacións incrementais que permiten reconstruir só aquelas paxinas que se cambian.

- **Manexo de pezas dinámicas (funcións na nube)**: Empregar JAMstack non significa que te desfagas do back-end. ¡Todo o contrario! Unha parte importante do enfoque de JAMstack son as funcións sen servidor. 

  Isto significa que as partes de back-end do teu sitio web/aplicación, non só se escalarán case infinitamente e sen apenas mantemento, senón que tamén permitirán aos usuarios obter datos de back-end do centro de datos xeográfico máis próximo.

## JAMstack é para calquera?

Pois creo que non. 

- Se non tes inconveniente en pelexarte coas melloras de rendemento, a administración da caché ou estás satisfeito cunha solución sen código como Webflow, non te mudes a JAMstack.
- Se o teu equipo está acostumado a WordPress deberás valorar se realmente merece a pena inverter tempo e cartos para adoptar novas tecnoloxías. Se é que non: déixao pasar.
- Se o teu proxecto depende dunha tonelada de usuarios e/ou os datos en tempo real, non vaias polo camiño de JAMstack.



**Se estás buscando aumentar o rendimento do teu sitio web, facelo máis rápido para o usuario e máis seguro para ti podes considerar se JAMstack pode ser o camiño a seguir!**





## Configuración do proxecto

Sen servidor ou base de datos para configurar, un proxecto JAMstack é en grande parte unha simple estrutura de carpetas chea de arquivos de texto. Os contidos dun proxecto JAMstack xeralmente incluirán o seguinte:

- Un cartafol de orixe para almacenar os arquivos de contido
- Un cartafol para deseños e maquetas
- Un arquivo de configuración, cos axustes para o proceso de construción.
- Un xerador de sitio estático (SSG), xeralmente agregado como dependencia 
- Un cartafol de destino para gardar a saída final 



## Estratexias para administrar contido
Un sitio web comeza có contido. Nun sistema de xestión de contido (CMS) como Drupal ou Wordpress, os sitios administran o contido dunha base de datos, e os editores utilizan unha interface de administración para escribir e gardar o contido na base de datos.
Con JAMstack hai outros enfoques de contido:

- **Arquivos de texto**
  Para muitos sitios de JAMstack, o manexo do contido é do máis sinxelo: unha carpeta cos arquivos dentro do proxecto ao lado mesmo doutras carpetas  vive directamente coas plantillas, complementos e outros activos. Creando un novo arquivo no directorio de contido crearase unha nova páxina despois de que se publique o sitio. Os cambios se realizan editando os arquivos de contido nun texto editor e logo confirmar os cambios no repositorio de Git.

  O nome de cada arquivo e a carpeta na que se atopa determinarán a súa ruta URL despois de que xerar o sitio.

  De que tipo son os arquivos de contido?  Poden ser HTML, inda que normalmente este se emparella só coas partes únicas da paxina. Os elementos comúns como encabezados e pes de páxina se agregan mediante o xerador do sitio durante o paso de construción - build-.
  Pero crear contido en HTML pode resultar moi laborioso. Así que podes adoptar a sintaxe Markdown, que parece unha mellor alternativa para redactar contido textual estruturado.









_____

_ref.:_ [Jamstack Explained: What it is and how to get started? - Bejamas](https://bejamas.io/blog/jamstack/#:~:text=Today Jamstack refers to a web development architecture,attributes of a database-oriented CMS without the database.)

