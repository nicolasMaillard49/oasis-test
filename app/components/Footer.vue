<script setup lang="ts">

    //ici je defini les props avec des valeurs par defaut pour le footer
const props = withDefaults(defineProps<{
  title?: string
  icons?: string[]
  iconSize?: 'sm' | 'md' | 'lg' | 'xl' | '2xl'
  iconColor?: string
}>(), 
//les valeur par defaut
{
  title: 'Test de typo avec les pictos',
  icons: () => [
    'simple-icons:discord',
    'simple-icons:github',
    'simple-icons:x',
    'simple-icons:instagram',
    'simple-icons:linkedin',
    'simple-icons:facebook'
  ],
  iconSize: 'md',
  iconColor: 'slate-600'
})

//je defint les differentes tailles d'icons

//le computed me permet de crer une valeur reactive en fonction de la props iconSize envoyé dans le composant parent
const iconSizeClass = computed(() => ({
  sm: 'w-8 h-8',
  md: 'w-12 h-12',
  lg: 'w-16 h-16',
  xl: 'w-[66.667px] h-[66.667px]',
  '2xl': 'w-24 h-24'
}[props.iconSize]))
</script>

<template>
  <div class="flex flex-col items-center gap-10 w-full bg-none ">
    <p class="text-center text-lg font-semibold text-slate-600 ">
      {{ title }}
    </p>

    <div class="flex flex-wrap items-center justify-center gap-8 lg:gap-16 w-full">
        <!-- je boucle sur la liste d'icons passée en props ce qui me permet d'ajouter autant d'icons que je veux dans le footer et de les afficher avec la bonne taille... -->
      <a
        v-for="icon in icons"
        :key="icon"
        href="#"
        class="hover:opacity-70"
        :class="iconSizeClass"
      >  
      <!-- je donne la possibilité de bindé l'icon color en fonction de la props iconColor -->
        <UIcon
          :name="icon"
          :class="[`text-${iconColor}`, 'w-full h-full']"
        />
      </a>
    </div>
  </div>
</template>
