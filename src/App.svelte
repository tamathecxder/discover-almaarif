<script lang="ts">
  import Footer from "./lib/components/Footer.svelte";
  import Header from "./lib/components/Header.svelte";

  const heroOverlay = "./assets/hero-overlay.png";
</script>

<div class="relative min-h-[810px] bg-[url('{heroOverlay}')] bg-center bg-cover bg-no-repeat">
  <div class="mix-blend-multiply absolute inset-0 bg-overlay/90 z-10"></div> <!-- Overlay -->
  <Header />
</div>

<main class="flex-1 container py-8 px-20">
  <h1 class="font-hanken-grotesk">Testing</h1>
</main>

<Footer />
