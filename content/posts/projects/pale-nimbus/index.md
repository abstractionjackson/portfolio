+++
title = "Pale Nimbus"
subtitle = 'Build a Dynamic and Professional Business Card Web Component Using HTML, CSS, and JS'
summary = "Dive into our cutting-edge project where we construct an interactive business card leveraging the power of web standards: CustomElements API, Shadow DOM, and HTML's template and slot elements. This initiative is a fusion of advanced web technologies and creative design, ideal for tech-savvy professionals eager to leave a memorable impact with a unique digital presence."
date = 2023-11-26T14:36:09-08:00
draft = false
github_repo = "https://github.com/abstractionjackson/business-card"
[[resources]]
name = 'preview'
src = 'biz.png'
+++

{{< figure src="/images/patrick_bateman.jpeg" caption="A Professional -- Albiet Static -- Business Card; <i>American Psycho (2000)</i>">}}

## Summary

Dive into our cutting-edge project where we construct an interactive business card leveraging the power of web standards: CustomElements API, Shadow DOM, and HTML's template and slot elements. This initiative is a fusion of advanced web technologies and creative design, ideal for tech-savvy professionals eager to leave a memorable impact with a unique digital presence.

## Features

The "Web Components Business Card" project stands out with its unique set of features, designed to cater to a wide range of developers, from beginners to experts. Here's what makes this project special:

- **Framework Agnostic**: At the core of our project is its universal compatibility. Built using standard web APIs, this web component is meticulously crafted to be framework-agnostic. Whether you're working with React, Vue, Angular, or even without any JavaScript framework, our business card component seamlessly integrates into your project. This flexibility ensures that no matter what your project's stack is, our component can be a part of it without any hassle.

- **Ease of Adoption**: We believe in simplicity and accessibility. If you're familiar with basic HTML, you're all set to use our Web Component. There's no steep learning curve or complex setup involved. This ease of adoption makes it an ideal choice for those who are new to web development or those who prefer to work with straightforward, uncomplicated tools. It's as simple as integrating standard HTML elements into your web pages.

- **Lightweight Design**: In today's digital world, where speed and efficiency are paramount, our business card component is designed to be lightweight and fast. With no external dependencies, it ensures that your website remains speedy and responsive. This lightweight nature also contributes to better overall performance and user experience, making your website not just visually appealing but also technically robust.

In summary, the "Web Components Business Card" is not just a tool; it's a solution designed to be adaptable, easy to use, and performance-oriented, making it a valuable asset for any web development project.

## Notes

### Styling at the Component Level

- template markup includes a style tag that doesn’t leak from the shadow DOM
  - were you to place the same tag in the standard DOM, CSS therein would apply to subsequent elements (in a cascade, of sorts).
  - encapsulated in an instance of the with shadow DOM, those styles apply only to sibling markup
  - it is possible to bring the CSS in from a separate location, using a link tag
  - local CSS will not apply to elements loaded via the slot attribute. In other words, styles defined in the global CSS apply to slotted elements. The shadow CSS floats around their markup, like a magical cloud. _Expelliarmus_!
    - Potter nerds, help a brother out.
- take the above into consideration when deciding what areas of the component should receive content from an attr., and what from a slot.
  - how much control do you want to give the user?
  - how much complexity do you want to abstract off their shoulders?

### A Note about Slotting

When you slot elements into the markup, the actual `slot` element remains in the shadow DOM. If you inspect the DOM, you’ll see the slotted element as child of your custom element, above which the shadow DOM appears with the slot elements and any default content. This, unlike many templating languages that swap out the default.

Structurally, this looks disorienting, as a container like `figure` may appear on the shadow DOM, and its slotted child `img` on the normal DOM, ie. outside. Furthermore, the `slot` element will appear on the shadow DOM as a child of `figure`. That is all.
