CSS

## Declarative vs Imperative

CSS is a **declarative language**. 

**Declarative programming** is when you write your code in such a way that it describes what you want to do, and not how you want to do it. It is left up to the compiler to figure out the how. 

Declarative programming is “the act of programming in languages that conform to the mental model of the developer rather than the operational model of the machine”.

Declarative languages contrast with **imperative languages** which specify explicit manipulation of the computer’s internal state; or procedural languages which specify an explicit sequence of steps to follow. Imperative languages include C, C++, and Java. 

A **compiler** is software that translates the high-level code written by a developer into low-level **object code** (binary)/machine language that can be understood by the processor. It's how the hardware understands what you want it to do.

The processor executes object code. Object code is recognizable and executable machine code instructions. 


## Declarations

Property + value = **declaration**.

Properties and values are case sensitive.

Declarations are grouped in **declaration blocks** (between curly braces). Each declaration in a block must be separated with a semicolon. The last declaration in a block doesn't NEED to end with a semicolon - but it's good practice to do it anyway.

Selector + declaration block = **rule**.

Append `!important` to a declaration to make sure it always supersedes any others. `border: none !important;` But don't use it unless you for some reason absolutely have to - it'll mess up debugging.

`/* CSS comments */`

HTML elements can have multiple classes!!! You just have to separate them with a space (i.e. `class="first second"`)


## Selectors

`.classname`
`#idname`
`* `(selects everything)


## Attribute selectors
You can select elements with specific attributes. 

List of attributes here: https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes

However, you can make up your own custom attribute following the pattern `data-*`. For example:

`<li data-noice>Noice</li>`
`<li data-noice="hella">Toit</li>`

Then, I can select all elements with the attribute `data-noice`:

`[data-noice] {}`

or just elements with the attribute `data-noice` and the exact value `hella`:

`[data-noice="hella"] {}`

You can make really complicated, specific RegEx-like attribute selectors, but that's for another time: https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors

But essentially it's possible to select only elements with a specific string at the beginning, end, anywhere in the value. `a[href$=".org"] {}` selects all links ending in .org

## Pseudo-classes & pseudo-elements

Pseudo-class specifies styling an element when it's in a specific state, i.e. `a:hover` 

Pseudo-elements selects a certain part of an element. Examples include `::after` and `::first-letter`

Cool example: This selects all elements with attribute "href" (so, links), and then specifies that an arrow should be added after the element.

`[href^=http]::after {
  content: '⤴';
}`

## Combinators

**Group of selectors**

- `A, B`

- Any element matching A and/or B


**Descendent combinator**

- `A B`

- Any element matching B that is a descendent of an element matching A

**Child combinator**

- `A > B`

- Any element matching B that is a DIRECT child of an element matching A

**Adjacent sibling combinator**

- `A + B`

- Any element matching B that is the next sibling of an element matching A 

**General sibling combinator**

- `A ~ B`

- Any element matching B that is one of the next siblings of an element matching A
