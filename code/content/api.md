Content view registration:

CotnentTabbedView is jquery.ui.tabs based collection view which is responsible for tabs handling. 

CotnentTabbedView::getChildView() - overrides  child view selection behaviour via global Framework method

![mime-type:application/vnd.umlsync.json] (http://umlsync.org/github?path=/code/content/content_view_classes.umlsync "")


typeViewController - was introduces to handle multiple view behaviour to share: canvas, icon menus, context menus and element menus between diagrams

**onRegister** - allows to get FW and extend it with diagram menu region

**onRequest** - allows to initialize diagram menu

**onActivate** - handles diagram menu show-hide use-cases


