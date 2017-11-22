# What is SASS

---

### SASS stands for Syntactically Awesome Style Sheets.

- <span style="font-size:.8em;">Syntactical meaning that the structure is supposed to be more logical, easier to read</span>
- <span style="font-size:.8em;">Awesome because it’s just plain great.</span>
- <span style="font-size:.8em;">Style Sheets because it helps define the layout of the website.</span>


Note: 

---

- It is a language that sits on top of CSS and attempts to make style codes look cleaner and more descriptive.

- It is an interpreted language. Meaning, that it is not stand-alone like CSS. It needs to be compiled on run time.


---

# HOW IS IT DIFFERENT FROM PLAIN CSS?

---

From a coding perspective, there is no difference from CSS and SASS. You can use exactly the same CSS codes as you do for SASS codes.

What it does is that it enhances CSS codes so that it will look cleaner and in some cases, saves time by re-using often-used codes.

Much like this guy.
<div style="transform:scale(.6,.6);">
![alt text](img/sass/Picture1.png "Logo Title Text 1")
</div>

---

## WHY DO WE NEED TO CONVERT OUR CSS TO SASS?

---

- It makes maintenance much easier. 
- We can turn off whole sections of codes to make the stylesheet size smaller.
- It makes the CSS codes flexible
- You can re-use styles
- It makes everything look more organized
- There’s little to no learning curve involved if all you want is a functional CSS.


---

<div style="transform:scale(1,1);">
![alt text](img/sass/Screenshot_3.png "Logo Title Text 1")
</div>

---

## HOW DID WE SEPARATE THE STYLE RULES INTO DIFFERENT FILES?

- As previously discussed, SASS makes the whole stylesheet more organized.

---

Consider this plain CSS code:
<div style="transform:scale(1,1);">
![alt text](img/sass/Screenshot_1.png "Logo Title Text 1")
</div>

---
Now take a look at the new SASS file:

<div style="transform:scale(1,1);">
![alt text](img/sass/Screenshot_2.png "Logo Title Text 1")
</div>

- Each section is now in its own file. It’s now easier to know where you can find the style rule.


---

- We used the folder architecture suggested in <a href="http://www.sass-guidelin.es" target="sass-link">www.sass-guidelin.es</a>
- The guideline suggests using one main stylesheet to link to other sass files.
- That main stylesheet is <span style="color:#ff9200;">common.scss</span>. All it contains are links to the other SASS files.
- There are 5 distinct folders that we use that stores the SASS files:

---

- components
- base
- layout
- pages
- abstract

---
```scss
sass/
|– abstracts/
|   |– *.scss             # Sass Variables, Mixins, Functions
|
|– base/
|   |– *.scss             # Reset/normalize, Typography rules
|
|– components/
|   |– *.scss             # Buttons, Carousel
|
|– layout/
|   |– *.scss             # Navigation, Header,Footer, Etc.
|
|– pages/
|   |– *.scss             # Page specific styles
|
`– common.scss              # Main Sass file
```
---
## SASS Architecture
### /Components

Will contain SASS files that contains styles related to displaying parts of a page.
Rules for modals, buttons, widgets will fall into this category.

---
## SASS Architecture
### /Base

Will contain SASS files that are related to fonts, resets, colors, etc

---
## SASS Architecture
### /Layout

Will contain SASS files that contains styles that gives a page its overall look.

Header, Footers, Navbars would be included in this folder.

---
## SASS Architecture
### /Pages
Contains style rules that are specific to a page.
---
## SASS Architecture
### /Abstract

 Will contain SASS files that doesn’t actually generate any CSS code, but contains important functions that are referred by the other files.

 Mixins and functions would be included here.

---

# SASS VARIABES

Sometimes, we’d want to re-use a certain property like color, font size, etc. and want to make sure that it applies to the whole site globally. 

---
For example, suppose we have a button, a div box, and an input form that uses the color orange (#ff9200).

```scss
button {
    background-color: #ff9200;
}

div {
    border:1px solid  #ff9200;
}

input {
    background-color:#ff9200;
}
```
---
- A few months later the user decides to change the color to #ff5200.

```scss
button {
    background-color: #ff9200;
}

/* HUNDREDS OF LINES OF CODES ADDED BETWEEN THE CODES DUE 
TO NUMEROUS CHANGE REQUESTS IN THE PAST*/

div {
    border:1px solid  #ff9200;
}

input {
    background-color: #ff9200;
}
```
- Normally, we’d have to find each and every CSS rules were we used the old value (#FF9200) and change it one by one. 

---
- With SASS, we can just assign that color to a variable:

```scss

$brand-orange: #ff9200;

button {
    background-color: $brand-orange;
}

/* HUNDREDS OF LINES OF CODES ADDED BETWEEN THE CODES DUE 
TO NUMEROUS CHANGE REQUESTS IN THE PAST*/

div {
    border:1px solid $brand-orange;
}

input {
    background-color: $brand-orange;
}

```
---

# ARRAYS

---

It is also possible to assign a variable to the selector, as well as assign multiple values to a single variable, making it an array:

```scss
$color-collection: red, orange;


    .color-#{nth($color-collection, 1)} {
        color: nth($color-collection, 1);
    }
    
        .color-#{nth($color-collection, 2)} {
        color: nth($color-collection, 2);
    }
```

<span style="font-size:.6em;">We use #{$variable} syntax if we want the variable to be inlined with the rest of the text.</span>

<span style="font-size:.6em;">Note that SASS arrays start at index 1 (not 0)</span>



===
This will compile to:
```scss
.color-red {  
	color: red;
}

.color-orange {  
	color: orange;
}
```

---

# NESTING

In SASS, you can nest CSS styles to make it more organized

---

So instead of writing it like this:

```scss
.link { text-decoration: none; color: #323232;}

.link.style-alt1 { color: #424242; }

.link.style-alt2 { color: #525252;}
```

You can write it like this:

```scss
.link { text-decoration: none; color: #323232;
          &.style-alt1 { color: #424242;}
          &.style-alt2 { color: #525252; }
       }
```
<span style="font-size:.6em;">Note that the & character means that SASS will remove the whitespace between .style-alt1 and .style-alt2 from .link, in effect, making it inline.</span>

===

Which is applicable to the HTML

```html 
<el class="link style-alt1">
</el>

```

---
If you remove the & character

```scss
.link { text-decoration: none; color: #323232;
          .style-alt1 { color: #424242;}
          .style-alt2 { color: #525252; }
       }
```
It will compile like this:

```scss
.link { text-decoration: none; color: #323232;}

.link
.style-alt1 { color: #424242; }

.link
.style-alt2 { color: #525252;}
```
===

Which is applicable to the HTML


```html 
<el class="link">
    <el class="style-alt1"></el>
</el>

```

---
# COLOR  
## MANIPULATION

Let's suppose you want to create a hover effect for a button. You want the hover effect to have lighter color, but you don't know what its HEX color is.
```scss
.link {
    color:red;
}
.link:hover {
    color: /*I don't know*/
}
```
---
In SASS, you just have to call in a built-in function:
```scss
.link {
    color:red;
    &:hover {
        color: lighten(red,10%); // will produce #ff3333
    }
}
```
===
or its opposite:
```scss
.link {
    color:red;
    &:hover {
        color: darken(red,10%); // will produce #cc0000
    }
}
```
---

# MIXINS

A mixin is a chunk of css rule that can be re-used throughout the stylesheet.

```scss
@mixin size($width, $height) {
  width: $width*1px; height: $height*1px;
}

.header {
  color:red;
  @include size(10,10);
}

```

Will compile to:
```scss
.header {
  color:red; width: 10px; height:10px;
}
```
---
# LOOPS

SASS also has the ability to create logical loops. 
---
So instead of writing it like this in CSS:
```scss
h1 { font-size: 1em; }
h2 { font-size: 2em; }
h3 { font-size: 3em; }
...
h6 { font-size: 6em; }
```
---

You can write it as:
```scss
@for $i from 1 through 6 {
    h#{$i} { font-size: $i*1em; }
}
```


---
# Advantages
---

- Switching to SASS will allow us to truly optimize the stylesheet in a way that is both highly maintainable and less error prone.
---
- In Mobile App CSS, for example, we were able to reduce the file size by <span style="color:lightgreen;">22%</span>. This is because we were able to remove a whole section of the stylesheet by simply commenting out one line of code from the main stylesheet.
---
- In Mobile Web, we were able to remove <span style="color:lightgreen;">18%</span> of the file size because it made it easier to see duplicate rules once the style rules were cut up into smaller chunks.
---
- In Desktop, we were able to save <span style="color:lightgreen;">16%</span> of the file size by removing unused or outdated rules.

---

# Q&A

---

# THANK YOU











