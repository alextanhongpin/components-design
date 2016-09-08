#Custom Elements

With customElements, it is possible to create your own custom tags. E.g `<my-tag></my-tag>`.


```javascript

class TagComponent extends HTMLElement {
  constructor() {
    super()
  }
  
  createdCallback() {
    // an instance of the element is created
  }
  
  attachedCallback() {
    // an instance was inserted into the document
  }
  
  detachedCallback() {
    // 	an instance was removed from the document
  }
  
  attributeChangedCallback(attrName, oldVal, newVal) {
    // an attribute was added, removed, or updated
  }
}

const Tag = document.registerElement('my-tag', TagComponent);

//CSS4 Grid Layout
```
