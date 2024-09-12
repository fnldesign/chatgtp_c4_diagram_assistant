Blog - Create C4 models and diagrams               

Create C4 models and diagrams
=============================

The C4 modelling is used to describe and define architectures in an abstract and simple way. Designed by Simon Brown, C4 is a different way to approach modelling software development which focuses on four c’s: context (people), containers, components, and code.  
![An example C4 system container diagram](drawio_using_c4_model_c4-container.png)

draw.io provides you with a C4 shape library with the shapes you need to create all of these diagrams, including extensive UML shape libraries for the detailed diagrams typically used at the code level. Labels are added to these shapes using metadata.

C4 model diagrams capture the three levels of design that are needed when crafting any general software or business system. The first diagram is a high-level abstract overview of your system, stepping into more detail at each level, with the fourth level typically reserved for implementation details.

Shapes used in C4 notation
--------------------------

The C4 notation is very simple compared to other modelling notations. It is recommended that on any C4 diagram, you include a legend of which shapes are used to represent each element.

*   Person
*   Software system
*   Container
*   Component
*   Relationship - use the standard connectors in draw.io

### C4 shape library in draw.io

The following shapes are available in the C4 shape library.

![Shapes available in the C4 shape library in draw.io](drawio_using_c4_model_c4-shape-library.png)

**Enable the C4 shape library**

1.  Click _More Shapes_ in the left panel.
2.  Select the _C4_ shape library in the _Software_ section, then click _Apply_.

Alternatively, create a new C4 diagram immediately in our free online editor using the following link: [https://app.diagrams.net/?libs=c4](https://app.diagrams.net/?libs=c4)

**Tip:** To show systems that are outside the scope of your software, change their style in the format panel.

**Edit the C4 shape**

1.  Once you’ve added the shape to the drawing canvas, double click on it to open the shape’s metadata.
2.  Enter the details as indicated in the text fields, then click _Apply_.

![Shapes available in the C4 shape library in draw.io](drawio_using_c4_model_c4-component-metadata.png)

When you hover over each shape in the draw.io editor or viewer, a tooltip will show you this metadata.

![Shapes available in the C4 shape library in draw.io](drawio_using_c4_model_c4-hover-metadata.png)

C4 system context diagram
-------------------------

This top-level diagram is also the most abstract. C4 system context diagrams show the big picture, how users interact with your software system as a whole, and how your software fits together with other existing software systems. These are good diagrams for showing what is in the scope of your software project, and what lies outside that scope.

![An example C4 system context diagram](drawio_using_c4_model_c4-context.png)

[Open this example context diagram in the draw.io editor](https://app.diagrams.net/?lightbox=0&highlight=0000ff&edit=_blank&layers=1&nav=1&title=#Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fjgraph%2Fdrawio-diagrams%2Fmaster%2Fblog%2FC4.drawio)

C4 container diagram
--------------------

Representing the high-level technology choices, C4 container diagrams show the big elements in your software - web and desktop applications, mobile apps, databases, file systems, etc. A container is a standalone piece of software in your system that executes code or stores data. This diagram is a useful design document for software engineers and IT support.

[![An example C4 system container diagram](/assets/img/blog/c4-container.png)](https://viewer.diagrams.net/?lightbox=1&highlight=0000ff&edit=_blank&layers=1&page=1&nav=1&title=#Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fjgraph%2Fdrawio-diagrams%2Fmaster%2Fblog%2FC4.drawio)

[Open this example container diagram in the draw.io editor](https://app.diagrams.net/?lightbox=0&highlight=0000ff&edit=_blank&layers=1&page=1&nav=1&title=#Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fjgraph%2Fdrawio-diagrams%2Fmaster%2Fblog%2FC4.drawio)

C4 component diagram
--------------------

Simpler than their [UML counterparts](/blog/component-diagrams.html), C4 component diagrams provide more detail about each container in your system, showing what elements or components they are made up of and how they interact, occasionally with implementation details for software architects and developers.

[![An example C4 component diagram](/assets/img/blog/c4-component.png)](https://viewer.diagrams.net/?lightbox=1&highlight=0000ff&edit=_blank&layers=1&page=2&nav=1&title=#Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fjgraph%2Fdrawio-diagrams%2Fmaster%2Fblog%2FC4.drawio)

[Open this example component diagram in the draw.io editor](https://app.diagrams.net/?lightbox=0&highlight=0000ff&edit=_blank&layers=1&page=2&nav=1&title=#Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fjgraph%2Fdrawio-diagrams%2Fmaster%2Fblog%2FC4.drawio)

C4 class diagram (UML)
----------------------

Representing the actual implementation details, UML class diagrams, entity relationship diagrams and others from the UML set of diagrams are used in the final level of C4 modelling. Often, these diagrams can be automatically created from code in a development environment, or described quickly in text form using systems like PlantUML (which can be imported into draw.io).

[![An example C4 class diagram in UML](/assets/img/blog/c4-class-example.png)](https://viewer.diagrams.net/?lightbox=1&highlight=0000ff&edit=_blank&layers=1&page=3&nav=1&title=#Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fjgraph%2Fdrawio-diagrams%2Fmaster%2Fblog%2FC4.drawio)

[Open this example UML class diagram in the draw.io editor](https://app.diagrams.net/?lightbox=0&highlight=0000ff&edit=_blank&layers=1&page=3&nav=1&title=#Uhttps%3A%2F%2Fraw.githubusercontent.com%2Fjgraph%2Fdrawio-diagrams%2Fmaster%2Fblog%2FC4.drawio)

Extend your C4 models in draw.io
--------------------------------

Several features in draw.io make it more convenient to view layered diagrams such as those used in C4 models, and extend them with supplementary diagrams.

*   **[Multi-page diagrams](/blog/multiple-page-diagrams.html):** Keep all of the related diagrams together in one file.
*   **Links between pages:** Add a link to each system, container and component shape which jumps to the appropriate page in your diagram.
*   **UML, infrastructure and other shape libraries:** If you want to go into more detail at the implementation level with UML or [network diagrams](/blog/network-diagrams.html), or supporting diagrams such as [threat modelling](/blog/threat-modelling.html) you can use the many other shape libraries available in draw.io.
*   **[Use smart labels and placeholders](/blog/placeholders.html):** For advanced diagrammers, you can define placeholder styles that can automatically style shapes as in-scope or out-of-scope.

Follow us on [GitHub](https://github.com/jgraph/drawio), [Twitter](https://twitter.com/drawio), [Facebook](https://www.facebook.com/drawioapp/).



#### Help and advice

*   [Getting started](/doc/)
*   [Features](/features.html)
*   [Integrations](/integrations.html)
*   [Example diagrams](/example-diagrams.html)
*   [FAQs](/doc/faq/)

#### About us

*   [About draw.io](/about.html)
*   [GitHub](https://github.com/jgraph)
*   [Mastodon](https://hostux.social/@drawio)
*   [Legal & Privacy](/trust/)

#### Search the site

Search

© 2005-2023 JGraph Ltd, Artisans' House, 7 Queensbridge, NN4 7BF, Northampton, England. Company #04051179.