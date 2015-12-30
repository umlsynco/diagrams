### New content dialog

New content dialog is a bridge between supported formats and data providers. It is based on AJAX JSON description, therefore it is not so interesting re-request JSON on each dialog initalization.

Therefore it was wrapped with a singleton-controller which is responsible for attach/detach dialog from the Framework.DialogRegion

![mime-type:application/vnd.umlsync.json] (http://umlsync.org/github?path=/code/content/new_dialog_classes.umlsync "")

An alternative solution for AJAX could be content type view registration with the list of supported formats OR we could register types views based on JSON.

### New content create sequence


### Content path auto-completion