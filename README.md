---
<img src="https://i.imgur.com/qsSi07H.png">

# Intro to<br>Flexbox & CSS Grid

---
## Learning Objectives
<br>

<p>Students Will Be Able To:</p>

- Describe the Use Case of Flexbox & CSS Grid

- Use Flexbox for One-Dimensional Layout 

- Use CSS Grid for Two-Dimensional Layout 

---
## Roadmap
<br>

- Setup
- Intro to Flexbox & CSS Grid
- Why use Flexbox?
- Flexbox Fundamentals
- Your First Flexbox
- Why use CSS Grid?
- CSS Grid Fundamentals
- Your First CSS Grid

---
### Setup

- Start by creating a new **index.html and style.css** file in the lesson's directory using terminal commands.  These should be second nature by now.

- First, let's add our boilerplate HTML by typing `! + tab`. 

- Next, let's be sure and link our HTML file to our CSS file by adding the following line of code on line 6:

	```html
	<link rel="stylesheet" href="style.css">
	```

- Finally, let's add a bit of starting CSS inside of the `style.css` file that we just created:

	```css
	* {
	  box-sizing: border-box;
	}
	
	body {
	  margin: 0;
	  font-family: Helvetica;
	}
	```

---
### Intro to Flexbox & CSS Grid
<br>

- As a front-end developer, you will be required to precisely layout the elements on web pages.

- Prior to Flexbox & CSS Grid, laying out the parts of a web page from basic navigation headers to complex full-page layouts has not been as straightforward as it could be - Flexbox & Grid, however, are game changers.

- The capabilities of Flexbox & CSS Grid complement each other and using both side-by-side and even nesting one within the other.

- To best understand Flexbox & CSS Grid, it's important to remember what CSS stands for - **Cascading Style Sheets**. Understanding how the different sections of your web page relate to each other is critical to understadning how the CSS you write will affect it.

- CSS operates on a parent/child structure with the outermost sections of a page affecting the innermost (Russian Dolls).

---
### Intro to Flexbox & CSS Grid

- The difference between Flexbox and CSS Grid is how they are designed to lay out their children:

<img src="https://i.imgur.com/2ie45ct.png">

---
## Flexbox

---
### Why Use Flexbox?
<br>

- Flexbox excels at assisting devs with the following tasks:
	
	- Vertically centering content & elements within a container element
	
	- Spacing child elements within a container uniformly
	
	- Making the height of child elements laid out in columns the same even though they have a different amount of content.

---
### Flexbox Fundamentals
<br>

- We use a CSS `display: flex;` declaration to make an element a **flex container**, for example: 

	```css
	section {
	  display: flex;
	}
	```
	The above would make all `<section>` elements **flex containers** and all direct children become **flex items**.

- Let's open a separate tab in our browser and briefly review what has become the [de facto guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/).

---
### Your First Flexbox
<br>

- We're going to make a navigation bar using Flexbox.

- Add the following markup for the nav bar inside of the `<body>` tags in our HTML file (don't copy and paste; build that muscle memory!):

	```html
	<nav>
	  <div>HOME</div>
	  <div>ABOUT</div>
	  <div>WIDGETS</div>
	  <div>LOG OUT</div>
	</nav>
	```

---
### Your First Flexbox
<br>

- Run the Live Server in VS Code to check it out - definitely not what we're looking for!

- **Which element do we need to make the flex container?**

---
### Your First Flexbox
<br>

- Let's make the `<nav>` a Flexbox:

	```css
	nav {
	  display: flex;
	}
	```

- Run again, and we can make the following observations:
	- The **flex items** are laid out horizontally in a **row** - this is the default layout of a **flex container**.
	- The `<div>` elements have become **flex items** and no longer behave as block elements - their width has collapsed to that of their content and they are willing to sit side-by-side other elements.

---
### Your First Flexbox
<br>

- This just in... our client has informed us that:
	- The navigation bar must:
		- Be `50px` in height
		- Have a background color of `#F03F3C`.
	- The menu items in the nav bar need:
		- A font size of `20px`
		- A margin of `10px` on all 4 sides
		- A text color of `#FFFFFF`

- Add the CSS to make the client happy!

---
### Your First Flexbox
<br>

- A **flex container** has a `flex-direction` property that defines the direction of its **main axis**.

- There are four values:
	- `row` - the default
	- `row-reverse`
	- `column`
	- `column-reverse`

- Let's check them out by adding a `flex-direction` to the `<nav>`.

---
### Your First Flexbox
<br>

- In addition to the concept of a **main axis**, a **flex container** has a **cross axis** which represents the opposite direction of its **main axis**.

- For example, if the `flex-direction` is set to `row` (the default), the:
	- **main axis** is **horizontal**
	- **cross axis** is **vertical**

- If the `flex-direction` is set to `column`, they flip:
	- **main axis** is **vertical**
	- **cross axis** is **horizontal**

---
### Your First Flexbox
<br>

- The concepts of **main axis** & **cross axis** come into play when it comes to sizing and layout properties, such as:

- `justify-content`: Controls alignment for the **main axis**

- `align-items`: Controls alignment for the **cross axis**

---
### Your First Flexbox
<br>

- With the following alignment properties set:

	```css
	nav {
	  display: flex;
	  flex-direction: row; /* default */
	  justify-content: flex-start; /* default */
	  height: 50px;
	  background-color: #F03F3C;
	}
	```
	The nav bar's not looking too bad...

	<img src="https://i.imgur.com/3aEZZ2B.png">

---
### Your First Flexbox
<br>

- Let's say you want the `LOG OUT` menu item to be aligned on the right:

	<img src="https://i.imgur.com/b8WhtDa.png">
	
- You could wrap the other three with another element and set `justify-content` to `space-between`.

- Or, we can use this bit of CSS goodness:

	```css
	nav > div:last-child {
	  margin-left: auto;
	}
	```
	
---
### Review Questions - Flexbox
<br>

- **When an element has a CSS property of `display: flex;`, that element becomes a flex __________.**

- **When an element has a CSS property of `display: flex;`, its direct children become flex __________.**

- **What value is the default for the `flex-direction` property?**

- **Is it `justify-content` or `align-items` that controls the alignment along the _cross axis_?**

---
## CSS Grid

---
### Why use CSS Grid?
<br>

- **CSS Grid** is a great option when you have:
	1. A page layout like this (or as complex as you'd like):
	<img src="https://i.imgur.com/tkBPUd0.png">
	2. Any other "components" that would benefit from a grid-type layout such as a "profile card", in other words, CSS Grid doesn't have to apply to the whole page - it can be useful for laying out smaller "components" as well.

---
### CSS Grid Fundamentals
<br>

- Unlike Flexbox, **CSS Grid** lays out its **grid items** in **two-dimensions**.

- **CSS Grids** have the concept of the following:
	- **Tracks**
	- **Cells**
	- **Areas**
	- **Gaps**

- Let's examine a diagram to visualize these components...

---
### CSS Grid Fundamentals

<img src="https://i.imgur.com/yNTGxhx.png">

---
### CSS Grid Fundamentals
<br>

- As you might expect, there are plenty of CSS Grid-related properties and values.

- Here's the [CSS Grid equivalent of that Flexbox guide we used earlier](https://css-tricks.com/snippets/css/complete-guide-grid/).

- Let's open it up in a new tab and take a peek.

---
### Your First CSS Grid
<br>

- To try out CSS Grid, we'll continue to work in the VS Code to layout this UI:

<img src="https://i.imgur.com/n4yADRK.png">

---
### Your First CSS Grid
<br>

- The following CSS turns the `<body>` element into a **grid container**:

	```css
	body {
	  display: grid;
	  height: 100vh;
	  margin: 0;
	  font-family: Helvetica;
	}
	```

- Using `height: 100vh;` will make the `<body>` fill the height of the browser window so that the `<footer>` is at the bottom.

---
### Your First CSS Grid
<br>

- Let's add the additional HTML required by the UI:

	```html
	<body>
	  <nav>
	    <div>HOME</div>
	    <div>ABOUT</div>
	    <div>WIDGETS</div>
	    <div>LOG OUT</div>
	  </nav>
	  <aside>SIDE BAR</aside>
	  <main>MAIN CONTENT</main>
	  <footer>FOOTER</footer>
	</body>
	```

- Now for a touch of styling...

---
### Your First CSS Grid
<br>

- Let's change the color of the elements we just added so that we can more easily see them:

	```css
	aside {
	  background-color: #FAE00C;
	}
	
	main {
	  background-color: #226AFA;
	}
	
	footer {
	  background-color: #63D629;
	}
	```

---
### Your First CSS Grid
<br>

- One more stylistic touch. What if we want to center the text in those elements both horizontally and vertically?

- Wanting to center/center content is so common, let's create a class that will make any element with that class a Flexbox:

	```css
	.flex-ctr {
	  display: flex;
	  justify-content: center;
	  align-items: center;
	}
	```

- With the class defined - **go ahead and add it to the `<aside>`, `<main>` & `<footer>` elements.**

---
### Your First CSS Grid
<br>

- Using Chrome DevTools to explore the page's elements, we can make the following observations:
	- A **CSS Grid** has a single column by default.
	- Each **grid item** (direct child) was placed its own row by default.

- Now let's define the columns and rows necessary to layout our page as desired.  Go back and look at the UI we want to layout and answer these questions:
	- **How many columns will we need to define?**
	- **How many rows?**

---
### Your First CSS Grid
<br>

- Okay, let's define those column and rows:

	```css
	body {
	  display: grid;
	  grid-template-columns: 1fr 4fr;
	  grid-template-rows: 50px 1fr 30px;
	  ...
	```

- The `fr` unit is used by CSS Grid to represent a _fraction_ of the available space. So in our layout, the first column will be 1/5th the width of the window.

---
### Your First CSS Grid
<br>

- Running the Live Server shows that we've made a mess.  But notice how each **grid item** is simply being placed in each cell across the columns from left to right. This is the default behavior.

- However, we need both the `<nav>` and the `<footer>` to span two columns each...

---
### Your First CSS Grid
<br>

- There are a couple of ways to make **grid items** cover rectangular grid **areas**.

- One way is by defining `grid-template-areas` on the grid container; then using the `grid-area` property on the **grid item**.

- However, in this lesson, we'll look at another option...

---
### Your First CSS Grid
<br>

- The `grid-column` CSS property determines which **grid lines** a **grid item** starts and ends on.

- For example:

	```css
	nav, footer {
	  grid-column: 1 / 3;
	}
	```

- The lines are numbered starting with 1 (not zero).

---
### Your First CSS Grid
<br>

- We will use `span x` to specify how many columns we want to span:

	```css
	nav, footer {
	  grid-column: span 2;
	}
	```

- Unsurprisingly, there's a `grid-row` property as well.

- Both `grid-column` & `grid-row` are shorthand for `grid-column-start` & `grid-column-end`, and `grid-row-start` & `grid-row-end`, respectively.

---
### Your First CSS Grid
<br>

- The last thing we'll look at in regards to CSS Grid are grid **gaps** which specify the size of the **grid lines**.

- Update the CSS of the `<body>` (grid container) to the following:

	```css
	body {
	  display: grid;
	  grid-template-columns: 1fr 4fr;
	  grid-template-rows: 50px 1fr 30px;
	  grid-gap: 5px;  /* specifies width of grid lines */
	  ...
	```
	
- Note that the grid gaps cannot be styled - the grid's background simply shows through.

---
### Flexbox & CSS Grid Practice Sites
<br>

- We've covered the key properties of these two fine additions to CSS, but...

- Here are a couple of really fun ways to learn more about them:
	- [FLEXBOX FROGGY](https://flexboxfroggy.com/)
	- [GRID GARDEN](https://cssgridgarden.com/)

---
### References
<br>

- [MDN - Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)

- [MDN - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
