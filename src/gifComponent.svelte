<!-- SCRIPT -->
<script>

	let search = '';
	let loading = false;
    // 'https://api.giphy.com/v1/gifs/search?api_key=yAQFKnN1xs5b6lXKQitvudVg5WadxtH0&limit=10&offset=0&rating=g&lang=en&q='

    async function getApi() {

        let response = await fetch("https://api.mocki.io/v1/7ce1d76a");
                let users = await response.json();
    return users;
  }
  const promise = getApi();
  
//   https://app.sportdataapi.com/api/v1/soccer/countries?apikey=268faa80-a866-11ec-9bf2-c70f0d52f7c5&continent=Europe
	const API_URL ='https://www.scorebat.com/video-api/v3/feed/?token=MTU5MTJfMTY0Nzc5MzE5NF82MjJhNDYzZjkyNWJmMjgzZGI5NGZmYzU2MWJmMmE5ZjYyYmY5MjRk';
	let gifs = [];
	async function formSubmitted(event) {
		event.preventDefault();
		loading = true;
		gifs = [];
		const url = `${API_URL}`;
		const response = await fetch(url);
        console.log(response);
		const json = await response.json();
        console.log(json.data);
		// gifs = json.data.map(gif => gif.images.fixed_height.url);
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

<div>
    {#await promise}
        <p>Loading...</p>
    {:then user}
        {#each user as user}
        <p>Name is {user.name}, ID: {user.id}</p>
        {/each}
    {:catch error}
        <p style="color: red">{error.message}</p>
    {/await}
    </div>
