# HTML, CSS guidelines

## I.Why guidelines?

In working on `large, long-running projects`, with dozens of developers of `differing specialities and abilities`, it is important that we all work in `a unified way` in order to among other things:

- keep stylesheets maintainable;
- keep code transparent, sane, and readable;
- keep stylesheets scalable.

A coding styleguide is a valuable tool for teams who:

- build and maintain products for `a reasonable length of time`;
- have developers of `differing abilities and specialisms`;
- on-board new staff `regularly`;

A good styleguide, when well followed, will:

- set the `standard` for code quality across a codebase;
- promote `consistency` across codebases;
- give developers `a feeling of familiarity` across codebases;

## II. References:

I took a serious ref from https://cssguidelin.es/.

## III. Rules

### 1. 80 Characters Wide

Where possible, limit CSS files’ width to 80 characters. Reasons for this include

- the ability to have multiple files open side by side;
- viewing CSS on sites like GitHub, or in terminal windows;
- providing a comfortable line length for comments.

```css
/**
 * I am a long-form comment. I describe, in detail, the CSS that follows. I am
 * such a long comment that I easily break the 80 character limit, so I am
 * broken across several lines.
 */
```

### 2. Titling

The title of the section is prefixed with a hash (#) symbol to allow us to perform more targeted searches (e.g. grep, etc.): instead of searching for just SECTION-TITLE—which may yield many results—a more scoped search of #SECTION-TITLE should return only the section in question.

- If you are working on a project where `each section is its own file`, this title should appear at the top of each one.

```
/*------------------------------------*\
  #SECTION-TITLE
\*------------------------------------*/

.selector { }
```

- If you are working on a project with `multiple sections per file`, each title should be preceded by five (5) carriage returns. 

```
/*------------------------------------*\
  #A-SECTION
\*------------------------------------*/

.selector { }





/*------------------------------------*\
  #ANOTHER-SECTION
\*------------------------------------*/

/**
 * Comment
 */

.another-selector { }
```

### 3. CSS Ruleset

```
[selector] {
    [property]: [value];
    [<- Declaration ->]
}
```

- related selectors on the same line; unrelated selectors on new lines;
- a space before our opening brace ({);
- the opening brace ({) on the same line as our last selector;
- our first declaration on a new line after our opening brace ({);
- properties and values on the same line;
- a space after our property–value delimiting colon (:);
- each declaration on its own new line;
- our closing brace (}) on its own new line;
- each declaration indented by two (2) spaces;
- a trailing semi-colon (;) on our last declaration.
- long, comma-separated property values—such as collections of gradients or shadows—arranged across multiple new lines, making sure all values are indented at the same level as the first;

###### :heavy_multiplication_x: NOT GOOD

```scss
// Not having each selector on its own line
.selector-1, .selector-2
// Not having the opening brace (`{`) on the same line as the last selector
{
  // Not having each declaration on its own line
  background-color: $color-brand; background-image: linear-gradient($color-white, $color-grey-mercury), linear-gradient($color-black, $color-grey-alabaster);
  // Not using new lines for the comma-separated property values and not
  // indenting all the values at the same level as the first
  box-shadow: 1px 1px 1px $color-black, 2px 2px 1px 1px $color-grey-mercury inset;
  // Not using a space after the colon (`:`)
  color:$color-text-base;
  // Not indenting a declaration with four (2) spaces
  display: block;
  // Not using a trailing semi-colon (`;`) at the end of the declaration
  // and not having the closing brace (`}`) on its own new line
  padding: rem($spacing-base) }
```

###### :heavy_check_mark: GOOD

```scss
.selector-1,
.selector-2 {
  background-color: $color-brand;
  background-image: linear-gradient($color-white, $color-grey-mercury),
                    linear-gradient($color-black, $color-grey-alabaster);
  box-shadow: 1px 1px 1px $color-black,
              2px 2px 1px 1px $color-grey-mercury inset;
  color: $color-text-base;
  display: block;
  padding: rem($spacing-base);
}
```

### 4. Indenting

Indent entire related rulesets to signal their relation to one another. we stick to the same two (2) spaces, and we also leave a blank line before and after the nested ruleset.

```
.foo {
  color: red;

  .bar {
    color: blue;
  }

}
```

### 5. Meaningful Whitespace

- One (1) empty line between closely related rulesets.
- Two (2) empty lines between loosely related rulesets.
- Five (5) empty lines between entirely new sections.

- **CSS**
```
/*------------------------------------*\
  #FOO
\*------------------------------------*/

.foo { }

  .foo__bar { }


.foo--baz { }





/*------------------------------------*\
  #BAR
\*------------------------------------*/

.bar { }

  .bar__baz { }

  .bar__foo { }
```

- **HTML**
```
<header class="page-head">

  <ul class="primary-nav">

    <li class="primary-nav__item">
      <a href="/" class="primary-nav__link">Home</a>
    </li>

    <li class="primary-nav__item  primary-nav__trigger">
      <a href="/about" class="primary-nav__link">About</a>

      <ul class="primary-nav__sub-nav">
        <li><a href="/about/products">Products</a></li>
        <li><a href="/about/company">Company</a></li>
      </ul>

    </li>

    <li class="primary-nav__item">
      <a href="/contact" class="primary-nav__link">Contact</a>
    </li>

  </ul>
  
</header>





<main class="page-content">
  ...
</main>





<footer class="page-foot">
  ...
</footer>
```

### 6. CSS Units

CSS absolute or relative units?

### 7. Commenting

As a rule, you should comment anything that isn’t immediately obvious from the code alone. That is to say, there is no need to tell someone that color: red; will make something red, but if you’re using overflow: hidden; to clear floats—as opposed to clipping an element’s overflow—this is probably something worth documenting.

### 8. Namming

Naming conventions in CSS are hugely useful in making your code more strict, more transparent, and more informative. 
The naming convention: hyphen (-) delimited strings, with BEM-like naming for more complex pieces of code.

- **Hyphen Delimited and All Lowercase**

All strings in classes are lowercase and delimited with a hyphen (-), like so:

```
.page-head { }

.sub-content { }
```

- **BEM-like Naming**
```
// TODO
```
### 9. CSS selectors

#### - **Selector Intent**

It is important when writing CSS that we scope our selectors correctly, and that we’re selecting the right things for the right reasons.`Selector Intent` is the process of deciding and defining what you want to style and how you will go about selecting it.

For example, style the website’s main navigation menu:

```
// Bad

header ul { }
```
This selector’s intent is to style `any ul` inside `any header` element, whereas our intent was to style `the site’s main navigation`.
```
// Better

.site-nav { }
```

#### - **Reusability - Location Independence**

Given the ever-changing nature of most UI projects, and the move to more component-based architectures, it is in our interests not to style things based on `where` they are, but on `what` they are. 

For example, a call-to-action button has the following selector:

```
// Bad

.promo a { }
```
Not only does this have poor Selector Intent—it will greedily style any and every link inside of a `.promo` to look like a button—it is also pretty wasteful as a result of being so locationally dependent: we can’t reuse that button with its correct styling outside of .promo because it is explicitly tied to that location.

```
// Better 

.btn { }
```
This single class can be reused anywhere outside of .promo and will always carry its correct styling. As a result of a better selector, this piece of UI is more portable, more recyclable, doesn’t have any dependencies, and has much better Selector Intent.

#### - **Selector Performance**

That is to say, how quickly a browser can match the selectors your write in CSS up with the nodes it finds in the DOM. Generally speaking, the longer a selector is (i.e. the more component parts) the slower it is, for example:

```
body.home div.header ul { }
```
…is a far less efficient selector than:

```
.primary-nav { }
```

This is because browsers read CSS selectors `right-to-left`. A browser will read the first selector as

  - find `all ul` elements in the DOM;
  - now check if they live anywhere inside an element with a class of `.header`;
  - next check that `.header` class exists on a `div` element;
  - now check that all lives anywhere inside any elements with a class of `.home`;
  - finally, check that `.home` exists on a `body` element.

The second, in contrast, is simply a case of the browser reading

  - find all the elements with a class of `.primary-nav`.

To further compound the problem, we are using descendant selectors (e.g. `.foo .bar {}`). The upshot of this is that a browser is required to start with the rightmost part of the selector (i.e. .bar) and keep looking up the DOM indefinitely until it finds the next part (i.e. `.foo`). This could mean stepping up the DOM dozens of times until a match is found.

This is just one reason why nesting with preprocessors is often a `false economy`; as well as making selectors unnecessarily more specific, and creating location dependency, it also creates more work for the browser.

By using a child selector (e.g. `.foo > .bar {}`) we can make the process much more efficient, because this only requires the browser to look one level higher in the DOM, and it will stop regardless of whether or not it found a match.

#### - **Specificity**

No matter how well considered your naming, regardless of how perfect your source order and cascade are managed, and how well you’ve scoped your rulesets, just one overly-specific selector can undo everything. It is a gigantic curveball, and undermines CSS’ very nature of the cascade, inheritance, and source order.

The problem with specificity is that it sets precedents and trumps that cannot simply be undone.
```
#content table { }
```
For example: 

```
#content table { }

/**
 * Uh oh! My styles get overwritten by `#content table {}`.
 */
.my-new-table { }
```

The first selector was trumping the specificity of the one defined after it, working against CSS’ source-order based application of styles. In order to remedy this, we had two main options

  - refactor my CSS and HTML to remove that ID;
  - write a more specific selector to override it.

So, keep it low at all times (not using IDs in your CSS / not nesting selectors / not qualifying classes / not chaining selectors.)


