<script>
  const paths = Object.keys(
    import.meta.glob("/static/Birds/*.jpg", { query: { enhanced: true } }),
  ).map((p) => `${p.substring(7)}?url`);
</script>

<header class="min-h-screen bg-white">
  <nav class="flex items-center py-8 px-14 justify-between">
    <div class="flex items-center">
      <h1 class="text-2xl font-bold text-gray-700">Beacon Backyard Birding</h1>
      <div class="ml-10"></div>
    </div>
  </nav>
  <!-- End Navigation Bar -->

  <!-- Section Hero -->
  <!-- Box left -->
  <div class="bg-[#7CA9D8]">
    <div class="size-1/3 pt-44 pl-8 pb-10">
      <enhanced:img src="/static/IMG_0911.jpg" alt="eagle" />
    </div>
  </div>
  <div
    class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 py-8 px-14"
  >
    {#each paths as img}
      {#if img !== undefined}
        <img src={img} />
        <!-- <enhanced:img src={img} class="rounded-md" alt={img} /> -->
      {:else}
        <p>undefined</p>
      {/if}
    {/each}
  </div>
</header>
