The C4 model for visualising software architecture      

The C4 model for visualising software architecture
==================================================

Context, Containers, Components, and Code
-----------------------------------------

[1\. System context diagram](#SystemContextDiagram) [2\. Container diagram](#ContainerDiagram) [3\. Component diagram](#ComponentDiagram) [4\. Code diagram](#CodeDiagram)

[System landscape diagram](#SystemLandscapeDiagram) [Dynamic diagram](#DynamicDiagram) [Deployment diagram](#DeploymentDiagram)  
[Abstractions](#Abstractions) [Notation](#Notation) [Tooling](#Tooling) [FAQ](#FAQ) [Training](https://architectis.je) [Diagram review checklist](review) [Diagram bingo](bingo)

  
  

  

The C4 model is...

1\. A set of hierarchical abstractions (software systems, containers, components, and code).  
2\. A set of hierarchical diagrams (system context, containers, components, and code).  
3\. Notation independent.  
4\. Tooling independent.  

  

Uses and benefits

The C4 model is an easy to learn, developer friendly approach to software architecture diagramming. Good software architecture diagrams assist with communication inside/outside of software development/product teams, efficient onboarding of new staff, architecture reviews/evaluations, risk identification (e.g. [risk-storming](https://riskstorming.com)), threat modelling, etc.

Introduction
------------

Ask somebody in the building industry to visually communicate the architecture of a building and you'll be presented with site plans, floor plans, elevation views, cross-section views and detail drawings. In contrast, ask a software developer to communicate the software architecture of a software system using diagrams and you'll likely get a confused mess of boxes and lines ... inconsistent notation (colour coding, shapes, line styles, etc), ambiguous naming, unlabelled relationships, generic terminology, missing technology choices, mixed abstractions, etc.

[![A software architecture sketch](./img/sketch-1.jpg)](/bingo?diagram=../img/sketch-1.jpg)

[![A software architecture sketch](./img/sketch-2.jpg)](/bingo?diagram=../img/sketch-2.jpg)

[![A software architecture sketch](./img/sketch-3.jpg)](/bingo?diagram=../img/sketch-3.jpg)

[![A software architecture sketch](./img/sketch-4.jpg)](/bingo?diagram=../img/sketch-4.jpg)

As an industry, we do have the Unified Modeling Language (UML), ArchiMate and SysML, but asking whether these provide an effective way to communicate software architecture is often irrelevant because many teams have already thrown them out in favour of much simpler "boxes and lines" diagrams. Abandoning these modelling languages is one thing but, perhaps in the race for agility, many software development teams have lost the ability to communicate visually.

  
  

### Maps of your code

The C4 model was created as a way to help software development teams describe and communicate software architecture, both during up-front design sessions and when retrospectively documenting an existing codebase. It's a way to create maps of your code, at various levels of detail, in the same way you would use something like Google Maps to zoom in and out of an area you are interested in.
  

[![](https://static.structurizr.com/workspace/36141/diagrams/SystemContext.png)](https://static.structurizr.com/workspace/36141/diagrams/SystemContext.png)

Level 1: A **System Context** diagram provides a starting point, showing how the software system in scope fits into the world around it.

[![](https://static.structurizr.com/workspace/36141/diagrams/Containers.png)](https://static.structurizr.com/workspace/36141/diagrams/Containers.png)

Level 2: A **Container** diagram zooms into the software system in scope, showing the high-level technical building blocks.

[![](https://static.structurizr.com/workspace/36141/diagrams/Components.png)](https://static.structurizr.com/workspace/36141/diagrams/Components.png)

Level 3: A **Component** diagram zooms into an individual container, showing the components inside it.

![](./img/class-diagram.png)

Level 4: A **code** (e.g. UML class) diagram can be used to zoom into an individual component, showing how that component is implemented.

  
  

The C4 model is an "abstraction-first" approach to diagramming software architecture, based upon abstractions that reflect how software architects and developers think about and build software. The small set of abstractions and diagram types makes the C4 model easy to learn and use. Please note that you don't need to use all 4 levels of diagram; only those that add value - the System Context and Container diagrams are sufficient for many software development teams.

  

[![An overview of the C4 model](./img/c4-overview.png)](./img/c4-overview.png)

Different levels of zoom allow you to tell different stories to different audiences.

Hover your mouse over the diagram, find elements with a ![](img/zoom-in.svg), and double-click to zoom-in.

Abstractions
------------

In order to create these maps of your code, we first need a common set of abstractions to create a ubiquitous language that we can use to describe the static structure of a software system. A **software system** is made up of one or more **containers** (applications and data stores), each of which contains one or more **components**, which in turn are implemented by one or more **code elements** (classes, interfaces, objects, functions, etc). And **people** may use the software systems that we build.

  

[![Abstractions](./img/abstractions.png)](./img/abstractions.png)

  
  

### Person

A person represents one of the human users of your software system (e.g. actors, roles, personas, etc).

  

### Software System

A software system is the highest level of abstraction and describes something that delivers value to its users, whether they are human or not. This includes the software system you are modelling, and the other software systems upon which your software system depends (or vice versa).

Unfortunately the term "software system" is the hardest of the C4 model abstractions to define, and this isn't helped by the fact that each organisation will also have their own terminology for describing the same thing, typically using terms such as "application", "product", "service", etc. One way to think about it is that a software system is something a single software development team is building, owns, has responsibility for, and can see the internal implementation details of. Perhaps the code for that software system resides in a single source code repository, and anybody on the team is entitled to modify it. In many cases, the boundary of a software system will correspond to the boundary of a single team. It may also be the case that everything inside the boundary of a software system is deployed at the same time.

  

### Container (applications and data stores)

Not Docker! In the C4 model, a container represents an **application** or a **data store**. A container is something that needs to be running in order for the overall software system to work. In real terms, a container is something like:

*   **Server-side web application**: A Java EE web application running on Apache Tomcat, an ASP.NET MVC application running on Microsoft IIS, a Ruby on Rails application running on WEBrick, a Node.js application, etc.
*   **Client-side web application**: A JavaScript application running in a web browser using Angular, Backbone.JS, jQuery, etc.
*   **Client-side desktop application**: A Windows desktop application written using WPF, an OS X desktop application written using Objective-C, a cross-platform desktop application written using JavaFX, etc.
*   **Mobile app**: An Apple iOS app, an Android app, a Microsoft Windows Phone app, etc.
*   **Server-side console application**: A standalone (e.g. "public static void main") application, a batch process, etc.
*   **Serverless function**: A single serverless function (e.g. Amazon Lambda, Azure Function, etc).
*   **Database**: A schema or database in a relational database management system, document store, graph database, etc such as MySQL, Microsoft SQL Server, Oracle Database, MongoDB, Riak, Cassandra, Neo4j, etc.
*   **Blob or content store**: A blob store (e.g. Amazon S3, Microsoft Azure Blob Storage, etc) or content delivery network (e.g. Akamai, Amazon CloudFront, etc).
*   **File system**: A full local file system or a portion of a larger networked file system (e.g. SAN, NAS, etc).
*   **Shell script**: A single shell script written in Bash, etc.
*   **etc**

  

### Component

The word "component" is a hugely overloaded term in the software development industry, but in this context a component is a grouping of related functionality encapsulated behind a well-defined interface. If you're using a language like Java or C#, the simplest way to think of a component is that it's a collection of implementation classes behind an interface. Aspects such as how those components are packaged (e.g. one component vs many components per JAR file, DLL, shared library, etc) is a separate and orthogonal concern.

An important point to note here is that all components inside a container typically execute in the same process space. **In the C4 model, components are not separately deployable units.**

1\. System Context diagram [![Link](./img/glyphicons-basic-351-link.svg)](#SystemContextDiagram)
------------------------------------------------------------------------------------------------

[![A System Context diagram](https://static.structurizr.com/workspace/36141/diagrams/SystemContext.png)](https://static.structurizr.com/workspace/36141/diagrams/SystemContext.png)

[![Diagram key](https://static.structurizr.com/workspace/36141/diagrams/SystemContext-key.png)](https://static.structurizr.com/workspace/36141/diagrams/SystemContext-key.png)

A System Context diagram is a good starting point for diagramming and documenting a software system, allowing you to step back and see the big picture. Draw a diagram showing your system as a box in the centre, surrounded by its users and the other systems that it interacts with.

Detail isn't important here as this is your zoomed out view showing a big picture of the system landscape. The focus should be on people (actors, roles, personas, etc) and software systems rather than technologies, protocols and other low-level details. It's the sort of diagram that you could show to non-technical people.

**Scope**: A single software system.

**Primary elements**: The software system in scope.  
**Supporting elements**: People (e.g. users, actors, roles, or personas) and software systems (external dependencies) that are directly connected to the software system in scope. Typically these other software systems sit outside the scope or boundary of your own software system, and you don't have responsibility or ownership of them.

**Intended audience**: Everybody, both technical and non-technical people, inside and outside of the software development team.

**Recommended for most teams**: Yes.

2\. Container diagram [![Link](./img/glyphicons-basic-351-link.svg)](#ContainerDiagram)
---------------------------------------------------------------------------------------

[![A Container diagram](https://static.structurizr.com/workspace/36141/diagrams/Containers.png)](https://static.structurizr.com/workspace/36141/diagrams/Containers.png)

[![Diagram key](https://static.structurizr.com/workspace/36141/diagrams/Containers-key.png)](https://static.structurizr.com/workspace/36141/diagrams/Containers-key.png)

Once you understand how your system fits in to the overall IT environment, a really useful next step is to zoom-in to the system boundary with a Container diagram. A "container" is something like a server-side web application, single-page application, desktop application, mobile app, database schema, file system, etc. Essentially, a container is a separately runnable/deployable unit (e.g. a separate process space) that executes code or stores data.

The Container diagram shows the high-level shape of the software architecture and how responsibilities are distributed across it. It also shows the major technology choices and how the containers communicate with one another. It's a simple, high-level technology focussed diagram that is useful for software developers and support/operations staff alike.

**Scope**: A single software system.

**Primary elements**: Containers within the software system in scope.  
**Supporting elements**: People and software systems directly connected to the containers.

**Intended audience**: Technical people inside and outside of the software development team; including software architects, developers and operations/support staff.

**Recommended for most teams**: Yes.

**Notes**: This diagram says nothing about clustering, load balancers, replication, failover, etc because it will likely vary across different environments (e.g. production, staging, development, etc). This information is better captured via one or more [deployment diagrams](#DeploymentDiagram).

3\. Component diagram [![Link](./img/glyphicons-basic-351-link.svg)](#ComponentDiagram)
---------------------------------------------------------------------------------------

[![A Component diagram](https://static.structurizr.com/workspace/36141/diagrams/Components.png)](https://static.structurizr.com/workspace/36141/diagrams/Components.png)

[![Diagram key](https://static.structurizr.com/workspace/36141/diagrams/Components-key.png)](https://static.structurizr.com/workspace/36141/diagrams/Components-key.png)

Next you can zoom in and decompose each container further to identify the major structural building blocks and their interactions.

The Component diagram shows how a container is made up of a number of "components", what each of those components are, their responsibilities and the technology/implementation details.

**Scope**: A single container.

**Primary elements**: Components within the container in scope.  
**Supporting elements**: Containers (within the software system in scope) plus people and software systems directly connected to the components.

**Intended audience**: Software architects and developers.

**Recommended for most teams**: No, only create component diagrams if you feel they add value, and consider automating their creation for long-lived documentation.

4\. Code diagram[![Link](./img/glyphicons-basic-351-link.svg)](#CodeDiagram)
----------------------------------------------------------------------------

[![A UML class diagram](./img/class-diagram.png)](./img/class-diagram.png)

Finally, you can zoom in to each component to show how it is implemented as code; using UML class diagrams, entity relationship diagrams or similar.

This is an optional level of detail and is often available on-demand from tooling such as IDEs. Ideally this diagram would be automatically generated using tooling (e.g. an IDE or UML modelling tool), and you should consider showing only those attributes and methods that allow you to tell the story that you want to tell. This level of detail is not recommended for anything but the most important or complex components.

**Scope**: A single component.

**Primary elements**: Code elements (e.g. classes, interfaces, objects, functions, database tables, etc) within the component in scope.

**Intended audience**: Software architects and developers.

**Recommended for most teams**: No, particularly for long-lived documentation because most IDEs can generate this level of detail on demand.

System Landscape diagram [![Link](./img/glyphicons-basic-351-link.svg)](#SystemLandscapeDiagram)
------------------------------------------------------------------------------------------------

[![A System Landscape diagram](https://static.structurizr.com/workspace/28201/diagrams/SystemLandscape.png)](https://static.structurizr.com/workspace/28201/diagrams/SystemLandscape.png)

[![Diagram key](https://static.structurizr.com/workspace/28201/diagrams/SystemLandscape-key.png)](https://static.structurizr.com/workspace/28201/diagrams/SystemLandscape-key.png)

The C4 model provides a static view of a **single software system** but, in the real-world, software systems never live in isolation. For this reason, and particularly if you are responsible for a collection/portfolio of software systems, it's often useful to understand how all of these software systems fit together within a given enterprise, organisation, department, etc. Essentially this is a map of the software systems within the chosen scope, with a C4 drill-down for each software system of interest.

From a practical perspective, a system landscape diagram is really just a system context diagram without a specific focus on a particular software system.

**Scope**: An enterprise/organisation/department/etc.

**Primary elements**: People and software systems related to the chosen scope.

**Intended audience**: Technical and non-technical people, inside and outside of the software development team.

Dynamic diagram [![Link](./img/glyphicons-basic-351-link.svg)](#DynamicDiagram)
-------------------------------------------------------------------------------

[![A dynamic diagram](https://static.structurizr.com/workspace/36141/diagrams/SignIn.png)](https://static.structurizr.com/workspace/36141/diagrams/SignIn.png)

[![Diagram key](https://static.structurizr.com/workspace/36141/diagrams/SignIn-key.png)](https://static.structurizr.com/workspace/36141/diagrams/SignIn-key.png)

A dynamic diagram can be useful when you want to show how elements in the static model collaborate at runtime to implement a user story, use case, feature, etc. This dynamic diagram is based upon a [UML communication diagram](https://en.wikipedia.org/wiki/Communication_diagram) (previously known as a "UML collaboration diagram"). It is similar to a [UML sequence diagram](https://en.wikipedia.org/wiki/Sequence_diagram) although it allows a free-form arrangement of diagram elements with numbered interactions to indicate ordering.

**Scope**: A particular feature, story, use case, etc.

**Primary and supporting elements**: Your choice - you can show software systems, containers, or components interacting at runtime.

**Intended audience**: Technical and non-technical people, inside and outside of the software development team.

**Notes**: Feel free to use a UML sequence diagram if you prefer that visual style.

Deployment diagram [![Link](./img/glyphicons-basic-351-link.svg)](#DeploymentDiagram)
-------------------------------------------------------------------------------------

[![A deployment diagram](https://static.structurizr.com/workspace/36141/diagrams/LiveDeployment.png)](https://static.structurizr.com/workspace/36141/diagrams/LiveDeployment.png)

[![Diagram key](https://static.structurizr.com/workspace/36141/diagrams/LiveDeployment-key.png)](https://static.structurizr.com/workspace/36141/diagrams/LiveDeployment-key.png)

[![An example AWS deployment diagram](https://static.structurizr.com/workspace/54915/diagrams/AmazonWebServicesDeployment.png)](https://static.structurizr.com/workspace/54915/diagrams/AmazonWebServicesDeployment.png)

A deployment diagram allows you to illustrate how instances of software systems and/or containers in the static model are deployed on to the infrastructure within a given **deployment environment** (e.g. production, staging, development, etc). It's based upon a [UML deployment diagram](https://en.wikipedia.org/wiki/Deployment_diagram).

A **deployment node** represents where an instance of a software system/container is running; perhaps physical infrastructure (e.g. a physical server or device), virtualised infrastructure (e.g. IaaS, PaaS, a virtual machine), containerised infrastructure (e.g. a Docker container), an execution environment (e.g. a database server, Java EE web/application server, Microsoft IIS), etc. Deployment nodes can be nested.

You may also want to include **infrastructure nodes** such as DNS services, load balancers, firewalls, etc.

Feel free to use icons provided by Amazon Web Services, Azure, etc to complement your deployment diagrams ... just make sure any icons you use are included in your diagram key/legend.

**Scope**: One or more software systems within a single deployment environment (e.g. production, staging, development, etc).

**Primary elements**: Deployment nodes, software system instances, and container instances.  
**Supporting elements**: Infrastructure nodes used in the deployment of the software system.

**Intended audience**: Technical people inside and outside of the software development team; including software architects, developers, infrastructure architects, and operations/support staff.

Notation
--------

The C4 model is **notation independent**, and doesn't prescribe any particular notation. As a starting point though, a simple notation that works well on whiteboards, paper, sticky notes, index cards and a variety of diagraming tools is as follows.

[![Person](./img/notation-person.png)](./img/notation-person.png)

Person

[![Software System](./img/notation-software-system.png)](./img/notation-software-system.png)

Software System

[![Container](./img/notation-container.png)](./img/notation-container.png)

Container

[![Component](./img/notation-component.png)](./img/notation-component.png)

Component

[![Relationship](./img/notation-relationship.png)](./img/notation-relationship.png)

Relationship

You can then use colour and shapes to supplement the diagram, either to add additional information or simply to make the diagram more aesthetically pleasing.

### C4 and UML

Although the example diagrams above are created using a "boxes and lines" notation, the core diagrams can be illustrated using UML with the appropriate use of packages, components and stereotypes. The resulting UML diagrams do tend to lack the same degree of descriptive text though, because adding such text isn't possible (or easy) with some UML tools.

Here are three examples of a System Context, Container and Component diagram for comparison.

[![A system context diagram](./img/spring-petclinic-system-context.png)](./img/spring-petclinic-system-context.png)

[![A container diagram](./img/spring-petclinic-containers.png)](./img/spring-petclinic-containers.png)

[![A component diagram](./img/spring-petclinic-components.png)](./img/spring-petclinic-components.png)

System Context diagram

Container diagram

Component diagram

[![A system context diagram](./img/spring-petclinic-system-context-plantuml.png)](./img/spring-petclinic-system-context-plantuml.png)

[![A container diagram](./img/spring-petclinic-containers-plantuml.png)](./img/spring-petclinic-containers-plantuml.png)

[![A component diagram](./img/spring-petclinic-components-plantuml.png)](./img/spring-petclinic-components-plantuml.png)

[![A system context diagram](./img/spring-petclinic-system-context-staruml.png)](./img/spring-petclinic-system-context-staruml.png)

[![A container diagram](./img/spring-petclinic-containers-staruml.png)](./img/spring-petclinic-containers-staruml.png)

[![A component diagram](./img/spring-petclinic-components-staruml.png)](./img/spring-petclinic-components-staruml.png)

### C4 and ArchiMate

See [C4 Model, Architecture Viewpoint and Archi 4.7](https://www.archimatetool.com/blog/2020/04/18/c4-model-architecture-viewpoint-and-archi-4-7/) for details of how to create C4 model diagrams with ArchiMate.

  
  

### Diagram key/legend

Any notation used should be as self-describing as possible, but **all diagrams should have a key/legend** to make the notation explicit. This applies to diagrams created with notations such as UML, ArchiMate and SysML too, as not everybody will know the notation being used.

[![Diagram key](https://static.structurizr.com/workspace/36141/diagrams/Containers-key.png)](https://static.structurizr.com/workspace/36141/diagrams/Containers-key.png)

  
  

### Notation, notation, notation

Although the C4 model is an abstraction-first approach and notation independent, you still need to ensure that your diagram notation makes sense, and that the diagrams are comprehensible. A good way to think about this is to ask yourself whether each diagram can stand alone, and be (mostly) understood without a narrative. You can use this short [software architecture diagram review checklist](review) to help. And here are some recommendations related to notation.

#### Diagrams

*   Every diagram should have a title describing the diagram type and scope (e.g. "System Context diagram for My Software System").
*   Every diagram should have a key/legend explaining the notation being used (e.g. shapes, colours, border styles, line types, arrow heads, etc).
*   Acronyms and abbreviations (business/domain or technology) should be understandable by all audiences, or explained in the diagram key/legend.

#### Elements

*   The type of every element should be explicitly specified (e.g. Person, Software System, Container or Component).
*   Every element should have a short description, to provide an "at a glance" view of key responsibilities.
*   Every container and component should have a technology explicitly specified.

#### Relationships

*   Every line should represent a unidirectional relationship.
*   Every line should be labelled, the label being consistent with the direction and intent of the relationship (e.g. dependency or data flow). Try to be as specific as possible with the label, ideally avoiding single words like, "Uses".
*   Relationships between containers (typically these represent inter-process communication) should have a technology/protocol explicitly labelled.

  
  

### Alternative visualisations

Finally, don't feel that you need to always use a traditional "boxes and arrows" diagram. Although this is usually the default approach, there are other, often interactive, visualisations that can be used to show the same C4 model abstractions in very different ways.

[![](./img/alternative-1.png)](https://structurizr.com/dsl?example=microservices)

Traditional "boxes and arrows" diagrams are the default approach for documentation and presentations.

[![](./img/alternative-2.png)](https://structurizr.com/dsl?example=microservices&renderer=graph)

A D3.js force-directed graph is a very concise way to visualise larger software architectures, also providing an easy way to explore dependencies.

[![](./img/alternative-3.png)](https://structurizr.com/dsl?example=microservices&renderer=ilograph)

Ilograph's interactive diagrams provide a way to selectively zoom in and out, allowing you to explore your entire software architecture model.

Tooling
-------

For design sessions, you might find a whiteboard or flip chart paper better for collaboration, and iterating quickly. For long-lived documentation, there are a number of tools can help create software architecture diagrams based upon the C4 model.

Don't forget to ask yourself some questions when looking at tooling, to understand the features you need. Who are the diagram authors, and how technical are they? A "drag and drop" UI vs "diagrams as code"? Data stored in git next to your source code vs stored in the tool/cloud service? Closed vs open data format? Interactive vs static diagrams? Free vs paid vs open source? Short-lived vs long-lived documentation? Team only diagramming vs enterprise-wide modelling? Who is the diagram audience, and how would they access the diagrams/documentation?

  

 Static diagrams

(e.g. system context, container, and component diagrams)

 Dynamic diagrams

(e.g. collaboration or sequence diagrams)

 Deployment diagrams

(e.g. diagrams showing deployment and infrastructure concerns)

 Open source

(free, fork/customize, etc)

 Diagrams and models as code

(for easy version control and integration into build pipelines/other tools)

 Reuse elements across multiple diagrams

(to keep multiple diagrams in sync automatically when you rename elements)

Recommended

 Rendering tool independent

(to render diagrams with different tools or visualisation formats such as [diagrams, graphs, etc](#AlternativeVisualisations))

[Archi](https://www.archimatetool.com/blog/2020/04/18/c4-model-architecture-viewpoint-and-archi-4-7/)

[Archinsight](https://github.com/lonely-lockley/archinsight)

[Archipeg](https://www.archipeg.com/learn/c4-model-v1-metamodel)

[Astah](https://github.com/ChangeVision/astah-c4model-plugin)

[C4-PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML)

[c4builder](https://adrianvlupu.github.io/C4-Builder)

[C4InterFlow](https://github.com/SlavaVedernikov/C4InterFlow)

[C4Sharp](https://github.com/8T4/c4sharp)

[Carbide](https://carbide.dev)

[CUE4Puml4C4](https://owulveryck.github.io/cue4puml4c4/)

[Diagrams](https://diagrams.mingrammer.com/docs/nodes/c4)

[diagrams.net](https://www.diagrams.net/blog/c4-modelling)

[Excalidraw](https://libraries.excalidraw.com/#dmitry-burnyshev-c4-architecture)

[Figma](https://www.figma.com/templates/c4-model-examples/)

[Gaphor](https://gaphor.org)

[Gliffy](https://www.gliffy.com/blog/c4-model)

[IcePanel](https://icepanel.io/c4-model)

[Keadex Mina](https://keadex.dev/en/projects/keadex-mina)

[Lucidchart](https://www.lucidchart.com/pages/templates/c-4-model-example)

[Microsoft Visio](https://github.com/pihalve/c4model-visio-stencil)

[Mermaid](https://mermaid.js.org/syntax/c4.html)

[Miro](https://miro.com/miroverse/c4-architecture/)

[Model](https://github.com/goadesign/model)

[MooD](https://supportportal.moodinternational.com/hc/en-us/articles/360015465100-MooD-and-the-C4-model)

[OmniGraffle](https://stenciltown.omnigroup.com/stencils/c4/)

[Overarch](https://github.com/soulspace-org/overarch)

[pumla](https://github.com/DrMarkusVoss/pumla/blob/main/test/examples/C4example/pumlaC4Example.md)

[PyStructurizr](https://github.com/nielsvanspauwen/pystructurizr)

[Sparx Enterprise Architect](http://www.sparxsystems.eu/c4/)

[RDB modeling](https://rdbmodel.github.io)

[Structurizr](https://structurizr.org)

[Visual Paradigm](https://online.visual-paradigm.com/diagrams/features/c4-model-tool/)

[yEd](https://github.com/Ferhat67/C4-yEd)

$('#toolingOpenSourceFilter, #toolingModelBasedFilter, #toolingAsCodeFilter, #toolingRenderingToolIndependentFilter, #toolingStaticDiagramsFilter, #toolingDynamicDiagramsFilter, #toolingDeploymentDiagramsFilter').change(function() { filterToolingOptions(); }); function filterToolingOptions() { var classes = ''; if ($('#toolingOpenSourceFilter').is(":checked")) { classes = classes + '.toolingOpenSource'; } if ($('#toolingModelBasedFilter').is(":checked")) { classes = classes + '.toolingModelBased'; } if ($('#toolingAsCodeFilter').is(":checked")) { classes = classes + '.toolingAsCode'; } if ($('#toolingRenderingToolIndependentFilter').is(":checked")) { classes = classes + '.toolingRenderingToolIndependent'; } if ($('#toolingStaticDiagramsFilter').is(":checked")) { classes = classes + '.toolingStaticDiagrams'; } if ($('#toolingDynamicDiagramsFilter').is(":checked")) { classes = classes + '.toolingDynamicDiagrams'; } if ($('#toolingDeploymentDiagramsFilter').is(":checked")) { classes = classes + '.toolingDeploymentDiagrams'; } if (classes.length === 0) { $('.toolingOption').removeClass('faded'); } else { $('.toolingOption').addClass('faded'); $('.toolingOption').filter(classes).removeClass('faded'); } } filterToolingOptions();

Frequently asked questions
--------------------------

#### What's the background behind the C4 model?

The C4 model was created by [Simon Brown](http://simonbrown.je), who started teaching software architecture, while working as a software developer/architect. Part of Simon's training course was a design exercise, where groups of people were given some requirements, asked to do some design, and to draw some diagrams to express that design.

Although this was a design focussed exercise, the wide variety of diagrams made it evident that the visualisation of ideas was a skill that most people sorely lacked. The C4 model is essentially a formalisation of how Simon used to visualise software architecture, which has evolved over the years.

Exact dates are hard to pin down, but the roots of the C4 model can be traced back to somewhere in the region of 2006-2009, the diagram types ("context", "containers", "components", "classes") were named in early 2010, with the "C4" name being first used in early 2011. The fourth diagram type was renamed from "classes" to "code" during 2015-2016.

#### What's the inspiration behind the C4 model?

The C4 model was created during a time where teams, influenced by the agile movement, were less than enthusiastic about using the [Unified Modeling Language](https://en.wikipedia.org/wiki/Unified_Modeling_Language) (UML) to document software architecture, if they were creating diagrams at all. Despite this, the C4 model was inspired by UML and the [4+1 model for software architecture](https://en.wikipedia.org/wiki/4%2B1_architectural_view_model). In summary, you can think of the C4 model as a simplified version of the underlying concepts, designed to (1) make it easier for software developers to describe and understand how a software system works and (2) to minimise the gap between the software architecture model/description and the source code.

#### Isn't the C4 model a step backwards? Why are you reinventing UML? Why not just use UML?

Whether you see the C4 model as a step forwards or a step backwards depends upon where you are. If you're using UML (or SysML, ArchiMate, etc) and it's working for you, stick with it. Unfortunately, UML usage seems to be in decline, and many teams have reverted to using ad hoc boxes and lines diagrams once again. Given that many of those teams don't want to use UML (for various reasons), the C4 model helps introduce some structure and discipline into the way software architecture is communicated. For many teams, the C4 model is sufficient. And for others, perhaps it's a stepping stone to UML.

#### How many people use the C4 model?

The honest answer is that nobody knows. Simon has personally taught the C4 model to somewhere over 10,000 people in more than 30 countries; with conference talks, videos, books and articles reaching many more than this. Other people are also teaching, speaking and writing about the C4 model too. It's definitely being used though, in organisations ranging from startups to global household names.

#### Why "container"?

Terms like "process", "application", "app", "server", "deployable unit", etc all have associated implications, so the name "container" was chosen as a generic way to describe something in which components live. From one perspective, it's unfortunate that containerisation has become popular, because many software developers now associate the term "container" with Docker. From another perspective though, there is sometimes a nice parity between a container in the C4 model and an infrastructure (e.g. Docker) container.

While many teams successfully use the C4 model as is, feel free to change the terminology if needed.

#### Can we change the terminology?

This terminology (context, containers, components and code) works for many organisations and many types of software. However, sometimes an organisation will have an existing terminology that people are already familiar with. Or perhaps "components" and "classes" don't easily map on to the technology being used (e.g. functional languages often use the terms "module" and "function").

Feel free to modify the terminology that you use to describe software architecture at different levels of abstraction. Just make sure that everybody explicitly understands it.

#### How do you model microservices and serverless?

Broadly speaking, there are two options for diagramming microservices when using the C4 model, although it depends what you mean by "microservice".

**Approach 1: Each "microservice" is owned by a separate team**  
If your software system has a dependency upon a number of microservices that are outside of your control (e.g. they are owned and/or operated by a separate team), model these microservices as external software systems, that you can't see inside of.

**Approach 2: A single team owns multiple "microservices"**

Imagine that you have an API app (e.g. Spring Boot, ASP.NET MVC, etc) that reads/writes to a relational database schema. Regardless of whether you consider the term "microservice" to refer to just the API app, or the combination of the API app and database schema ... if the microservices are a part of a software system that you are building (i.e. you own them), model every deployable thing as a container. In other words, you'd show two containers: the API app, and the database schema. Feel free to draw a box around these two containers to indicate they are related/grouped.

The same is true for serverless functions/lambdas/etc; treat them as software systems or containers based upon ownership.

#### How do you diagram large and complex software systems?

Even with a relatively small software system, it's tempting to try and include the entire story on a single diagram. For example, if you have a web application, it seems logical to create a single component diagram that shows all of the components that make up that web application. Unless your software system really is that small, you're likely to run out of room on the diagram canvas or find it difficult to discover a layout that isn't cluttered by a myriad of overlapping lines. Using a larger diagram canvas can sometimes help, but large diagrams are usually hard to interpret and comprehend because the cognitive load is too high. And if nobody understands the diagram, nobody is going to look at it.

Instead, don't be afraid to split that single complex diagram into a larger number of simpler diagrams, each with a specific focus around a business area, functional area, functional grouping, bounded context, use case, user interaction, feature set, etc. The key is to ensure that each of the separate diagrams tells a different part of the same overall story, at the same level of abstraction. You can also use an [alternative visualisation](#AlternativeVisualisations).

#### Will the diagrams become outdated quickly?

Due to the hierarchical nature of the C4 model, each diagram will change at a different rate.

*   **System Context diagram**: In most cases, the system context diagram will change very slowly, as this describes the landscape that the software system is operating within.
*   **Container diagram**: Unless you're building a software system that makes heavy use of microservices or serverless lambdas/functions/etc, the container diagram will also change relatively slowly.
*   **Component diagram**: For any software system under active development, the component diagrams may change frequently as the team adds, removes or restructures the code into cohesive components. Automating the generation of this level of detail with tooling can help.
*   **Code diagram**: The level 4 code (e.g. class) diagrams will potentially become outdated very quickly if the codebase is under active development. For this reason, the recommendation is to (1) not create them at all or (2) generate them on-demand using tooling such as your IDE.

#### Why doesn't the C4 model cover business processes, workflows, state machines, domain models, data models, etc?

The focus of the C4 model is the static structures that make up a software system, at different levels of abstraction. If you need to describe other aspects, feel free to supplement the C4 diagrams with UML diagrams, BPML diagrams, ArchiMate diagrams, entity relationship diagrams, etc.

#### The C4 model vs UML, ArchiMate and SysML?

Although existing notations such as UML, ArchiMate and SysML already exist, many software development teams don't seem to use them. Often this is because teams don't know these notations well enough, perceive them to be too complicated, think they are not compatible with agile approaches or don't have the required tooling.

If you are already successfully using one of these notations to communicate software architecture and it's working, stick with it. If not, try the C4 model. And don't be afraid to supplement the C4 diagrams with UML state diagrams, timing diagrams, etc if you need to.

#### Can we combine C4 and arc42?

Yes, many teams do, and the C4 model is compatible with the [arc42 documentation template](http://arc42.org) as follows.

*   Context and Scope => System Context diagram
*   Building Block View (level 1) => Container diagram
*   Building Block View (level 2) => Component diagram
*   Building Block View (level 3) => Code (e.g. class) diagram

#### Does the C4 model imply a design process or team structure?

A common misconception is that a team's design process should follow the levels in the C4 model hierarchy, perhaps with different people on the team being responsible for different levels of diagrams. For example, a business analyst creates the system context diagram, the architect creates the container diagram, while the developers look after the remaining levels of detail.

Although you can certainly use the C4 model in this way, this is not the intended or recommended usage pattern. The C4 model is just a way to describe a software system, from different levels of abstraction, and it implies nothing about the process of delivering software.

#### Using C4 to describe libraries, frameworks and SDKs?

The C4 model is really designed to model a software system, at various levels of abstraction. To document a library, framework or SDK, you might be better off using something like UML. Alternatively, you could use the C4 model to describe a usage example of your framework, library or SDK; perhaps using colour coding to signify which parts of the software system are bespoke vs those provided for you.

#### Web applications; one container or two?

If you're building a server-side web application (e.g. Spring MVC, ASP.NET, Ruby on Rails, Django, etc) that is predominantly generating static HTML content, then that's a single container. If there's a significant quantity of JavaScript being delivered by the server-side web application (e.g. a single-page application built using Angular), then that's two containers. [Here's an example](https://static.structurizr.com/workspace/36141/diagrams/Containers.png).

Although, at deployment time, the server-side web application includes both the server-side and client-side code, treating the client and server as two separate containers makes it explicit that these are two separate process spaces, communicating via an inter-process/remote communication mechanism (e.g. JSON/HTTPS). It also provides a basis for zooming in to each container separately to show the components inside them.

#### Should the lines represent dependencies or data flow?

This is your choice. Sometimes diagrams work better showing dependency relationships (e.g. uses, reads from, etc), and sometimes data flow (e.g. customer update events) works better. Whichever you choose, make sure that the description of the line matches the direction of the arrow.

It's also worth remembering that most relationships can be expressed either way, and the more explicit you can be, the better. For example, describing a relationship as "sends customer update events to" can be more descriptive than simply "customer update events".

#### Is a Java JAR, C# assembly, DLL, module, etc a container?

Typically not. A container is a runtime construct, like an application; whereas Java JAR files, C# assemblies, DLLs, modules, etc are used to organise the code within those applications.

#### Is a Java JAR, C# assembly, DLL, module, package, namespace, folder etc a component?

Perhaps but, again, typically not. The C4 model is about showing the runtime units (containers) and how functionality is partitioned across them (components), rather than organisational units such as Java JAR files, C# assemblies, DLLs, modules, packages, namespaces or folder structures.

Of course, there may be a one-to-one mapping between these constructs and a component; e.g. if you're building a hexagonal architecture, you may create a single Java JAR file or C# assembly per component. On the other hand, a single component might be implemented using code from a number of JAR files, which is typically what happens when you start to consider third-party frameworks/libraries, and how they become embedded in your codebase.

#### Should you include message buses, API gateways, service meshes, etc?

If you have two services, A and B, that communicate by sending a message via a message bus (irrespective of topics, queues, p2p, pub/sub, etc) or another intermediary (e.g. an API gateway or service mesh), you have a couple of options. The first option is to show service A sending a message to the intermediary, and the intermediary subsequently forwarding that message to service B. While accurate, the "hub and spoke" nature of the diagram tends to obscure the notion that there's coupling between the message producer and consumer.

The other approach is to omit the intermediary, and instead use notation (e.g. a textual description, colour coding, line style, etc) to signify that the interaction between service A and B happens via an intermediary. This approach tends to result in diagrams that tell a clearer story.

#### Should data storage services be shown as software systems or containers?

A frequently asked question is whether services like Amazon S3, Amazon RDS, Azure SQL Database, content delivery networks, etc should be shown as software systems or containers. After all, these are external services that most of us don't own or run ourselves.

If you're building a software system that is using Amazon S3 for storing data, it's true that you don't run S3 yourself, but you do have ownership and responsibility for the buckets you are using. Similarly with Amazon RDS, you have (more or less) complete control over any database schemas that you create. For this reason, treat them as containers because they are an integral part of your software architecture, although they are hosted elsewhere.

#### Is the C4 model universally applicable?

The C4 model was designed to help describe, document, and diagram custom-built, bespoke software systems. From this perspective, the C4 model can be used to describe a variety of software architectures (monolithic or distributed), built in a variety of programming languages, deployed on a variety of platforms (on-premises or cloud).

Solutions that are perhaps less suited to the C4 model include embedded systems/firmware, and solutions that rely on heavy customization rather than bespoke development (e.g. SAP and Salesforce). Even with these solutions, you still may find the System Context and Container diagrams useful.

More information
----------------

The following resources are recommended if you're looking for more information about visualising software architecture and the C4 model.

[![The C4 model for visualising software architecture](./img/book.png)](https://leanpub.com/visualising-software-architecture)

This is Simon Brown's [The C4 model for visualising software architecture](https://leanpub.com/visualising-software-architecture) ebook, which is available to purchase from Leanpub as an ebook in PDF, EPUB and MOBI formats. It's a short guide to visualising your software architecture with the C4 model.

**Visualising software architecture with the C4 model**  
Agile on the Beach 2019 - Falmouth, England - July 2019

**Diagrams as code 2.0**  
JBCNConf - Barcelona, Spain - July 2022

And here are some of the significant resources that reference the C4 model:

*   [InfoQ: The C4 model for software architecture](https://www.infoq.com/articles/C4-architecture-model)
*   [InfoQ: O modelo C4 de documentação para Arquitetura de Software](https://www.infoq.com/br/articles/C4-architecture-model)
*   [InfoQ: 用于软件架构的C4模型](https://www.infoq.com/cn/articles/C4-architecture-model)
*   [InfoQ: ソフトウェアアーキテクチャのためのC4モデル](https://www.infoq.com/jp/articles/C4-architecture-model)
*   [Spotify Engineering: Software Visualization - Challenge, Accepted](https://engineering.atspotify.com/2022/07/software-visualization-challenge-accepted/)
*   [The Engineering Leader: A Moment on C4 Architectural Design with Amar Mehan](https://www.theengineeringleader.com/1946930/10648894-a-moment-on-c4-architectural-design-with-amar-mehan)
*   [Open Agile Architecture™, a Standard of The Open Group](https://publications.opengroup.org/c208)
*   [Agile Architecture Modeling using the ArchiMate® Language](https://publications.opengroup.org/g20e)
*   [Fundamentals of Software Architecture](https://www.oreilly.com/library/view/fundamentals-of-software/9781492043447/) (Mark Richards, Neal Ford)
*   [Design It!](https://pragprog.com/titles/mkdsa/design-it/) (Michael Keeling)
*   [Software Architecture with Spring 5.0](https://www.packtpub.com/free-ebook/software-architecture-with-spring-5-0/9781788992992) (René Enríquez, Alberto Salazar)
*   [Software Architecture](https://leanpub.com/software-architecture) (Cesare Pautasso)
*   [Martin Fowler: Building Infrastructure Platforms - Communicate your technical vision](https://martinfowler.com/articles/building-infrastructure-platform.html#CommunicateYourTechnicalVision) (Poppy Rowse and Chris Shepherd)
*   [Wikipedia](https://en.wikipedia.org/wiki/C4_model)

The Structurizr DSL (designed to support the C4 model) has also appeared on the [ThoughtWorks Tech Radar - Techniques - Diagrams as code](https://www.thoughtworks.com/radar/techniques/diagrams-as-code).

[![Creative Commons License](https://i.creativecommons.org/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)  
This website and example diagrams are licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

![Simon Brown](./img/simonbrown.jpg)  
The C4 model and this website were created by Simon Brown - [@simonbrown](https://twitter.com/simonbrown) | [simonbrown.je](http://simonbrown.je)

![Structurizr](./img/structurizr.png)  
The example diagrams were created with Structurizr - [About](https://structurizr.com) | [Diagram source](https://structurizr.com/dsl?example=big-bank-plc)

