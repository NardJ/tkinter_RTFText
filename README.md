# Tkinter widget to display Rich Formatted Text (rtf)

This widget is based on the tkinter.Text widget.
The rtf-text should be formatted using html-like commands between '<'/'>'-brackets.
Line endings are parsed as html linebreaks ```<BR>```. Links, Images and Tables are not available.

The following commands act the same as in standard html:
~~~
<H1> ... </H1>                    text size 18 pt
<H2> ... </H2>                    text size 15 pt
<H3> ... </H3>                    text size 12 pt
<H4> ... </H4>                    text size 10 pt
<b>  ... </b>                     bold
<i>  ... </i>                     italic
<u>  ... <u>                      underline
<center> ... </center>            center
~~~

The following custom commands are present
~~~
<family:...> ... </family>        font name
<size:...>   ... </font>          font size
<color:...>  ... </color>         text color (use colornames like 'red', without quotes)
<background...> ...</background>  text background color
<code> ... <code>                 set text to monospaced and 10 pt
<codei>... <codei>                same, but with lightgrey background
<hr> ...
...</hr>                          horizontal rule
~~~
