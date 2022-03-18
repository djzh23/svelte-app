<script>

function selectColor(colorNum, colors){
    if (colors < 1) colors = 1; // defaults to one color - avoid divide by zero
    return "hsl(" + (colorNum * (360 / colors) % 360) + ",100%,50%)";
}

function chBackcolor() {
   document.body.style.background = selectColor(Math.floor(Math.random() * 999), 10);;
}	
</script>

		<button style="display: flex;
		justify-content: center;
		align-items: center;
		height: 50px;
		border:5px solid blue;
		font-size: x-large;
		" on:click={chBackcolor}>
			5tar LOUN|FARBE 3AFAK!
		</button>



