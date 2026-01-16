<script>
  import "../app.css";
  import Navbar from "$lib/components/Navbar.svelte";

  let { children } = $props();
</script>

<svelte:head></svelte:head>
<Navbar></Navbar>
{@render children()}
