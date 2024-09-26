<script lang="ts">
	export let pokemonId: string;

	let promise = fetch(`https://pokeapi.co/api/v2/pokemon/${pokemonId}`).then((res) => res.json());
</script>

{#await promise}
	<p>Cargando...</p>
{:then data}
	<div class="card border bg-base-100 col-span-4 shadow-xl">
		<figure>
			<img
				src={`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${pokemonId}.png`}
				alt=""
				width={200}
				height={200}
				class="size-[200px]"
			/>
		</figure>
		<div class="card-body">
			<h2 class="card-title">
				{data.name.charAt(0).toUpperCase() + data.name.slice(1)}
			</h2>
			<p>Pokedex ID: {pokemonId}</p>
			<p>Peso: {data.weight}</p>
			<p>Altura: {data.height}</p>
			<div class="card-actions justify-end"></div>
		</div>
	</div>
{/await}