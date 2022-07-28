<script>
	import { fade, fly, slide } from 'svelte/transition';
	import { Button, Radio, Checkbox } from 'spaper';
	import Activities from './Activities.svelte';
	import Food from './Food.svelte';
	import Summary from './Summary.svelte'
	
	let activities = [];
	let foodChoice = undefined;
	let summary = undefined;
	let sceneCounter = 0;
	
	const attending = (event) => activities.includes(event)
	
	const optionsObject = {
		attendTennis: false,
		attendKarts: false,
		attendEscapeRoom: false,
		chilaquiles: false
	};
	
	const attendingEvents = [];
	
	const handleClick = () => {
		if(activities.length == 0) {
			alert('Tienes que seleccionar una opcion');
		} else {
			sceneCounter += 1;
			if(sceneCounter == 2) {
				summary = {
					activities,
					foodChoice
				}
			}
		}
	}
</script>
<link rel="stylesheet" href="https://unpkg.com/papercss@1.8.3/dist/paper.min.css">
<h1>La Salida del Sabado</h1>

{#if sceneCounter == 0}
<Activities bind:activities/>
{:else if sceneCounter == 1}
<Food bind:foodChoice/>
{:else if sceneCounter == 2}
<Summary bind:summary/>
{/if}

{#if sceneCounter < 2}
<Button size="small" on:click={handleClick}>Siguiente</Button>
{/if}
