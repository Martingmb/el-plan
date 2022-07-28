<script>
  import { Button, Card } from "spaper";
  import { slide } from "svelte/transition";
  import { onMount } from "svelte";
  import SC from "./SummaryComponent.svelte";
  import dataJson from "./data";

  export let summary;

  let places = [];

  onMount(() => {
    places.push(dataJson[summary["foodChoice"]]);
    for (const activity of summary.activities) {
      places.push(dataJson[activity]);
    }
    places = places.sort(function (a, b) {
      return a.startTime - b.startTime;
    });
  });
</script>

<div class="paper border border-secondary border-dotted">
  <h3>Itinerario, ps tomale foto</h3>
  <div class="row" transition:slide>
    {#each places as place}
      <SC bind:data={place} />
    {/each}
  </div>
</div>
