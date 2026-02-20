<script lang="ts">
  export let activeFilter = 'All';

  const filters = [
    { name: 'All', count: 1929 },
    { name: '3D Websites', count: 512 },
    { name: 'SaaS', count: 74 },
    { name: 'AI', count: 34 },
    { name: 'Portfolio', count: 511 },
    { name: 'Dark Mode', count: 573 },
    { name: 'E-commerce', count: 182 },
    { name: 'Agency', count: 335 },
    { name: 'Food & drink', count: 60 },
    { name: 'P', count: null }, // Cut off in screenshot? Or maybe "Product"? I'll just put P as per screenshot
    { name: 'See More', count: null }
  ];
</script>

<div class="w-full overflow-x-auto py-4 px-6 md:px-10 flex gap-3 items-center no-scrollbar">
  {#each filters as filter}
    <button 
      class="whitespace-nowrap px-4 py-2 rounded-full border text-sm font-medium transition-colors flex items-center gap-2
      {activeFilter === filter.name 
        ? 'bg-gray-900 text-white border-gray-900' 
        : 'bg-white text-gray-700 border-gray-200 hover:border-gray-300 hover:bg-gray-50'}"
      on:click={() => activeFilter = filter.name}
    >
      {filter.name}
      {#if filter.count !== null}
        <span class="text-xs opacity-60 ml-0.5">{filter.count}</span>
      {/if}
    </button>
  {/each}
</div>

<style>
  .no-scrollbar::-webkit-scrollbar {
    display: none;
  }
  .no-scrollbar {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }
</style>
