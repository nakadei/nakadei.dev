<script setup lang="ts">
import { Avatar, AvatarFallback, AvatarImage } from '@/components/ui/avatar'
import { Badge } from '@/components/ui/badge'
import { Button } from '@/components/ui/button'
import { Github, Twitter } from 'lucide-vue-next'
import iconUrl from '@/assets/icon.png'
</script>

<template>
  <section class="min-h-[60vh] flex flex-col items-center justify-center space-y-8 py-20">
    <!-- Icon / Avatar -->
    <div class="relative group">
      <Avatar class="h-32 w-32 sm:h-40 sm:w-40 border-4 border-white shadow-xl">
        <AvatarImage :src="iconUrl" alt="@nakadeng" />
        <AvatarFallback>nakadei</AvatarFallback>
      </Avatar>
      <!-- Decorative ring or effect could go here -->
    </div>

    <!-- Typography -->
    <div class="text-center space-y-4">
      <h1 class="text-4xl sm:text-5xl font-extrabold tracking-tight lg:text-6xl text-foreground">
        nakadei.dev
      </h1>
      <div class="flex items-center justify-center gap-2 text-muted-foreground">
        <span class="text-lg sm:text-xl font-medium">Daisuke Nakata</span>
      </div>
      <div class="pt-2">
         <Badge variant="outline" class="text-sm px-4 py-1">
           Web Engineer / PC Gamer
         </Badge>
      </div>
    </div>

    <!-- Social Actions -->
    <div class="flex gap-4">
      <Button variant="outline" size="lg" as-child>
        <a href="https://github.com/nakadei" target="_blank" rel="noopener noreferrer">
          <Github class="mr-2 h-4 w-4" />
          GitHub
        </a>
      </Button>
      <Button variant="outline" size="lg" as-child>
        <a href="https://x.com/nakadeng" target="_blank" rel="noopener noreferrer">
          <Twitter class="mr-2 h-4 w-4" />
          Twitter
        </a>
      </Button>
    </div>
  </section>
</template>
