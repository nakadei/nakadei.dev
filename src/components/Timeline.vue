<script setup lang="ts">
import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from '@/components/ui/card'
import { Badge } from '@/components/ui/badge'
import { Button } from '@/components/ui/button'
import { Briefcase, GraduationCap, Star, ChevronDown, ChevronUp } from 'lucide-vue-next'
import { ref } from 'vue'

const expandedItems = ref<Set<number>>(new Set())

const toggleExpand = (index: number) => {
  const newSet = new Set(expandedItems.value)
  if (newSet.has(index)) {
    newSet.delete(index)
  } else {
    newSet.add(index)
  }
  expandedItems.value = newSet
}

const events = [
  {
    year: '2022/12 ~ Present',
    title: 'Web Frontend / Infra Engineer',
    company: 'Fanfare Inc.',
    description: '',
    details: `・Frontend development with Vue 3 / TypeScript
・Infrastructure management using AWS / Terraform
・Leading the migration from legacy systems to modern architecture`,
    icon: Briefcase,
    type: 'work'
  },
  {
    year: '2022/07 ~ 2022/09',
    title: 'Web Frontend Engineer',
    company: 'Freelance',
    description: '',
    details: `・Supported development of a SaaS product using React / Next.js
・Implemented complex UI components and data visualizations`,
    icon: Briefcase,
    type: 'work'
  },
  {
    year: '2019/10 ~ 2022/03',
    title: 'Infra / Web Frontend Engineer',
    company: 'Japan Digital Design Inc.',
    description: '',
    details: `・Designed and built cloud infrastructure on GCP
・Developed internal tools and dashboards using Vue.js
・Collaborated with design teams to implement pixel-perfect UIs`,
    icon: Briefcase,
    type: 'work'
  },
  {
    year: '2018/09 ~ 2019/09',
    title: 'Infra / Corporate Engineer',
    company: 'Japan Digital Design Inc.',
    description: '',
    details: `・Corporate IT support and network administration
・Managed security policies and compliance audits`,
    icon: Briefcase,
    type: 'work'
  },
  {
    year: '2016/04 ~ 2017/12',
    title: 'Infra Engineer',
    company: 'Asia Quest Inc.',
    description: '',
    details: `・Server maintenance and monitoring (Linux/Windows)
・Network troubleshooting and performance tuning`,
    icon: Briefcase,
    type: 'work'
  },
  {
    year: '2013/04 ~ 2016/03',
    title: 'Student',
    company: 'Funabashi-Infomation-Business College of Technology',
    description: '',
    details: `・Majored in Information Technology
・Learned basics of programming (Java, C) and Database management`,
    icon: GraduationCap,
    type: 'education'
  }
]
</script>

<template>
  <section class="max-w-2xl mx-auto py-20 px-4">
    <h2 class="text-3xl font-bold mb-12 text-center tracking-tight">Career History</h2>
    
    <div class="relative border-l-2 border-border ml-3 md:ml-6 space-y-12 pb-12">
      <div v-for="(event, index) in events" :key="index" class="relative pl-8 md:pl-12">
        <!-- Timeline Dot -->
        <span 
          class="absolute -left-[10.5px] top-1/2 -translate-y-1/2 h-5 w-5 rounded-full border-4 border-background bg-primary flex items-center justify-center z-10"
        >
        </span>
        
        <!-- Content Card -->
        <div class="relative group">
            <Card class="transition-all duration-300 hover:shadow-lg border-muted hover:border-primary/20">
            <CardHeader>
                <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-2 mb-2">
                <Badge variant="secondary" class="w-fit">{{ event.year }}</Badge>
                <span class="text-xs text-muted-foreground tracking-wider font-semibold">{{ event.company }}</span>
                </div>
                <CardTitle class="text-xl flex items-center gap-2">
                <component :is="event.icon" class="h-5 w-5 text-primary" />
                {{ event.title }}
                </CardTitle>
            </CardHeader>
            <CardContent v-if="event.details && expandedItems.has(index)">
                <div class="pt-4 border-t border-border mt-4 text-sm text-muted-foreground whitespace-pre-line leading-relaxed">
                  {{ event.details }}
                </div>
            </CardContent>
            
            <!-- Expand Indicator -->
            <!-- Expand Indicator -->
            <div class="flex justify-end px-6 pb-6 pt-2">
               <button 
                 @click.stop="toggleExpand(index)"
                 class="flex items-center gap-1 bg-secondary/50 px-3 py-1.5 rounded-full text-xs font-medium text-muted-foreground hover:bg-secondary hover:text-foreground transition-colors shadow-sm cursor-pointer"
               >
                 <span v-if="!expandedItems.has(index)">Details</span>
                 <span v-else>Close</span>
                 <component :is="expandedItems.has(index) ? ChevronUp : ChevronDown" class="h-3 w-3" />
               </button>
            </div>
            </Card>
        </div>
      </div>
    </div>
  </section>
</template>
