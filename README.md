This is a community driven vegan cookbook, we aim to cover as much information as we can, and to be as light on the wallet as possible.

### Requirements:
* latex
* bibLaTeX + biber 
* git - to clone this repository
* a PDF viewer
* a text editor



### building:
To build the entire document as one PDF run the following script from the scripts directory `build-all.sh` on \*nix systems, or on windows run `build-all.bat`

To build an indivual page run the following script from the scripts directory `build-page.sh tex-pages/file.tex` on \*nix systems, or on windows run `build-page.bat tex-pages/file.tex`

Inorder to clean the build envrionment and remove documents generated during compilation, ethier for tidyness, or if you wish to submit to the upstream git tree, you should run the following script from the script folder `clean.sh` on \*nix systems, or on windows run this bat script `clean.bat`

### customizations:
To increase the font size, you can open `main.tex` and chnage the `12pt` on the first line to something diffrent.

### for authors:

This section is intended to help the authors with content incluision, however if you wish to become an author too following the becoming an author instructions.

## adding a new topic:
To add a new topic, simply in `main.tex` find the document content and add the following line at the bottom of the other included documents `\subfile{tex-files/filename.tex}` where filename is the actual name of the LaTeX file.

OPen this file in a text editor, and add the following content
```\documentcladd[main.tex]{subfiles}
\begin{document}
% content goes here
\end{document}
```
 and add you're content under the `% content goes here` line.

## images:
You can include images like so into the external latex document `\includegraphics{imagesname}` which will insert an image into the current possition on the page, this can look kinda ehh at times, so i would use the following format `\includegraphics[width=\textwidth]{imagenme}` this will make the image be the same width as the text is, you can also add `scale=` if you wish like so `[scale=scale_value,width=\textwidth]` where `scale_value` is a number, such as 0.5 etc.

## lists:

To add a numbered list into you're document, simpley add the following lines to the document
```
\begin{enumerate}
\item you're item here
...
\end{enumerate}
```

To add bullet pointed listed, in a similar way, you can add the following lines to you're document:
```
\begin{itemize}
\item you're item here
...
\end{itemize}
```

You can use these inside of eachother to get number lists, with sublists that are bullet pointed, and vice versa.

## tables:
There are many diffrent ways of using tables, and diffrent ways to format cells, this will briefly cover the common ways of accomplishing them.

This is the standard way to add tables, i do not like this way personally, as the tables can go off the page if they are too long.
```
\begin{tabular}{|l|c|r}
left aligned & centered & right aligned \\
another row & more centered & more right \\
\end{tabular}
```

This way can work for longer single worded tables:
```\begin{tabular*}{\textwidth}{|l|c|r}
same & deal & as before \\
...
\end{tabular*}
```

This way is better suited to longer blocks of text:
```\begin{tabularx}{\textwidth}{|X|X|X|}
aligned text & to the & width of the text \\
...
\end{tabularx}
```

## sections and subsections:
These can be added like so for sections `\section{section name}` and `\subsection{subsection name` for subsections.

## refrences:
To add a refrence is a little more work then the above listed items, but still fairly easy to do. To start with open up the `bibliography.bib` file in a text editor, and add the following to the bottom of the file
```
@misc{somename,
	title = website_title,
		howpublished = {\url{website_url_here}}
		}
```
then in the `main.tex` file towards the bottom, add the following line `\nocite{somename}` where somename is the name you gave the citeation in the bibligorapy file.

### becoming a author:
there is no registration, as this is a community project, just simply, go to the author section in `main.tex` and add you're name, and any contact information you want to be public, followed by a \\ for example `baby-princess \\` then just start working on whatever topic you see fit, then simply include it as mentioned above, and look at the author documentation above for some pointers.
