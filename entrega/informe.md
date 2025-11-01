# Informe Técnico del Taller
---
## Nombre del Taller

Taller 3 - Arquitectura C4

---
## Intergantes del equipo

- Julián David Alvarado Gantiva
- Julián Camilo Durán Valencia
- Sebastián Piñeros Castellanos
---

## Descripción general del trabajo

En el presente taller se implementó la metodología de modelado de software bajo la notación C4 Model, con el fin de representar la arquitectura del caso aplicado al Software de Contabilidad. A través de este enfoque, se buscó describir la manera en que los diferentes actores interactúan con el sistema, así como la organización de los principales contenedores internos que conforman la solución tecnológica.

En el directorio del proyecto se incluyen los diagramas elaborados:

- Vista de Contexto (C1): donde se definen los actores externos, los sistemas involucrados y las interacciones principales.

- Vista de Contenedores (C2): donde se descompone el sistema central en contenedores de software y se muestran sus relaciones con la base de datos y sistemas externos.

---
## Proceso de desarrollo

Para la construcción de la arquitectura del sistema se decidió utilizar la notación C4 en sus dos primeros niveles (C1 y C2).

En primer lugar, se elaboró la Vista de Contexto (C1), donde se identificaron tres actores principales: Cliente, Contador y Administrador. También se incluyó un sistema externo clave: el Portal de Extractos, el cual provee los documentos bancarios necesarios para su integración posterior en el sistema contable. Se representaron las relaciones con etiquetas orientadas al negocio, tales como “consulta reportes”, “registra información contable” y “gestiona usuarios y procesos”.

En una segunda etapa, se construyó la Vista de Contenedores (C2), desglosando el Software de Contabilidad en sus módulos internos: Módulo de gestión contable, Módulo de reportes financieros, Módulo de integración de extractos y Módulo de usuarios y roles. Asimismo, se representó la Base de datos contable como contenedor de persistencia central. Finalmente, se modeló la interacción con el Portal de extractos, encargado de suministrar los documentos descargados por los clientes.

---
##  Análisis del modelo propuesto

El modelo arquitectónico propuesto busca representar de manera clara la estructura tecnológica del Software de Contabilidad en dos niveles de detalle (C1 y C2).

Análisis del modelo:

- Estructura del modelo: La vista de contexto refleja cómo los actores interactúan con el sistema principal, mostrando el límite entre el software contable y el sistema externo (Portal de extractos). La vista de contenedores, por su parte, detalla la organización interna del sistema en módulos especializados, lo que aporta mayor granularidad y facilita comprender la responsabilidad de cada componente.

- Representación de las necesidades del negocio: El modelo responde a la necesidad de registrar operaciones contables, consultar estados financieros y gestionar usuarios. El módulo de integración de extractos atiende la carga de documentos descargados externamente, mientras que el módulo de reportes financieros facilita la consulta de balances y estados financieros por parte de clientes y contadores.

- Supuestos tomados: Se asumió que la base de datos contable centraliza todas las operaciones, usuarios y extractos de manera segura, y que la comunicación con el portal externo de extractos es estable y confiable. Asimismo, se consideró que los actores acceden al sistema mediante aplicaciones soportadas en web, sin integración con APIs bancarias ni notificaciones externas adicionales.

En conclusión, los modelos C4 elaborados ofrecen una representación clara, coherente y alineada con las necesidades operativas del Software de Contabilidad, permitiendo visualizar tanto las interacciones de alto nivel como la composición interna del sistema central.

---
## Diagrama final entregado

Diagrama C1 - RedExpress:
![alt text](C1final.png)

Diagrama C2 - RedExpress:
![alt text](C2final.png)

---
## Tabla de actores, entidades o componentes

| Nombre del elemento                | Tipo         | Descripción                                                                | Responsable    |
| ---------------------------------- | ------------ | -------------------------------------------------------------------------- | -------------- |
| Cliente                            | Actor        | Persona que usa el sistema para consultar sus estados financieros          | Cliente        |
| Contador                           | Actor        | Registra y valida la información contable                                  | Contador       |
| Administrador                      | Actor        | Gestiona usuarios, permisos y procesos internos                            | Administrador  |
| Portal de extractos                | Sistema ext. | Permite descargar extractos bancarios que se integran al software contable | Cliente        |
| Módulo de gestión contable         | Contenedor   | Registra ingresos, egresos y asientos contables                            | Equipo interno |
| Módulo de reportes financieros     | Contenedor   | Genera balances y reportes personalizados                                  | Equipo interno |
| Módulo de integración de extractos | Contenedor   | Permite cargar extractos descargados desde el portal externo               | Equipo interno |
| Módulo de usuarios y roles         | Contenedor   | Maneja autenticación, permisos y perfiles de acceso                        | Administrador  |
| Base de datos contable             | Contenedor   | Almacena transacciones, usuarios, extractos y reportes                     | Equipo interno |


---
## Investigación complementaria

El C4 Model se ha consolidado como una metodología efectiva para documentar y comunicar arquitecturas de software en distintos niveles de detalle. Una buena práctica fundamental consiste en mantener la simplicidad de los diagramas, evitando sobrecargar con información innecesaria (Brown, 2019). Asimismo, se recomienda mantener una clara separación entre actores, sistemas, contenedores y componentes, lo que favorece la comprensión por parte de equipos técnicos y no técnicos.

Otra práctica clave es utilizar etiquetas claras en las relaciones, orientadas al negocio y no únicamente técnicas, de modo que el diagrama refleje el valor que aporta cada interacción. Además, se aconseja complementar los diagramas con tablas descriptivas que especifiquen los roles, responsabilidades y detalles de los componentes modelados.

Estas recomendaciones se aplicaron directamente en el presente taller: se priorizó la claridad en las relaciones, se delimitaron actores y sistemas externos en la vista de contexto, y se describieron los módulos internos en la vista de contenedores junto con una base de datos centralizada.

---

## Referencias

Brown, S. (2019). The C4 model for visualising software architecture. Recuperado el 7 de septiembre de 2025 de https://c4model.com/

Visual Paradigm. (s.f.). C4 model: Software architecture visualization. Recuperado el 7 de septiembre de 2025 de https://online.visual-paradigm.com/knowledge/c4-model/