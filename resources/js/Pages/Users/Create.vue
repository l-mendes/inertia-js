<script setup>
import { Head, router } from '@inertiajs/vue3';
import { reactive } from 'vue';

const form = reactive({
  first_name: null,
  last_name: null,
  email: null
});

function submit() {
  router.post('/users', form);
}

</script>

<template>
  <div>

    <Head title="Create User" />

    <form @submit.prevent="submit">
      <label for="first_name">First name:</label>
      <input id="first_name" v-model="form.first_name" />
      <label for="last_name">Last name:</label>
      <input id="last_name" v-model="form.last_name" />
      <label for="email">Email:</label>
      <input id="email" v-model="form.email" />
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<style scoped></style>