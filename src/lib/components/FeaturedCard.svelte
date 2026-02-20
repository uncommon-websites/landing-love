<script lang="ts">
  export let image = '';
  export let title = '';
  export let description = '';
  export let tags: string[] = [];
</script>

<div class="group flex flex-col h-full w-full cursor-pointer">
  <div class="relative overflow-hidden rounded-lg bg-gray-100 aspect-[16/10] mb-4 border border-gray-100">
    <img 
      src={image} 
      alt={title} 
      class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105"
    />
    <div class="absolute inset-0 bg-black/0 group-hover:bg-black/5 transition-colors duration-300"></div>
    
    <!-- Play button overlay -->
    <div class="absolute bottom-4 right-4 bg-black rounded-full p-3 shadow-lg group-hover:scale-110 transition-transform duration-300">
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="white" stroke="none" class="w-4 h-4"><polygon points="5 3 19 12 5 21 5 3"/></svg>
    </div>
  </div>
  
  <div class="flex flex-col gap-2">
    <h3 class="font-bold text-gray-900 text-xl leading-tight group-hover:text-pink-600 transition-colors">{title}</h3>
    <p class="text-gray-500 text-base leading-relaxed line-clamp-2">{description}</p>
    
    {#if tags.length > 0}
      <div class="flex flex-wrap gap-x-3 gap-y-1 text-xs text-gray-400 mt-1">
        {#each tags as tag}
          <span>{tag}</span>
        {/each}
      </div>
    {/if}
  </div>
</div>
