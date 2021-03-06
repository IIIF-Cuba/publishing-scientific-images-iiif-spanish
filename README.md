# International Image Interoperability Framework (IIIF) para editoriales científicas
Traducción del artículo del sitio https://elifesciences.org/labs/aabe94cd/publishing-scientific-images-using-the-iiif

Nos complace presentar International Image Interoperability Framework (IIIF), un marco de imagen impulsado por la comunidad con APIs definidas para hacer que los repositorios de imágenes del mundo sean inter-operables y accesibles.

Para comunicar descubrimientos importantes, a veces las imágenes pueden ser tan efectivas como el texto simple, si no más. Este blogpost proporciona una visión general del estándar IIIF, con énfasis en su potencial para editoriales Científicas, Técnicas, y Médicas (CTM), e invita a esas organizaciones a participar en un servicio piloto ofrecido por la Biblioteca Wellcome.

Apoyado en el marco IIIF, el nuevo [Digital Library Cloud Service(DLCS)](https://dlcs.gitbooks.io/book/content/overview.html) del Fideicomiso Wellcome es una infraestructura basada en la nube que pretende ofrecer servicios rápidos, escalables, y de amplia disponibilidad para la presentación de imágenes en formas enriquecidas y atractivas.

Muchas grandes bibliotecas de investigación han adoptado IIIF para presentar sus imágenes digitales, pero muchas editoriales CTM aún deben experimentar sus beneficios.

Blogpost de Robert Kiley, Jefe de Servicios Digitales, Biblioteca Wellcome [kiley@wellcome.ac.uk](mailto:r.kiley@wellcome.ac.uk), y Tom Crane, Director Técnico, Digirati [tom.crane@digirati.com](mailto:tom.crane@digirati.com).

## El potencial de IIIF para las editoriales CTM

Es ampliamente reconocido que una imagen vale mil palabras, y eso es especialmente cierto en la web. No obstante, combinar en un único objeto digital colecciones de imágenes mantenidas en sitios web distintos, y presentar las mismas mediante una aplicación rica en funcionalidad, es una tarea difícil.

Ese fue el problema que quiso solucionar un grupo de bibliotecarios con interés especial en los manuscritos medievales. La meta era proporcionar a sus usuarios una sola herramienta para acceder a las imágenes digitalizadas, y que la experiencia de visualización incluyera funcionalidades como zoom profundo, búsqueda, y anotación. Todo eso llevó al desarrollo de IIIF.

En los últimos dos años, muchas grandes bibliotecas de investigación del mundo han comenzado a presentar sus imágenes digitalizadas usando ese marco. Sin embargo, pocas editoriales CTM han adoptado el estándar, aun cuando las imágenes, en forma de figuras, juegan un papel fundamental en la diseminación de la información académica.

![](img/default.jpg)

**Figura 1.** Una colección IIIF de imágenes biomédicas de la Biblioteca Wellcome [https://alpha.wellcomelibrary.org/collections/biomed](https://alpha.wellcomelibrary.org/collections/biomed)

Son varios los beneficios de IIIF para las editoriales CTM:

- Permite presentar imágenes en plataformas propias en forma enriquecida y atractiva. Muchas editoriales ofrecen imágenes en tamaño completo en sus artículos online, pero muy pocas proporcionan al usuario la opción de ver la imagen en un cliente de zoom profundo. Eso puede resultar difícil para quienes se hayan habituado a la funcionalidad de zoom profundo.
- Cuando las imágenes estén disponibles como endpoints IIIF, una editorial CTM podrá construir fácilmente una serie de aplicaciones web para combinar todas sus imágenes, y ofrecer un servicio de biblioteca de imágenes a los usuarios.
- Los usos anteriores de IIIF serían útiles para editoriales individuales; pero se podrían construir aplicaciones mucho más enriquecidas si todas las editoriales presentaran sus imágenes de esa manera. Por ejemplo, la reciente emergencia de salud pública motivada por el virus Zika hizo que varias editoriales acordaran publicar gratuitamente las investigaciones que poseían sobre el tema. Si esas mismas editoriales presentaran las imágenes de esos documentos como endpoints IIIF, los investigadores tendrían un único objeto digital donde acceder a todas las imágenes relacionadas con el virus.
- Finalmente, IIIF se está utilizando en proyectos de crowdsourcing de Patrimonio Cultural para transcripción, traducción, y etiquetado. Esas actividades son igualmente aplicables a material CTM.

## El DLCS de la Biblioteca Wellcome

La [Biblioteca Wellcome](http://wellcomelibrary.org/) está desarrollando una infraestructura basada en la nube, compatible con IIIF, con el fin de ofrecer servicios de amplia disponibilidad para presentar sus imágenes digitales, proporcionar búsqueda de texto completo y servicios de autenticación y, con el tiempo, funcionalidad de anotación.

Desarrollar servicios para ofrecer endpoints IIIF es una tarea difícil que requiere el dominio e implantación de tecnología de servidor de imagen por parte de la institución/editorial. Por tanto, estamos explorando como proporcionar esos servicios en forma de servicio totalmente gestionado, a través de un proyecto piloto en el cual unas 40 instituciones pueden emplear nuestra infraestructura DLCS para generar endpoints IIIF de todas las imágenes que presentan mediante esa plataforma. Más detalles en: [https://dlcs.gitbooks.io/book/content/index.html](https://dlcs.gitbooks.io/book/content/index.html). Si alguna editorial desea probar este servicio, lean las Preguntas Frecuentes de DLCS y contacten a Robert Kiley.

## ¿Qué es IIIF?

IIIF soporta dos APIs, una de Imagen y una de Presentación, y dos APIs relacionadas, autenticación y búsqueda.

## API de Imagen de IIIF

El objetivo de la API de Imagen es permitir al usuario (humano o computadora) solicitar una imagen con un endpoint IIIF de diversas maneras, modificando tamaño, región, rotación, y formato según se requiera.

![](img/fig2_iiif_image_api.JPG)

**Figura 2.** Una imagen vista mediante la API de Imagen de IIIF

Todos los detalles de la API de Imagen se encuentran en [http://iiif.io/api/image/2.0/](http://iiif.io/api/image/2.0/). En esencia, cada petición usa la sintaxis siguiente: {esquema}://{servidor}{/prefijo}/{identificador}/{región}/{tamaño}/{rotación}/{calidad}.{formato}.Por ejemplo: www.example.org/image-service/abcd1234/full/max/0/default.jpg

Con esa sintaxis, un usuario podría, por ejemplo, construir una página web que presente una imagen en, digamos, 300x300 píxeles, mientras otro usuario utiliza la misma imagen, pero la muestra con tamaño y rotación diferentes, y centrada en una región específica. En todos los casos, el servidor de imagen IIIF posee una imagen máster, y presenta las imágenes al cliente como sean solicitadas. 

El potencial de esta API es mejor ilustrado en los ejemplos de la Tabla 1. Note que es suficiente editar la URL para generar distintas respuestas del servidor IIIF:

<table style="width:500px" cellspacing="1" cellpadding="1" border="1">
                                            <tbody>
                                              <tr>
                                                <td>Tarea</td>
                                                <td>URL y Comentarios</td>
                                              </tr>
                                              <tr>
                                                <td>Ver una
                                                  imagen IIIF</td>
                                                <td>
                                                  <p><a href="http://wellcomelibrary.org/iiif-img/b20432033-0/d7b80202-a1d7-4f88-ab57-0f6b369fe41b/full/full/0/default.jpg">http://wellcomelibrary.org/iiif-img/b20432033-0/d7b80202-a1d7-4f88-ab57-0f6b369fe41b/full/full/0/default.jpg</a></p>
                                                  <p>Esta es la petición
                                                    predeterminada –
                                                    mostrar la imagen en
                                                    tamaño completo, sin
                                                    rotación, como
                                                    archivo jpg.</p>
                                                </td>
                                              </tr>
                                              <tr>
                                                <td>
                                                  <p>Solicitar otro
                                                    tamaño de imagen<br>
                                                  </p>
                                                </td>
                                                <td>
                                                  <p><a href="http://wellcomelibrary.org/iiif-img/b20432033-0/d7b80202-a1d7-4f88-ab57-0f6b369fe41b/full/500,500/0/default.jpg">http://wellcomelibrary.org/iiif-img/b20432033-0/d7b80202-a1d7-4f88-ab57-0f6b369fe41b/full/500,500/0/default.jpg</a></p>
                                                  <p>En este ejemplo,
                                                    pedimos que la
                                                    imagen se presente
                                                    con un tamaño de
                                                    500x500 píxeles.</p>
                                                </td>
                                              </tr>
                                              <tr>
                                                <td>Rotar una imagen</td>
                                                <td>
                                                  <p><a href="http://wellcomelibrary.org/iiif-img/b20432033-0/d7b80202-a1d7-4f88-ab57-0f6b369fe41b/full/,500/90/default.jpg">http://wellcomelibrary.org/iiif-img/b20432033-0/d7b80202-a1d7-4f88-ab57-0f6b369fe41b/full/,500/90/default.jpg</a>&nbsp;(ver Figura 2)</p>
                                                </td>
                                              </tr>
                                            </tbody>
                                          </table>
										  
**Tabla 1.** API de Imagen de IIIF: ejemplos

**¿Cómo sabemos que una imagen admite esas manipulaciones?**

Para determinar los servicios IIIF soportados por una imagen IIIF, mire el recurso info.json. En el ejemplo anterior, para pedir el archivo JSON en lugar de la imagen, use: http://wellcomelibrary.org/iiif-img/b20432033-0/d7b80202-a1d7-4f88-ab57-0f6b369fe41b/info.json

Verá que acepta la rotación, pero a pasos de 90 grados ("rotationBy90s").

## API de Presentación de IIIF

En palabras de IIIF, la API de Presentación “especifica un servicio web que retorna documentos estructurados JSON-LD los cuales, en conjunto, describen la estructura y layout de un objeto digitalizado.” Expresado más sencillamente, la API de Presentación proporciona suficientes metadatos para impulsar la aplicación de visualización. En el mundo IIIF, esos documentos estructurados se llaman manifests.

![](img/fig3_iiif_presentation_api.JPG)

**Figura 3.** Usando Universal Viewer para ver una imagen IIIF

Los ejemplos de la Tabla 2 son una simple demostración de la API de Presentación de IIIF.  Los detalles se encuentran en: http://iiif.io/api/presentation/2.1/

<table style="width:500px" cellspacing="1" cellpadding="1" border="1">
                                            <tbody>
                                              <tr>
                                                <td>Tarea</td>
                                                <td>URL y Comentarios</td>
                                              </tr>
                                              <tr>
                                                <td>Visualizar un
                                                  manifest IIIF</td>
                                                <td>
                                                  <p><a href="http://wellcomelibrary.org/iiif/b20432033/manifest">http://wellcomelibrary.org/iiif/b20432033/manifest</a></p>
                                                  <p>Esto muestra el
                                                    manifest de la
                                                    imagen del embrión
                                                    de pez cebra vista
                                                    mediante la API de
                                                    Imagen (arriba).</p>
                                                </td>
                                              </tr>
                                              <tr>
                                                <td>Abrir un manifest en
                                                  Universal Viewer</td>
                                                <td>
                                                  <p><a href="http://wellcomelibrary.org/item/b20432033">http://wellcomelibrary.org/item/b20432033</a></p>
                                                  <p>La Biblioteca
                                                    Wellcome implementó
                                                    Universal Viewer
                                                    (UV) (<a href="https://github.com/UniversalViewer/universalviewer">https://github.com/UniversalViewer/universalviewer</a>)
                                                    como su visor
                                                    IIIF.&nbsp; Para ver
                                                    este objeto, abra la
                                                    siguiente URL:
                                                    [Inserte URL aquí]</p>
                                                </td>
                                              </tr>
                                              <tr>
                                                <td>
                                                  <p>Visualizar en otro
                                                    visor IIIF<br>
                                                  </p>
                                                </td>
                                                <td>
                                                  <p>Otra fortaleza de
                                                    IIIF es que admite
                                                    cualquier visor
                                                    compatible con IIIF
                                                    para renderizar las
                                                    imágenes.</p>
                                                  <p>Aquí vemos la
                                                    imagen del pez cebra
                                                    en el visor IIIF
                                                    Mirador,
                                                    desarrollado por
                                                    Stanford.</p>
                                                  <p><a href="http://projectmirador.org/demo/">http://projectmirador.org/demo/</a></p>
                                                  <p>Clic en "Add new object from URL" - y pegar <a href="http://wellcomelibrary.org/iiif/b20432033/manifest">http://wellcomelibrary.org/iiif/b20432033/manifest</a></p>
                                                </td>
                                              </tr>
                                            </tbody>
                                          </table>									  

**Servicios de autenticación y búsqueda**

Además de proporcionar acceso a endpoints de imagen, IIIF soporta servicios de autenticación y búsqueda.

**Autenticación**

Sabiendo que no todas las imágenes se exponen con un modelo de acceso abierto, la infraestructura de IIIF permite describir y hacer cumplir controles de acceso a las imágenes.

La API de Autenticación de IIIF es un patrón de interacción que un visor cliente puede implementar para que el usuario pueda ganar acceso a las imágenes. Esto es esencial pues distintas instituciones tienen diferentes mecanismos de autenticación y autorización, y IIIF debe trabajar con todos. Esta API admite varios usos, desde la simple opción click-through (si el servidor no necesita establecer la identidad del usuario), hasta la autenticación completa delegada, que pasa las peticiones de acceso a la aplicación de autenticación de la organización que aloja las imágenes.

Se puede construir un manifest IIIF que referencie imágenes de endpoints distintos, que tengan políticas diferentes para gestionar la autenticación. Por ejemplo, asuma que se construyó un manifest IIIF que muestra todas las imágenes relacionadas con la malaria, publicadas por Science, Nature y eLife. Sería posible ver de inmediato las imágenes de eLife ya que son de acceso abierto pero, cuando el usuario navegue a una imagen alojada por Nature o Science, se le pedirá autenticación en esas publicaciones, pues sus imágenes no son de acceso abierto. Si la autenticación fuera denegada, esas imágenes no estarían disponibles. La API de Autenticación de IIIF describe como el visor cliente controla la experiencia de usuario a través de ese flujo.

La Tabla 3 muestra ejemplos de controles de acceso implementados por la Biblioteca Wellcome para su contenido. 

<table style="width:500px" cellspacing="1" cellpadding="1" border="1">
                                            <tbody>
                                              <tr>
                                                <td>Tarea</td>
                                                <td>
                                                  <p>URL y Comentarios</p>
                                                </td>
                                              </tr>
                                              <tr>
                                                <td>
                                                  <p>Licencia
                                                    click-through</p>
                                                </td>
                                                <td>
                                                  <p><a href="http://wellcomelibrary.org/item/b18170183">http://wellcomelibrary.org/item/b18170183</a></p>
                                                  <div>
                                                    <p>Como el archivo
                                                      podría contener
                                                      datos personales,
                                                      pedimos que el
                                                      usuario se
                                                      comprometa a no
                                                      usar
                                                      inapropiadamente
                                                      esos datos.</p>
                                                  </div>
                                                </td>
                                              </tr>
                                              <tr>
                                                <td>
                                                  <p>Autenticación
                                                    delegada</p>
                                                </td>
                                                <td>
                                                  <p><a href="http://wellcomelibrary.org/item/b16728701">http://wellcomelibrary.org/item/b16728701</a></p>
                                                  <div>
                                                    <p>La Biblioteca
                                                      Wellcome contiene
                                                      algunas imágenes
                                                      clínicas a las que
                                                      sólo pueden
                                                      acceder los
                                                      profesionales de
                                                      la salud. Al
                                                      intentar ver esta
                                                      imagen, será
                                                      redireccionado al
                                                      servidor CAS de la
                                                      Biblioteca
                                                      Wellcome.</p>
                                                  </div>
                                                </td>
                                              </tr>
                                            </tbody>
                                          </table>

**Tabla 3.** API de Autenticación de IIIF: ejemplos

**Búsqueda**

IIIF también ofrece una API de Búsqueda que retorna anotaciones disponibles en los recursos buscados. Esas anotaciones pueden ser transcripciones, comentarios, etiquetas, e identificaciones, entre otras.

Un uso significativo de esto es buscar en una obra que tenga imágenes con texto buscable. Los resultados textuales se pueden retornar como anotaciones para que los visores pueden resaltar los términos. La búsqueda también se puede emplear para:

- Encontrar todos los comentarios hechos por una persona particular.
- Encontrar todas las etiquetas en una colección particular.
- Encontrar todos los resaltados que contengan la palabra “cólera” en anotaciones de los reportes del Medical Officer of Health de la Biblioteca Wellcome.

La Tabla 4 tiene algunos ejemplos de como funciona esta API. Note que los parámetros adicionales usados después del primer ejemplo no son soportados actualmente por el servicio de ejemplo.

<table style="width:500px" cellspacing="1" cellpadding="1" border="1">
                                            <tbody>
                                              <tr>
                                                <td>Tarea</td>
                                                <td>
                                                  <p>URL y Comentarios</p>
                                                </td>
                                              </tr>
                                              <tr>
                                                <td>
                                                  <p>Encontrar el
                                                    término x en un
                                                    documento específico</p>
                                                </td>
                                                <td>
                                                  <p><a href="http://wellcomelibrary.org/annoservices/search/b19956435?q=london">http://wellcomelibrary.org/annoservices/search/b19956435?q=london</a></p>
                                                  <p>Las anotaciones
                                                    retornadas incluyen
                                                    información
                                                    contextual, y
                                                    suficiente
                                                    información de
                                                    ubicación para que
                                                    un visor renderice
                                                    resaltados:</p>
                                                  <p><a href="http://wellcomelibrary.org/item/b19956435#?cv=24&amp;h=london">http://wellcomelibrary.org/item/b19956435#?cv=24&amp;h=london</a></p>
                                                </td>
                                              </tr>
                                              <tr>
                                                <td>Encontrar término en
                                                  las anotaciones de un
                                                  usuario particular</td>
                                                <td>
                                                  <p><a href="http://wellcomelibrary.org/annoservices/search/b19956435?q=london&amp;user=wellcome:87678">http://wellcomelibrary.org/annoservices/search/b19956435?q=london&amp;user=wellcome:87678</a></p>
                                                </td>
                                              </tr>
                                              <tr>
                                                <td>
                                                  <p>Encontrar las
                                                    identificaciones de
                                                    personas del usuario
                                                    X en una región
                                                    particular de una
                                                    fotografía, entre
                                                    dos fechas</p>
                                                </td>
                                                <td>
                                                  <p><a href="http://wellcomelibrary.org/annoservices/search/canvas-123454321?motivation=identifying&amp;user=wellcome:87678&amp;box=200,200,1000,1000&amp;date=2016-01-01/2016-02-01">http://wellcomelibrary.org/annoservices/search/canvas-123454321?motivation=identifying&amp;user=wellcome:87678&amp;box=200,200,1000,1000&amp;date=2016-01-01/2016-02-01</a></p>
                                                </td>
                                              </tr>
                                            </tbody>
                                          </table>
										  
**Tabla 4.** API de Búsqueda de IIIF: ejemplos

El servicio de búsqueda está acompañado por un servicio de autocompletamiento, útil para ofrecer completamientos de términos o etiquetas. Ambos servicios son descritos en la API de Búsqueda de IIIF en http://iiif.io/api/search/1.0/

**Conclusión**

Con la flexibilidad y riqueza de las APIs de IIIF, es sorprendente que muchas editoriales CTM no se hayan apresurado a adoptar el nuevo estándar para publicar imágenes en la web. Es posible que desconozcan su existencia, o sientan que IIIF sólo es relevante para artículos de acceso abierto, y no sepan a ciencia cierta como aplicarlo a sus necesidades.

La ambición de IIIF es hacer posible un acceso más enriquecido a las imágenes del mundo. Con suerte, más editoriales CTM se animarán a presentar de ese modo sus materiales basados en imágenes.

