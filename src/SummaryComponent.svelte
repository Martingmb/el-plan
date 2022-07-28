<script>
  import { Card } from "spaper";
  import { onMount } from "svelte";
  export let data;

  onMount(() => {});

  const handleClick = async () => {
    await navigator.clipboard.writeText(data.address);
  };
</script>

<div class="col">
  <Card title={data.title} image={data.imageUrl}>
    {data.address}
    <p slot="bottom" />
  </Card>
</div>
