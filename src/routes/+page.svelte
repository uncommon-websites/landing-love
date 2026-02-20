<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  import FilterBar from "$lib/components/FilterBar.svelte";
  import Card from "$lib/components/Card.svelte";
  import FeaturedCard from "$lib/components/FeaturedCard.svelte";
  import Pagination from "$lib/components/Pagination.svelte";
  import Footer from "$lib/components/Footer.svelte";

  // Mock Data
  const featuredCard = {
    title: "maikasui",
    description: "Natural beauty from sake treasures. Vegan Japanese cosmetics that care for your hands — free from parabens and silicones.",
    tags: ["Beauty", "eCommerce", "Minimal", "Lifestyle"],
    image: "https://images.unsplash.com/photo-1573164713714-d95e436ab8d6?q=80&w=2069&auto=format&fit=crop" // Woman in office
  };

  const topGridCards = [
    {
      title: "Webflow: Real-time collaboration",
      tags: ["No-Code", "Recommended", "Our Sponsor"],
      image: "https://placehold.co/600x400/3b82f6/ffffff?text=Enterprise\nguardrails+for\nspeed+and+scale",
      isSponsored: true
    },
    {
      title: "Framer: The website builder love...",
      tags: ["No-Code", "Recommended", "Our Sponsor"],
      image: "https://placehold.co/600x400/000000/ffffff?text=Imagine+it\npublish+it",
      isSponsored: true
    },
    {
      title: "Studio Arvin Leeuwis",
      tags: ["Portfolio", "Studio", "Minimal"],
      image: "https://placehold.co/600x400/333333/ffffff?text=Studio+Arvin+Leeuwis",
      isSponsored: false
    },
    {
      title: "Cathy Dolle",
      tags: ["Portfolio", "Minimal"],
      image: "https://placehold.co/600x400/e5e5e5/000000?text=Cathy+Dolle",
      isSponsored: false
    }
  ];

  const gridCards = [
    { title: "Richard Mille Art Prize", tags: ["3D Website", "Design", "Art", "Lifestyle", "Minimal"], image: "https://placehold.co/600x400/f3e8ff/000000?text=Richard+Mille" },
    { title: "laSlf", tags: ["Portfolio", "Minimal"], image: "https://placehold.co/600x400/f0f9ff/000000?text=laSlf" },
    { title: "Naked City Films", tags: ["Agency", "Studio", "Film", "Marketing"], image: "https://placehold.co/600x400/111827/ffffff?text=Naked+City" },
    { title: "Framer - Build better sites, faster", tags: ["No-Code", "Recommended", "Our Sponsor"], image: "https://placehold.co/600x400/000000/3b82f6?text=Framer", isSponsored: true },
    { title: "Side Stage Ventures", tags: ["Venture", "Business", "Finance"], image: "https://placehold.co/600x400/fdf2f8/db2777?text=SIDE+STAGE+VENTURES" },
    { title: "maikasui", tags: ["Beauty", "eCommerce", "Minimal", "Lifestyle"], image: "https://images.unsplash.com/photo-1573164713714-d95e436ab8d6?q=80&w=2069&auto=format&fit=crop" }, // Reuse image
    { title: "Webflow: Real-time collaboration", tags: ["No-Code", "Recommended", "Our Sponsor"], image: "https://placehold.co/600x400/3b82f6/ffffff?text=Webflow", isSponsored: true },
    { title: "Tea Teearu", tags: ["Portfolio", "Minimal"], image: "https://placehold.co/600x400/ccfbf1/0f766e?text=Tea+Teearu" },
    { title: "Balance Farm", tags: ["Business", "Minimal", "Technology", "Health"], image: "https://placehold.co/600x400/000000/ffffff?text=Balance+Farm" },
    { title: "Featured Partner", tags: [], isPartner: true, partnerLabel: "Sponsored Content" },
    { title: "Nicola Romei", tags: ["Portfolio", "Minimal"], image: "https://placehold.co/600x400/4b5563/ffffff?text=Nicola+Romei" },
    { title: "Cathy Dolle", tags: ["Portfolio", "Minimal"], image: "https://placehold.co/600x400/e5e5e5/000000?text=Cathy+Dolle" },
    { title: "Studio Arvin Leeuwis", tags: ["Portfolio", "Studio", "Minimal"], image: "https://placehold.co/600x400/333333/ffffff?text=Studio+Arvin" },
    { title: "Mojo Studio", tags: ["Studio", "Marketing"], image: "https://placehold.co/600x400/fef3c7/92400e?text=Mojo+Studio" },
    { title: "Ironhill", tags: ["Illustration", "Design"], image: "https://placehold.co/600x400/fef9c3/a16207?text=Ironhill" },
    { title: "Featured Partner", tags: [], isPartner: true, partnerLabel: "Sponsored Content" },
    { title: "Yomy", tags: ["eCommerce", "Hardware", "Technology", "Home Living"], image: "https://placehold.co/600x400/f3f4f6/1f2937?text=Yomy" },
    { title: "Featured Partner", tags: [], isPartner: true, partnerLabel: "Sponsored Content" },
    { title: "Wendy Andrade", tags: ["Portfolio", "Photography", "Art"], image: "https://placehold.co/600x400/f8fafc/64748b?text=Wendy+Andrade" },
    { title: "Victoria Gee", tags: ["Portfolio", "Photography", "Minimal"], image: "https://placehold.co/600x400/000000/ffffff?text=VICTORIA+GEE" }
  ];
</script>

<div class="min-h-screen bg-white font-body flex flex-col">
  <Header />

  <main class="flex-grow">
    <!-- Hero Section -->
    <div class="py-16 px-6 md:px-10 text-center max-w-5xl mx-auto">
      <h1 class="text-3xl md:text-5xl font-bold text-gray-900 mb-4 tracking-tight">
        Showcase of the best 1929 Animation Websites
      </h1>
      <p class="text-gray-500 text-lg md:text-xl">
        Get inspired by the best website examples with full-page video recordings.
      </p>
    </div>

    <!-- Filter Bar -->
    <div class="sticky top-[72px] z-40 bg-white/95 backdrop-blur-sm border-b border-gray-100 mb-8">
      <FilterBar />
    </div>

    <div class="px-6 md:px-10 pb-20 max-w-[1600px] mx-auto">
      
      <!-- Top Section: Featured + 4 Grid -->
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 mb-12">
        <!-- Left: Large Featured Card -->
        <div class="h-full">
          <FeaturedCard 
            title={featuredCard.title}
            description={featuredCard.description}
            tags={featuredCard.tags}
            image={featuredCard.image}
          />
        </div>

        <!-- Right: 2x2 Grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-x-8 gap-y-10">
          {#each topGridCards as card}
            <Card 
              title={card.title}
              tags={card.tags}
              image={card.image}
            />
          {/each}
        </div>
      </div>

      <!-- Main Grid -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-x-8 gap-y-12">
        {#each gridCards as card}
          <Card 
            title={card.title}
            tags={card.tags}
            image={card.image}
            isPartner={card.isPartner}
            partnerLabel={card.partnerLabel}
          />
        {/each}
      </div>

      <!-- Pagination -->
      <Pagination />
      
    </div>
  </main>

  <Footer />
</div>

