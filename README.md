# sublime-text-editor-trick
## Sublime Text Editor Handful Trick

### Ctrl = Control Key = ^ (Sign) is equivalent to Cmd key in Mac
### Alt = Alter Key is equivalent to Option key in Mac

1.	Ctrl +D = multiple selection of a text (Cmd+D in Mac)
2.	Ctrl+Shift+L =Convert  a multiline text into multiple single line end selection
3.	Alt+Shift+W = Wrapup a given text with html start and end tag                                       
e.g., 
Given text for selection
* a.	Select all by Ctrl+A
* b.	Ctrl+Shift+L
* c.	Alt+Shift+W
* The output will be: 
```html
<p>Given text for selection</p>
```

4.	Ctrl+Shift+L = Duplicate content
5.	Ctrl+Shift+[ = code fold
6.	Ctrl+Shift+] = code unfold
7.	Ctrl +[ = left indent a line
8.	Ctrl +] = right indent a line
9.	Ctrl+Shift+UpArrow or DownArrow = Move  a line up or down 

e.g.,
* a. place the anywhere in a line which you want to move
* b. Ctrl+Shift+UpArrow  to move the whole line up

10.	Ctrl+Shift+K = delete a whole line

e.g.,
* a. place the anywhere in a line which you want to move
* b. Ctrl+Shift+K  to delete a whole line 

11.	 Re-indent entire text

e.g.,
* a. Select all by Ctrl+A
* b. Goto Edit->Line->Reindent

12.	Intelligent paste
Ctrl+Shift+V to paste the text as it is(with same indentation)

**N.B:** Let’s imagine we want to copy and paste someone else’s html div and other tag and we will lose the indentation and the above trick will save us from that situation.

13.	Tagging each html line to custom tagging

* a.	Select all by Ctrl+A
* b.	Ctrl+Shift+L
* c.	Alt+Shift+W
* d.	Type your desired html tag and voilla!

14.	Convert to upper case letter Ctrl +K then Ctrl +U
15.	Convert to lower case letter Ctrl +K then Ctrl +L
16.	 Column selection tool

* a.	Shift+right click+drag(in windows) or Alt+left click+drag(in Mac)
* b.	Shift+ctrl+G

17.	Ctrl+P = open a file Navigation

* a. @ open function
* b. # select word
* c. @.  Open class
* d. : open line number

18. Ctrl+Shift+P = open command pallet
19. F9 = for sorting
20. Ctrl+F9 = for case sorting
21. Ctrl+Q record an action(macro)
22. Key binding for reindent

* Goto->Preferences->Key Bindings 
* Then open file default.sublime-keymap
* Put a coma and paste the following line
```
{ "keys": ["ctrl+shift+l"], "command": "split_selection_into_lines" }
```
Final output will be:
```
[
	{ "keys": ["ctrl+shift+l"], "command": "split_selection_into_lines" },
	{ "keys": ["ctrl+shift+i"], "command": "reindent" }
]
```

**23. emmet snippet tab completion**

* a. fun+tab gives function
* b. ife+tab gives if else clause
* c. if+tab gives if clause
* d. !+tab gives html5
* e. art+tab gives article
* f. foot+tab gives footer
* g. .banner+tab gives 
`
```html
<div class="banner"></div>
```
* h .banner|c+tab gives 
```html
<div class="banner"></div>
<!-- /.banner -->
```
* i ul>li+tab gives 
```html
<ul>
	<li></li>
</ul>
```
* j.	ul>li.item-$*10>a+tab gives 
```html
<ul>
	<li class="item-1"><a href=""></a></li>
	<li class="item-2"><a href=""></a></li>
	<li class="item-3"><a href=""></a></li>
	<li class="item-4"><a href=""></a></li>
	<li class="item-5"><a href=""></a></li>
	<li class="item-6"><a href=""></a></li>
	<li class="item-7"><a href=""></a></li>
	<li class="item-8"><a href=""></a></li>
	<li class="item-9"><a href=""></a></li>
	<li class="item-10"><a href=""></a></li>
</ul>
```
* k.	ul>li#item-$$*5>a gives
```html
<ul>
	<li id="item-01"><a href=""></a></li>
	<li id="item-02"><a href=""></a></li>
	<li id="item-03"><a href=""></a></li>
	<li id="item-04"><a href=""></a></li>
	<li id="item-05"><a href=""></a></li>
</ul>
```

## create your own customize snippet
### How to create your own custom snippet in Sublime Text Code Editor

1.	Open Tools -> Developer -> New Snippet……
2.	It will open this:

**STEP 1:**

```
<snippet>
	<content><![CDATA[
Hello, ${1:this} is a ${2:snippet}.
]]></content>
	<!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
	<!--<tabTrigger>hello</tabTrigger> -->
	<!-- Optional: Set a scope to limit where the snippet will trigger -->
	<!--<scope>source.python</scope> -->
</snippet>
```
**STEP 2:**

```
Replace  {Hello, ${1:this} is a ${2:snippet}.}  the code within braces with your snippet
```

**STEP 3:** uncomment 

```
<!--<tabTrigger>hello</tabTrigger> -->
```

**STEP 4:** save the file with anything you like but with the following extension .sublime-snippet
**STEP 5: ** uncomment this and replace source.python with text.html
```
<!--<scope>source.python</scope> -->
```
e.g., 
```
<scope>text.html</scope>
```

**STEP 6:**  type the word between tabTrigger  like <tabTrigger>hello</tabTrigger>
e.g., hello and press tab

**STEP 7:** you will get the snippet


**Example 1: div with class and start and end comment**

```
<snippet>
	<content><![CDATA[
	<!-- $1 div start -->
	<div class="$1">
		$2${3}
	</div><!-- ${1/\*//} div end -->${4}
	$0
]]></content>
	<!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
	<tabTrigger>d</tabTrigger>
	<!-- Optional: Set a scope to limit where the snippet will trigger -->
	<scope>text.html</scope>
</snippet>
```

**Example 2: html form**

```
<snippet>
	<content><![CDATA[
<form method="${1:get}" action="${2: }">
	<label for="$3">$3</label>
	<input type="${4:text}" name="$3" id="$3"><br>
	$0
	<input type="submit" value="Submit">
</form>
]]></content>
	<!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
	<tabTrigger>frm</tabTrigger>
	<!-- Optional: Set a scope to limit where the snippet will trigger -->
	<scope>text.html</scope>
</snippet>
```

**Example 3: html variable form input**

```
<snippet>
	<content><![CDATA[
<label for="$1">$1</label>
<input type="${2:text}" name="$1" id="$1"><br>
]]></content>
	<!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
	<tabTrigger>imp</tabTrigger>
	<!-- Optional: Set a scope to limit where the snippet will trigger -->
	<scope>text.html</scope>
</snippet>
```
