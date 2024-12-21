<script>
  import Header from "../components/layout/Header.svelte";
  import Sidebar from "../components/layout/Sidebar.svelte";
  import Layout from "../components/layout/Layout.svelte";
  import "../app.css";
</script>

<div class="app-container">
  <Header />

  <div class="content-wrapper">
    <Sidebar />
    <Layout />
  </div>
</div>

<style>
  .app-container {
    display: flex;
    flex-direction: column;
    height: 100vh;
  }

  .content-wrapper {
    display: flex;
    flex: 1;
    overflow: hidden;
  }

  @media (max-width: 768px) {
    .content-wrapper {
      flex-direction: column;
    }
  }
</style>
