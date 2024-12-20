<script>
  import { deviceTypes } from "../../stores/deviceStore.js";
  import { Datepicker } from "flowbite-svelte";
  let startDate = null;
  let endDate = null;
</script>

<aside class="sidebar">
  <form class="config-form">
    <div class="date-range-container">
      <h2>Date Range</h2>
      <div class="form-group">
        <label>Start Date</label>
        <Datepicker bind:value={startDate} class="date-picker" />
      </div>
      <div class="form-group">
        <label>End Date</label>
        <Datepicker bind:value={endDate} class="date-picker" />
      </div>
    </div>

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
</aside>

<style>
  .sidebar {
    width: 300px;
    background: white;
    box-shadow: 2px 0 4px rgba(0, 0, 0, 0.1);
    overflow-y: auto;
    flex-shrink: 0;
  }

  .config-form {
    padding: 1.5rem;
  }

  .date-range-container {
    margin-bottom: 2rem;
    padding-bottom: 1.5rem;
    border-bottom: 2px solid #eee;
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

  /* Datepicker specific styles */
  :global(.date-picker) {
    width: 100%;
  }

  :global(.date-picker input) {
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

  :global(.date-picker input:focus) {
    outline: none;
    border-color: #3498db;
    box-shadow: 0 0 0 2px rgba(52, 152, 219, 0.2);
  }

  :global(.date-picker input:hover) {
    border-color: #3498db;
  }

  /* Calendar popup styles */
  :global(.datepicker-picker) {
    background: white;
    border: 1px solid #ddd;
    border-radius: 4px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    padding: 1rem;
    margin-top: 0.5rem;
  }

  :global(.datepicker-grid) {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 2px;
  }

  :global(.datepicker-cell) {
    padding: 0.5rem;
    text-align: center;
    cursor: pointer;
    border-radius: 4px;
  }

  :global(.datepicker-cell:hover) {
    background-color: #f0f4f8;
  }

  :global(.datepicker-cell.selected) {
    background-color: #3498db;
    color: white;
  }

  :global(.datepicker-header) {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
  }

  :global(.datepicker-controls button) {
    background: none;
    border: none;
    padding: 0.5rem;
    cursor: pointer;
    color: #2c3e50;
  }

  :global(.datepicker-controls button:hover) {
    background-color: #f0f4f8;
    border-radius: 4px;
  }

  @media (max-width: 768px) {
    .sidebar {
      width: 100%;
      max-height: 300px;
    }
  }
</style>
