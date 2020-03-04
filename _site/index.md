
Just goofing around. Software stars.

Step 1: google for javascript draw on canvas find https://www.w3schools.com/graphics/canvas_drawing.asp
copy and paste (see <script/> below)

2: google for javascript timer. get https://www.w3schools.com/js/js_timing.asp copy the code at the end. Try to remember javascript language.

3: put the draw in the myTimer.

4: google for javascript array of objects. find https://www.w3schools.com/js/js_arrays.asp. add stars. 

5: Curse go for making me always forget parens in if statements.

6: push, get a snack. 

<button type="button" id="stopbutton" >Go</button> <button type="button" id="sizebutton" >Big</button>

<canvas id="myCanvas" width="512" height="512"></canvas>

<script>
var canvas = document.getElementById("myCanvas");
var ctx = canvas.getContext("2d");

var myVar = setInterval(myTimer, 10);

var stars = new Array();

var running = false
var mid = 256

function myTimer() {

    if ( running == false )
        return;
  
    ctx.fillStyle = "#000000";
    ctx.fillRect(0, 0, mid*2, mid*2);
    ctx.fillStyle = "#FFFFFF";

    for ( i = 0; i < 1000 ; i ++ ){
        if (stars.length <= i) {
            star = {x:0,y:0,z:0}
            stars[i] = star;
        }
        star = stars[i]
        xt = star.x / star.z + mid
        yt = star.y / star.z + mid
        size = 0.2 + 1/400 / star.z

        if (size >= 2.0) {
            ctx.beginPath();
            ctx.arc(xt+size/2, yt+size/2, size, 0, 2 * Math.PI, false);
            ctx.fillStyle = 'white';
            ctx.fill(); 
        } else {
            ctx.fillRect(xt, yt, size, size);
        }

        star.z = star.z - 1/50000

        if (xt < 0 || xt >= mid*2 || yt < 0 || yt >= mid*2 || star.z <= 0) {
            star.x = 2*Math.random() - 1
            star.y = 2*Math.random() - 1
            star.z = Math.random()/100
        } 
    }
}

button = document.getElementById('stopbutton');
function whenClicked(e) {
    running = ! running
    console.log("running="+running)
}
button.onclick = whenClicked
button = document.getElementById('sizebutton');
button.onclick = function(e) {
    canvas.width = 1024
    canvas.height = 1024
    mid = 512
    console.log("big="+mid)
}

</script>

Looking at the text of this page shows how the stars are made inside of a 'static' blog page:

```javascript

Just goofing around. Software stars.

Step 1: google for javascript draw on canvas find https://www.w3schools.com/graphics/canvas_drawing.asp
copy and paste (see <script/> below)

2: google for javascript timer. get https://www.w3schools.com/js/js_timing.asp copy the code at the end. Try to remember javascript language.

3: put the draw in the myTimer.

4: google for javascript array of objects. find https://www.w3schools.com/js/js_arrays.asp. add stars. 

5: Curse go for making me always forget parens in if statements.

6: push, get a snack. 

<canvas id="myCanvas" width="512" height="512"></canvas>

<script>
var canvas = document.getElementById("myCanvas");
var ctx = canvas.getContext("2d");

var myVar = setInterval(myTimer, 10);

var stars = new Array();

function myTimer() {

    console.log(stars.length)
  
    ctx.fillStyle = "#000000";
    ctx.fillRect(0, 0, 512, 512);
    ctx.fillStyle = "#FFFFFF";

    for ( i = 0; i < 1000 ; i ++ ){
        if (stars.length <= i) {
            star = {x:0,y:0,z:0}
            stars[i] = star;
        }
        star = stars[i]
        xt = star.x / star.z + mid
        yt = star.y / star.z + mid
        size = 0.2 + 1/400 / star.z

        if (size >= 2.0) {
            ctx.beginPath();
            ctx.arc(xt+size/2, yt+size/2, size, 0, 2 * Math.PI, false);
            ctx.fillStyle = 'white';
            ctx.fill(); 
        } else {
            ctx.fillRect(xt, yt, size, size);
        }

        star.z = star.z - 1/50000

        if (xt < 0 || xt >= 512 || yt < 0 || yt >= 512 || star.z <= 0) {
            star.x = 2*Math.random() - 1
            star.y = 2*Math.random() - 1
            star.z = Math.random()/100
        } 
    }
}

</script>

Looking at the text of this page shows how the stars are made inside of a 'static' blog page. 

<div id = "atwheader" >
- Alan Tracey Wootton -
</div>

<!-- <div id="commento"></div>
<script src="https://cdn.commento.io/js/commento.js"></script> -->

```

<div id = "atwheader" >
- Alan Tracey Wootton -
</div>


<div id="commento"></div>
<script src="https://cdn.commento.io/js/commento.js"></script>
