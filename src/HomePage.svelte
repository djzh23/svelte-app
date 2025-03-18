<div class="header">
  <h1>LIMADA NA7NOU HOUNA !</h1>
  <p>A website created by IDFKN.</p>
</div>

<!-- <div class="navbar">
  <a href="#a">Link</a>
  <a href="#s">Link</a>
  <a href="#d">Link</a>
  <a href="#current-blog-post" class="right">Blog</a>
</div> -->



<script>
	import Card from './components/common/Card.svelte';
	import { List, ListItem, Divider, Subheader, Avatar, MaterialApp } from 'svelte-materialify';
</script>

<MaterialApp>
	<div class="hero">
		<div class="hero-content">
			<h1>Welcome to Our App</h1>
			<p>Your one-stop solution for managing tasks and staying organized</p>
		</div>
	</div>

	<div class="features-grid">
		<Card title="Main Features" icon="✨">
			<List>
				<ListItem>
					<div slot="prepend">
						<Avatar><img src="//picsum.photos/100?random=1" alt="Shopping" /></Avatar>
					</div>
					Shopping List
					<span slot="subtitle">Manage your grocery shopping efficiently</span>
				</ListItem>
				<Divider inset />
				<ListItem>
					<div slot="prepend">
						<Avatar><img src="//picsum.photos/100?random=2" alt="Gallery" /></Avatar>
					</div>
					Photo Gallery
					<span slot="subtitle">View and organize your memories</span>
				</ListItem>
				<Divider inset />
				<ListItem>
					<div slot="prepend">
						<Avatar><img src="//picsum.photos/100?random=3" alt="Todo" /></Avatar>
					</div>
					Todo List
					<span slot="subtitle">Keep track of your daily tasks</span>
				</ListItem>
			</List>
		</Card>

		<Card title="Quick Actions" icon="⚡">
			<List>
				<ListItem>
					<div slot="prepend">
						<Avatar><span>📝</span></Avatar>
					</div>
					Create New Todo
					<span slot="subtitle">Add a new task to your list</span>
				</ListItem>
				<Divider inset />
				<ListItem>
					<div slot="prepend">
						<Avatar><span>📸</span></Avatar>
					</div>
					Upload Photos
					<span slot="subtitle">Add new photos to your gallery</span>
				</ListItem>
				<Divider inset />
				<ListItem>
					<div slot="prepend">
						<Avatar><span>🛒</span></Avatar>
					</div>
					New Shopping List
					<span slot="subtitle">Start a new shopping list</span>
				</ListItem>
			</List>
		</Card>
	</div>
</MaterialApp>

<div class="footer">
  <h2>Footer</h2>
</div>


<style>
	* {
		box-sizing: border-box;
	}
	
	/* Header/logo Title */
	.header {
		padding: 80px;
		text-align: center;
		background: #1abc9c;
		color: white;
	}

	/* Increase the font size of the heading */
	.header h1 {
		font-size: 40px;
	}

	/* Style the top navigation bar */
	.navbar {
		overflow: hidden;
		background-color: #333;
	}

	/* Style the navigation bar links */
	.navbar a {
		float: left;
		display: block;
		color: white;
		text-align: center;
		padding: 14px 20px;
		text-decoration: none;
	}

	/* Right-aligned link */
	.navbar a.right {
		float: right;
	}

	/* Change color on hover */
	.navbar a:hover {
		background-color: #ddd;
		color: black;
	}

	/* Column container */
	.row {  
		display: -ms-flexbox; /* IE10 */
		display: flex;
		-ms-flex-wrap: wrap; /* IE10 */
		flex-wrap: wrap;

	}

	/* Create two unequal columns that sits next to each other */
	/* Sidebar/left column */
	.side {
		-ms-flex: 30%; /* IE10 */
		flex: 30%;
		background-color: #f1f1f1;
		padding: 20px;
	}

	/* Main column */
	.main {   
		-ms-flex: 70%; /* IE10 */
		flex: 70%;
		background-color: white;
		padding: 20px;
	}

	/* Fake image, just for this example */
	.fakeimg {
		background-color: #aaa;
		width: 100%;
		padding: 20px;
	}
	
	
	/* Footer */
	.footer {
		padding: 20px;
		text-align: center;
		background: #ddd;
	}

	/* Responsive layout - when the screen is less than 700px wide, make the two columns stack on top of each other instead of next to each other */
	@media screen and (max-width: 700px) {
		.row {   
			flex-direction: column;
		}
	}

	/* Responsive layout - when the screen is less than 400px wide, make the navigation links stack on top of each other instead of next to each other */
	@media screen and (max-width: 400px) {
		.navbar a {
			float: none;
			width: 100%;
		}
	}

	.hero {
		background: linear-gradient(135deg, #1976d2, #64b5f6);
		color: white;
		padding: 4rem 2rem;
		text-align: center;
		margin-bottom: 2rem;
		border-radius: 8px;
	}

	.hero-content {
		max-width: 800px;
		margin: 0 auto;
	}

	.hero h1 {
		font-size: 2.5rem;
		margin-bottom: 1rem;
	}

	.hero p {
		font-size: 1.2rem;
		opacity: 0.9;
	}

	.features-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		gap: 2rem;
		margin-top: 2rem;
	}

	:global(.mdc-list-item) {
		padding: 1rem;
	}

	:global(.mdc-list-item__text) {
		padding: 0 1rem;
	}

	@media (max-width: 768px) {
		.hero {
			padding: 3rem 1rem;
		}

		.hero h1 {
			font-size: 2rem;
		}

		.features-grid {
			grid-template-columns: 1fr;
		}
	}
</style>