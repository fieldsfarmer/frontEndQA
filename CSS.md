###### positions
- static: default. positioned by the flow model
- relative: positioned relative to its normal position
- fixed: positioned relative to browser window; will not move when window is scrolled
- absolute: positioned relative to the first ancestor where position!=static
 
###### div vs span
- div: block element (p, h1, ..., h6, form)
- span: container of text, inline element (a, img)

###### shorthand
```css
p{
	padding-top: 50px;
    padding-right: 30px;
    padding-bottom: 50px;
    padding-left: 80px;
}
/* the order matters */
p{
	padding: 50px 30px 50px 80px;
}
p{
	padding: 50px 30px 80px; /*top 50px; right, left are 30px, bottom 80px*/
	padding: 50px 80px; /*top, bottom are 50px; left, right are 80px*/
	padding: 50px; /*all are 50px*/
}
```

###### group selectors
```css
h1 {
    text-align: center;
    color: red;
}
h2 {
    text-align: center;
    color: red;
}
p {
    text-align: center;
    color: red;
}

h1, h2, p{
	text-align: center;
    color: red;
}
```

###### box model
content, padding, border, margin

###### What might need to be changed in CSS?
