<script>
  import Slider from "@bulatdashiev/svelte-slider";
  import { page } from "$app/state";
  import {
    ChartPieSolid,
    GridSolid,
    MailBoxSolid,
    UserSolid,
    ArrowRightToBracketOutline,
    EditOutline,
  } from "flowbite-svelte-icons";

  let temp_devices = $state([
    { name: "Temp1" },
    { name: "Temp2" },
    { name: "Temp3" },
    { name: "All Devices" },
  ]);

  let turb_devices = $state([
    { name: "Turb1" },
    { name: "Turb2" },
    { name: "Turb3" },
    { name: "All Devices" },
  ]);

  let detect_devices = $state([
    { name: "Detect1" },
    { name: "Detect2" },
    { name: "Detect3" },
    { name: "All Devices" },
  ]);

  let temp_selected = $state();
  let turb_selected = $state();
  let detect_selected = $state();
</script>

<header><h1>MeterThings</h1></header>
<div class="layout">
  <form>
    <h1>Chart Configurations</h1>
    <p>Select Temperature Device</p>
    <select bind:value={temp_selected}>
      {#each temp_devices as temp_device}
        <option value={temp_device}>
          {temp_device.name}
        </option>
      {/each}
    </select>
    <p>Select Turbidity Device</p>
    <select bind:value={turb_selected}>
      {#each turb_devices as turb_device}
        <option value={turb_device}>
          {turb_device.name}
        </option>
      {/each}
    </select>
    <p>Select Water Detection Devices</p>
    <select bind:value={detect_selected}>
      {#each detect_devices as detect_device}
        <option value={detect_device}>
          {detect_device.name}
        </option>
      {/each}
    </select>
  </form>
</div>

<style>
  div {
    --thumb-bg: transparent;
    --progress-bg: #ff9355;
    --track-bg: #deffd7;
    background-color: burlywood;
  }

  .layout {
    display: flex;
    min-height: 100vh;
  }
</style>
