---
title: Widgets - CurrentRefinements
layout: widget.pug
canonical: https://www.algolia.com/doc/api-reference/widgets/current-refinements/angular/
---

# Current Refinements

## Description

The current refinements widget has two purposes:

* give the user a synthetic view of the current filters.
* give the user the ability to remove a filter.

This widget is usually in the top part of the search UI.

## Options

| Attribute        | Type                            | Description
| -                | -                               | -
| `attributes?`    | `{name: string, label: string}` | Label definitions for the different filters
| `onlyListedAttributes?` | `boolean` | Only use the declared attributes. By default, the widget displays the refinements for the whole search state. If true, the list of `attributes` in attributes is used
| `clearRefinements?`      | `"before" / "after" / boolean`  | Defines the clear all button position. By default, it is placed before the set of current filters. If the value is false, the button won’t be added in the widget
| `clearsQuery?`   | `boolean`                       | If true, the clear all button also clears the active search query.
| `clearRefinementsLabel?` | `string`                        | Label used on the clear all button.
| `autoHideContainer?` | `boolean`  | Hides the widget if there's no refinements to display
| `transformItems?` | `(items) => items` | Function to modify the items being displayed, e.g. for filtering or sorting them

## Code example

```html
<ais-current-refinements [clearsQuery]="true" [transformItems]="translate">
</ais-current-refinements>
```

```ts
export class AppComponent {
  // ...
  translate(items) {
    return items.map(item => ({
      ...item,
      highlighted: myTranslateFunc(item.highlighted)
    }));
  }
}
```
