<script lang="ts">
	export let name: string;
	export let url: string;

	const pokemonId = url.slice(0, -1).split("/").pop();
</script>

<div class="card border bg-base-100 col-span-4 shadow-xl">
	<figure>
		<img
			src={`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${pokemonId}.png`}
			alt={name}
			width={200}
			height={200}
			class="size-[200px]"
		/>
	</figure>
	<div class="card-body">
		<h2 class="card-title">
			{name.charAt(0).toUpperCase() + name.slice(1)}
		</h2>
		<p>Pokedex ID: {pokemonId}</p>
		<div class="card-actions justify-end">
			<a href={`/pokemon/${pokemonId}`} class="btn btn-primary"> Ver Pokemon </a>
		</div>
	</div>
</div>