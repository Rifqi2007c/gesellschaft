### heading
- # heading 1
	-	`### heading1`
- ## heading 2
	- `## heading 2`
- ### heading 3
	- `heading 3`
- #### heading 4
	- `#### heading 4`
- heading 5
	- `##### heading 5`
- heading 6
	- `###### heading 6`

### bold, italics, highlights

| style                  | markdown               | example                      | output                   |
| ---------------------- | ---------------------- | ---------------------------- | ------------------------ |
| bold                   | `** **` or `__ __`     | `**text**` or `__text__`     | **text** or __text__     |
| italic                 | `* *` or `_ _`         | `*text*` or `_text_`         | *text* or _text_         |
| strikethrough          | `~~ ~~`                | `~~text~~`                   | ~~text~~                 |
| highlight              | `== ==`                | `==text==`                   | ==text==                 |
| bold and nested italic | `_ _` inside `** **`   | `**text _text2_ text**`      | **text _text2_ text**    |
| bold and italic        | `*** ***` or `___ ___` | `***text***` or `___text___` | ***text*** or ___text___ |
### internal link
- wikilink example: `[[gesellschaft]]`
	output: [[@ gesellschaft]]
- markdown example: `[windows](windows%20apps.md)`. (`[windows](path/to/note)`)
	output: [windows](windows%20apps.md)
> markdown destination link:
> if link/note name has spaces, replace it with `%20`
> you can also put it in `< >`. example: `<windows apps.md>`

### external link
- also known as link to site with custom name, example: `[github](https://github.com/Rifqi2007c)`
	output: [github](https://github.com/Rifqi2007c)

### embedded image
- use `![[]]` put `path/to/image` or url and resize to suitable pixel size with `|witdh x height` or just width after `path/to/image` or url
	- internal image example: `![[the silly.jpg|200]]`
		![[the silly.jpg|200]]
	- external image example: `![mili-k2](https://preview.redd.it/mili-mascot-k2-v0-2r6229w5zvzf1.jpg?width=1080&crop=smart&auto=webp&s=9d78bac41e904983f69d7c29cb14d4b141c47667)`
		![mili-k2|200](https://preview.redd.it/mili-mascot-k2-v0-2r6229w5zvzf1.jpg?width=1080&crop=smart&auto=webp&s=9d78bac41e904983f69d7c29cb14d4b141c47667)

### list
- #### unodered list
	- create list by using `-`, `*`, or `+`
	- example:
```
- text 1
- text 2
- text 3
```
ouput :
- text 1
- text 2
- text 3
> you can use different list syntax to make list space-out when put on top of each other.
> press TAB to quickly make sub-list

- #### ordered list
	- create odered/numbered list using number followed by `.` or `)` after each number
	- example:
```
1. text 1
2. text 2
3. text 3
```
output:
1. text 1
2. text 2
3. text 3
> You can use `Shift+Enter` to insert a [line break](https://help.obsidian.md/syntax#Line%20breaks) within an ordered list without altering the numbering

- ### task list
	- create task list using `- [ ]`
	- example:
```
- [ ] task 1
- [ ] task 2
- [ ] task 3
```
output:
- [ ] task 1
- [ ] task 2
- [ ] task 3
> when the list is tick, the syntax will become `- [x]`
- example:
```
- [x] task 1
- [x] task 2
- [x] task 3
```
output:
- [x] task 1
- [x] task 2
- [x] task 3
> you also can press TAB to create subtask

### horizontal rule/line
- create line using three or more `***`, `---`, `___`
	- example:
```
***
****
* * *
---
----
- - -
___
____
_ _ _
```
output (`****`):
****

### code
- #### inline code
	- put text inside _backtick_(\`\`)
	- example: \`text\`
		output: `text`
- #### code block
	- create code block using use three _backtick_ or _tilde_(\~\~\~) and put another three after it or your text/code
	- example(\`\`\`):
		````md
		```
		text
		```
		````
	- output:
	```
	text
	```
> You can add syntax highlighting to a code block, by adding a language code after the first set of backticks, example:
> \`\`\`js
> text
> \`\`\`
> example(javascript):
````md
```js
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```
````
output:
`````js
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
`````

- ### nesting code block (for making note)
	- create nested code block using there or more _backtick_ (more that the _backtick_ use for code that needed to be nested)
	- example + output:
`````md
````md
```
text
```
````
`````
> You can also mix backticks and tildes. This is particularly useful when working with code that generates other code blocks:
`````md
````md
```dataviewjs
dv.paragraph(`
~~~mermaid
graph TD
    A --> B
~~~
`)
```
````
`````

### footnote
```md
[^1]: This is the referenced text
[^2]: Add 2 spaces at the start of each new line
  This lets you write footnotes that span multiple lines
[^note]: Named footnotes still appear as numbers, but can make it easier to identify and link references
```
example + output:
- footnote [^1]
- footnote [^2]
- named footnode [^heheheha]

### comments
- create comment using `%%`, text in the middle and close with another `%%`
- example: `text %%comment%%`
	output:
	text %%coment%%
> commend only visible in editing view

### escaping markdown syntax
- in other word, when special character that are syntax is needed without triggering their formating, put `\` before your note
- example:
````md
\`\`\` text
````
output: \`\`\` text

[^1]: ignore these footnote its just for the footote example

[^2]: wawawaawawawa

[^heheheha]: wweeeeee

----
#obsidian 