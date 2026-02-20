<script lang="ts">
  export let currentPage = 1;
  export let totalPages = 129;

  // Simplified logic for display
  const pages = [1, 2, 3, '...', 127, 128, 129];
</script>

<div class="flex items-center justify-center gap-2 py-12">
  <button class="w-10 h-10 rounded-full border border-gray-200 flex items-center justify-center text-gray-400 hover:border-gray-300 hover:text-gray-600 transition-colors disabled:opacity-50" disabled>
    <span class="sr-only">First</span>
    «
  </button>
  <button class="w-10 h-10 rounded-full border border-gray-200 flex items-center justify-center text-gray-400 hover:border-gray-300 hover:text-gray-600 transition-colors disabled:opacity-50" disabled>
    <span class="sr-only">Previous</span>
    ‹
  </button>

  {#each pages as page}
    {#if page === '...'}
      <span class="w-10 h-10 flex items-center justify-center text-gray-400">...</span>
    {:else}
      <button 
        class="w-10 h-10 rounded-full border flex items-center justify-center text-sm font-medium transition-colors
        {currentPage === page 
          ? 'bg-pink-500 text-white border-pink-500 shadow-sm' 
          : 'bg-white text-gray-500 border-gray-200 hover:border-pink-200 hover:text-pink-500'}"
      >
        {page}
      </button>
    {/if}
  {/each}

  <button class="w-10 h-10 rounded-full border border-gray-200 flex items-center justify-center text-pink-500 hover:border-pink-200 hover:bg-pink-50 transition-colors">
    <span class="sr-only">Next</span>
    ›
  </button>
  <button class="w-10 h-10 rounded-full border border-gray-200 flex items-center justify-center text-pink-500 hover:border-pink-200 hover:bg-pink-50 transition-colors">
    <span class="sr-only">Last</span>
    »
  </button>
</div>
