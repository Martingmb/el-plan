<script>
  import { slide } from "svelte/transition";
  import { Checkbox } from "spaper";

  export let activities = [];
  const attending = (event) => activities.includes(event);
</script>

<div
  class="paper container-md border border-success border-dashed"
  transition:slide
>
  <fieldset class="form-group">
    <h3>Actividades</h3>
    <p>Escoge las actividades que te interesan:</p>
    <Checkbox
      label="Tennis 🎾"
      value="tennis"
      bind:group={activities}
      disabled={activities.length >= 2 && !attending("tennis")}
    />
    <Checkbox
      label="Indoor Kart 🏎️"
      value="karting"
      bind:group={activities}
      disabled={activities.length >= 3 && !attending("karting")}
    />
    <Checkbox
      label="Escape Room 🕵️‍♀️"
      value="escapeRooms"
      bind:group={activities}
      disabled={activities.length >= 2 && !attending("escapeRooms")}
    />
    <Checkbox
      label="Virtual Reality 🎮"
      value="vr"
      bind:group={activities}
      disabled={activities.length >= 3 && !attending("vr")}
    />
    <Checkbox
      label="Shopping 🛍️"
      value="shopping"
      bind:group={activities}
      disabled={activities.length >= 2 && !attending("shopping")}
    />
    <Checkbox
      label="Legos 🧱"
      value="lego"
      bind:group={activities}
      disabled={activities.length >= 2 && !attending("lego")}
    />
    <Checkbox
      label="Arcade 👾"
      value="arcade"
      bind:group={activities}
      disabled={activities.length >= 2 && !attending("arcade")}
    />
  </fieldset>
</div>
