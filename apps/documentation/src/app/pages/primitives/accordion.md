---
title: 'Accordion'
---

# Accordion

Display a series of panels that can be expanded or collapsed.

<docs-example name="accordion"></docs-example>

## Usage

Assemble the accordion directives in your template.

```html
<div ngpAccordion ngpAccordionType="single" ngpAccordionCollapsible>
  <div ngpAccordionItem ngpAccordionItemValue="item-1">
    <button ngpAccordionTrigger>Would you like to learn more?</button>
    <div ngpAccordionContent>If you would like to learn more please reach out to us on GitHub.</div>
  </div>

  <div ngpAccordionItem ngpAccordionItemValue="item-2">
    <button ngpAccordionTrigger>Can I use this in my project?</button>
    <div ngpAccordionContent>Yes, this is open source and you can use it in your project.</div>
  </div>
</div>
```

## API Reference

The following directives are available to import from the `@ng-primitives/ng-primitives/accordion` package:

### NgpAccordion

<response-field name="ngpAccordionType" type="single | multiple" default="single">
  Define whether only one or multiple accordion items can be open at a time.
</response-field>

<response-field name="ngpAccordionCollapsible" type="boolean" default="false">
  Define an accordion can be collapsed. This is only applicable when `ngpAccordionType` is set to
  `single`.
</response-field>

<response-field name="ngpAccordionValue" type="T | T[]">
  Define the expanded accordion items. This should be a single value when `ngpAccordionType` is set
  to `single` and an array when set to `multiple`.
</response-field>

<response-field name="ngpAccordionDisabled" type="boolean" default="false">
  Define whether the accordion is disabled.
</response-field>

<response-field name="ngpAccordionOrientation" type="horizontal | vertical" default="vertical">
  Define the orientation of the accordion.
</response-field>

<response-field name="ngpAccordionValueChange" type="T | T[]">
  Emitted when the expanded accordion items change. This will be a single value when
  `ngpAccordionType` is set to `single` and an array when set to `multiple`.
</response-field>

### NgpAccordionItem

<response-field name="ngpAccordionItemValue" type="T" required>
  Define the value of the accordion item.
</response-field>

<response-field name="ngpAccordionItemDisabled" type="boolean" default="false">
  Define whether the accordion item is disabled.
</response-field>

### NgpAccordionTrigger

There are no inputs or outputs for this directive.

### NgpAccordionContent

There are no inputs or outputs for this directive.

## Global Configuration

You can configure the default options for all accordions in your application by using the `provideNgpAccordionConfig` function in a providers array.

```ts
import { provideNgpAccordionConfig } from '@ng-primitives/ng-primitives/accordion';

bootstrapApplication(AppComponent, {
  providers: [
    provideNgpAccordionConfig({
      type: 'multiple',
      collapsible: true,
      orientation: 'horizontal',
    }),
  ],
});
```

### NgpAccordionConfig

<response-field name="type" type="single | multiple">
  Define whether only one or multiple accordion items can be open at a time.
</response-field>

<response-field name="collapsible" type="boolean">
  Define an accordion can be collapsed. This is only applicable when `type` is set to `single`.
</response-field>

<response-field name="orientation" type="horizontal | vertical">
  Define the orientation of the accordion.
</response-field>