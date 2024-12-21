<script>
  // Import any required stores or dependencies
  import { deviceTypes } from "../../stores/deviceStore.js";
  import TemperatureGraph from "./Charts/Graphs/TemperatureGraph.svelte";
</script>

<main class="main-content">
  <TemperatureGraph />
</main>

<style>
  .main-content {
    flex: 1;
    padding: 2rem;
    background: #1f1f23;
    overflow-y: auto;
  }
</style>
