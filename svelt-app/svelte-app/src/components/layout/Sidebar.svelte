<script>
  import DeviceSelection from "./Sidebar/DeviceSelection.svelte";
</script>

<aside class="sidebar">
  <DeviceSelection />
</aside>

<style>
  .sidebar {
    width: 300px;
    background: white;
    box-shadow: 2px 0 4px rgba(0, 0, 0, 0.1);
    overflow-y: auto;
    flex-shrink: 0;
  }
</style>
