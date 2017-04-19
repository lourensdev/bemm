# BEMM (Block Element Modifier Modified)
A modified take on the popular BEM (Block Element Modifier) CSS methodology.

## Block 
**Prefix: " .b-* "*

Components are broken down into blocks to group code and visual elements together. These elements are given a unique name and prefixed by "b-" to represent a block element. This makes reading the HTML much more legible without knowing much about the CSS itself. An example of a block element is usually the component as a whole, i.e. dropdowns, buttons, tabs, media objects and etc. Block elements can be nested inside other block elements.

## Element 
**Prefix: " .e-* "*

Elements are contained within component blocks, usually as the first child descendant but not restricted to and prefixed by "e-". These elements are what makes up a block component, i.e for a dropdown this would be the list items inside the drop down. For Domofond, the styling of elements are dependent on the immediate parent block element, in other words they are nested in CSS. This allows reusing the names elements without affecting the CSS globally or having to use unique and lengthy class names. Elements should never live on a root level without being wrapped by a block element.

## Modifiers 
**Prefix: " .m-* "*

Modifiers are applied at any level of the component, they can be block, element or even global modifiers. These can also be seen as helper classes. In the stylesheet these are generally nested at the level they are needed to avoid having to use unique class names. Modifiers can be anything from subtle style changes like background colours or font sizes to layout floating or entire component theme colours.

## Global Modifiers 
**Prefix: " .g-* "*

The only differences between regular modifiers and global modifiers is the prefix and the fact that global modifiers have to be generic enough to be used on any component without requiring special style overwrites.


# Main BEM Differences 
Traditional BEM | BEMM
--------------- | ----
Block, Element and Modifiers live at the root level and should be reusable anywhere, by used long class names and chaining them for specificity. I.e ".block block__element .block__element--modifier" | Only block elements and global modifiers live at root level and are the only class names needed to be unique. This allows for shorter class names and relies on nesting for specificity. I.e ".b-block > .e-element .m-modifier"


# Code Example 
**HTML**
```
<a class="b-btn m-big m-orange" href="#">
  <span class="e-price">R9.99</span>
  <span class="e-text g-bold">Subscribe</span>
</a>
```

**CSS/LESS**
```
.b-btn {
    .e-price {}
    .e-text {}
    &.m-big {}
    &.m-orange {}
}

.g-bold {}
```

## Naming Convention 
All custom styling class names should have the required prefix ".b-, .e-, .m-, .g-", and long class names are separated by dashes.
".b-promo-header" - ***Names can be abbreviated to shorten the name as long as it's legible or clear what it means.***

## Further Reading 
More information on BEM here:
- BEM Info [(en.bem.info)](https://en.bem.info)
- BEM 101 [(css-tricks.com)](https://css-tricks.com)
- Get BEM [(getbem.com)](http://getbem.com)
