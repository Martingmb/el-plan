<script>
  import { Radio } from "spaper";
  import { slide } from "svelte/transition";

  export let foodChoice = undefined;
</script>

<div
  class="paper container-md border border-success border-dashed"
  transition:slide
>
  <fieldset class="form-group">
    <h3>Comidas</h3>
    <p>Â¿QuÃ© te gustaria comer?</p>
    <Radio value="chilaquiles" label="Chilaquiles ð²" bind:group={foodChoice} />
    <Radio
      value="fogodechao"
      label="Churrasco Brasileiro ð"
      bind:group={foodChoice}
    />
    <Radio value="americano" label="Americano ð" bind:group={foodChoice} />
    <Radio value="italiano" label="Italiano ð" bind:group={foodChoice} />
    <Radio value="cortes" label="Steakhouse ð¥©" bind:group={foodChoice} />
    <Radio value="mexicano" label="Mexicana ð¶ï¸" bind:group={foodChoice} />
    <Radio value="null" label="Ninguno" bind:group={foodChoice} />
  </fieldset>
</div>
