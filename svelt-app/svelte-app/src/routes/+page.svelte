<script>
  import Slider from "@bulatdashiev/svelte-slider";
  let range = [0, 200];
</script>

Thumb order: left: {range[0]}
right: {range[1]}
<Slider max="200" step="10" bind:value={range} range order />

<style>
  div {
    --thumb-bg: transparent;
    --progress-bg: #ff9355;
    --track-bg: #deffd7;
  }
</style>
