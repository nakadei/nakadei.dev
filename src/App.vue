<script setup lang="ts">
import Hero from '@/components/Hero.vue'
import Timeline from '@/components/Timeline.vue'
import SpaceBackground from '@/components/SpaceBackground.vue'
import { Button } from '@/components/ui/button'
import { Separator } from '@/components/ui/separator'
import { ExternalLink } from 'lucide-vue-next'
</script>

<template>
  <SpaceBackground />
  <main class="min-h-screen bg-transparent font-sans text-foreground antialiased container max-w-screen-md mx-auto px-4 relative z-10">
    <Hero />
    <Timeline />
    
    <!-- Profile / Footer -->
    <section class="max-w-2xl mx-auto py-20 px-4 text-center">
      <Separator class="my-12" />
      <h3 class="text-2xl font-bold mb-6 tracking-tight">Want to know more?</h3>
      <Button size="lg" class="rounded-full px-8" as-child>
        <a href="https://nakadei.notion.site/Profile-e0b417f15271c020dc92bc69de1a7552" target="_blank" rel="noopener noreferrer">
          View Full Profile on Notion
          <ExternalLink class="ml-2 h-4 w-4" />
        </a>
      </Button>
      <p class="mt-16 text-muted-foreground text-sm">
        © 2025 nakadei.dev. All rights reserved.
      </p>
    </section>
  </main>
</template>

<style scoped>

</style>
