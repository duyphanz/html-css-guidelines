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

### 3. Ruleset

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

```
.foo, .foo--bar,
.baz {
  display: block;
  background-color: green;
  color: red;
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

**CSS**
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

**HTML**
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
