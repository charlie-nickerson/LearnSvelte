<script>
  import { deviceTypes } from "../../../stores/deviceStore.js";
</script>

<form class="config-form">
  <div class="configurations-section">
    <h2>Chart Configurations</h2>
    {#each Object.entries($deviceTypes) as [type, config]}
      <div class="form-group">
        <label for={type}>{config.label}</label>
        <select id={type} bind:value={config.selected}>
          {#each config.devices as name}
            <option value={name}>{name}</option>
          {/each}
        </select>
      </div>
    {/each}
  </div>
</form>

<style>
  .config-form {
    padding: 1.5rem;
  }

  .configurations-section {
    margin-top: 1rem;
  }

  h2 {
    color: #2c3e50;
    font-size: 1.25rem;
    margin: 0 0 1.5rem 0;
    padding-bottom: 0.5rem;
    border-bottom: 2px solid #eee;
  }

  .form-group {
    margin-bottom: 1.5rem;
  }

  .form-group:last-child {
    margin-bottom: 0;
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
</style>
