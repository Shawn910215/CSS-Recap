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
--looks inline box from outside, but can apply vertical change.
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

P66 Design and development

P67 Rules #1 Typography
1.Serif
-Traditional and class looking

2.Sans-Serif
-clean and simple

3. Use good typefaces
   1.Only use good and popular typefaces
   --Inter,Open Sans, Roboto,Montserrat,Work Sans
   2.use one typeface per page!limit to 2.
   3.less than 75 characters per line.
   4.font size between 16-32px for normal text
   5.long text 20px or bigger to make it easy to read
   6.headlines, go really big 50px+ and bold(600+)
   7.for any text, do not use a font weight under 400.
   8.for normal text,line height between 1.5-2. For big text, go below 1.5
   9.Decrease letter spacing in headlines, if it looks unnatural.
   10.Experiment with all caps for short titles.make them samll and bold and increase letter-spacing.
   11.Usually, don't justify text.
   12.Don't center long text blocks. Small blocks are fine.

P69 Web Design Rules#2 Colors
1.Open color,Tailwindcss,palleton.com,coolors,Tint & Shade Generator. -well designed color to choose.
2.two types of colors in your color palette: main and grey(dark version of main)
3.with more experience, you can add more colors:accent colors(use a tool)
4.for diversity, create lighter and darker versions(tints and shades)
5.Use main colors to draw attention to the most important elements on the page(logo, button etc.)
6.use colors to add interesting accents to make entire components or sections stand out.
7.try to use color strategically in images and illustrations
8.on dark colored background, try to use a tint of the background("lighter version") for text
9.Text should usually not be completely black. Lighten if up it looks heavy and uninviting.
11.Do not make text too light! use a tool to check contrast between text and background colors:
--contrast ratio needs to be at least 4.5:1 for normal text and 3:1 for large text(18px+)

P71 Rules#3 Images and Illustrations
1.different types of images: product photos, storytelling photos,illustrations,patterns
2.Use images to support your website's message and story. So only use relevant images!
3.Prefer original images. if not possible, use original-looking stock images(not generic ones)
4.Image tools: Unsplash,Pexels,DrawKit,unDraw 5. Try to show real people to trigger user's emotions
6.if necessary, crop images to fit your message.
7.Handling Text on images
7.1 Darker or brighten image(completely or partially, using a gradient)
7.2Position text into neutral image area.
7.3 Put text in a box. 8. To account for high-res screens, make image dimensions 2x as big as their displayed size
9.Compress images for a lower file size and better performance(use Squoosh tool to compress images.😁)
10.When using multiple images side-by-side,make sure they have the exact same dimensions.

P72 Rules#4 Icons
1.Use a good icon pack, there are tons of gree and paid icons packs(Phosphor icons,ionicons,icons8)
2.Use only one icon pack. Do not mix icons from different icon packs.
3.Use SVG icons or icon fonts. Do not use bitmap image formats(.jpg and .png).
4.Adjust to website personality!Roundness,weight and filled/outlined depend on typography.
5.Use icons to provide visual assistance to text.
6.Use icons for product feature blocks
7.Use icons associated with actions, and label them
8.Use icons as bullet points.
9.1 To keep icons neutral, use same color as text. To draw more attention, use different color.
9.2 Do not confuse your users: icons need to make sense and fit the text or action!
9.3 Do not make icons larger that what they were designed for. if needed, enclose them in a shape.

P73: use online tools to copy svg(ex.heroicons) to the list.
Use multiple cursors: press option(alt) key when select multiple svg codes. and to the place you want to paste. do it again.

P74 Rule#5 shadows
1.After an era of 100% flat design, we're now back to using shadows in UI design("flat design 2.0")
2.Shadow creates depth(3D): the more shadow, the further away from the interface the element is
3.1 You don't have to use shadows! Only use them if it makes sense for the website personality.

---

## Serious/Elegant less shadows while Playful/fun more shadows.

3.2 Use shadows in small doses: don't add shadows to every element!
3.3 Go light on shadows, don't make them too dark!
3.4 Use small shadows for smaller elements that should stand out(to draw attention)
example: buttons,contact input box...
3.5 Use mediun-sized shadows for larger areas that should stand out a bit more. (carts)
3.6 Use large shadows for elements that should really float above the interface.(pop up windows or navigation dropdown)
3.7 Experiment with changing shadows on mouse interaction(click and hover)(example: hover medium-sized shadow, click smaller sized shadow)
3.8 Experiment with glows(color shadows)

P76 Rule#6 Border-radius
1.Use border-radius to increase the playfulness and fun of the design, to make it less serious
2.Typefaces have a certain roundness: make sure that border-radius matches that roundness!
3.Use border-radius on buttons,images,around icons,standout sections and other elements

P78 Rules#7 Whitespace
1.the right amount of whitespace makes designs look clean,modern and polished
2.whitespace implies invisible relationships between the elements of a layout
3.Use tons of whitespace between sections.
4.Use a lot of whitespace between groups of elements.
5.Use whitespace between elements
6.Inside groups of elements, try to use whitespace instead of lines.
7.The more some elements belong together, the closer they should be!
8.Start with a lot of whitespace, then remove whitespace from there.
9.Match other design choices.If you have big text or big icons, you need more whitespace.
10.Try a hard rule, such as using multiples of 16px for all spaceing.

P79 Rules#8 Visual Hierarchy
1.Visual hierarchy is about establishing which elements of a design are the most important ones.
2.Visual hierarchy is about drawing attention to these most important elements.
3.Visual hierarchy is about defining a "path" for users, to guide them through the page.
4.We use a combination of position,size,colors,spacing,borders and shadows to establish a meaningful visual hierarchy betwee elements/components.

5.Position important elements closer to the of the page. where they get more attention.
6.Images draw a lot of attention(larger images get more attention)
7.Use whitespace strategically to emphasize elements.
8.For text elements, use font size, font weight, color and whitespace to convery importance.
9.Emphasize Title,sub-titles,links,buttons,data points,icons; De-emphasize less important text, like labels or secondary/additional informations.

10.Emphasize an important component using background color, shadow, or border.
11.Try emphasizing some component A over component B by de-emphasizing component B.
12 Components to emphasize:Testmonials,call-to-action sections,highlight sections,preview cards,forms,pricing tables,important rows/columns in tables,etc.

P80 Rule#8 UI and UX
1.Do not design complicated layouts. Do not reinvent the wheel. Use patterns that users know.
2.Make your call-to-action the most prominent element, and make the text descriptive
3.Use blue text and underlined text only for links!
4.Animations should have a purpose and be fast: between 200 and 500ms 5. In forms,align labels and fields in a single vertical line, to make the form easier to scan
6.Offer users good feedback for all actions: form errors, form success,etc.[Web apps]
7.Place action buttons where they will create an effect(law of locality)[web apps]

UX rules for website content:
8.Use a descriptive,keyword-focused headline on hour main page. Do not be vague or fancy!
9.Only include relevant information, efficientlya1 Cut out fluff and make the content 100% clear.
10.Use simple words! Avoid technical jargon and "smart-sounding" words.
11.Bread up long text with sub-headings,images,block quotes, bullet points,etc.

P82.The website-personalities-Framework
Q1:How do you want website to appear to users? What "vibe" do you want to transmit?
A1:Choose one of the website personalities accordingly

------The 7 Personalities------
1.Serious/Elegant
2.Minimalist/Simple
3.Plain/Neutral
4.Bold/Confident
5.Calm/Peaceful
6.Startup/Upbeat
7.Playful/Fun

P83.Steal like an artist
Not completely copying a design!
Taking good parts and adapting them to our needs.

get inspiration from following website:

Land-book.com
awwwards.com
screenlane.com
onepagelove.com

New section
P85 Rule#10. Elements and components
From Elements to Webpage
Elements==>Components==>Layouts==>webpage

1. Use common elements and components to convey your website's information
   2.Combine comonents into layouts using common layout patterns
   3.Assemble different layout areas into a complete, final page
