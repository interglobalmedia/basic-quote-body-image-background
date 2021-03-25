<h1 class="capitalize">COMD2561 Web Design 1</h1>
<h2 class="sentence center">Creating a Background Image with the Body Element</h2>

---

<section class="section">
	<h2 class="sentence">The CSS background-image property and the body element</h2>

***One way*** one can **add** a `background-image` is to the `body element`. That ***means*** it (potentially) can `cover` the ***whole*** `web page`.

**Unlike** the [other way](https://github.com/interglobalmedia/basic-quote-image-background/blob/master/basic-quote-image-background.md) in which we **used** `JavaScript` to ***style*** some of the **dynamically generated** `background-images` of the `article element`, here we **style** it ***completely*** with `CSS`. The ***only thing*** we **use** the `JavaScript` for is to **generate** a `random quote` that is **placed** on **top** of the `background-image` on the `click` of the `body` of the **web page** (or the **text content** `Click for quote!`).

I **add** the ***following*** `body element selector` **rule set** below my `CSS reset` and my `html element selector` in my `external stylesheet`:

```css
body {
	background-image: url(/images/bryan-minear-317365.jpg);
	background-position: center center;
	background-repeat: no-repeat;
	background-size: cover;
	color: #dcf0fb;
	font-family: 'Barlow', sans-serif;
	font-size: 0.75em;
	font-weight: normal;
	line-height: 1.5;
	min-height: 100vh;
	overflow-x: hidden;
}
```

Along with ***other*** `property declarations` such as `color: #dcf0fb;`, `font-family: 'Barlow', sans-serif;`, `font-size: 0.75em;`, `font-weight: normal;` or `line-height: 1.5;`, I **add** the ***following*** `property declarations` ***specifically targeting*** the `background-image` **set** to the `body element` in the `HTML markup`:

```css
body {
	background-image: url(/images/bryan-minear-317365.jpg);
	background-position: center center;
	background-repeat: no-repeat;
	background-size: cover;
	min-height: 100vh;
	overflow-x: hidden;
}
```

I **set** the `background-image property` to the **value** of `url(/images/bryan-minear-317365.jpg);`. It is ***not*** injected dynamically. This way, the `image` is ***there*** from the **get-go**.

I **set** the `background-position property` of the `background-image` to `center center`, because I **want** the `image` to be **centered** on the `horizontal` AND the `vertical axes`. This becomes ***important*** in `smaller viewports`. I will **explain this** a ***bit later*** when I **get** to the `min-height` **property declaration**.

I **set** the `background-repeat property` of the `background-image` to `no-repeat`, because I ***don't want*** it to **repeat** either on the `horizontal` or `vertical axis` if there is **space available** for it to ***do so***. The **default behavior** is for the `image` to ***repeat*** as much as needed to **fill** the **available space** both on the `horizontal` and `vertical axes`.

I **set** the `background-size property` of the `background-image` to the **value** of the **keyword** `cover`. This ***means*** that the `background-image` will **cover** the ***entire*** `body container`, **even if** it has to **stretch** the `image` or **"cut"** a `little bit` off of **one** of the **edges**.

I **set** the `min-height property` of the `background-image` to the **value** of `100vh;`. if I did ***not*** do this, in ***smaller*** `viewport widths`, the `image` would ***reduce*** in `height` as well as `width`, ***thereby maintaining*** its `original proportions`. But I **wanted** to **be able** to **cover** the ***entire*** `viewport height` in these ***smaller*** `viewport widths`, so I **set** the `min-height` to `100vh;`. `100vh` **stands for** `100%` of the `viewport height`.

Then I **set** the `overflow-x property` to the **value** of `hidden;`, because **chances were** that there would be `overflow` on the `x axis`. In ***my case***, there **actually was**. It is ***important*** to **get rid** of this `overflow`, because it can ***cause problems*** in `mobile devices`.

</section>

---

<section class="section">
	<h2 class="sentence">Generating a random quote on top of the background-image with JavaScript</h2>

***Next***, I **wanted** to ***dynamically generate*** a `random quote` on **top** of the `body element`'s `background-image`. I **styled** the `text content` of the `quote` in my `external stylesheet`, but I ***dynamically generate*** the `quote` with `JavaScript` inside my `external JavaScript` file. ***First*** I **do** the ***following***:

```javascript
const quotes = [
    `Dancing is silent poetry. - Simonides`,
    `It does not matter how slowly you go, so long as you do not stop. — Confucius`,
    `Wait a minute, wait a minute. You ain\'t heard nothin\' yet! - The Jazz Singer`,
    `One morning I shot an elephant in my pajamas. How he got in my pajamas, I don\'t know. - Animal Crackers`,
    `Do, or do not. There is no "try". - Star Wars: Empire Strikes Back`,
    `Once you eliminate the impossible, whatever remains, no matter how improbable, must be the truth. - Sherlock Holmes`,
    `I can write better than anybody who can write faster, and I can write faster than anybody who can write better. - A. J. Liebling`,
    `The significant problems we face cannot be solved at the same level of thinking we were at when we created them. - Albert Einstein`,
    `Everybody pities the weak. Jealousy you have to earn. - Arnold Schwarzenegger`,
    `Mother of mercy, is this the end of Rico? - Little Caesar`,
    `I have not failed. I've just found 10,000 ways that won't work. - Thomas Alba Edison`
]
```

I `declare` and `initialize` a `const variable` called `quotes`. I `assign` it the **value** of an `array` of `quotes`. ***Each*** `quote` is **wrapped** in a `template string literal` `(``)`, and **separated** by `commas`.

So **what** is a [JavaScript array](https://www.w3schools.com/js/js_arrays.asp) and **what** is it ***used for***? A `JavaScript array` is a `variable`, which can **contain** as its `value`, ***more*** than `one value` at `a time`.

`JavaScript arrays` are **used** to ***store*** `multiple values` in a `single variable`.

An `array` can **hold** `many values` under a `single name`, and you can ***access*** the `values` by **referring** to an `index number`.

In the ***above*** `value` of the `quotes variable`, we **create** an `array` **using** an `array literal`. `[]`.

</section>

---

<section class="section">
	<h2 class="sentence">Accessing the elements of an array</h2>

We can ***access*** an `array element` by **referring** to the `index number`. If we **wanted** to `access` an `individual element` (`quote`) in the `quotes array`, we would **do** the ***following***:

```javascript
quotes[3]
```

The **number** `3` **represents** an `index number` of the `quotes array`. ***However***, in `JavaScript`, we ***always*** `start counting` from the **number** `0` (**just** as we **do** with `24 hour`, `military time`, ***for example***), so `3` does ***not represent*** the `index` of `3` **pointing** to the `3rd element` (`quote`) in the `array`, but the `index` of `4` **pointing** to the `4th element` (`quote`) in the `quotes array`.

</section>

---

<section class="section">
	<h2 class="sentence">Accessing the quoteContainer with JavaScript</h2>

***Next***, I **have** to **be able** to ***access*** the `quoteContainer` in **order** to **be able** to ***manipulate*** it with `JavaScript`. So ***next***, I **add** the ***following*** right below the `declaration` and `initialization` of the `quotes variable`:

```javascript
const quoteContainer = document.querySelector('.quote-container');
```

</section>

---

<section class="section">
	<h2 class='sentence'>Accessing the articleHeading with JavaScript</h2>

***Next***, I **have** to **be able** to ***access*** the `articleHeading` in **order** to **be able** to ***manipulate*** it with `JavaScript`. So ***next***, I **do** the ***following*** right below the `declaration` and `initialization` of the `quoteContainer variable`:

```javascript
const articleHeading = document.querySelector('h2');
```

By default, this h2 element inside the article element with the class of oud" in the HTML markup looks like the following:

```html5
<h2>Click for quote!</h2>
```

But we **want** to ***remove*** that `element` and its `text content` and **replace** it with the `text content` of a **randomly generated** `quote` with the **help** of `JavaScript`. That is ***why*** we **need** to ***access*** it **using** the `document.querySelector()` **method**.

</section>

---

<section class="section">
	<h2 class="sentence">Setting the articleHeading fontWeight to normal using JavaScript</h2>

***Next***, I **wanted** to **set** the `articleHeading` (`h2 element` **inside** the `article element` with the **class** of `.quote-cloud`) to the `fontWeight` of `normal`. i do this because I ***don't want*** the `text content` of the `h2 element` to ***appear*** `thick` and `heavy`. I **want** it to **appear** `normal`, so I **add** the ***following*** right below the `declaration` and `initialization` of the `articleHeading variable`:

```javascript
articleHeading.style.fontWeight = `normal`
```

I **set** the **JavaScript** `.style` **property** on the `articleHeading variable` **using** the **camel-cased** `fontWeight property` to ***apply*** the **value** of `normal` to the `articleHeading`.

</section>

---

<section class="section">
	<h2 class="sentence">So why use camel-case when naming variables (and anything else) in JavaScript?</h2>

It is **industry convention** to ***name*** variables **using** `camel-case` in `JavaScript`. ***Almost every*** `major JavaScript library` and the `core API` **uses** `camel-case`, so it is ***advisable*** that we **do** the ***same***.

`camel-case` **means** that the ***first part*** of the `name` which **represents** `one word` is ***all*** `lowercase`, and the ***second part*** of the `name`, which **represents** the `second word`, is **capitalized**. ***Not all*** `names` will contain `"two words"` (***or more*** in some cases), but **when** the `name` ***does contain*** `two` ore `more "words"`, the `name` is `"camel-cased"`.

</section>

---

<section class="section">
	<h2 class="sentence">Setting the .addEventListener() method on the quoteContainer</h2>

***Next***, I **wanted** to **be able** to ***manipulate*** the `quoteContainer`'s `content` when I ***clicked*** on it. So I **added** the ***following*** right below the **line** `articleHeading.style.fontWeight = "normal"`:

```javascript
/* randomize the index retrieval of the quotes array so that each time the user
clicks on the text rendered to the page, a random quote appears.*/
quoteContainer.addEventListener('click', () => {
	const blockQuote = document.querySelector('blockquote')
	const randomIndex = Math.floor(Math.random() * quotes.length);
	articleHeading.innerHTML = ``
	blockQuote.textContent = quotes[randomIndex]
})
```

By **setting** the `.addEventListener()` **method** on the `quoteContainer`, I ***attach*** a `click` **event handler** to the `quoteContainer`. The `name` of the `event` is `click`, and the `event handler` is the `anonymous function` **represented** by `() => {}`. ***Inside*** the `event handler` is the `code` which is `"executed"` when the `user` ***clicks*** on the `quoteContainer`.

**Inside** the `.addEventListener()` **method**, ***first*** I `declare` and `initialize` a `const variable` called `blockQuote`. I ***assign*** it the **value** of `document.querySelector('blockquote')` to ***access*** the `HTML element` in the `HTML markup` with the `name` of `blockquote`.

***Next***, I `declare` and `initialize` a `const variable` called `randomQuote`. I ***assign*** it the **value** of  `Math.floor(Math.random() * quotes.length);`. We **did** the ***same thing*** when ***generating*** a `random quote` on **top** of the `article element` with the (***same***) **class** of `.quote-cloud`.

So ***what*** does the **value** of the `randomQuote variable` ***mean***? First let's **break down** `Math.random() * quotes.length`.

`quotes.length` **represents** the `"length"` of the `quotes array`. The `number` of `quotes` **inside** the `quotes array`, ***each*** surrounded by `template strings`. In our `quotes array`, we have `11` **quotes**.

```javascript
const quotes = [
	`Dancing is silent poetry. - Simonides`,
    `It does not matter how slowly you go, so long as you do not stop. — Confucius`,
    `Wait a minute, wait a minute. You ain\'t heard nothin\' yet! - The Jazz Singer`,
    `One morning I shot an elephant in my pajamas. How he got in my pajamas, I don\'t know. - Animal Crackers`,
    `Do, or do not. There is no "try". - Star Wars: Empire Strikes Back`,
    `Once you eliminate the impossible, whatever remains, no matter how improbable, must be the truth. - Sherlock Holmes`,
    `I can write better than anybody who can write faster, and I can write faster than anybody who can write better. - A. J. Liebling`,
    `The significant problems we face cannot be solved at the same level of thinking we were at when we created them. - Albert Einstein`,
    `Everybody pities the weak. Jealousy you have to earn. - Arnold Schwarzenegger`,
    `Mother of mercy, is this the end of Rico? - Little Caesar`,
    `I have not failed. I've just found 10,000 ways that won't work. - Thomas Alba Edison`
]
```

`quotes.length` is **equal** to `11`. ***However***, we ***never*** start with the **number** `1` when ***counting*** the `number` of `items` in an `array`. We ***start with*** `0`. So `quotes[0]` would **represent** the ***first quote*** in the `array`, and `quotes[10]` would **represent** the `11`th **quote** in the `array`. ***Multiplying*** `quotes.length` by` Math.random()` will `return` a **number** between `0` and `10`, ***which is*** what **we want**!

The `Math.floor()` **method** simply **rounds down** a `number` to a ***whole integer*** instead of **keeping** a `number` that ***contains*** `decimal places`. We ***can't access*** an `element` (`quote`) in the `quotes array` that ***contains*** `decimal places`!

***Next***, I **needed** to **make sure** to ***clear*** the ***default*** `text content` of the `articleHeading`. So I **added** the ***following*** below the `declaration` and `initialization` of the `randomIndex variable`:

```javascript
articleHeading.innerHTML = ``
```

**Setting** the `.innerHTML property` on the `articleHeading` with the **value** of an `empty template string` `(``)` **clears** ALL the **content** between the ***opening*** and ***closing*** `h2 tags` of the `articleHeading` in the `HTML markup`.

***Next***, I **needed** to ***dynamically generate*** a `random quote` on **top** of the `body`'s `background-image`. I **added** the ***following*** to the `code block` **represented** by (`{}`) of the `quoteContainer.addEventListener()` **method**:

```javascript
blockQuote.textContent = quotes[randomIndex]
```

***Here***, the **JavaScript** `.textContent property` **sets** the `text content` of the `blockQuote` ***inside*** the `article element` with the **class** of `.quote-cloud` which is ***inside*** the `section element` with the **class** of `quote-container`. It is ***randomly generated*** because the `index` that we ***pass*** to the `quotes array`'s `index` ***created*** by **wrapping** it with ***opening*** and ***closing*** `square brackets` is a `random index`. The `quote` ***represented*** by the `template string` which is ***also*** a **representation** of an `element` (`quote`) in the `quotes array`, is then ***dynamically injected*** on **top** of the `background-image` of the `body element`.

</section>

---

<section class="section">
<h2 class="sentence">Styling the quoteContainer and its contents using the external stylesheet</h2>

**Unlike** the ***other way*** that I **present** in the `slide deck` entitled [Creating a Basic Background Image Using CSS (and JS)](https://github.com/interglobalmedia/basic-quote-image-background/blob/master/basic-quote-image-background.md), I am ***styling everything*** in my `external stylesheet`, and ***nothing*** with `JavaScript`. I **add** the ***following*** to my `external stylesheet`:

```css
body {
	background-image: url(/images/bryan-minear-317365.jpg);
	background-position: center center;
	background-repeat: no-repeat;
	background-size: cover;
	color: #dcf0fb;
	font-family: 'Barlow', sans-serif;
	font-size: 0.75em;
	font-weight: normal;
	line-height: 1.5;
	min-height: 100vh;
	overflow-x: hidden;
}
/* styles the h1 with the text content of Favorite Quotes */

main h1 {
	color: #44006c;
	font-size: 3.5em;
	font-weight: normal;
	line-height: 2;
	margin-top: 5rem;
	text-align: center;
	text-shadow: 1px 2px 2px rgba(0, 0 ,0, 0.5);
}

/* Quote Cloud */

.quote-container {
	cursor: pointer;
	display: flex;
	flex-direction: column;
	align-items: center;
	height: 50vh;
	justify-content: center;
	margin: 0 auto;
	padding: 0 1.5rem;
	width: 75%;
}

.quote-cloud {
	text-align: center;
}

h2 {
	font-size: 2.5em;
	text-shadow: 1px 2px 2px rgba(0, 0, 0, 0.7);
}

blockquote {
	font-size: 1.5em;
	text-shadow: 1px 2px 2px rgba(0, 0, 0, 0.7);
}

@media (min-width: 600px) {

	h1 {
		font-size: 3.5em;
	}

	h2 {
		font-size: 2.5em;
	}

    blockquote {
        font-size: 2.5em;
	}
}

/* media query for the Microsoft Lumia 550 with the width of 640px
and the height of 360px */
@media (max-width: 640px) and (max-height: 360px) {
    h2, blockquote {
        font-size: 1.5em;
	}
}

/* end .quote-container and .quote-cloud related styling */
```

***Everything*** is pretty much **self-explanatory** in the `CSS` ***provided above***. I just **wanted** to ***point out*** that I ***did add*** the `html element selector` **rule set** containing the ***following*** `font-size` **property declaration**:

```css
html {
	font-size: 100.01%;
}
```

***Then***, **inside** my `body element selector`, I **set** the ***base*** `font-size` and `line-height`:

```css
body {
	font-size: 0.75em;
	line-height: 1.5;
}
```

And ***then***:

```css
main h1 {
	font-size: 3.5em;
	line-height: 2;
}

h2 {
    font-size: 2.5em;
}

blockquote {
    font-size: 1.5em;
}

@media (min-width: 600px) {

    h1 {
        font-size: 3.5em;
    }

    h2 {
        font-size: 2.5em;
    }

    blockquote {
        font-size: 2.5em;
    }
}

/* media query for the Microsoft Lumia 550 with the width of 640px
and the height of 360px */
@media (max-width: 640px) and (max-height: 360px) {
    h2, blockquote {
        font-size: 1.5em;
    }
}
/* end .quote-container and .quote-cloud related styling */
```

I **wanted** to ***keep*** with the ***base*** `font-size` **set against** the `font-size` **property value** of the `html element selector`, but ***wanted*** to **set** `margins`, `padding`, etc. ***relative*** to the `viewport`. It **ended** up **working well** for me.

</section>

---

<section class="section">
	<h2 class="sentence">Related Resources</h2>

+ [CSS background-image Property: w3schools](https://www.w3schools.com/cssref/pr_background-image.asp)

+ [Creating a Basic Background Image Using CSS (and JS): Maria D. Campbell](https://github.com/interglobalmedia/basic-quote-image-background/blob/master/basic-quote-image-background.md)

+ [Images and their backgrounds in HTML5: Maria D. Campbell](https://github.com/interglobalmedia/image-backgrounds-rel-abs-paths/blob/master/image-backgrounds-rel-abs-paths.md)

</section>
