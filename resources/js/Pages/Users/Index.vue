<script setup>
import { Head, router } from '@inertiajs/vue3';

defineProps({
  users: {
    type: Array,
    default: () => []
  }
})

function destroy(id) {
  router.delete(`/users/${id}`);
}

</script>

<template>
  <div>

    <Head title="Users" />
    <h1>Users</h1>

    <ul>
      <li v-for="user in users">
        {{ user.name }}

        <button @click="destroy(user.id)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<style scoped></style>