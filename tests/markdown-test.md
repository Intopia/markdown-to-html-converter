# Markdown test document

This is the opening paragraph. It sits directly under the H1, so it should come through as a plain paragraph inside `main`. This H1 is also the only H1 in the document, so its text should end up as the `title` in the `head`.

This paragraph is hard wrapped across
three separate lines in the source, which
should still come through as one paragraph.

## Heading level 2

### Heading level 3

#### Heading level 4

##### Heading level 5

###### Heading level 6

## Inline formatting

Some **bold text using asterisks** and some __bold text using underscores__.

Some *italic text using asterisks* and some _italic text using underscores_.

Some ***bold and italic together*** in one run.

Some `inline code` in the middle of a sentence.

Inline code containing markup, like `<div class="example">`, and inline code containing an ampersand, like `a && b`.

A sentence that mixes **bold with `code` inside it** and *italic with a [link](https://intopia.digital) inside it*.

## Inline formatting edge cases

A variable called snake_case_word should not turn into emphasis.

The sum 2*3*4 should not turn into emphasis either.

A plain ampersand & on its own, and a less than sign < on its own.

An asterisk that stands alone * like this.

## Links

A [simple link](https://intopia.digital).

A [link with a title attribute](https://intopia.digital "Intopia home page").

A [relative link](../about/index.html) to another page.

A [mailto link](mailto:hello@example.com).

A [link with **bold** in the text](https://intopia.digital).

An autolink: <https://intopia.digital>

An email autolink: <hello@example.com>

## Images

An image on its own line:

![A red square](red-square.png)

An image with a title attribute:

![A blue square](blue-square.png "Blue square")

An image with an empty alt attribute, for decorative use:

![](divider.png)

An image wrapped in a link:

[![A green square](green-square.png)](https://intopia.digital)

## Unordered lists

- First item
- Second item
- Third item

A list using asterisks:

* First item
* Second item

A list using plus signs:

+ First item
+ Second item

## Ordered lists

1. First item
2. Second item
3. Third item

A list using the closing bracket style:

1) First item
2) Second item

## Nested lists

- Top level item one
- Top level item two
  - Second level item
  - Another second level item
    - Third level item
- Top level item three

Numbered list with numbered children:

1. First item
2. Second item
   1. Sub item one
   2. Sub item two
3. Third item

Mixed nesting:

1. Numbered parent
   - Bulleted child
   - Another bulleted child
2. Second numbered parent

## Lists with more than one paragraph

- This item has a first paragraph.

  This is a second paragraph inside the same list item.

- This item only has one paragraph.

## An unordered list immediately followed by an ordered list

- Bullet one
- Bullet two

1. Number one
2. Number two

## Blockquotes

> A single line blockquote.

> A blockquote that runs
> across two lines in the source.

> A blockquote with a **bold** word and a [link](https://intopia.digital).

> A blockquote containing a list:
>
> - First item
> - Second item

## Code blocks

A fenced code block with no language:

```
function plain() {
  return true;
}
```

A fenced code block with a language:

```javascript
function greet(name) {
  return "Hello, " + name;
}
```

A fenced code block containing HTML, which should be escaped rather than passed through:

```html
<p class="example">Text &amp; more text</p>
```

A fenced code block using tildes:

~~~
This block uses tilde fences.
~~~

## Tables

A basic table:

| Name | Role | Location |
| --- | --- | --- |
| Russ | Educator | Sydney |
| Sam | Strategy | Melbourne |

A table with alignment markers:

| Left | Centre | Right |
|:-----|:------:|------:|
| One | Two | Three |
| Four | Five | Six |

A table with formatting inside cells:

| Element | Purpose |
| --- | --- |
| `<th>` | A **header** cell |
| `<td>` | A *data* cell |
| `<caption>` | A [table caption](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption) |

## Horizontal rules

Three hyphens:

---

Three asterisks:

***

Three underscores:

___

## Raw HTML

A raw HTML block, which should pass through untouched:

<div class="callout">
  <p>This markup was written directly in the markdown source.</p>
</div>

A paragraph with <strong>inline HTML</strong> and an <abbr title="Accessible Rich Internet Applications">ARIA</abbr> abbreviation in it.

A details element:

<details>
  <summary>Show more</summary>
  <p>Hidden content.</p>
</details>

## Syntax this converter does not handle

These are here so you can see exactly what happens to them, not because they are expected to work.

Setext style heading
====================

Another setext heading
----------------------

A [reference style link][intopia] and its definition at the bottom of the document.

Strikethrough: ~~this text is struck through~~.

A task list:

- [ ] An unchecked task
- [x] A checked task

A footnote reference[^1].

Term
: A definition list definition.

[^1]: The footnote text.

[intopia]: https://intopia.digital

## Last section

A final paragraph so the document does not end on a list or a table.
