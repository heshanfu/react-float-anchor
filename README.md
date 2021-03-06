# react-float-anchor

[![Circle CI](https://circleci.com/gh/StreakYC/react-float-anchor.svg?style=shield)](https://circleci.com/gh/StreakYC/react-float-anchor)
[![npm version](https://badge.fury.io/js/react-float-anchor.svg)](https://badge.fury.io/js/react-float-anchor)

This is a React component for anchoring a fixed position element, such as a
dropdown menu, to the edge of an element on the page. The fixed position
element will automatically be placed so that it fits on the screen if
possible, and it will automatically reposition if needed when the user scrolls.

![Example](https://streakyc.github.io/react-float-anchor/example.png)

The above example can be tried here:

https://streakyc.github.io/react-float-anchor/example/

You can find its code in the `example` directory. The example may be compiled
by running:

```
yarn
yarn example-build
```

You can build the example with live editing enabled (using
[react-transform-hmr](https://github.com/gaearon/react-transform-hmr) and
[browserify-hmr](https://github.com/AgentME/browserify-hmr)) by running:

```
yarn example-watch
```

## FloatAnchor

This module exports the `FloatAnchor` React component, which takes the
following props:

* `anchor` must be a single React Element. This element will be placed in the
 page where the `FloatAnchor` element was used, with no added wrapper elements
 around it.
* `float` must be null or a single React Element. This element will be placed
 in a container div which has `position:fixed` styling, is attached directly
 to the document body, and is positioned to line up with the anchor element.
* `options` is an optional object of options to control how the float element's
 container is aligned to the anchor element. The options are the same as those
 supported by [contain-by-screen (version ^1.0)](https://github.com/AgentME/contain-by-screen#readme).
* `zIndex` is an optional number controlling the z-index CSS property of the
 float element's container.
* `floatContainerClassName` is an optional string specifying a CSS class to
 apply to the float element's container div.

FloatAnchor has the following static methods:

* `parentNodes(node)` takes a DOM node, and returns an iterator that yields the
 node and then each parentNode, unless the current node is a `float` element's
 container div, then its corresponding `anchor` DOM node will be yielded next
 instead. This is useful when you are listening to events from the entire page
 and need to determine whether an event's target is logically contained by a
 React component that has children that use FloatAnchor.

The FloatAnchor component has a `reposition` method, which you should call if
you change the size of the contents of the anchor or float elements.

The container div of the `float` element has its `rfaAnchor` property set to
be equal to the `anchor` DOM element.

## Related

If you want interactive dropdown menus, check out the
[react-menu-list](https://github.com/StreakYC/react-menu-list) module that
is built with this!

## Types

[Flow](https://flowtype.org/) type declarations for this module are included!
If you are using Flow, they won't require any configuration to use.
