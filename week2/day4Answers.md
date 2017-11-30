//What does postion: absolute do?

    //This is a very powerful type of positioning that allows you to literally place any page element exactly where you want it. You use the positioning attributes top, left, bottom. and right to set the location. Remember that these values will be relative to the next parent element with relative (or absolute) positioning. If there is no such parent, it will default all the way back up to the <html> element itself meaning it will be placed relatively to the page itself.
    
    //The trade-off (and most important thing to remember) about absolute positioning is that these elements are removed from the flow of elements on the page. An element with this type of positioning is not affected by other elements and it doesn't affect other elements. This is a serious thing to consider every time you use absolute positioning. Its overuse or improper use can limit the flexibility of your site.
    
    // If the parent doesn't have the postion of realitive on it the children will not stay within it. 

//What does position: relative do?

   //Doesn't respect it's parents and will sit exactly where you tell them to sit. 

	 //The element is positioned relative to the browser window

   //This type of positioning is fairly rare but certainly has its uses. A fixed position element is positioned relative to the viewport, or the browser window itself. The viewport doesn't change when the window is scrolled, so a fixed positioned element will stay right where it is when the page is scrolled, creating an effect a bit like the old school "frames" days.

//What does position: fixed do?

    //This type of positioning is probably the most confusing and misused. What it really means is "relative to itself". If you set position: relative; on an element but no other positioning attributes (top, left, bottom or right), it will no effect on it's positioning at all, it will be exactly as it would be if you left it as position: static; But if you do give it some other positioning attribute, say, top: 10px;, it will shift its position 10 pixels down from where it would normally be. I'm sure you can imagine, the ability to shift an element around based on its regular position is pretty useful. I find myself using this to line up form elements many times that have a tendency to not want to line up how I want them to. 



///////FLEXBOX

// Where do you put the flexbox properties in your css?

    //On the parent. There are only a few like align-self that will go directly on the child all the rest go on the parent and affect the children.



// What is the default to display: flex?

    //By default stacks the children in a row. 

  
  
// The justify-content property accepts 5 different values what do each of those values do?

    //flex-start (default): items are packed toward the start line
    //flex-end: items are packed toward to end line
    //center: items are centered along the line
    //space-between: items are evenly distributed in the line; first item is on the start line, last item on the end line
    //space-around: items are evenly distributed in the line with equal space around them
    //space-evenly: items are distributed so that the spacing between any two adjacent alignment subjects, before the first alignment subject, and after the last alignment subject is the same
    
    

// What does the flex-grow property do?

    // flex-grow: 1;

    //sets width on element. Will look as siblings width and will base it's width off of that. 

    //IT defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

    //For example, if all items have flex-grow set to 1, every child will set to an equal size inside the container. If you were to give one of the children a value of 2, that child would take up twice as much space as the others.