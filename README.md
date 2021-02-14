# Tkinter RTF widget 

This widget is based on the tkinter.Text widget and displays rich formatted text (rtf).
The rtf-text should be formatted using html-like commands between '<'/'>'-brackets.
Line endings are parsed as html linebreaks ```<BR>```. Links, Images and Tables are not available.

### Supported formatting

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

### Example

~~~
import tkinter as tk
from tkRTFText import RTFText 
   
# Create window
root=tk.Tk()   
root.configure(background='white')

# Add widget RTFText
RTF=RTFText(root,bg='white')#root,bg="white")
RTF.pack(side=tk.TOP, fill=tk.BOTH,padx=(0,0),pady=(2,2))

# Make some rtf/'html' to display
rtf=("<family:verdana>Verdana <size:14>14pt</size> <size:18>18pt</size></family>\n"+
    "<color:red>red text</color>\n<background:yellow>yellow background</background>\n"+
    "<H1>Header</H1>\n<H2>Header</H2>\n<H3>Header</H3>\n<H4>Header </H4>\n"+
    "<b>Bold</b>\n<i>Italic</i>\n<u>Underscore</u>\n"+
    "<b>Bold <i>and italic</i> </b>\n"+
    "<center>Text can also be centered </center>\n"+
    "Page divider below:\n"+
    "<hr>\n"+
    "</hr>\n"+
    "Page divider above")    

# Set rtf to widget
RTF.setRTF(rtf,pad=(8,8),bg='white', font=tkf.Font(family='Terminal', weight = 'normal', size = 9))

# Display window and wait user actions
root.mainloop()
~~~
