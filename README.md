# Internship Report Template for DHBW Mannheim Faculty Technology
This template is in development. It's based on [Luca Vazzano's template](https://github.com/LucaVazz/Report-Template) and it's customized for use at DB Systel (it does not correspond to the DB Cooperate Design).  

Please use XeLaTeX or LuaLaTex for building.

## Features
- all formal layout-properties of the document are in accordance to the requirements given by the Technical Faculty of DHBW Mannheim.
- Titlepages for Internship Reports, Study Reports and Bachelor Thesis in accordance to these requirements included

<img alt="various Titlepages" src="http://i.imgur.com/ddOe000.png" width="70%">

- Fully customizable coloring

<img alt="Coloring" src="http://i.imgur.com/TGjZShi.png" width="70%">

- Easy switching between the (default) *english* and *german* version of the document



## How to Setup and Use
1. inside `./setup.tex`:
    - choose the type of your Report
	- choose your prefered Theme (DB Systel or DB default)
    - choose if you want to use the DB Font (have to be added by yourself - you can find instructions for that below)	
    - choose if you want to write your report in english or german
    - fill out the fields for your informations
2. places the entries for your bibliography into `./resources/references.bib`
3. place the `.tex`-files containing your content into `./content` and define the structure of your content inside `./content/structure.tex`
4. fill your acronyms and custom macros as needed into `./content/acronyms.tex` and `./content/macros.tex`
5. save your image files into `./resources`
    - you can then use them easily by just referencing `\includegraphics{asdf}` if you saved your file at `./resources/asdf.png`

## How to use DB Fonts
The DB Fonts aren't included in this Repository, so you have to add them by yourself.

1. Create a new directory `./lib/fonts/db/`
2. Add the font DB Sans as Truetypefont in the Styles:
    - regular: `DB_Sans.ttf`
    - bold: `DB_Sans_Bold.tff`
    - italic: `DB_Sans_Italic.tff`
	- bold italic: `DB_Sans_Bold_Italic.tff`
2. Add the font DB Head as Truetypefont in the Styles:
    - regular: `DB_Head.ttf`
    - black: `DB_Head_Black.tff`
    - italic: `DB_Head_Italic.tff`
	- black italic: `DB_Head_Black_Italic.tff`
4. Activate DbFont in `./setup.tex` by removing the `%` Symbol in front of `DbFont` in the `usepackage` section


## Included Custom Elements for Ease of Use
**Note:** `<asdf>` inside the general code denotes a placeholder


#### striped Tables
```Latex
\begin{stripedacenttable}
    {<caption>}
    {\label{tab:<label>}}
    {<formating>}
    {<Headings-Content>}
    <row definitions>
\end{stripedacenttable}

\begin{stripedtable}
    {<caption>}
    {\label{tab:<label>}}
    {<coloring>}
    {<formating>}
    {<Headings-Content>}
    <row definitions>
\end{stripedtable}
```

- *<label>* needs to be enclosed inside `\label` to keep the auto-completion functionality of your editor working correctly
- formating should have the form `x^x^x^...` where `x` specifies the alignment for the column
    + possible aligments: `l`: left-aligned , `c`: centered , `r`: right-aligned

> *Example (with captions):*
> ```Latex
\begin{stripedacenttable}
    {A plain but nice looking table}
    {\label{tab:ex1}}
    {c^l^l}
    {Quarter & asdf & foobar}
    prev. Year & 42 & 17 \\
    Q1 & -3 & -7 \\
    Q2 & +7 & -1 \\
    Q3 & -4 & +12 \\
    Q4 & +2 & +2 \\
\end{stripedacenttable}

>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Ut purus elit, vestibulum ut, placerat ac, adipiscing vitae, felis.

>\begin{stripedtable}
    {A colorful, nice looking table}
    {\label{tab:ex1}}
    {Green}
    {c^l^l}
    {Quarter & asdf & foobar}
    prev. Year & 42 & 17 \\
    Q1 & -3 & -7 \\
    Q2 & +7 & -1 \\
    Q3 & -4 & +12 \\
    Q4 & +2 & +2 \\
\end{stripedtable}
```

> <img alt="Tables" src="http://i.imgur.com/8FzhRYr.png" width="65%">


#### Code Listings
```Latex
\begin{lstlisting}[
    caption={<description of your program>}
    \label{lst:<label>},
    captionpos=b,
    language=<language-name>
]
<your code>
\end{lstlisting}
```

> *Example:*

> ```Latex
\begin{lstlisting}[
    caption={The Classic, realized in Python}
    \label{lst:python1},
    captionpos=b,
    language=Python
]
> # classic
>
> hi = "Hello Wolrd"
print(hi)
\end{lstlisting}
```

> <img alt="Code Lisitng" src="http://i.imgur.com/8zXqzOZ.png" width="70%">


#### Citations in the Footnotes
````Latex
\footnotecite{<source-reference>}
```


#### Mark Incomplete Things You Need To Do
````Latex
\incompletemarker{<note>}
```

> <img alt="Code Lisitng" src="http://i.imgur.com/eSQSoao.png" width="40%">


#### Prevent Pagebreaks absolutely, definitively
```Latex
\begin{absolutelynopagebreak}
    <content>
\end{absolutelynopagebreak}
```



---



## Contributing
I'm open for all forks, feedback and Pull Requests ;)
