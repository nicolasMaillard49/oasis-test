<script setup lang="ts">
interface ToastProps {
  message?: string
  description?: string
  progress?: number
}

// Define default props pour avoir des valeur par default 
withDefaults(defineProps<ToastProps>(), {
  message: 'Message',
  description: 'Texte du message ici. La couleur pourrait changer en fonction de l\'importance du message. A voir si on contraint le nombre de caractère ou par nombre de ligne',
  progress: 100
})
</script>

<template>
 
  <div 
    class="relative bg-white border border-slate-200 border-b-0 rounded-lg shadow-[0px_10px_15px_-3px_rgba(0,0,0,0.1),0px_4px_6px_-2px_rgba(0,0,0,0.05)] p-4 w-full"
    data-name="Toast"
    data-node-id="13:6259"
  >
    <!-- Title + Description -->
    <div 
      class="flex flex-col gap-1 flex-1 min-w-0 min-h-0 text-sm leading-5"
      data-name="Title + Description"
      data-node-id="I13:6259;1933:142279"
    >
      <!-- Message Title -->
      <p 
        class="font-semibold text-lg text-slate-900 dark:text-slate-100 shrink-0"
        data-node-id="I13:6259;1933:142280"
      >
        {{ message }}
      </p>
      
      <!-- Description Text -->
      <p 
        class="font-normal  text-md text-slate-600 dark:text-slate-400 shrink-0 w-full whitespace-pre-wrap"
        data-node-id="I13:6259;1933:142281"
      >
        {{ description }}
      </p>
    </div>

    <!-- Progress Bar -->
    <div class="absolute bottom-0 left-[-1px] right-[-1px] flex items-center justify-center h-1">
      <div class="flex-none h-1 scale-y-[-100%]" :style="{ width: `${progress}%` }">
        <div 
          class="bg-blue-500 w-full h-full"
          data-name="Progress"
          data-node-id="I13:6259;1933:142282"
        />
      </div>
    </div>
  </div>
</template>
