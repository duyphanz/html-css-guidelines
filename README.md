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

## III. CSS Rules

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



