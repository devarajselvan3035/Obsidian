## Summary 1

- Regex short Regular Expression
- Expressions need to be surrounded by forward slashes - Eg. /expression/
- Use without slashes in Regex tool when practicing

### Modes

- Standard - /expression/
- Case-insensitive - /expression/i
- Dot-matches-all - /expression/s
- Multiline - /expression/m

## Characters

**Standard matching (with the g mode)**
Always matches the closes word/letter to left without check the whole text

**Global matching (with the g)**
Find all matches in the text, no matter where they are

**Engine starts parsing data from left to right, sometimes backtracking when match is not found**
___

### Most simplest match is literal character match

*examples*
/super/ matches "bmw"
/super/matches the first five letters of this supermarket

**The matches are all Case-sensitive by default**
___
### We learned about the Wildcard Metacharacter

The dot (.), which matches any characters except newline

*Examples*
/c.r/matches car chr cor cir but NOT cass

If you want to match newlines you would need to use the Dot matches mode or the S on your expression

/c.r/s matches **car**

matches **cor** on this line since the mode S in there
___
### Metacharacters are characters with special meaning

the most common metacharacters we use in expressions are

`. +-* $ {} () [] !: = ^ |`

Some of these metacharacters can be use for more than one purpose. These metacharacters can also act slightly different in various engine but they mostly all behave the same across all engines.
___
### Escaping Metacharacters `\`

Sometimes we need to escape our symbols if they look the same as the text we want to find, for example

As you can see here /4.500/ these match will cause issues if we need to find 4.500 since the dot its the wildcard but what we need is the literal dot, we need to do something line this.

/4`\`.500/ we use a back slash here to escape the wildcard making it a literal character now, meaning its just a dot.

Quotes don't need to be escaped, since they are not meta-charaters.
___
### Some more characters to remember
`\t matches a tab`
`\n- matches a new line`
`\r-matches a carriage return`
___
## Sets

### Character sets

- We wrap everything in square brackets
- Any character of several character but only one character

*Examples*
/au[abcdt]o/matches auto
/au[xcvb]t/does not match auto
___
### Range sets

*examples*

- [A-Z] matches any uppercase character from A to Z
- [a-z] matches any lowercase character from A to Z
- [0-9] matches any digit character from 0 to 9
- [A-Za-z0-9] we can also combine them
___
### Negative sets

*examples*
- [^abc] match anything except abc or what is after the caret inside the brackets
- We are still matching one character here
- Remember that space is a character as well
___
### Metacharacters inside sets

Are already escaped

c/[abc.defo]r/ matches car and cor, but not cir or cur.

Here some characters that do nge to be escaped (remember we use a back slash in front `\`)
`-\^]`
___
### Shorthand for sets



*Examples*
`/\w\w\w/matches 123, abc, and_1Z`
`/\d\d\d/matches 123 bot not car`

9788282915