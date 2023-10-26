<script setup>
import { ref } from 'vue'

const nomor = ref(1);
const buku = ref({judul: ''});

const lihatData = async (e) => {
  
  const resp = await $fetch('http://localhost:8080/api/buku/1');
  console.log( resp );
  buku.value.judul = resp.judul;

}
</script>

<template>
  <section>
    <p>Cari Buku Berdasarkan Indeks ({{ nomor }}).</p>
    <input type="text" name="" id="" v-model="nomor" placeholder="Input ID">
    <input type="button" value="Cari" @click="lihatData">
    <NuxtLink to="/">
      Home page
    </NuxtLink>
    <hr>
    <div>
      <p>Judul: {{ buku.judul }} </p>
    </div>
  </section>
</template>
  