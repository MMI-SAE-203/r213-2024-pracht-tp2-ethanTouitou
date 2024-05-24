<script setup lang="ts">
import { pb } from '@/backend';
import MaisonCard from '@/components/MaisonCard.vue'
const maisonsListe = await pb.collection('maison').getFullList({
  filter: 'favori=true',
});
console.log(maisonsListe);

//
</script>

<template>
  <h1 class="text-2xl">Bonjour monde !</h1>
  <!--  <MaisonCard v-bind="maisonsListe[0]" />
  <MaisonCard v-bind="maisonsListe[1]" /> -->

  <MaisonCard v-for="uneMaison in maisonsListe" :key="uneMaison.id" v-bind="uneMaison" />
</template>
