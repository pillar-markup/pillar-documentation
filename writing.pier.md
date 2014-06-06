

##1\. Writing Pillar documents

<a name="writing"></a>
In this section we show how to write Pillar documents by presenting Pillar syntax\. You might want to have a look at the [cheat sheet](http://www.cheatography.com/benjaminvanryseghem/cheat-sheets/pillar) and even download and print it\.



###1\.1\. Chapters & Sections

A line starting with `!` becomes a chapter heading\. Use multiple `!` to create sections and subsections\.

<a name="chapterAndSections"></a>
To refer to a section or chapter, put an anchor \(equivalent to \\label\{chapterAndSections\} in Latex\) using the `@chapterAndSections` syntax on a *separate line*\. Then, when you want to link to it \(equivalent to \\ref\{chapterAndSections\} in Latex\), use the `*chapterAndSections*` syntax\. Anchors are invisible and links will be rendered as: [1\.1](#chapterAndSections)\.



###1\.2\. Paragraphs and framed paragraphs

An empty line starts a new paragraph\.

An annotated paragraph starts a line with `@@` followed by either `todo` or `note`\. For example,




    @@note this is a note annotation.



generates

&nbsp;<p class="note">this is a note annotation\.</p>
And,

&nbsp;


    @@todo this is a todo annotation



generates a todo annotation that is not visible in the output\.

&nbsp;<p class="todo">this is a todo annotation</p>


###1\.3\. Lists



####1\.3\.1\. Unordered lists

&nbsp;


    -A block of lines,
    -where each line starts with ==-==
    -is transformed to a bulleted list, where each line is an entry.



generates

&nbsp;

- A block of lines,
- where each line starts with `-`
- is transformed to a bulleted list, where each line is an entry\.



####1\.3\.2\. Ordered lists

&nbsp;


    #A block of lines,
    #where each line starts with ==#==
    #is transformed to an ordered list, where each line is an entry.



generates

&nbsp;

1. A block of lines,
2. where each line starts with `#`
3. is transformed to an ordered list, where each line is an entry\.



####1\.3\.3\. Definition lists

Definition lists \(*aka\.* description lists\) are lists with labels:

&nbsp;


    ;blue
    :color of the sky
    ;red
    :color of the fire



generates

<dl><dt>blue
</dt><dd>color of the sky</dd><dt>red
</dt><dd>color of the fire</dd></dl>


####1\.3\.4\. List nesting

&nbsp;


    - Lists can also be nested.
    -#Thus, a line starting with ==-#==
    -#is an element of a bulleted list that is part of an ordered list.



generates

&nbsp;

-  Lists can also be nested\.
    1. Thus, a line starting with `-#`
    2. is an element of a bulleted list that is part of an ordered list\.




###1\.4\. Formatting
There is some sugar for font formatting:

&nbsp;

- To make something **bold**, write `""bold""`
- To make something *italic*, write `''italic''`
- To make something `monospaced`, write `==monospaced==`
- To make something <del>strikethrough</del>, write `--strikethrough--`
- To make something <sub>subscript</sub>, write `@@subscript@@`
- To make something <sup>superscript</sup>, write `^^superscript^^`
- To make something <u>underlined</u>, write `__underlined__`



###1\.5\. Tables
To create a table, start off the lines with `|` and separate the elements with `|`s\. Each new line represents a new row of the table\. Add a single `!` to let the cell become a table heading\.

&nbsp;


    |!Language |!Coolness
    |Smalltalk | Hypra cool
    |Java | baaad





| Language  | Coolness
| :---:| :---:
| Smalltalk  |  Hypra cool
| Java  |  baaad



The contents of cells can be aligned left, centered or aligned right by using `|{`, `||` or `|}` respectively\.

&nbsp;


    ||centered||centered||centered
    |{ left |} right || center



generates



| centered | centered | centered
| :---:| :---:| :---:
|  left  |  right  |  center




###1\.6\. Links



####1\.6\.1\. Internal Links and Anchors

<a name="anchorName"></a>
To put an anchor \(equivalent to \\label in Latex\), use the `@anchorName` syntax on a *separate line*\. Then, when you want to link to it \(equivalent to \\ref in Latex\), use the `*anchorName*` syntax\. Anchors are invisible and links will be rendered as: [1\.6\.1](#anchorName)\.



####1\.6\.2\. External Links

To create links to externals resources, use the `*Pharo>http://pharo-project.org/*` syntax which is rendered as [Pharo](http://pharo-project.org/)\.



###1\.7\. Pictures

To include a picture, use the syntax `+caption>file://filename|parameters+`:

&nbsp;


    +Caption of the picture>file://figures/pier-logo.png|width=50|label=pierLogo+



generates Figure [1\.1](#pierLogo) \(this reference has been generated using `*pierLogo*`\)\.

<a name="pierLogo"></a><figure><img src="figures/pier-logo.png" width="50%"></img><figcaption>This is the caption of the picture</figcaption></figure>



###1\.8\. Scripts

Use scripts when you want to add code blocks to your document\.




    \[\[\[
        foo bar
    \]\]\]


generates

&nbsp;


    foo bar



If you want either a label \(to reference the script later\) or a caption \(to give a nice title to the script\), write the following:




    \[\[\[label=script1\|caption=My script that works\|language=Smalltalk
        self foo bar
    \]\]\]


which produces

&nbsp;

<a name="script1"></a>**My script that works**


    self foo bar



This script can then be referenced with `*script1*` \(produces [1\.1](#script1)\)\. Specifying the language \(here `Smalltalk`\) will give you syntax highlighting\.



###1\.9\. Raw

If you want to include raw text into a page you must enclose it in `{{{` and `}}}`, otherwise Pier ensures that text appears as you type it\.

A good practice is to always specify for which kind of export the raw text must be outputted by starting the block with `{{{latex:` or `{{{html:` \(for now only LaTeX, HTML and Markdown are supported\)\. For example, the following shows a formula, either using LaTeX or an image depending on the kind of export\.




    \{\{\{latex:
    \\begin\{equation\}
      \\label\{eq:1\}
      \\frac\{1\+\\sqrt\{2\}\}\{2\}
    \\end\{equation\}
    \}\}\}
    \{\{\{html:
    \(1\+sqrt\(2\)\) / 2
    \}\}\}



This results in




**Take care:** avoid terminating the verbatim text with a `}` as
this will confuse the parser\. So, don't write <del>`{{{\begin{scriptsize}}}}`</del> but `{{{\begin{scriptsize} }}}` instead\.



###1\.10\. Preformatted \(less used\)

To create a preformatted block, begin each line with `=`\. A preformatted block uses equally spaced text so that spacing is preserved\.




    = this is preformatted text
    = this line as well




###1\.11\. Commented lines

Lines that start with a `%` are considered comments and will not be rendered in the resulting document\.

