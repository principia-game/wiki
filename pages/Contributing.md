The source code for pages on the Principia Wiki is now versioned and hosted in a Git repository on GitHub, available [here](https://github.com/principia-game/wiki). The reason for this is

To contribute to the Wiki, simply fork the repository, make an edit and open a pull request. If you aren't experienced with Git, you may choose to use the GitHub web interface or the embedded Visual Studio Code editor (press `.` on your keyboard while on the repository page).

If you would like to suggest or discuss any changes or additions, feel free to drop by the `#wiki` channel on Discord or [open an issue on GitHub](https://github.com/principia-game/wiki/issues).

## Formatting
The Wiki uses Markdown syntax with some extensions. There is a lot of documentation about Markdown on the Internet, for the basics see this [Markdown Cheat Sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) for example. In addition to this there are some custom extensions to the syntax.

When writing text, split them up into reasonably sized paragraph to improve readability. If something can be a table or a list instead of a paragraph of text, make it so, as it will make the page more aesthetically pleasing. You should not hard wrap the source text, use the soft wrap option in your text editor. Hashtag-headings should be used, newline above heading but not below, and no 1st level heading should be used, as the Wiki software puts one automatically.

HTML is allowed if absolutely necessary and Markdown isn't enough. If it's something that may be reused (e.g. some kind of information box), it should become a template.

### Markdown extensions
To link to internal pages in the Wiki, there are `[[wikitext-like]]` links, like such: [[Viking Helmet]]. You should use these over regular Markdown links for internal pages, as it allows the Wiki software to create relationships between pages and e.g. figure out which pages are wanted or orphaned.

For larger pages with lots of headers, it is useful to have a table of contents at the top of the page, below the first block of text. A table of contents can be inserted into a page with `[toc]`.

The Wiki has a template system for reusable components such as infoboxes. They take a JSON string which is passed onto a Twig template. These templates can be found in `wiki/templates/functions/` in the principia-web codebase.

### Titles
Titles are taken from the file name. Usually page titles should be Title Cased Whenever Possible, but "small" words like prepositions should not be capitalised. We do not follow any particular handbook in terms of what constitutes as one, but use your best judgement.

Underscores in the file name is converted into spaces for the human readable name, e.g. `Creating_a_Bee_Smasher_Minigame.md` becomes `Creating a Bee Smasher Minigame`. In order to represent slashes in the file name while keeping all files in the same directory, the letter "Ä" is used as a replacement for a slash. For example, `LuaScriptÄthis.md` becomes `LuaScript/this`. This is subject to change.
