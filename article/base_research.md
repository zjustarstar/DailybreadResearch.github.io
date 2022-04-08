
# 基础研究

```json
{
  "test": "this is a json value"
}
```


## test test

I don't see how to use a README.md file instead of a string with manually escaped special characters. The usage examples don't involve any references to a .md document as input for the markdownString.

How can i pass the markdown string as a document (like form a file called README.md) instead of a manually escaped string and also have the final output include the styling?

The goal is to be able to pass in a linted (I'm using VS code markdownlint) README.md, the main document CSS and or highlightJS css and have the return value of the last line (marked(markdownString)) be something i can write directly to a .html file.

Another note if it matters: My markdown files also specify the the language in multi-line code blocks. For example a multi-line block of JSON in my README.md looks like this:

--- asdcas ---

*asdc*

> asdcasdca
> safdac
> 
> ascasd
