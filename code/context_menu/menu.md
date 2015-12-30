### Content menu registry

Context menu registry was introduced to prevent multiple implementation of the context menu. There is only one context menu region defined for the framework therefore registry should disable/hide previous one to show a new one
plus on click disable applicable for all implementations.

Registry know nothing about context menu view. It is simple wrapper to attach/detach region

![mime-type:application/vnd.umlsync.json] (http://umlsync.org/github?path=/code/context_menu/context_menu_registry_classes.umlsync "")

### Context menu actions load

Diagram context menu handler is pair of {"title", "command"} for example {title: "Remove", command: "diagram:element:remove"}.
For each diagram type we have to load corresponding command handlers by path: 'Modules/Diagrammer/Menus/' + subtype, where subtype is diagram subtype.

In scope of the command context the following fields are expected:

_context_ : {

_view_ - marionette view of the clicked element (optional, uses for fields and 

_element_ - uml element view

_diagram_ - uml diagram view

},

_subtype_ :  - optional subtype description [connector|connector-label|class-field|class-method|...],

_type_  : "diagram"

_event_: jquery catched event


### Context menu extension API (menu, sub-menus etc)

There is no sub-menus support and extensions yet