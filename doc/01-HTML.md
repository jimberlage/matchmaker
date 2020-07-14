# HTML

There's a file in this project called [`index.html`](../index.html).  HTML stands for HyperText Markup Language, and it's a language for representing websites.  Our document has a head, which is generally for stuff that isn't visual, and a body, for the stuff that is.

When they were making the internet, the eggheads over at Stanford thought that it would be the biggest academic paper-sharing network.  It's much more than that now, but HTML makes a lot of sense if you view it as a bunch of stuff bolted onto a tool for sharing academic papers.  It was created by [this dude Tim in 1990](https://en.wikipedia.org/wiki/HTML#Development).  You might think, why not use servers to send Word documents or something?  But one of the goals was to have a format for laying out documents that didn't require people to buy software from a specific vendor.

So that's what HTML is.  It's a format for letting people take text/images/etc., and display it a certain way (using certain fonts, or laying out elements in a list, or what have you.)

The way it works is that parts of the text are in the file, but not meant to be read.  A special program called a web browser (Chrome, Edge, Firefox, Safari, Internet Explorer, and other smaller ones you've never heard of) will take these files and display certain parts, and use other parts to figure out how to lay out the document visually.

Here's an example:

```html
<p>This is a paragraph</p>
```

The `<p>` and `</p>` aren't displayed; Chrome/Firefox/Edge/whatever use it to figure out what kind of display the text should get.  A (very simplified, not actually real) example of how the code is parsed is something like:

```javascript
var inElement = false;
for (letter of "<p>This is a paragraph</p>") {
    if (i === '<') {
        inElement = true;
        continue;
    }
    // ...
}
```

`for (letter of "<p>This is a paragraph</p>") {...}` is gonna go one-by-one through the letters (in computer science, these are called characters.)  So the way the computer has to read text is as a series of characters (`<`, `p`, `>`, `T`, `h`, ...)  The weird `<>`s help the computer determine where to start & stop.

The basic layout is that elements get placed between the lil' carats.  So a [paragraph element (`<p>`)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) is a identifier that all its children are intended to display as a paragraph, maybe with some padding between other visual elements.

Elements can hold other elements, called their "children"; for example, a [bold element (`<b>`)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/b) is supposed to bring attention to its children.  A "child" can also just be plain text, in HTML.  So you could have something like:

```html
<p>
    The <b>quick</b> brown fox jumped over the lazy dog.
</p>
```

This is all great, but one thing that came up almost immediately after making websites in HTML was, "how do I change the font of my paragraph?"  We've said that this is a paragraph, and that part of is is bold, but we haven't ever said what font this is supposed to use.  For that, there is CSS (Cascading Style Sheets), which we'll get into in a bit.

For now, here's a hint:  The CSS to change the font of all paragraphs to Times New Roman is also spelled out with HTML elements.  It uses the [style element (`<style>`)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style).  Here's the HTML you would put in your document to make that happen:

```html
<style type="text/css">
    p {
        font-family: "Times New Roman";
    }
</style>
```

## Homework

Google maintains a list of free fonts at https://fonts.google.com/.  Try to pick a font and write the CSS in our index.html to change paragraphs to the font of your choice.  You'll need to "embed" the font before you can use it with another HTML element, the [link element (`<link>`)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link).  You'll also need most of the style HTML we just went over.

If you don't see a paragraph element in our HTML, don't worry; it gets created later.  That's the subject of a future lesson.