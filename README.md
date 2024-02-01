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
