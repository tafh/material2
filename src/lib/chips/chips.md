`<md-chip-list>` displays a list of values as individual, keyboard accessible, chips.

<!-- example(chips-overview) -->

_Note: chips are still early in their development and more features are being actively worked on._

```html
<md-chip-list>
  <md-chip>Papadum</md-chip>
  <md-chip>Naan</md-chip>
  <md-chip>Dal</md-chip>
</md-chip-list>
```

### Unstyled chips
By default, `<md-chip>` has Material Design styles applied. For a chip with no styles applied,
use `<md-basic-chip>`. You can then customize the chip appearance by adding your own CSS.

_Hint: `<md-basic-chip>` receives the `mat-basic-chip` CSS class in addition to the `mat-chip` class._

### Selection
Chips can be selected via the `selected` property. Selection can be disabled by setting
`selectable` to `false` on the `<md-chip-list>`.

Whenever the selection state changes, a `ChipSelectionChange` event will be emitted via 
`(selectionChange)`.

### Disabled chips
Individual chips may be disabled by applying the `disabled` attribute to the chip. When disabled,
chips are neither selectable nor focusable. Currently, disabled chips receive no special styling.

### Chip input
The `MdChipInput` directive can be used together with a chip-list to streamline the interaction
between the two components. This directive adds chip-specific behaviors to the input element
within `<md-form-field>` for adding and removing chips. The `<input>` with `MdChipInput` can
be placed inside or outside the chip-list element.

An exmaple of chip input placed inside the chip-list element.
<!-- example(chips-input) -->

An example of chip input placed outside the chip-list element.

```html
<md-form-field>
  <md-chip-list #chipList>
    <md-chip>Chip 1</md-chip>
    <md-chip>Chip 2</md-chip>
  </md-chip-list>
  <input mdChipInputFor="chipList">
</md-form-field>
```

### Keyboard interaction
Users can move through the chips using the arrow keys and select/deselect them with the space. Chips
also gain focus when clicked, ensuring keyboard navigation starts at the appropriate chip.

### Orientation
If you want the chips in the list to be stacked vertically, instead of horizontally, you can apply
the `mat-chip-list-stacked` class, as well as the `aria-orientation="vertical"` attribute:

```html
<md-chip-list class="mat-chip-list-stacked" aria-orientation="vertical">
  <md-chip>Papadum</md-chip>
  <md-chip>Naan</md-chip>
  <md-chip>Dal</md-chip>
</md-chip-list>
```

### Theming
The selected color of an `<md-chip>` can be changed by using the `color` property. By default, chips
use a neutral background color based on the current theme (light or dark). This can be changed to
`'primary'`, `'accent'`, or `'warn'`.

### Accessibility
A chip-list behaves as a `role="listbox"`, with each chip being a `role="option"`. The chip input
should have a placeholder or be given a meaningful label via `aria-label` or `aria-labelledby`.
