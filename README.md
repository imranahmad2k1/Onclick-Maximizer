# Onclick-Maximizer
A javascript code-snippet for viewing images on full screen panel using mouse click.

## Instructions

### 1. Add following JavaScript code to your project
```html
const imgs = document.querySelectorAll('.gallery img');
const fullPage = document.querySelector('#fullpage');
const body = document.querySelector('body');

imgs.forEach(img => {
    img.addEventListener('click', function() {
           fullPage.style.backgroundImage = 'url(' + img.src + ')';
           fullPage.style.display = 'block';
           body.style.overflow = "hidden";
    });
 });

function closer(){
     let a = document.getElementById('fullpage');
     a.style.display='none';
     body.style.overflow = "visible";    
}
```
<br>
Replace <b>'.gallery img'</b> in the following line with class of your target images

Line: 45 `const imgs = document.querySelectorAll('.gallery img');`

### 2. Add following CSS styles to your Project

```html
#fullpage {
   display: none;
   position: absolute;
   z-index: 9999;
   top: 0;
   left: 0;
   width: 100vw;
   height: 100vh;
   background-size: contain;
   background-repeat: no-repeat no-repeat;
   background-position: center center;
   background-color: black;
}

#close{
   position:absolute;
   right: 0px;
}
```

### 3. Add the following code on the page you want to use 'Onclick Maximizer'

```html
<div id="fullpage">
  <button id="close" onclick="closer()">X</button>
</div>
```


