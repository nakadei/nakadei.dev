<script setup lang="ts">
// Pure CSS Space Background
</script>

<template>
  <div class="fixed inset-0 z-[-1] overflow-hidden pointer-events-none bg-background">
    <!-- Deep Space Gradient Base -->
    <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_bottom,_var(--tw-gradient-stops))] from-primary/20 via-background to-background"></div>
    
    <!-- Stars Layers -->
    <div class="stars-sm"></div>
    <div class="stars-md"></div>
    <div class="stars-lg"></div>
  </div>
</template>

<style scoped>
/* 
  Star generation using box-shadow.
  These coordinates create a static star field.
  The animation moves them upward to simulate travel/flow.
*/

.stars-sm {
  width: 1px;
  height: 1px;
  background: transparent;
  box-shadow: 
    10vw 10vh #FFF, 20vw 50vh #FFF, 30vw 30vh #FFF, 50vw 80vh #FFF, 
    70vw 20vh #FFF, 80vw 60vh #FFF, 90vw 10vh #FFF, 15vw 90vh #FFF,
    45vw 45vh #FFF, 65vw 15vh #FFF, 85vw 85vh #FFF, 5vw 35vh #FFF,
    25vw 75vh #FFF, 35vw 55vh #FFF, 55vw 25vh #FFF, 75vw 65vh #FFF,
    95vw 5vh #FFF, 12vw 68vh #FFF, 42vw 12vh #FFF, 62vw 92vh #FFF,
    30vw 10vh #FFF, 60vw 40vh #FFF, 90vw 70vh #FFF, 20vw 20vh #FFF,
    50vw 50vh #FFF, 80vw 80vh #FFF, 10vw 90vh #FFF, 40vw 10vh #FFF,
    70vw 40vh #FFF, 95vw 95vh #FFF, 25vw 5vh #FFF, 55vw 35vh #FFF;
  animation: animStar 600s linear infinite;
  opacity: 0.5;
}

.stars-md {
  width: 2px;
  height: 2px;
  background: transparent;
  box-shadow: 
    15vw 15vh #e0d4fc, 35vw 35vh #e0d4fc, 55vw 55vh #e0d4fc, 75vw 75vh #e0d4fc,
    25vw 85vh #e0d4fc, 65vw 25vh #e0d4fc, 85vw 45vh #e0d4fc, 45vw 65vh #e0d4fc,
    10vw 50vh #e0d4fc, 90vw 20vh #e0d4fc, 30vw 90vh #e0d4fc, 70vw 10vh #e0d4fc;
  animation: animStar 900s linear infinite, twinkle 10s ease-in-out infinite alternate;
  opacity: 0.8;
}

.stars-lg {
  width: 3px;
  height: 3px;
  background: transparent;
  box-shadow: 
    10vw 30vh #ffccaa, 80vw 10vh #aaeeff, 40vw 80vh #ffccaa, 
    60vw 40vh #aaeeff, 20vw 90vh #ffccaa, 90vw 60vh #aaeeff;
  border-radius: 50%;
  animation: animStar 1200s linear infinite, twinkle 15s ease-in-out infinite alternate;
  filter: blur(1px);
}

@keyframes animStar {
  from { transform: translateY(0px); }
  to { transform: translateY(-100vh); }
}

@keyframes twinkle {
  0% { opacity: 0.3; transform: scale(0.8); }
  100% { opacity: 1; transform: scale(1.2); }
}
</style>
