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

  // Define devices in a single data structure
  const deviceTypes = $state({
    temp: {
      label: "Temperature Device",
      devices: ["Temp1", "Temp2", "Temp3", "All Devices"],
      selected: null,
    },
    turb: {
      label: "Turbidity Device",
      devices: ["Turb1", "Turb2", "Turb3", "All Devices"],
      selected: null,
    },
    detect: {
      label: "Water Detection Devices",
      devices: ["Detect1", "Detect2", "Detect3", "All Devices"],
      selected: null,
    },
  });
</script>

<div class="app-container">
  <header class="app-header">
    <h1>MeterThings</h1>
  </header>

  <div class="content-wrapper">
    <aside class="sidebar">
      <form class="config-form">
        <h2>Chart Configurations</h2>
        {#each Object.entries(deviceTypes) as [type, config]}
          <div class="form-group">
            <label for={type}>{config.label}</label>
            <select id={type} bind:value={config.selected}>
              {#each config.devices as name}
                <option value={name}>{name}</option>
              {/each}
            </select>
          </div>
        {/each}
      </form>
    </aside>

    <main class="main-content">
      <!-- Your charts/content will go here -->
    </main>
  </div>
</div>

<style>
  .app-container {
    display: flex;
    flex-direction: column;
    height: 100vh;
  }

  .app-header {
    background: linear-gradient(to right, #2c3e50, #3498db);
    padding: 1rem 2rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }

  .app-header h1 {
    color: white;
    margin: 0;
    font-size: 1.8rem;
  }

  .content-wrapper {
    display: flex;
    flex: 1;
    overflow: hidden;
  }

  .sidebar {
    width: 300px;
    background: white;
    box-shadow: 2px 0 4px rgba(0, 0, 0, 0.1);
    overflow-y: auto;
    flex-shrink: 0;
  }

  .main-content {
    flex: 1;
    padding: 2rem;
    background: #f5f7fa;
    overflow-y: auto;
  }

  .config-form {
    padding: 1.5rem;
  }

  .config-form h2 {
    color: #2c3e50;
    font-size: 1.25rem;
    margin: 0 0 1.5rem 0;
    padding-bottom: 0.5rem;
    border-bottom: 2px solid #eee;
  }

  .form-group {
    margin-bottom: 1.5rem;
  }

  label {
    display: block;
    margin-bottom: 0.5rem;
    color: #2c3e50;
    font-weight: 500;
    font-size: 0.9rem;
  }

  select {
    width: 100%;
    padding: 0.5rem;
    border: 1px solid #ddd;
    border-radius: 4px;
    background-color: white;
    font-size: 0.9rem;
    color: #2c3e50;
    transition:
      border-color 0.2s,
      box-shadow 0.2s;
  }

  select:focus {
    outline: none;
    border-color: #3498db;
    box-shadow: 0 0 0 2px rgba(52, 152, 219, 0.2);
  }

  select:hover {
    border-color: #3498db;
  }

  @media (max-width: 768px) {
    .content-wrapper {
      flex-direction: column;
    }

    .sidebar {
      width: 100%;
      max-height: 300px;
    }

    .app-header {
      padding: 0.8rem 1rem;
    }

    .app-header h1 {
      font-size: 1.5rem;
    }
  }
</style>
