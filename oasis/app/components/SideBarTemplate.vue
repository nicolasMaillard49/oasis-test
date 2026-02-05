<script setup lang="ts">
import type { NavigationMenuItem } from '@nuxt/ui'
import type { TabsItem } from '@nuxt/ui'

const itemsNav: TabsItem[] = [
  {
    label: 'All',
    value: 'all'
  },
  {
    label: 'Unread',
    value: 'unread'
  }
]
const items: NavigationMenuItem[][] = [[{
  label: 'Menu',
  icon: 'lucide:book-open text-violet',
  active: true,
  // ici je change la couleur su texte du premier item grace a tailwind
  class: 'text-[#550E76] ',

}, {
  label: 'Menu',
  icon: 'lucide:book-open',
  badge: '4'
}, {
  label: 'Menu',
  icon: 'lucide:book-open',
}, {
  label: 'Menu',
  icon: 'lucide:book-open',
  defaultOpen: true,
  children: [{
    label: 'Sous-menu',
    icon: 'lucide:book-open',
  }, {
    label: 'Sous-menu',
    icon: 'lucide:book-open',
  }, {
    label: 'Sous-menu',
    icon: 'lucide:book-open',
  },
  {
    label: 'Sous-menu',
    icon: 'lucide:book-open',
  }]
}], [{
  label: 'Lien externe',
  icon: 'lucide:book-open',
  target: '_blank'
},
{
  label: 'Lien externe',
  icon: 'lucide:book-open',
  target: '_blank'
}]]
</script>

<template>

    <!-- ici on definit une size pour la sidebar il semble etre prise en compte seulement avec l'attribut resizable -->
  <UDashboardSidebar class="w-72" >
    <template #header="{ collapsed }">
    <AppLogo />
    </template>

    <template #default="{ collapsed }">
      <UNavigationMenu :collapsed="collapsed" :items="items[0]" orientation="vertical" 
      :ui="{
        //  marge de 0.5rem autour de CHAQUE élément 
        // ajout d'une bordure left couleur a default pour les child items 
        // ajout d'une marge left de 0.7rem pour le child list pour centrer la liste au millieu de l'icon 
        item: 'm-2  cursor-pointer',
        childList: ' ml-[0.7rem] border-l border-hidden ',
        childItem: 'm-2  border-l border-default cursor-pointer',
      }" />


    </template>
    <!-- ici en metyteant le #footer on edfinit le footer du menu sidebar -->
    <template #footer="{ collapsed }">
      <UNavigationMenu :collapsed="collapsed" :items="items[1]" orientation="vertical" />
    </template>
  </UDashboardSidebar>

 

    

</template>
