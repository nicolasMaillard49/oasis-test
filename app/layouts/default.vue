<script setup lang="ts">
import SideBarTemplate from '~/components/SideBarTemplate.vue'
import NavBarTemplate from '~/components/NavBarTemplate.vue'
import type { container } from '#build/ui';
</script>

<template>
  <UApp>
    <!-- dans le div principal on definit une structure en flex avec une sidebar et une partie principale contenant la navbar et le contenu de la page pour la page entiere on supprime la scrollbar  -->
    <div class="flex h-screen overflow-hidden">
      <SideBarTemplate />

      <div class="flex-1 flex flex-col overflow-hidden">
        <NavBarTemplate />

        <!-- ici on laisse la possibilité de scroller dans le contenu de la page dans le slot vient s'ajouter tout le contenu de notre page en dehors des menus  -->
        <containerBody class=" p-[5rem] flex-1 overflow-auto ">
          <slot />
        </containerBody>
        <containerFooter class="pb-[2.5rem] ">   
               <Footer title="test de title"  icon-size="sm"/>
          </containerFooter>
      </div>
    </div>
  </UApp>
</template>
