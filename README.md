[//]: # (generated using SlashBack 0.2.0)

![SlashBack](Icon/SlashBackCropped.svg)  
## An unsurprising markup language  
SlashBack attempts to make **professional** documentation **easier**\.  
If you ever wanted your **text** to appear **exactly as you wrote it**,  
**SlashBack is for you\!**  
  
The **only character** you need to tell **SlashBack** what to do, is **backslash** \(``` \ ```\)  
It's your **universal tool** to **style your text\!**  
  
  
* **No characters that suddenly vanish** \(or produce unexpected text formatting\)  
* **No cumbersome trickery** to make **indents** or **multiple spaces** \(like "&nbsp;&nbsp;&nbsp;&nbsp;"\)  
* **No need for escape characters** \(the only character you can escape is backslash\)  
  
  
# Using SlashBack  
## Syntax  
**SlashBack**'s syntax is **similar** to the syntax of **HTML**\.  
  
Every **text snippet** that's supposed to be displayed in a **given format** has to be **surrounded by a start and end tag**\.  
Every **tag** in turn has to be surrounded by backslashes\.  
In other words, a tag begins with a backslash and ends with one\.  
Example:  
&nbsp;&nbsp;&nbsp;&nbsp;Given you want to put a strong emphasis on the word "**money**"\.  
&nbsp;&nbsp;&nbsp;&nbsp;You can do so by writing ``` \b\money\b\ ```\.  
&nbsp;&nbsp;&nbsp;&nbsp;The "``` b ```"\-tag stands for **bold**\.  
&nbsp;&nbsp;&nbsp;&nbsp;  
To make it easier to **differentiate** between **start and end tags**, you can put **spaces** **after** start tags and **before** end tags, like so:  
``` This text is \b \important\ b\. ```  
  
Alternatively, tags can be **prefixed** with one \(or multiple\) of the following **symbols**: ``` !#/:|+.~>_< ``` \(i\.e\. these symbols can precede tag identifiers\)\. One example could be:  
``` This text is \+b\important\~b\. ```  
  
## Tags  
The following tags are supported:  
### Headers  
SlashBack supports six different header sizes:  
``` h1 ```, ``` h2 ```, ``` h3 ```, ``` h4 ```, ``` h5 ``` and ``` h6 ```  
Examples:  
# Header size 1 \(``` \h1 \Header size 1\ h1\ ```\)  
## Header size 2 \(``` \h2 \Header size 2\ h2\ ```\)  
### Header size 3 \(``` \h3 \Header size 3\ h3\ ```\)  
#### Header size 4 \(``` \h4 \Header size 4\ h4\ ```\)  
##### Header size 5 \(``` \h5 \Header size 5\ h5\ ```\)  
###### Header size 6 \(``` \h6 \Header size 6\ h6\ ```\)  
  
### Text formatting tags  
SlashBack supports only four different types of text formatting:  
  
* ``` b ``` \- **Bold** \(or **strong**\)  
* ``` i ``` \- *Italic*  
* ``` s ``` \- ~~Strikethrough~~  
* ``` u ``` \- <u>Underline</u>  
  
**And *any* ~~com<u>bi*n</u>ation*~~ of them**  
  
### Code snippets  
You can put code in your documentation using the ``` code ``` tag\.  
If you need multiline code, simply put a ``` code ``` tag in the lines before and after the code segment\.  
For multiline code you can even specify a programming language after the initial code tag\.  
Example:  
``` 
\code python \
import this
print("interesting...")
\ code\
 ```  
becomes  
``` python
import this
print("interesting...")
 ```  
  
A list of language IDs can be found over [here](https://github.com/jmm/gfm-lang-ids/wiki/GitHub-Flavored-Markdown-(GFM)-language-IDs)\.  
  
### Hyperlinks \(URLs, sections\)  
If you want to reference other websites or link to a specific section of your documentation, you can use the ``` url ``` tag\.  
The specified target could either be a real url \(or relative link\), such as [a useless website](ismycomputeron.com):  
``` \url ismycomputeron.com \a useless website\ url\ ```  
Alternatively, it can be a [link](#hyperlinks-urls-sections) to a header in your document:  
``` \url #hyperlinks-urls-sections \link\ url\ ```  
  
### Quotes  
>"To use quotes, thou must use the ``` quote ``` tag"  
&#126; The Author

  
Alternatively the ``` q ``` tag can be used\.  
  
### Images  
Images can be embedded using the ``` image ``` tag, like so:  
``` 
\image https://raw.githubusercontent.com/Zuzu-Typ/SlashBack/future/Icon/SB.svg?sanitize=true \Broken Image \ image\
 ```  
![Broken Image ](https://raw.githubusercontent.com/Zuzu-Typ/SlashBack/future/Icon/SB.svg?sanitize=true)  
\(in this case *Broken Image* will be displayed if the image couldn't be found\)  
  
You can alternatively use the ``` img ``` tag\.  
  
### Tasks  
- [x] Need to add support for tasks

  
Tasks can be created using the ``` task ``` tag\.  
Each ``` task ``` tag has to be defined as **checked** or **unchecked**\.  
You can use ``` task checked ```, ``` tc ``` or ``` x ``` for checked tasks  
and ``` task unchecked ```, ``` tu ``` or ``` o ``` for unchecked tasks\.  
In all of those cases, the end tag can be just ``` task ```\.  
  
### Lists  
  
* To create lists, you have to use the ``` list ``` tag\.  
   
    1. A list can either be **ordered** or **unordered**\.  
   
        * The start\-tag of an ordered list can be any of:  
   
            1. ``` list ordered ```  
            2. ``` lo ```  
            3. and ``` ol ```  
   
        * The start\-tag of an unordered list can be any of:  
   
            1. ``` list unordered ```  
            2. ``` lu ```  
            3. and ``` ul ```  
    2. A list entry can be added using dashes \(``` - ```\)\.  
   
        * The **amount of dashes** translates to the **indent depth** \(i\.e\. how far right the text is displayed\)  
        * This entry for example has depth **3** \- so it has three dashes \(``` --- ```\)\.  
   
    3. You can **switch** between **ordered** and **unordered** lists using the ``` list switch ```, ``` ls ``` or ``` sl ``` command\.  
    4. The **end tag** of a list can be ``` list ``` or any of the start tags\.  
  
Example:  
``` 
\list ordered \
\-\Install Python
\list switch\
\--\Go to \url http://python.org \python.org\ url\
\list switch\
\-\Run SlashBack.py
\-\Enjoy.
\ list\
 ```  
  
1. Install Python  
  
    * Go to [python\.org](http://python.org)  
  
2. Run SlashBack\.py  
3. Enjoy\.  
  
  
### Tables  

Tag|Usage
-|-
``` table ```|Start and end tag for tables\.
``` tbl ```|Same as ``` table ```
``` - ```|Table separator
  
For tables, each **line** of SlashBack code translates to one **row** in the table\.  
The **table separator** is used to separate **columns** of each row\.  
The **first line** of each table in SlashBack code will be used as the **titles** of the columns\.  
Example:  
``` 
\table \
USB connector \-\ Typical use                   \-\ Flippable
A             \-\ Desktop computers and laptops \-\ No
B             \-\ External devices              \-\ No
C             \-\ Anything                      \-\ Yes
\ table\
 ```  

USB connector | Typical use                   | Flippable
-|-|-
A             | Desktop computers and laptops | No
B             | External devices              | No
C             | Anything                      | Yes
  
  
### Raw Markdown  
Should you ever come across something that can't be done with SlashBack, please create a [new issue](https://github.com/Zuzu-Typ/SlashBack/issues)\.  
Until the feature is added \(or if it is not added\), you can use the ``` raw ``` tag\.  
Example:  
``` 
\raw \<font face="verdana" color="green" size=5em>This text may be green (but not on GitHub)</font>\ raw\
 ```  
<font face="verdana" color="green" size=5em>This text may be green (but not on GitHub)</font>  
  
### Comments  
You can add **comments** to your documentation using the ``` comment ``` or ``` c ``` tag\.  
If you want your **comments** to also be included in your **output markdown file** \(but not in the final HTML\), you may use the ``` icomment ``` or ``` ic ``` tag\.  
  
&nbsp;  
  
For reference, look at [README\.sb](https://github.com/Zuzu-Typ/SlashBack/blob/master/README.sb)\.  
  
This very README was composed in SlashBack \(:  
  
