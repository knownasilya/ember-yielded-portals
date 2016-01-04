# yielded-portals

An example of how to create advanced component APIs by combining
[ember-portal] and [contextual components].

:warning: This only works with Ember 2.3 (beta onward).

## Example

```hbs
{{#test-yields as |portals|}}
  {{#portals.header}}Header{{/portals.header}}

  Body

  {{#portals.footer}}Footer{{/portals.footer}}
{{/test-yields}}
```

Run this app for the working version. Note that you can use the component multiple
times and the portals will "wormhole" into the correct instance of the component.

## Potential Drawbacks

1. Currently the portal components that the user uses, leave remnant DOM nodes,
which you might have to account for in your CSS. They will be wherever the user
placed them in the component's block. Using `tagName=""` prevents nested divs, but
still renders a div where the portal was used in the block.

2. Using the same portal multiple times in the same block will only render
the last portal of that type in the block.

## Related discussions

- [slots rfc]

## Prerequisites

You will need the following things properly installed on your computer.

* [Git](http://git-scm.com/)
* [Node.js](http://nodejs.org/) (with NPM)
* [Bower](http://bower.io/)
* [Ember CLI](http://www.ember-cli.com/)
* [PhantomJS](http://phantomjs.org/)

## Installation

* `git clone <repository-url>` this repository
* change into the new directory
* `npm install`
* `bower install`

## Running / Development

* `ember server`
* Visit your app at [http://localhost:4200](http://localhost:4200).

### Code Generators

Make use of the many generators for code, try `ember help generate` for more details

### Running Tests

* `ember test`
* `ember test --server`

### Building

* `ember build` (development)
* `ember build --environment production` (production)

### Deploying

Specify what it takes to deploy your app.

## Further Reading / Useful Links

* [ember.js](http://emberjs.com/)
* [ember-cli](http://www.ember-cli.com/)
* Development Browser Extensions
  * [ember inspector for chrome](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)
  * [ember inspector for firefox](https://addons.mozilla.org/en-US/firefox/addon/ember-inspector/)


[ember-portal]: https://github.com/minutebase/ember-portal
[contextual components]: https://github.com/emberjs/rfcs/blob/master/text/0064-contextual-component-lookup.md
[slots rfc]: https://github.com/emberjs/rfcs/pull/72
