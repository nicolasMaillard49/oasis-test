<script setup lang="ts">
interface CardProps {
    title?: string
    descriptionn?: string
    buttonText?: string
    buttonIcon?: string
    buttonColor?: string
}

withDefaults(defineProps<CardProps>(), {
    title: 'XXX',
    descriptionn: 'Somentoksi jyyän sirvangin torjuse sil varmitusta helpporo.Somentoksi jyyän sirvangin torjuse sil varmitusta helpporo.',
    buttonText: 'Button',
    buttonIcon: 'lucide:rocket',
    buttonColor: 'warning'


})

const iconUrl = 'https://www.figma.com/api/mcp/asset/3f22afd9-f50b-4ca4-bb9a-8373f0922146'
</script>

<template>
    <!-- ajout d'un padding de 9 sur toute la cards suppression de la ligne dividide y ajout d'un bg et de contour  -->
    <UCard
        class="p-9 divide-y-0 w-full bg-secondary-50 rounded-lg outline outline-1 outline-offset-[-1px] outline-secondary-700">
        <template #header class="border-">
            <p class="text-secondary-700 text-3xl font-bold ">
                {{ title }}
            </p>
        </template>

        <template #default>
            <p class="text-[#90A1B9]">
                {{ descriptionn }}
            </p>
        </template>

        <template #footer>
            <!-- j'ajoute un div pour aligner le bouton a droite grace a flex et juustify end  -->
            <div class="flex justify-end">
                <!-- ici je donne la possibilité en bindant style de changer la couleur du bouton avec la props button-color et je rajoute un effet hover pour l'opacité -->
                <UButton :icon="buttonIcon" :style="{ backgroundColor: buttonColor }" target="_blank" class="hover:opacity-70" href="#">{{ buttonText }}</UButton>

            </div>
        </template>
    </UCard>
</template>
