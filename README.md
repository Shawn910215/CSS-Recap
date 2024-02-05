## P18

css Entity reference &...;

##P23
list selector: use commas to seperate them.
-h1,h2,h3,{property:value}

Descendent selector: use SPACE to seperate parent and children element.

- footer p {property:value}
- article footer p {property:value}

P24 always use Class selector instead of Id selector.

P25 work with colors
-RGB(255,255,255)
-rgba(255,255,255,0.6)
-hexadecimal notation 0 to ff(255)
--#ffffff
--#444
-when colors in all 3 channels arethe same, we get a gery color!

P26
Pseudo class
-li:first-child{property:value}
-li:last-child{property:value}
-li:nth-child(3){property:value}
-li:nth-child(odd){property:value}
-li:nth-child(even){property:value}

-artical p:first-child{:} not good,do not use .

P27 styling links
-a:link{text-decoration:none} style <a> who has a href property.
-a:visited{:}
-a:hover{:}
-a:active{:} the moment click the link;
/LVHA link,visited,hover,active/

P29
conflicts between selectors.
-priority:
-- !important keyword > Inline style > ID > class(psuedo class)> element selector > "\*" universal selector

always write selecotrs as simple as possible, not too much nesting!!

P30 inheritance
-usually the properties related to text will be inheritance.
-for example: border property will not be inheritance.
-property in child element will override the property that they inheritance

\*{
universal selector will apply to every element.
not inheritance,just work on every element.
}

P32 The CSS Box Model
-Content: width, height
-border
-padding
-margin
-fill area: filled with bg-color or bg-image

the content+border+padding are visible parts of elements.

P33 Using margins and paddings.
\*{
//use universal selecter to reset margin and padding is quite common. And it is easy to be override by other selectors.

margin:0;
padding:0;
}

-use margin-bottom to create vertical space
-bg-color --- padding.

P34 Adding dimentions
.post-images{
width:100%; // the percentage of parent box
}

//a div contain all the elements called container.
.container{
width:700px;
margin:0 auto; allow the whole page always center.
}

P37 Types of Boxes
-inline boxes (can side by side)
--heights and width do not apply
--padding and margin are only applied horizontally.

-block level box
--100% of width of parent box.
--stacked vertically.
can use display: inline/block to change the type of box.

-\*\*inline-block
--display:inline-block
--looks line inline box from outside, but can apply vertical change.
example:
nav a:link{
display:inline-block;
margin-right:10px;
margin-top:10px;
}

nav a:link:last-child{
margin-right:0;
}

P38 Absolute position(use this for small button etc. do not abuse it. )
-Normal flow: default position; position:relative
-Absolute Positioning:
--make this element "out of flow";
--no impact on surrounding elements,might overlap other elements.
example:

button{
position:absolute;
top:10px;
left:10px;
// these values can decide the position of it's relative position container, so next must set the parent to relative.
}

.container{
//this element should be the first parent container of button,set the position to relative
position:relative;

}

P39 Pseudo elements
//use following to style first letter.
h1::first-letter{
font-style:normal;
margin-right:5px
}

//style first line
p::first-line{
color:red
}

//adjacent sibling selector, use "+"
h3 + p::first-line{
//now select the first line of p after each h3.
}

//after pseudo selector:
h2::after{
content:"TOP";
background-color:#ffe70e;
font-size:16px;
font-weight:bold;
display:inline-block;// to make after pseudo element from inline to inline-box, to add paddings.
padding:5px 10px;
position:absolute;
top:-15px;
right:-25px;
}

P40 Developer Skills
-Search Google or MSN documents
-Debug

P42 Challenge.
//for link element, if you want to add margin-bottom, must change display:inline-box.

///////////////////////
P44 Layout!
Page Layout & Components Layout!
-Float Layouts (old way)
---float:left / float:right
---When use float, the element will be took out of document flow,but unlike absolute positioning, it will has effect on adjacent element.
---if all the child elements be floated. the parent will has no height, because as if they have been removed. this is called collapse
--- need to add a empty div and use clear:left/right/both to make it not collapse .clear{clear:both}(outdated)
---add a clearfix class name to the parent element. then .clearfix::after{
clear:both;
content:'';
display:block;
}

–––––––––––––––––––––

P48 box-sizing:border-box
this property is very important, it makes the width and height property include the content and padding(it was applied on content only original). so when you add the padding, it will reduce the width of content to make the total width not changed.
so put this property to universal selector!!!
-------------------––––––––
-Flex Box
--1-dimensional row
--empty space inside container can be automatically divided by its child elements.
--Flex container and Flex items
--Main axis and cross axis
--For container : gap:0;

## P53 Flex property

--flex-grow:<number [0,∞]>; to assign the remaining space of parent element.
----give flex items same flex:1; ensure their width are identical.
--flex-shrink:0/1; 1 means the flex items can adjust their width by content or width parent container.
--flex-basis:200px; // use this to determin the width of flex items instead of "width"

--for flex item: align-self:flex-start...

combine there 3 with flex property
flex:grow,shrink,basis;
example:flex:1 1 auto;
–––––––––––––––––––––––––
P57
-CSS Grid
--2-dimensional grid
--container: display:grid; grid-template-columns:200px 200px 300px; grid-template-rows:300px 200px; gap:30px;column-gap/row-gap;repeat(4,1fr);
--grid lines: lines between grid cells.
--gutters(gaps): space between grid items.
--grid tracks(row/column): space between two adjacent grid lines.
--for grid items: grid-column :1/2; grid-row:1/ span 2; grid-column: 1/-1;(from 1 to the end)
--aligning tracks inside container: justify-content:; align-content:;
--aligning items inside cells:
align-items:; justify-items:;
--for individual items, they can align themselves: align-self:; justify-self:;

P64 Web Design!!!
