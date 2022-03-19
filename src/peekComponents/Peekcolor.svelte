<script>

function selectColor(colorNum, colors){
    if (colors < 1) colors = 1; // defaults to one color - avoid divide by zero
    return "hsl(" + (colorNum * (360 / colors) % 360) + ",100%,50%)";
}

function chBackcolor() {
   document.body.style.background = selectColor(Math.floor(Math.random() * 999), 10);;
}	
function toNormal() {
   document.body.style.background = "white";
}	
// import { Button } from 'sveltestrap';
import {  Button } from 'svelte-materialify';
</script>


<Button class="orange white-text" on:click={chBackcolor}>5tar LOUN|FARBE 3AFAK!</Button>
<p></p>
<Button class="grey black-text" on:click={toNormal}>NORMAL PLease!</Button>




