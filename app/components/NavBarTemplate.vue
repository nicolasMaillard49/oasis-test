
<script setup lang="ts">
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
</script>
<template>
       <UDashboardNavbar title="Inbox" class="">

    <template #leading>
      <UDashboardSidebarCollapse />
    </template>

    <template #trailing>
      <UBadge label="4" variant="subtle" />
    </template>

    <template #right>
  <UAvatar src="https://github.com/benjamincanac.png" size="3xs"/>        
  <span class="text-xs font-medium text-gray-900 dark:text-white">John Doe</span>
  <span class="text-xs">Software Engineer</span>

  <UButton color="neutral" variant="outline">Changert de profil</UButton>


</template>

    </UDashboardNavbar>
</template>