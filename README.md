# HTML-CSS Generator

## Brief Overview

This script generates an HTML file (test.html) and a corresponding CSS file (styles.css). It utilizes two custom classes, HtmlBuilder and CSSGenerate, to create and style HTML elements programmatically. The script ensures the files are created afresh by deleting any existing files with the same names.

## Initialization

In order to get started with our CSS and HTML generator

```
<?php
require_once 'html_generator.php';
require_once 'CSSGenerate.php';
php?>
```

To initialize the code, use the following constructors

HTML: $builder = new HtmlBuilder();
CSS: $css = new CSSGenerate("styles.css");

## HTML

The HtmlElement class creates a flexible and efficient way to generate HTML elements and structures programmatically. It has private properties for the tag name, content, and attributes. The constructor allows you to set the tag name, content, and the attributes. Lastly, the render() function generates all defined HTML elements, arguments, and structures.

The HtmlBuilder class manages a collection of methods that implements the generation of the class HtmlElement.
Methods:
addElement() = Adds a htmlElement to the program
render() = renders the generated the specific html command/prompt
saveToFile() = pushes all rendered commands to a separate html file

Elements:
createElement($tag, $content = '', $attributes = []) = creates a generic html element.
    createLinkCss($filename) = Create a CSS link element.
createHeader($level, $text, $class = '') = Create a header element (h1, h2, etc.).
    createParagraph($text, $class = '') = Create a paragraph element.
    createBreak() = Create a line break element.
    createAnchor($href, $text, $class = '') = Create an anchor element (link).
    createImage($src, $alt, $class = '') = Create an image element.
    createSpan($text, $class = '') = Create a span element.
    createOrderedList($items, $class = '') = Create an ordered list.
    createUnorderedList($items, $class = '') = Create an unordered list
    createListItem($content) = Create a list item.
createTable($data, $class = '') = Create a table.
    createForm($action, $method, $class = '') = Create a form.
    createInput($type, $name, $placeholder = '', $class = '') = Create an input field.
    createButton($text, $type = 'button', $class = '') = Create a button.
    createDiv($elements, $class = '') = Create a div element.
    createCheckbox($name, $checked = false, $class = '') = Create a checkbox input.
    createTextarea($name, $id, $placeholder = '', $class = '') = Create a textarea.
    createSection($content, $class = '') = Create a section element.
    createDt($text, $class = '') = Create a definition term.
    createDd($text, $class = '') = Create a definition description.

How to use: - Instantiate HtmlBuilder.
$htmlBuilder = new HtmlBuilder(); - Use the function elements to create HTML elements
$htmlBuilder->addElement(createParagraph('Hello World!', 'text')); - Use the render function to generate the command.
$htmlBuilder->addElement(createParagraph('Hello World!', 'text'))
->render() - Lastly, push the code to the separate html file using the save to file function
$htmlBuilder->addElement(createParagraph('Hello World!', 'text'))
->render()
->saveToFile('test.html');

## CSS

The CSSGenerate class provides a fluent interface for creating CSS stylesheets programmatically. It allows users to add CSS rules for various HTML elements and classes, set a wide range of CSS properties, and then generate a CSS file with the defined styles. This class is useful for dynamically generating CSS files based on specific requirements, allowing for more flexible and maintainable styling in web applications.

List of Functions
Here is an overview of the available functions in the CSSGenerate class:

# List of Functions

Here is an overview of the available functions in the CSSGenerate class:

### Font Properties

**fontSize($value):** Sets the font-size property.

**fontWeight($value):** Sets the font-weight property.

**fontStyle($value):** Sets the font-style property.

**fontFamily($value):** Sets the font-family property.

**letterSpacing($value):** Sets the letter-spacing property.

**wordSpacing($value):** Sets the word-spacing property.

**textTransform($value):** Sets the text-transform property.

### Color Properties

**bgColor($value):** Sets the background-color property.

**fontColor($value):** Sets the color property.

**textDecorationColor($value):** Sets the text-decoration-color property.

**textShadow($value):** Sets the text-shadow property.

### Layout Properties

**display($value):** Sets the display property.

**position($value):** Sets the position property.

**top($value):** Sets the top property.

**bottom($value):** Sets the bottom property.

**left($value):** Sets the left property.

**right($value):** Sets the right property.

**float($value):** Sets the float property.

**clear($value):** Sets the clear property.

**overflow($value):** Sets the overflow property.

**overflowX($value):** Sets the overflow-x property.

**overflowY($value):** Sets the overflow-y property.

### Box Model Properties

**padding($value):** Sets the padding property.

**margin($value):** Sets the margin property.

**borderWidth($value):** Sets the border-width property.

**borderColor($value):** Sets the border-color property.

**borderStyle($value):** Sets the border-style property.

**borderRadius($value):** Sets the border-radius property.

**boxShadow($value):** Sets the box-shadow property.

**borderCollapse($value):** Sets the border-collapse property.

**borderSpacing($value):** Sets the border-spacing property.

**width($value):** Sets the width property.

**height($value):** Sets the height property.

### Text Properties

**textAlign($value):** Sets the text-align property.

**textDecoration($value):** Sets the text-decoration property.

**textDecorationStyle($value):** Sets the text-decoration-style property.

**textDecorationLine($value):** Sets the text-decoration-line property.

**textDecorationSkip($value):** Sets the text-decoration-skip property.

**textOverflow($value):** Sets the text-overflow property.

**lineHeight($value):** Sets the line-height property.

**whiteSpace($value):** Sets the white-space property.

**verticalAlign($value):** Sets the vertical-align property.

**opacity($value):** Sets the opacity property.

## Example Usage

```
$css = new CSSGenerate("styles.css");
$css->addTag("body")
    ->bgColor("#e0fcfc")
    ->fontFamily("Arial, sans-serif")
    ->endBracket();

$css->addTag(".header")
    ->fontSize("24px")
    ->fontWeight("bold")
    ->fontColor("red")
    ->textAlign("center")
    ->padding("10px")
    ->margin("0")
    ->endBracket();

$css->generateFile();
```
