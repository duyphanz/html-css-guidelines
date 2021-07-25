# HTML, CSS guidelines

## I.Why guidelines?

In working on large, long-running projects, with dozens of developers of differing specialities and abilities, it is important that we all work in a unified way in order to among other things:

- keep stylesheets maintainable;
- keep code transparent, sane, and readable;
- keep stylesheets scalable.

A coding styleguide is a valuable tool for teams who

- build and maintain products for a reasonable length of time;
- have developers of differing abilities and specialisms;
- have a number of different developers working on a product at any given time;
- on-board new staff regularly;
- have a number of codebases that developers dip in and out of.

A good styleguide, when well followed, will

- set the standard for code quality across a codebase;
- promote consistency across codebases;
- give developers a feeling of familiarity across codebases;
- increase productivity.

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



