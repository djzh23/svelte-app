<!-- SCRIPT -->
<script>
import {  Button } from 'svelte-materialify';

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

</script>

<!-- HTML -->
<div class="wrapper">
	<div class="link_wrapper">
		<Button class="orange white-text" on:click={chBackcolor}>5tar LOUN | FARBE 3AFAK !</Button>
	</div>
		<p></p>
		<Button class="grey black-text" on:click={toNormal}>NORMAL PLease !</Button>

</div>

<!-- STYLE -->
<style>
	.wrapper{
	  position: fixed;

	  top: 50%;
	  left: 50%;
	  transform: translate(-50%, -50%);
	}
	
	.link_wrapper{
		height: 50px;
	  position: relative;
	}
	
	a{
	  display: block;

	  width: 450px;
	  line-height: 80px;
	  font-weight: bold;
	  text-decoration: none;
	  /* background: #333; */
	  text-align: center;
	  color: #fff;
	  text-transform: uppercase;
	  letter-spacing: 1px;
	  transition: all .35s;
	}

	a:hover{
	  width: 300px;
	  background: transparent;
	  color: #d9f39d;
	}
	
  </style>
