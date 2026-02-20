<script lang="ts">
  import { onMount } from 'svelte';

  let isDarkMode = false;

  function toggleTheme() {
    isDarkMode = !isDarkMode;
    // In a real app, this would toggle class on html/body
  }
</script>

<header class="w-full bg-white border-b border-gray-100 py-4 px-6 md:px-10 flex items-center justify-between sticky top-0 z-50">
  <div class="flex items-center gap-8">
    <a href="/" class="text-2xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-pink-500 to-purple-600 tracking-tight">
      landinglove
    </a>
    
    <nav class="hidden md:flex items-center gap-6 text-sm font-medium text-gray-600">
      <div class="group relative cursor-pointer flex items-center gap-1 hover:text-gray-900 transition-colors">
        Websites
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="m6 9 6 6 6-6"/></svg>
      </div>
      <div class="group relative cursor-pointer flex items-center gap-1 hover:text-gray-900 transition-colors">
        Webflow Templates
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="m6 9 6 6 6-6"/></svg>
      </div>
      <div class="group relative cursor-pointer flex items-center gap-1 hover:text-gray-900 transition-colors">
        Framer Templates
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="m6 9 6 6 6-6"/></svg>
      </div>
      <a href="/about" class="hover:text-gray-900 transition-colors">About</a>
    </nav>
  </div>

  <div class="flex items-center gap-4">
    <div class="relative hidden md:block">
      <input 
        type="text" 
        placeholder="Search" 
        class="pl-10 pr-4 py-2 bg-white border border-gray-200 rounded-full text-sm focus:outline-none focus:border-pink-500 w-64 transition-colors placeholder-gray-400"
      />
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="absolute left-3.5 top-1/2 -translate-y-1/2 text-gray-400 w-4 h-4"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.3-4.3"/></svg>
    </div>

    <div class="flex items-center bg-gray-100 rounded-full p-1 border border-gray-200">
      <button 
        class="p-1.5 rounded-full transition-colors { !isDarkMode ? 'bg-pink-500 text-white shadow-sm' : 'text-gray-400 hover:text-gray-600' }"
        on:click={() => isDarkMode = false}
        aria-label="Light mode"
      >
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="4"/><path d="M12 2v2"/><path d="M12 20v2"/><path d="m4.93 4.93 1.41 1.41"/><path d="m17.66 17.66 1.41 1.41"/><path d="M2 12h2"/><path d="M20 12h2"/><path d="m6.34 17.66-1.41 1.41"/><path d="m19.07 4.93-1.41 1.41"/></svg>
      </button>
      <button 
        class="p-1.5 rounded-full transition-colors { isDarkMode ? 'bg-pink-500 text-white shadow-sm' : 'text-gray-400 hover:text-gray-600' }"
        on:click={() => isDarkMode = true}
        aria-label="Dark mode"
      >
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 3a6 6 0 0 0 9 9 9 9 0 1 1-9-9Z"/></svg>
      </button>
    </div>
  </div>
</header>
