# yielded-portals

An example of how to create advanced component APIs by combining
[ember-portal] and [contextual components].

![Ember Version][ember-version]

## Example

```hbs
{{#test-yields as |portals|}}
  {{#portals.header}}
    Header
  {{/portals.header}}

  Body

  {{#portals.footer}}
    Footer
  {{/portals.footer}}
{{/test-yields}}
```

Run this app for the working version. Note that you can use the component multiple
times and the portals will "wormhole" into the correct instance of the component.

You can also nest components with portals.

See the component definition [here](https://github.com/knownasilya/ember-yielded-portals/blob/master/app/components/test-yields/template.hbs).

## Potential Drawbacks

1. Currently the portal components that the user uses, leave remnant DOM nodes,
which you might have to account for in your CSS. They will be wherever the user
placed them in the component's block. Using `tagName=""` prevents nested divs, but
still renders a div where the portal was used in the block.

2. Using the same portal multiple times in the same block will only render
the last portal of that type in the block. **Workaround**: Add `showingPortalItem=true` to
the portal-content to append instead of replace.

## Related Discussions

- [slots rfc]

## Build

See the [ember-cli 1.13 readme template] for basic instructions.

[ember-portal]: https://github.com/minutebase/ember-portal
[contextual components]: https://github.com/emberjs/rfcs/blob/master/text/0064-contextual-component-lookup.md
[slots rfc]: https://github.com/emberjs/rfcs/pull/72
[ember-cli 1.13 Readme template]: https://github.com/ember-cli/ember-cli/blob/v1.13.13/blueprints/app/files/README.md
[ember-version]: https://embadge.io/v1/badge.svg?start=2.3.0
