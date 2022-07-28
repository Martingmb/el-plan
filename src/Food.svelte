<script>
	import { Radio } from 'spaper';
	import { slide } from 'svelte/transition';
	
	export let foodChoice = undefined;
</script>

<div class="paper container-md border border-success border-dashed" transition:slide>
	<fieldset class="form-group">
		<h3>
			Comidas
		</h3>
		<p>¿Qué te gustaria comer?</p>
		<Radio value="chilaquiles" label="Chilaquiles <" bind:group={foodChoice}/>
		<Radio value="fogodechao" label="Churrasco Brasileiro <" bind:group={foodChoice}/>
		<Radio value="americano" label="Americano <" bind:group={foodChoice}/>
		<Radio value="italiano" label="Italiano <" bind:group={foodChoice}/>
		<Radio value="cortes" label="Steakhouse >" bind:group={foodChoice}/>
		<Radio value="mexicano" label="Mexicana <" bind:group={foodChoice}/>
		<Radio value="null" label="Ninguno" bind:group={foodChoice}/>
	</fieldset>
</div>

