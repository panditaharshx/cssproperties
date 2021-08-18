 CSS Properties
=====================
There are many CSS properties we use in day to day CSS work, lets dive into some of the common concepts used while working with CSS.

### 5.1. Working with fonts
- Controlling `typography-text-font` is one of the most important things to do with CSS
- CSS `Font` property is used to control the look of font-texts 
- By the use of CSS font property, you can change the font type, font-text size, color, style, bold etc.
- **Font styles**: Properties that affect the font that is applied to the text, affecting what font is applied, how big it is, whether it is bold, italic, etc.
> **Example/font attributes-properties**: font-family, font-size, color, font-style, font-weight, font-variant. https://www.fontsquirrel.com/   

#### CSS Font Choices
1. System Fonts
2. Web Fonts

1. **System Fonts**:
    - Older / Widely supported basic fonts
    - Limited numbers of fonts to use/apply
    - Only installed fonts on user/client machine to used/viewed
    - **Example**: (4 main category of fonts families)
        - **generic fonts family:** Serif, Sans-Serif, MonoSpace, Cursive**
        - **font family**: Times, Arial, Courier, Comic Sans
    - **Requesting fonts in fallback manner (Font stacks)**: `selector { font-family: Arial, Helvetica, Verdana, Sans-serif; }` (if requested font not available use default `serif` fonts)
2. **Web Fonts**:
    - Emerging technique
    - Lack of support in older browsers
    - Web Fonts refer to the technique of having the browser download and install fonts that are requested in the pages's styles using the `@font-face` syntax/method
    - https://fonts.adobe.com/  https://fonts.google.com/

> **Syntax & Example**:
```html
<!-- internal style -->
<style>
    /* css selector: { property:value; } */
    .headingText, h2, h3 {
        font-family: Arial, Helvetica, sans-serif;
        font-size: 3em; /* base font size * 3 = (16 * 3) = 48*/
        font-style: italic;
        font-variant: small-caps;
        font-weight: lighter;
        color:#008080;
        
        -webkit-font-smoothing: antialiased;
        -moz-font-smoothing: antialiased;
        -o-font-smoothing: antialiased;
        -ms-font-smoothing: antialiased;
        /* font-smoothing: antialiased; */
    }
</style>
```

### 5.2. Formatting text
- CSS text properties allow you to define several text styles such as color, alignment, spacing, decoration, transformation etc. very easily an effectively
- **Text layout styles**: Properties that affect the spacing and other layout features of the text, allowing manipulation of the space between lines and letters, and how the text is aligned within the content box
> **Example**: color, text-align, text-decoration, text-transform, line-height, direction, word-spacing, text-shadow

> **Syntax & Example**:
```html
<!-- internal style -->
<style>
    /* css selector: { property:value; } */
    .headingText, h2 {
        text-align: center;
        text-decoration: overline;
        text-transform: uppercase;
        color:#008080;
    }

    .normalList {
        letter-spacing: 4px;
        word-spacing: 8px;
        line-height: 30px;
        color: #008080;
    }
</style>
```

### 5.3. Color
- Colors are a pretty powerful way to express different feelings and emotions in our human life and play an important role while designing UI or UX
- Typically, `color` is used to set a color either for the foreground of an element (i.e., its text), for the background of the element,  or else affect the color of borders/decorative effects
- The CSS `color` property defines the foreground color (text color), `background-color` property defines the background color of an element
> **Example**: color, border-color, background-color

**One can specify color values in various formats, Following table lists all the possible formats**:
| Format	        |        Syntax	        |    Example
| ----------------- |---------------------|-----------------------------|
| Hex Code	        | #RRGGBB	            | h1 { color:#FF0000; }         |
| Short Hex Code	| #RGB	                | h1 { color:#F00; }            |
| RGB %	            | rgb(red%,green%,blue%)   | h1 { color:rgb(50%,50%,50%); }|    
| RGB Absolute	    | rgb(red,green,blue)	    | h1 { color:rgb(0,0,255); }    |
| RGBA	            | rgb(red,green,blue, alpha)| h1 { color:rgb(0,0,255,0.5); }    |
| HSL	            | hsl(hue, saturation, lightness)| h1 { color: hsl(140, 50%, 60%); }    |
| HSLA	            | hsl(hue, saturation, lightness, alpha)| h1 { color: hsl(140, 50%, 60%, 0.5); }    |
| Keyword/color name| red, black, etc.	    | h1 { color:teal; }            |

> **Note:**
> - RGB stands for Red Green Blue (3 main colors of web/screen) 
>    - defines the intensity of the color between 0 and 255.
> - HSL stands for Hue Saturation Lightness
>   - ***Hue*** is a degree on the color wheel from 0 to 360. 0 is red, 120 is green, and 240 is blue
>   - ***Saturation*** is a percentage value, 0% means a shade of gray, and 100% is the full color.
>   - ***Lightness*** is also a percentage, 0% is black, 50% is neither light or dark, 100% is white
> - 150+ color keywords/color names are supported by CSS

> **Syntax & Example**:
```html
<!-- internal style -->
<style>
    /* css selector: { property:value; } */
    .headingText, h2 {
        text-align: center;
        text-decoration: overline;
        text-transform: uppercase;
        color: hsl(140, 50%, 60%); /* Hue=140 -> green color, Saturation=50% -> 50% green not full green, lightness=60% -> lighter shade of green*/
    }

    h2 {
        color:rgba(0,155,0,0.5);
    }

    .normalList {
        letter-spacing: 4px;
        word-spacing: 8px;
        line-height: 30px;
        background-color: wheat;
        color:#000;
        border-bottom: 5px solid #2f4f4f;
        padding-bottom: 20px;
    }
</style>
```

### 5.4. Common Measurement units
- Units are used to specify non-zero length value in CSS properties
- Length measured can be either `absolute units such as pixels, points` and so on, or `relative such as percentages (%) and em` units
- CSS properties take "length" values, such as width, height, margin, padding, font-size, border-width etc.

**There are two unit types:** 
1. Absolute Values/Units
2. Relative Values/Units

1. **Absolute Values/Units**
    - Absolute values are also referred to as fixed values specify an exact measurement values
    - Typically used when physical properties of user agents are known
    - The absolute length units will appear as exactly as size mentioned
    - Absolute physical units such as `in, cm, mm`, etc. should be used for `print media and similar high-resolution devices`. 
    - An on-screen display such as `desktop and lower-resolution devices`, it is recommended to use the `pixel or em` units.
    - **Example**: in (inches), cm (centimeters), mm (millimeters), pt (points), pc (picas), * px (pixel units)
    > **Note**: * px (Pixels Units) are relative to the viewing device. 
    
2. **Relative Values/Units**
    - Relative Values/Units are relative to the units of parent/container or other elements
    - **Example**: %, em, rem, vw (viewport width), vh (viewport height)

| Unit	  | Description	                                            | Example                                                 |
|:-------:|-------------------------------------------------------|-------------------------------------------------------|
| %       | Relative to the parent/container element	            | p { font-size: 200%; }                                  |
| em      | Relative to the current font-size (a base font size), (1em = base size of the current font)                       | p { font-size: 2em; }  | 
| rem     | Relative to the font-size of the root element	        | p { font-size: 2rem }                                   |
| vw      | Relative to 1% of the width of viewport*	            | div { width: 100vw }                                    |
| vh      | Relative to 1% of the height of viewport*	            | div { height: 100vh }                                   |

> **Note**: * Viewport = the browser window size

> **Syntax & Example**:
```html
 <!-- internal style -->
<style>
    /* css selector: { property:value; } */
        body {
        font-size: 20px;
        margin: 0px;
        padding: 0px;
    }

    h1 {
        margin: 0px;
        padding: 0px;
    }

    .normalList {
        font-size: 0.5em;
        line-height: 3em;
        border:0.2em dashed #666;
        padding: 3em;
        margin: 2em;
    }

    .container {
        background-color: darkseagreen;
        height: 100vh;
        width: 100vw;
        display: table-cell;
        vertical-align: middle;
    }

    .sub-container {
        background-color:burlywood;
        padding:20px;
        width: 50vw;
        margin: 0 auto;
    }
</style>


<body>
    
    <div class="container">

      <div class="sub-container">

        <h1 class="headingText" id="mainHeadingText">5. Common CSS Concepts</h1>

        <p class="paraText" id="mainParaText">There are many CSS concepts and properties we use in day to day CSS work, lets dive into some of the common concepts used while working with CSS. </p>

        <h2>05.4. Common Measurement units</h2>

        <ul class="normalList">
          <li>Units are used to specify non-zero length value in CSS properties</li>
          <li>Length measured can be either `absolute units such as pixels, points` and so on, or `relative such as percentages (%) and em` units</li>
          <li>CSS properties take "length" values, such as width, height, margin, padding, font-size, border-width etc.</li>
        </ul>

        <h3>**There are two unit types:** </h3>

        <ol>
          <li>Absolute Values/Units</li>
          <li>Relative Values/Units</li>
        </ol>

      </div>

    </div>
    
</body>
```

### 5.5. Backgrounds
- CSS background properties are used to define background styles/effects for the elements

### Background Properties
The CSS provides several properties for styling the background of an element, like: 
1. **background-color**
    - The `background-color` property is used to set the `background color` of an element
2. **background-image**
    - The `background-image` property `set an image as a background` of an HTML element
3. **background-repeat**
    - By default, the `background-image` property `repeats an image` both horizontally and vertically
    - By using `background-repeat` property one can control how a background image is tiled in the background of an HTML element
    - Properties like `repeat-x & repeat-y` are used to repeat images horizontally (x-axis) or  vertically (y-axis) respectively
4. **background-attachment**
    - The `background-attachment` property determines whether the background image is `fixed with regard to the viewport or scrolls` along with the containing block
    - Sets whether a background image is fixed or scrolls with the rest of the page
    - The background-attachment property is used to control the scrolling of an image in the background
5. **background-position**
    - The `background-position` property is used to control the position of the background image
    - The background-position property is used to define the initial position of the background image. By default, the background image is placed on the top-left of the webpage.
    - Sets the starting position of a background image

> **Syntax & Example**: 
```css
<!-- internal style -->
<style>
    /* css selector: { property:value; } */
    ol li {
        height: 100px;
        font-weight: bold;
        margin-top: 20px;
        padding: 5px;
        border: 2px solid brown;
    }

    ol li:nth-child(1) {
        background-color: thistle;
    }

    ol li:nth-child(2) {
        background-image: url("../assets/images/css3.png");
        background-color: bisque;
    }

    ol li:nth-child(3) {
        background-image: url("../assets/images/css3.png");
        background-repeat: no-repeat; 
        background-color: darkseagreen;
    }

        /* body {
        background-image: url("../assets/images/css3.png");
        background-attachment: fixed;
    } */

    ol li:nth-child(5) {
        background-image: url("../assets/images/css3.png");
        background-repeat: no-repeat;
        background-color: wheat;
        background-position: center -50px; /* horizontal X and vertical Y position*/
    }

    ol li:nth-child(6) {
        background-image: url("../assets/images/css3.png");
        background-repeat: no-repeat;
        background-color: wheat;
        background-position: center center; /* horizontal X and vertical Y position*/
        background-size: contain;
    }
</style>


<ol>
    <li>**background-color**</li>
    <li>**background-image**</li>
    <li>**background-repeat**</li>
    <li>**background-attachment** <br />  uncomment and check body styles</li>
    <li>**background-position**</li>
    <li>**background-position**</li>
</ol>
```

### 5.6. Box Model
- The Box Model refers to the physical properties of an element rectangular box
- Every element displayed is comprised of one or more rectangular boxes. CSS box model typically describes how these rectangular boxes are laid out on a web page
- The Box Model concepts help to make layout/designing task easier
- **Box Model consists of properties like**: Margins, Borders, Padding and content width, height (these properties make physical dimension of an element)
    - Margin = Space outside/around an element
    - Border = Rectangular outline/border surrouding an element/box
    - Padding = Breathing space inside an element border
> Total width of an element: left border + left padding + content width + right padding + right border

The following diagram demonstrates how the margin, padding, and border CSS properties determine how much space an element can take on a web page:
<p align="center">
    <img src="_examples-css3-fundamentals/assets/images/box-model.png" alt="CSS Box Model" title="CSS Box Model" width="400" />
</p>

> **Syntax & Example**:
```css
.container {
    background-color: burlywood;
    width: 80%;
    padding: 20px;
    border:5px solid #c5760f;
    margin: 20px auto;
}
```

```html
<body>
    
    <div class="container"> 

    </div>

</body>
```

### 5.7. Margin 
- The margin is `Space outside/around an element`, Margin represents the `space between elements`
- Margin values are not calculated as part of an elements total width
- The margins do `not have a background-color`, it is `completely transparent`
- `Margin is outside` and Padding is inside
- Margin can be defined either to Top, Right, Bottom, Left or to each side of an element

> **Syntax & Example**:
```css
element {
    margin: margin-width/value;
}


div {
    margin: 10px 20px 30px 40px; /* Top, Right, Bottom, Left */
    margin-left: 50px; /* all sides equally */
}

--------------------

.normalList li:nth-child(odd) {
    /* margin: 10px 20px 10px 20px; /* Top, Right, Bottom, Left */
    /* margin: 10px 20px;  /* pair top-bottom & right-left */
    margin: 15px; /* all sides equally */
    background-color: bisque;
}
```


```html
<ul class="normalList">
    <li>Margin is `Space outside/around an element`, Margin represent the `space between elements`</li>
    <li>Margin values are not calculated as part of an elements total width</li>
    <li>The margins does `not have a background-color`, it is `completely transparent`</li>
    <li>Margin can be defined either to Top, Right, Bottom, Left or to each side of an element</li>
</ul>
```

### 5.8. Padding
- Padding is the `breathing space inside an element border` which holds the content away from edge/border and allows readability
- CSS Padding property is used to define the space between the element content and the element border
- `Padding is inside` and Margin is outside
- Padding can be defined either to Top, Right, Bottom, Left or to each side of an element

> **Syntax & Example**:
```css
element {
    padding: padding-width/value;
}

div {
    padding: 10px 20px 30px 40px; /* Top, Right, Bottom, Left */
    padding-top: 50px; /* all sides equally */
}

--------------------

.normalList li:nth-child(odd) {
    /* padding: 10px 20px 10px 20px; /* Top, Right, Bottom, Left */
    /* padding: 10px 20px;  /* pair top-bottom & right-left */
    padding: 15px; /* all sides equally */
    background-color: bisque;
}
```

```html
<ul class="normalList">
    <li>Padding is the `breathing space inside an element border` which holds the content aways from edge/border and allows readibility</li>
    <li>CSS Padding property is used to define the space between the element content and the element border</li>
    <li>`Padding is inside` and Margin is outside</li>
    <li>Padding can be defined either to Top, Right, Bottom, Left or to each side of an element</li>
</ul>

```

### 5.9. Borders
- Border defines the `outside edge` of an element 
- Widely used to define/apply `decorative effects/visual separation` to an element
- The border of an element goes around the padding and content
- Borders are defined with 3 properties: `border-width, border-style, border-color, border-radius`
- The border can be defined either to Top, Right, Bottom, Left or to the whole element 

> **Syntax & Example**: 
```css
element {
    border: border-width/value || border-style || border-color
}

div {
    border: 2px solid #0000ff;
    border-top: 2px solid #ff0000;
}

--------------------

.border-style-ilst li {
    font-weight: bold;
    margin-top: 20px;
    padding: 10px;
}

.border-style-ilst li:nth-child(1){
    border: 2px solid brown;
}

.border-style-ilst li:nth-child(2){
    border: 2px dashed brown;
}

.border-style-ilst li:nth-child(3){
    border: 2px dotted brown;
}

.border-style-ilst li:nth-child(4){
    border: 5px double brown;

    /* border-color: brown;
    border-style: double; */
}

.border-style-ilst li:nth-child(5){
    /* border-style: ridge; */
    border: 5px ridge brown;
}

.border-style-ilst li:nth-child(6){
    /* border-style: groove; */
    border: 5px groove brown;
}

.border-style-ilst li:nth-child(7){
    border-color: brown;
    border-style: solid dashed double dotted ;
}

.border-style-ilst li:nth-child(8){
    border:2px solid brown;
    border-radius: 15px;
}

.border-style-ilst li:nth-child(9){
    padding: 20px;
    border:2px solid brown;
    border-radius: 100px 0px;
    background-color: bisque;
}

.colors-channel-logo, .colors-channel-logo div {
    width: 100px;
    height:100px;
    border-radius: 100% 0%;
    position: relative;
}

.colors-channel-logo {
    background-color: #7d2792;
}

.colors-channel-logo div {
    width: 80px;
    height:80px;
    background-color: #ea008a;
    top: 20px;
}

.colors-channel-logo div  div{
    width: 60px;
    height:60px;
    background-color: #f98900;
}
```

```html
<ul class="border-style-ilst">
    <li>border: solid</li>
    <li>border: dashed</li>
    <li>border: dotted</li>
    <li>border: double</li>
    <li>border: ridge</li>
    <li>border: groove</li>
    <li>border: border-style:multiple type border</li>
    <li>border: border-radius: rounded corner</li>
    <li>border: border-radius: rounded corner: design</li>
</ul>

<h3>Colors channel logo created with border-radius</h3>
<div class="colors-channel-logo">
    <div>
        <div></div>
    </div>
</div> 
<br />
```

### 5.10. Element Positioning
- Positioning allows to take an element on the page and `control where and how it can be positioned`
- The CSS `position property` is used to `set position` for an element
- It is also used to place an element `behind another` and also useful for `scripted animation effect`

#### CSS positioning schemes
- Normal Flow
- Element Floating
- Absolute Positioning

- **Normal Flow**
    - The default layout method of CSS and Browser
    - Elements defined in HTML page stacks and show the layout/Document Flow in the browser (`static` is default positioning)
    - `position` property is used to position elements manually

> **Syntax & Example**: 
```css
div {
    position: static | relative | absolute | fixed | inherit
}
```

#### Relative Positioning 
- Elements are still considered as part of normal document flow, but one can offset the elements from its normal position using top, right, bottom, or left offset values
- Relative positioning changes the position of the HTML element `relative to where it normally` appears (`positioned relative to its normal position`)
- Relative Positioning helps to nudge or re-position an element from its `current position/location`

> **Syntax & Example**: 
```html
<!-- internal style -->
<style>
    /* css selector: { property:value; } */
    body {
        margin: 0px;
        padding: 0px;
    }

    .container {
        background-color: burlywood;
        width: 80%;
        padding: 20px;
        border:5px solid #c5760f;
        margin: 20px auto;
    }

    .relative-pos-box {
        color: #fff;
        background: #00c4cc;
        padding: 10px;
        width: 80%;
        
        position: relative;
        left: 150px;
    }

</style>


<body>
    
    <div class="container">

        <div class="sub-container">

            <div class="relative-pos-box">
                <h2>Relative Positioning </h2>
                
                <ol>
                    <li>Elements are still considered as part of normal document flow, but one can offset the elements from its normal position using top, right, bottom, or left offset values</li>
                    <li>Relative positioning changes the position of the HTML element `relative to where it normally` appears (`positioned relative to its normal position`)</li>
                    <li>Relative Positioning helps to nudge or re-position an element from its `current position/location`</li>
                </ol>
            </div>

        </div>

    </div>

</body>
```

- **Element Floating**
    - Floating simply denotes an element `shifted/placed on the left or right side`

- **Absolute Positioning**
    - Absolute Positioning is `not considered as a part of Normal Document flow`
    - Absolute Positioning removes the document from Normal Document flow and repositioned based on top, right, bottom, or left offset values
    - Other elements in flow move up and take empty space made by an absolute positioned element
    - Elements are placed relative to the nearest positioned ancestor/parent element OR body OR viewport

> **Syntax & Example**: 
```html
<!-- internal style -->
<style>
    /* css selector: { property:value; } */
    body {
        margin: 0px;
        padding: 0px;
    }

    .container {
        background-color: burlywood;
        width: 80%;
        padding: 20px;
        border:5px solid #c5760f;
        margin: 20px auto;
    }

    .absolute-pos-box {
        color: #fff;
        background: #00c4cc;
        padding: 10px;
        width: 50%;
        
        position: absolute;
        left: 0px;
        top: 0px;
    }
</style>


<body>
    
    <div class="container">

      <div class="sub-container">

        <div class="absolute-pos-box">
            <h2>Absolute Positioning </h2>

            <ol>
                <li>Absolute Positioning is `not considered as a part of Normal Document flow`</li>
                <li>Absolute Positioning removes the document from Normal Document flow and respositioned based on top, right, bottom, or left offset values</li>
                <li>Other elements in flow moves up and takes empty space made by an absolute positioned element</li>
                <li>Elements are placed relative to the nearest positioned ancestor/parent element OR body OR viewport</li>
            </ol>
        </div>

      </div>

    </div>
    
</body>
```

#### Fixed Positioning 
- The fixed positioning property helps to put the text fixed on the browser
- Fixed Positioned elements are considered to be an Absolute Positioned elements itself but it always positioned relative to the `active viewport`
- As Fixed Positioned elements are positioned relative to the `active viewport` scrollbar doesn't affect it
- Fixed positioning is a subcategory of absolute positioning (the difference is, a fixed positioned element is fixed with respect to the browser's viewport and does not move when scrolled)

> **Syntax & Example**: 
```html
<!-- internal style -->
<style>
    /* css selector: { property:value; } */
    body {
        margin: 0px;
        padding: 0px;
    }

    .container {
        background-color: burlywood;
        width: 80%;
        padding: 20px;
        border:5px solid #c5760f;
        margin: 20px auto;

        position: relative;
    }

    .fixed-pos-box {
        color: #fff;
        background: #00c4cc;
        padding: 10px;
        width: 50%;
        
        position: fixed;
        right: 95px;
    }

</style>


<body>
    
    <div class="container">

      <div class="sub-container">

        <h2 class="fixed-pos-box">Fixed Positioning 1 : </h2>
          
      </div>

    </div>
    
</body>
```

### 5.11. Floats
- Floating simply denotes an element shifted/placed on the left or right side
- Floating is one of the widely used CSS layout techniques
- Floats are used to create: Layout Design, Horizontal Menu/Navigation, Columner/Column Layouts
- The CSS float property is a `positioning property`
- The `float` property is used for positioning and formatting content e.g. let box/an image float left or right side of a container
- `clear: both` property is used to stop the floats of an element and start the normal document flow

### How Float works
- Elements are floated only horizontally. So it is possible only to float elements left or right, not up or down
- A floated element may be moved as far to the left or the right as possible. it simply means that a floated element can display at the extreme left or extreme right
- The elements before the floating element will not be affected. The elements after the floating element will flow around it
- If the image floated to the right, the texts flow around it, to the left and if the image floated to the left, the text flows around it, to the right

> **Note**: A floated element is taken `out of the normal flow and shifted to the left or right` as far as possible in the space available of the containing element. Other elements normally flow around the floated items, unless they are prevented from doing so by their `clear` property. 

> **Syntax & Example**: 
```css
div {
    float: left | righ | none | inherit
}

div {
    clear: both;
}
```

```html
<!-- internal style -->
<style>
    /* css selector: { property:value; } */
    body {
        margin: 0px;
        padding: 0px;
    }

    .container {
        background-color: burlywood;
        width: 80%;
        padding: 20px;
        border:5px solid #c5760f;
        margin: 20px auto;
    }

    .float-left-div {
        border: 1px solid brown;
        padding: 20px;
        margin: 10px;
        width: 25%;
        float: left;
    }

    .float-right-div {
        border: 1px solid brown;
        padding: 20px;
        margin: 10px;
        width: 25%;
        float: right;
    }

    .float-clear-div {
        border: 1px solid brown;
        padding: 20px;
        margin: 10px;
        clear:both;
    }
</style>


<div class="float-left-div">@ left - float: left;</div>
<div class="float-right-div">@ right - float: right;</div>
<div class="float-clear-div">@ normal float - clear:both</div> 
```

### 5.12. Basic Layout Concepts
- Create different `content regions` with DIVs or New HTML5 Semantics Tags and then do `region styling` as per layout requirements.
There are different ways to create multicolumn layouts. Each way/layout techniques has its pros and cons:
1. **HTML Layout using Tables `(not recommended)`**
	- Use Table, TR, TD tag to create a whole layout
	- Table based layouts are not at all flexible and difficult to manage and modify
2. **Layouts using Div and Span `(CSS float property)`**
	- You can use `Div - the block level element` to create a complete web layout with CSS `float` property  
	- It is a common and widely used technique to create entire web layouts using the CSS float property (float - helps to align block level elements)
	- Floating elements are tied to the document flow, which may harm the flexibility and sometimes its difficult to manage the whole layout
3. **HTML5 Semantic Tags based Layout`(CSS float property)`**
	- You can use HTML5 semantic tags like main, header, nav, section, article, aside, footer etc. to create a fully functional web layout
	- It is a common and widely used technique to create entire web layouts using the CSS float property (float - helps to align block level elements)
4. **CSS flexbox Layout**
	- Flexbox is a new layout mode in CSS3
5. **CSS framework**
	- Create layout faster and quicker by using a framework like Bootstrap,W3.CSS or so
6. **CSS grid Layout**
	- The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.
	- The CSS grid layout is a new layout model optimized for two-dimensional layouts. 
	- It's ideal for website layouts, forms, image galleries, and anything that requires precise and responsive positioning.

#### 1. Creating Table-based Layout `(not recommended)`
- The purpose of the `<table>` element is to display tabular data
- The simplest and most popular way of creating layouts is using HTML `<table>` tag. These tables are arranged in columns and rows, so you can utilize these rows and columns in whatever way you like.
- The `<table>` element was not designed to be a layout tool! Before introduction to Div tag, web designers/developers use to follow table based layout
> **Note**: Do not use tables for your page layout! They will make code length, tedious and brings a mess into your code

> **Syntax & Example (CSS Table base layout)**: 
```

Please Check example/demo: 05.12.1a.html.table.layout & 05.12.1b.css.table.layout

```

#### 2. Layouts using Div and Span `(CSS float property)`

> **Syntax & Example (CSS Div base layout)**: 
```

Please Check example/demo: 05.12.2.css.div.layout

```

#### 3. HTML5 Semantic Tags based Layout`(CSS float property)`

> **Syntax & Example (HTML5 Sementic tag based layout)**: 
```

Please Check example/demo: 05.12.3.semantic.tag.layout

```

### 5.13. Media Types and Media Queries
- One of the great benefit of using HTML5 & CSS3 to separate structure and presentation also an ability to present the same content in a different way on multiple devices
- CSS3 allows targeting multiple devices by using `media types & media queries`
- **Media Types**: Allows us to control/serve a different set of styles to multiple devices based on device type
- The same content can be viewed with different styles/layouts on different media devices (screen, printer, screen readers) 

> **Syntax & Example**: 
```css
1. @media screen {
    /* different styles for screen *\
    property: value;
}

/*2. @import syntax*/
@import url("style.css") screen;
```

```html
3. link element syntax
<link rel="stylesheet" type="text/css" href="style.css" media="screen, projection">
```

#### Media Type Benefits
- A powerful way to control the look and functionality of sites across multiple devices
- **Different Media Types**: all, print, projection, screen, speech (screen readers), tv

#### Media Queries
- Media queries allow combining media types with media property expressions, to further when styles are applied based on color, screen width, and other many factors
- **Different Media features**: width, height, (min-width, max-width)

### 5.14. CSS3
- CSS3 is brand, a latest specification/module of CSS which consists of many latest and upgraded features/functionalities/powerful tools+options
- **CSS3 feature**: 
    - border-radius, border-image, multiple backgrounds images 
    - colors: rgba & hsla (alpha color values)
    - Text formatting: text-shadow, multiple columns, @font-face
    - New Selectors: many psuedo selectors like nth:
    - box-shadow
    - gradients
    - transforms
    - transitions
    - animations

### 5.15. CSS Vendor Prefixes (CSS Browser Prefixes)
- Vendor Prefixes allows browsers manufacturers to add support for `proprietary features which are still in development`
- Browser manufacturers have used browser specific `prefixes for experimental APIs`
- Vendor Prefixes gives the designer/developer an opportunity to use experimental/evolving features-properties
- CSS vendor prefixes/CSS browser prefixes are a way for browser makers to add support for new CSS features before those features are fully supported in all browsers

> **Note**: CSS vendor prefixes/CSS browser prefixes are used only for latest CSS3 properties which are not fully developed/supported by all browser

#### Common Vendor Prefixes
| Prefix        | Browser                                               |
| ------------- |-----------------------------------------------------|
| -webkit       | Webkit (Google Chrome, Safari)                        |
| -moz-         | Mozilla (Mozilla Firefox)                             |
| -ms-          | Microsoft (Internet EXplorer)                         |
| -o-           | Opera                                                 |
| -khtml-       | Konqueror                                             |

> **Syntax & Example**: 
```css
<!-- internal style -->
<style>
    /* css selector: { property:value; } */
    .heading-text {
        padding: 10px;
        border: 2px solid #c5760f;

        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        -ms-border-radius: 20px;
        -o-border-radius: 20px;

        border-radius: 20px;
    }

    .sub-heading-text {
        -webkit-text-shadow: 5px 5px 2px #c5760f;
        -moz-text-shadow: 5px 5px 2px #c5760f;
        -ms-text-shadow: 5px 5px 2px #c5760f;
        -o-text-shadow: 5px 5px 2px #c5760f;

        text-shadow: 5px 5px 2px #c5760f;
    }
</style>
```

```html
<body>
    <h1 class="heading-text" id="mainHeadingText">5. Common CSS Concepts</h1>

    <h2 class="sub-heading-text" id="subHeadingText">5.15. CSS Vendor Prefixes (CSS Browser Prefixes)</h2>
</body>
```

### 5.16. CSS Reset
- CSS Reset is a set of styles that `nullify a browsers default style` sheet
- CSS Reset a collection of styles allows designers to avoid conflicts between their styles and browser default styles
- Every browser has its own default `user agent stylesheet`, that it uses to make unstyled websites appear more beautiful/legible. (By default apply variable font-sizes to H1 to H6, a certain amount of padding to almost every element, make links blue and visited links purple, give tables a certain amount of border and padding)
- Using a CSS Reset, we can force every browser to have all its styles reset to null, thus `avoiding cross-browser differences` as much as possible
- The goal of a reset style is to `reduce browser inconsistencies` in things like default line heights, margins and font sizes of headings etc.

- **Common CSS Reset Properties**:
    - margin
    - adding
    - borders
    - font-size
    - line-height

> **Syntax & Example**: 
```css
/* css reset styles goes here */
body, h1, h2, h3, h4, h5, h6, p, input,li {
    margin:0px;
    padding:0px;
}   
```


![image](https://user-images.githubusercontent.com/55940353/129929804-254ed767-c559-415a-873c-6e6d0be7444f.png)

![image](https://user-images.githubusercontent.com/55940353/129929888-c626b9e3-524e-48eb-a31c-0d2044f36814.png)

![image](https://user-images.githubusercontent.com/55940353/129929941-5e60a72f-65ce-481a-9780-1b651388c6d0.png)

![image](https://user-images.githubusercontent.com/55940353/129930043-0806cd45-8c95-42bf-a8db-8b2a8ae37172.png)

![image](https://user-images.githubusercontent.com/55940353/129930133-965f5b78-ecd6-4bf8-ab95-cc97c0af7b2c.png)

![image](https://user-images.githubusercontent.com/55940353/129930184-41f7d3cd-f4e6-42aa-b463-e1d397731d28.png)

![image](https://user-images.githubusercontent.com/55940353/129930256-845cb828-f067-4bfd-a1b6-bfeb1452b3a9.png)

![image](https://user-images.githubusercontent.com/55940353/129930352-406e2036-323e-4651-9997-02eb41621c19.png)

![image](https://user-images.githubusercontent.com/55940353/129930450-48dd3dff-5c0f-4c4d-b725-53eff8039a8e.png)

![image](https://user-images.githubusercontent.com/55940353/129930491-21501ea1-ee35-4e20-87d2-622440944943.png)

![image](https://user-images.githubusercontent.com/55940353/129930542-cd606f10-c678-40ec-918b-bfab02cda6a6.png)

![image](https://user-images.githubusercontent.com/55940353/129930602-9c5c468d-e722-4c6a-9ba7-fef7bd0a130a.png)

![image](https://user-images.githubusercontent.com/55940353/129930650-a5c112d9-9ebc-4c0f-bf4c-c9058d4d8760.png)

![image](https://user-images.githubusercontent.com/55940353/129930706-918a9595-0b0f-4651-80d5-2bdc1942e069.png)

![image](https://user-images.githubusercontent.com/55940353/129930767-d45bd0f0-0748-46d7-ae55-9219260a2eaf.png)

![image](https://user-images.githubusercontent.com/55940353/129930859-ad92f767-a89a-4c4f-9cf6-557ec88b6cb0.png)

![image](https://user-images.githubusercontent.com/55940353/129930980-8c5223cb-18fd-4eff-aa75-ff057a460c83.png)

![image](https://user-images.githubusercontent.com/55940353/129931053-9f003a79-ba26-4f04-81b8-c6749000e8e2.png)

![image](https://user-images.githubusercontent.com/55940353/129931156-533c9e6e-aa03-4438-9622-c9e8173e2377.png)

![image](https://user-images.githubusercontent.com/55940353/129931260-97570352-adc8-44be-a3ec-fd3a708d8bad.png)



