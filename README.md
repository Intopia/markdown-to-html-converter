# Markdown to HTML converter

A single page tool that turns markdown into simple, clean HTML you can copy and use.

Paste markdown into the text box or upload a `.md` file, press convert, then copy the result. The output is a complete document: a `head` with a title taken from the first H1, and a `body` containing a `main` element with the converted content inside it.

Everything happens in the browser. Nothing you paste or upload is sent anywhere.

## What it converts

- Headings, levels 1 to 6
- Paragraphs, with hard wrapped lines joined back into one paragraph
- Bold, italic, and bold italic, using either asterisks or underscores
- Inline code, and fenced code blocks using either backticks or tildes
- Unordered lists using `-`, `*` or `+`
- Ordered lists using `1.` or `1)`
- Nested lists, to any depth, with 2 space, 3 space, 4 space or tab indenting
- List items containing more than one paragraph
- Blockquotes, including blockquotes with lists inside them
- Tables, with the header row marked up as `th` elements with `scope="col"`
- Inline links, with or without a title
- Reference links, in full, collapsed and shortcut form
- Autolinks, including email autolinks
- Images, including images with a title and images with empty alt text
- Horizontal rules

Raw HTML written directly in the markdown source is passed through untouched, so you can drop in elements markdown has no syntax for. A stray `<` or `&` in ordinary text is escaped, so the output still validates.

## What it does not convert

- Footnotes
- Definition lists
- Setext headings, the kind underlined with `===` or `---`
- Task lists
- Strikethrough

These are markdown extensions rather than part of the core language. Anything on this list is left alone and comes through as visible text, rather than being turned into broken markup.

## How the output is formatted

The generated HTML is indented with tabs, and there is a blank line between each top level block.

Tabs are deliberate, so please don't convert them to spaces. A tab is the only indent character the reader controls: anyone can set tab width in their editor to suit how they read code, whether that means a wider indent to track nesting or a narrower one to avoid horizontal scrolling at high magnification. Spaces are a fixed number of columns for everyone, and the reader gets no say. It is the same principle as not hardcoding a font size.

One exception. The contents of fenced code blocks are passed through exactly as written, because whitespace inside `pre` is significant and rewriting it would change what the page displays. If a code sample in your markdown is indented with spaces, it stays indented with spaces. Keep that in mind if you ever run a find and replace across the output.

## Repo structure

```
index.html          the converter itself, self contained, no dependencies
tests/              markdown files used to test the converter
tests-output/       the HTML those test files produce
README.md
LICENSE
```

## Testing it

`tests/markdown-test.md` exercises everything listed above, plus the edge cases that usually trip up converters, like `snake_case_word` and `2*3*4`. It also has a final section of unsupported syntax, so you can see exactly how that degrades.

`tests/markdown-nested-list-test.md` is a narrower test for list nesting, five levels deep, including items that climb back out several levels at once.

The converted results live in `tests-output/`. Convert a test file and compare against the matching output to check nothing has regressed.
