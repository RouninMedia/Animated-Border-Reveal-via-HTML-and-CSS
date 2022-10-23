# Animated Border Reveal (via HTML and CSS)
*Using a combination of CSS Grid and CSS Animation, any rectangular HTML Element may be given an Animated Border Reveal.*

## HTML:
```html
<div class="animatedBorder">
  <div class="topRightOuter">
    <div class="topRightInner inner"></div>
  </div>
  
  <div class="rightOuter">
    <div class="rightInner inner"></div>
  </div>
  
  <div class="bottomOuter">
    <div class="bottomInner inner"></div>
  </div>
  
  <div class="leftOuter">
    <div class="leftInner inner"></div>
  </div>
  
  <div class="topLeftOuter">
    <div class="topLeftInner inner"></div>
  </div>
</div>
  
<div class="textbox">
  <p>Hover me</p>  
</div>
```

## CSS:
```css

.animatedBorder,
.textbox {
  position: absolute;
  top: 0;
  left: 0;
}

.textbox {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 4px;
  background-color: rgb(127, 127, 127);
}

.animatedBorder {
  display: grid;
  grid-template-columns: 2% 1fr 1fr 2%;
  grid-template-rows: 2% 1fr 2%;
  width: 200px;
  height: 200px;
  border: 1px solid rgb(127, 0, 0);
}

.animatedBorder:hover {
  cursor: pointer;
}

.topRightInner,
.rightInner,
.bottomOuter,
.leftOuter,
.topLeftInner {
  background-color: rgb(191, 0, 0);
}

.bottomInner,
.leftInner {
  width: 100%;
  height: 100%;
  background-color: rgb(255, 255, 255);
}

.topRightInner,
.topLeftInner {
  width: 0%;
  height: 100%;
}

.rightInner {
  width: 100%;
  height: 0%;
}

.topRightOuter {
  grid-column: 3 / 4;
  grid-row: 1 / 2;
}

.rightOuter {
  grid-column: 4 / 5;
  grid-row: 1 / 4;
}

.bottomOuter {
  grid-column: 2 / 4;
  grid-row: 3 / 4;
}

.leftOuter {
  grid-column: 1 / 2;
  grid-row: 1 / 4;
}

.topLeftOuter {
  grid-column: 2 / 3;
  grid-row: 1 / 2;
}

.animatedBorder:hover .topRightInner {
  animation: animateTopRightBorder 0.2s ease-in forwards; 
}

.animatedBorder:hover .rightInner {
  animation: animateRightBorder 0.4s linear 0.2s forwards; 
}

.animatedBorder:hover .bottomInner {
  animation: animateBottomBorder 0.4s linear 0.6s forwards; 
}

.animatedBorder:hover .leftInner {
  animation: animateLeftBorder 0.4s linear 1s forwards;
}

.animatedBorder:hover .topLeftInner {
  animation: animateTopLeftBorder 0.2s ease-out 1.4s forwards; 
}

@keyframes animateTopRightBorder {100% {width: 100%;}}
@keyframes animateRightBorder {100% {height: 100%;}}
@keyframes animateBottomBorder {100% {width: 0%;}}
@keyframes animateLeftBorder {100% {height: 0%;}}
@keyframes animateTopLeftBorder {100% {width: 100%;}}
```
