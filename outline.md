## Cool CSS: 6 Cool CSS Tricks

### Initial Setup

1. Have terminal window open full screen (bump font size up four times)
2. Have VSCode open (make sure to bump font size up twice Cmd-Shift-+)
3. Webcam should be in the lower right corner to begin
4. Turn on do not disturb

### Outline

1. Basic Setup
2. Sidebar Layout
3. Pancake Layout
4. Pancake with Sidebars Layout
5. One Line Center
6. Evenly Spaced Card
7. C-Span Grid
8. Conclusion

#### Basic Setup

1. Create directory for project: _mkdir css-tricks_
2. Navigate into that directory: _cd css-tricks_
3. Create outline file _touch outline.md_
4. Open VSCode _code ._
5. Open VSCode Terminal _Ctrl-`_
6. Bring in outline contents and preview (Markdown Preview Enhanced Plugin) _Cmd-K, V_
7. Create main.css: _touch main.css_
8. Add the following code main.css

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: system-ui, sans-serif;
}
```

#### Sidebar Layout

1. Create sidebar-layout.html: _touch sidebar-layout.html_
2. Create sidebar-layout.css: _touch sidebar-layout.css_
3. Open sidebar-layout.html
4. Create html skeleten document with Emmet _html:5_
5. Add css link to sidebar-layout.css & main.css in sidebar-layout.html

```html
<link rel="stylesheet" href="main.css" />
<link rel="stylesheet" href="sidebar-layout.css" />
```

6. Add the following code to the body sidebar-layout.html

```html
<div class="container">
  <aside class="sidebar"><h1>Sidebar (☕️)</h1></aside>
  <div class="content"></div>
</div>
```

7. Add the following code sidebar-layout.css

```css
.container {
  display: grid;
  /* side bar*/
  grid-template-columns: minmax(150px, 25%) 1fr;
  /* end side bar*/
}

.sidebar {
  height: 100vh;
  background-color: cornflowerblue;
  padding-left: 20px;
}
```

#### Pancake Layout

1. Create pancake-layout.html: _touch pancake-layout.html_
2. Create pancake-layout.css: _touch pancake-layout.css_
3. Open pancake-layout.html
4. Create html skeleten document with Emmet _html:5_
5. Add css link to pancake-layout.css & main.css in pancake-layout.html

```html
<link rel="stylesheet" href="main.css" />
<link rel="stylesheet" href="pancake-layout.css" />
```

6. Add the following code to the body pancake-layout.html

```html
<div class="container">
  <header>Header</header>
  <main class="">Main</main>
  <footer>Footer &copy;2020</footer>
</div>
```

7. Add the following code pancake-layout.css

```css
.container {
  display: grid;
  height: 100vh;

  /* pancake layout */
  grid-template-rows: auto 1fr auto;
  /* end pancake layout */
}

header {
  padding: 1.5rem;
  color: white;
  background: navy;
}

footer {
  padding: 1.5rem;
  text-align: center;
  color: white;
  background: navy;
}
```

#### Pancake with Sidebars Layout

1. Create pancake-sides-layout.html: _touch pancake-sides-layout.html_
2. Create pancake-sides-layout.css: _touch pancake-sides-layout.css_
3. Open pancake-sides-layout.html
4. Create html skeleten document with Emmet _html:5_
5. Add css link to pancake-sides-layout.css & main.css in pancake-sides-layout.html

```html
<link rel="stylesheet" href="main.css" />
<link rel="stylesheet" href="pancake-sides-layout.css" />
```

6. Add the following code to the body pancake-sides-layout.html

```html
<div class="container">
  <header>Header</header>
  <div class="left-sidebar">Left Sidebar</div>
  <main>Main</main>
  <div class="right-sidebar">Right Sidebar</div>
  <footer>Footer &copy;2020</footer>
</div>
```

7. Add the following code pancake-sides-layout.css

```css
.container {
  display: grid;
  height: 100vh;

  /* basic three column layout*/
  grid-template: auto 1fr auto / auto 1fr auto;
}

header {
  background: navy;
  grid-column: 1 / 4;
  padding: 1rem;
  color: white;
}

.left-sidebar {
  background: aliceblue;
  grid-column: 1 / 2;
}

main {
  grid-column: 2 / 3;
}

.right-sidebar {
  background: aliceblue;
  grid-column: 3 / 4;
}

footer {
  background: navy;
  padding: 1rem;
  text-align: center;
  grid-column: 1 / 4;
  color: white;
}

.left-sidebar,
.right-sidebar {
  padding: 2rem;
}
```

#### One Line Center

1. Open sidebar-layout.html and update the following code

```html
<div class="content"><div class="icon-box">☕️</div></div>
```

2. Open sidebar-layout.css and add the following code

```css
.content {
  display: grid;
  /* one line center*/
  place-items: center;
  /* end one line center*/
}
```

3. Open main.css and add the following code

```css
.icon-box {
  height: 125px;
  background: aquamarine;
  display: grid;
  place-items: center;
  font-size: 3em;
}
```

#### Evenly Spaced Card

1. Open pancake-sides-layout.html and update the following code

```html
<main>
  <div class="card-container">
    <div class="card">
      <h3>Coding Tech</h3>
      <p contenteditable>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas, dolore
        dicta minima laboriosam repudiandae dolorem sit! Tempora exercitationem
        rem error!
      </p>
      <div class="icon-box">💻</div>
    </div>
    <div class="card">
      <h3>Lessons</h3>
      <p contenteditable>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas, dolore
        dicta minima laboriosam repudiandae dolorem sit! Tempora exercitationem
        rem error!
      </p>
      <div class="icon-box">📱</div>
    </div>
    <div class="card">
      <h3>HTML/CSS/JavaScript</h3>
      <p contenteditable>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas, dolore
        dicta minima laboriosam repudiandae dolorem sit! Tempora exercitationem
        rem error!
      </p>
      <div class="icon-box">🎮</div>
    </div>
  </div>
</main>
```

2. Open main.css and add the following code

```css
.card {
  /* even card spacing */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  /* end even card spacing */

  background: skyblue;
  padding: 1rem;
  margin: 5px;
}
```

3. Open pancake-sides-layout.css and add the following code

```css
.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.card {
  /* pancake no stretch */
  /* flex: 1 1 200px;  */
  /* end pancake no stretch */

  /* pancake with stretch */
  flex: 0 1 200px;
  /* end pancake with stretch */
}
```

#### C-Span Grid

1. Open pancake-layout.html and update the following code

```html
<div class="container">
  <header class="content-centered">Results</header>
  <main>
    <div class="c-span-grid">
      <div class="span-grid-text span-gold icon-box">🥇</div>
    </div>
    <div class="c-span-grid">
      <div class="span-grid-text span-silver icon-box">🥈</div>
      <div class="span-grid-text span-bronze icon-box">🥉</div>
    </div>
  </main>
  <footer class="dark-blue">Footer &copy;2020</footer>
</div>
```

2. Open pancake-layout.css and add the following code

```css
.c-span-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
}

.span-grid-text {
  display: grid;
  place-items: center;
}

.span-results {
  grid-column: 1 / 13;
  background-color: wheat;
}

.span-gold {
  grid-column: 6 / 8;
  background-color: gold;
}
.span-silver {
  grid-column: 4 / 6;
  background-color: silver;
}
.span-bronze {
  grid-column: 8 / span 2;
  background-color: #cd7f32;
}
```

## Conclusion

1. You can find a link to code on GitHub below in the description of this video
2. Don't forget to like, comment, subscribe and share so we can keep bring you this free content.
3. What would you like to see next?
4. Alright, so you all on the next one! Happy Coding!
