# element-registrie
Allows to register CustomElement behavior for html elements based on tagName or is attribute, similar to customElement api.


## Importent concepts

1. when a element gets registered via define we search for existing matching elements and apply the upgrade hook of the definition
2. we look if a definition uses call parameters for the hooks or does use this. when it uses this we use apply else we call the hook with the element.
3. the registrie is a hashMap of tagName.toLowerCase(). 
4. connectedCallback is the most importent it can return a function that gets runned when the element gets removed

## Cleanup of event listners

when you assign functions for the listners on the element via the connectedCallback hook you do not need to clean that up.
When you need to assign listners outside of the element then you should use weakmap with the element as key to get that cleaned up.
when you do not use any of the prev methods you need to use the disconnectedCallback or the returned function from the connectedCallback.

## use

```js
import {} from 'element-registrie'
// Register a Element

```
