<script setup lang="ts">
import { faker } from '@faker-js/faker'

// Génération d'un texte de 50 mots
const description = faker.lorem.words(50)
</script>

<template>


<div class="w-full">

    <Toast 
        message="Message"
        description="Texte du message ici. La couleur pourrait changer en fonction de l'importance du message. A voir si on contraint le nombre de caractère ou par nombre de ligne"
        class="w-full p-[2.2rem]"
        size="lg">
       
    </Toast>


        <!-- on ajout flex dans le contaienr de card e lui indiquand une hauteur max ainsi qu'un espacement entre les cards -->
    <Container-Card class="self-stretch h-[530px] pt-[2.5rem] pb-[2.5rem]  flex justify-start items-start gap-4  ">
        <!--  -->
        <Card button-color="#4F39F6" title="card 1" :descriptionn= description />
        <Card button-color="#4F39F6" title="card 2" :descriptionn= description />



    </Container-Card>
</div>



</template>
