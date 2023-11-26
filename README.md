# Build a Social Links Web Component Using HTML, CSS, and JS

- skip the js framework
- take advantage of browser APIs
    - customElements
    - the shadow DOM
        - encapsulate CSS at the component level
- take advantage of HTML `template` and `slot` elements
    - allows for styling at the document level

## Outcome

A (portable?) component that renders links to your social profile pages

## Features

### Styling at the Component Level

- template markup includes a style tag that doesn’t leak from the shadow DOM
    - were you to place the same tag in the standard DOM, CSS therein would apply to subsequent elements (in a cascade, of sorts).
    - encapsulated in an instance of the with shadow DOM, those styles apply only to sibling markup
    - it is possible to bring the CSS in from a separate location, using a link tag
    - local CSS will not apply to elements loaded via the slot attribute. In other words, styles defined in the global CSS apply to slotted elements. The shadow CSS floats around their markup, like a magical cloud. *Expelliarmus*!
        - Potter nerds, help a brother out.
- take the above into consideration when deciding what areas of the component should receive content from an attr., and what from a slot.
    - how much control do you want to give the user?
    - how much complexity do you want to abstract off their shoulders?

### A Note about Slotting

When you slot elements into the markup, the actual `slot` element remains in the shadow DOM. If you inspect the DOM, you’ll see the slotted element as child of your custom element, above which the shadow DOM appears with the slot elements and any default content. This, unlike many templating languages that swap out the default. 

Structurally, this looks disorienting, as a container  like `figure` may appear on the shadow DOM, and its slotted child `img` on the normal DOM, ie. outside. Furthermore, the `slot` element will appear on the shadow DOM as a child of `figure`. That is all.
