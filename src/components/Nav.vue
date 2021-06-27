<template>
  <nav class="d-flex">
    <!-- HOME SETTING LOGOUT -->
    <ul>
      <li>
        <router-link :to="{ name: 'Home' }"> Home </router-link>
      </li>
      <li>
        <router-link :to="{ name: 'Settings' }"> Setings </router-link>
      </li>
      <li>LOGOUT</li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Nav",
};
</script>
