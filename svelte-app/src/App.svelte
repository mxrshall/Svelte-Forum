<script>
	import Navigation from './components/Navigation.svelte'
	import Search from './components/Search.svelte'
	import Prispevok from './components/Prispevok.svelte'

	let informacie = [
		{nazov: "Basketbal", kategoria: "Sport", text: "Toto je text!", id: 0},
		{nazov: "Tenis", kategoria: "Sport", text: "Mam rad tenis", id: 1},
	];

	const addInfo = (e) =>{
		const info = e.detail;
		informacie = [info, ...informacie];
	}

</script>

<header>
	<Navigation></Navigation>
	<Search></Search>
</header>

<main>
	
<section>
	<Prispevok on:addInfo={addInfo}></Prispevok>
	{#each informacie as info (info.id)}

<div class="container">
	<div class="profile"></div>
	<div class="row">
		<div class="nazov">
			<h1>{info.nazov}</h1>
		</div>
		<div class="kategoria">
			<small>#{info.kategoria}</small>
		</div>
		<div class="text">
			<h4>{info.text}</h4>	
		</div>
		<div class="icon">
			<img src="../assets/icon1.png" alt="Icon1" width="20px" height="20px">	
		</div>
	</div>
</div>
	{/each}

</section>
</main>

<style>

@import url('https://fonts.cdnfonts.com/css/helvetica-neue-9');

.container{
	width: 700px;
    height: 100px;
	padding: 5px;
    margin: 5px;
	display: flex;
	justify-content: right;
	align-items: center;
}

.profile{
	width: 70px;
	height: 70px;
	background-image: url(../assets/profile_icon.png);
    background-size: cover;
	border-radius: 50%;
	border: 3px solid #7DC5D4;
}

.row{
    width: 600px;
    height: 100px;
    display: grid;
	grid-template-columns: 500px 100px;
    padding: 5px;
    margin: 5px;
    border-radius: 15px;
	border: 2px solid #7DC5D4;
	font-size: 15px;
	font-family: 'Helvetica Neue', sans-serif;
}

.nazov{
	background-color: yellow;
}

.kategoria{
	padding-top: 4px;
	background-color: blueviolet;
}

.text{
	background-color: chartreuse;
	word-break: break-all;
}

.icon{
	display: flex;
	justify-content: center;
	align-items: center;
}

</style>