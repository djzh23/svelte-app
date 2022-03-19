<!-- SCRIPT -->
<script>

	let search = '';
	let loading = false;
	const API_URL = 'https://api.giphy.com/v1/gifs/search?api_key=yAQFKnN1xs5b6lXKQitvudVg5WadxtH0&limit=10&offset=0&rating=g&lang=en&q=';
	let gifs = [];
	async function formSubmitted(event) {
		event.preventDefault();
		loading = true;
		gifs = [];
		const url = `${API_URL}${search}`;
		const response = await fetch(url);
		const json = await response.json();
		gifs = json.data.map(gif => gif.images.fixed_height.url);
		loading = false;
	}



    import { Button, MaterialApp,TextField } from 'svelte-materialify';
</script>

<!-- CSS -->
<style>
.results {
	column-count: 3;
}
img {
	width: 100%;
	height: auto;
}
.formdiv{
    /* background-color: rgb(4, 20, 20); */
    margin: auto;
  width: 50%;
  /* border: 3px solid green; */
  padding: 10px;
}
.labeldiv{
    /* margin: auto; */
    /* width: 50%; */
    /* border: 3px solid green; */
    /* padding: 10px; */
    /* background-color: rgb(39, 177, 177); */
    text-align: center;
    /* border: 2px solid green; */
}
</style>


<!-- HTML -->

<div class="formdiv" >
    <h1 style="text-align: center; font-size:xx-large;"><b>&#127820; GIFs</b>'khaloutabhjcbjvd </h1>
    <form on:submit={formSubmitted}>
        
        <div class="labeldiv"   style="text-align: letf ;">
            <MaterialApp>
            <label for="search"  style="font-family: 'Nunito', sans-serif; color: white; font-weight: bolder;">Search</label>
            <MaterialApp>
                <TextField bind:value={search} id="search" name="search" placeholder="mchicha ... ?"  solo />
            </MaterialApp>
                <Button type="submit" class="primary-color">Hop</Button>
            </MaterialApp>
        </div>
    </form>
</div>

{#if loading}
	<img alt="loading" src="https://media2.giphy.com/media/l3nWhI38IWDofyDrW/giphy.gif?cid=790b76115d055ab7424f75514dcb4d7a&rid=giphy.gif" />
{/if}

<div class="results">
	{#each gifs as gif}
		<img alt="gif" src={gif} />
	{/each}
</div>
