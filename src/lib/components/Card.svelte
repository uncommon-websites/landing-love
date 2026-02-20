<script lang="ts">
  export let image = '';
  export let title = '';
  export let tags: string[] = [];
  export let isPartner = false;
  export let partnerLogo = '';
  export let partnerLabel = 'Sponsored Content';
  export let isSponsored = false; // Added to prevent prop errors, though handled via tags/image
  
  // For specific styling of text/tags
  export let titleClass = 'font-bold text-gray-900 text-[15px] leading-tight group-hover:text-pink-600 transition-colors';
  export let tagClass = 'text-xs text-gray-500';
</script>

<div class="group flex flex-col h-full w-full cursor-pointer">
  {#if isPartner}
    <div class="relative overflow-hidden rounded-lg bg-gray-200 aspect-[1.5] mb-3 flex items-center justify-center border border-gray-100">
      {#if partnerLogo}
        <img src={partnerLogo} alt={title} class="w-1/3 h-auto object-contain opacity-60 mix-blend-multiply" />
      {:else}
        <div class="w-12 h-12 bg-gray-300 rounded-full opacity-50"></div>
      {/if}
    </div>
    <div class="flex flex-col gap-0.5">
      <h3 class="font-bold text-gray-900 text-[15px] leading-tight">{title || 'Featured Partner'}</h3>
      <span class="text-xs text-gray-400">{partnerLabel}</span>
    </div>
  {:else}
    <div class="relative overflow-hidden rounded-lg bg-gray-100 aspect-[1.5] mb-3 border border-gray-100">
      {#if image}
        <img 
          src={image} 
          alt={title} 
          class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105"
        />
      {/if}
      <!-- Play button overlay on hover could be added here -->
      <div class="absolute inset-0 bg-black/0 group-hover:bg-black/5 transition-colors duration-300"></div>
    </div>
    <div class="flex flex-col gap-1">
      <h3 class={titleClass}>{title}</h3>
      {#if tags.length > 0}
        <div class="flex flex-wrap gap-x-2 gap-y-1 {tagClass}">
          {#each tags as tag}
            <span>{tag}</span>
          {/each}
        </div>
      {/if}
    </div>
  {/if}
</div>
