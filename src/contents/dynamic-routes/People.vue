<script setup>
import { people } from '~/data/tng.json'
</script>

<template>
  <div class="page page-people">
    <div class="list-choose">
      <h2>characters</h2>
      <ul>
        <li v-for="person in people" :key="person.id">
          <router-link :to="{ name: 'person', params: { id: person.id } }">
            {{ person.name }}
          </router-link>
        </li>
      </ul>
    </div>

    <div class="person-view">
      <router-view></router-view>
    </div>
  </div>
</template>

<style scoped>
.page-people {
  padding-left: 0;
  padding-top: 0;
  padding-bottom: 0;
  padding-right: 0;
}
.list-choose {
  /* background-color: #303030; */
  background-color: var(--color-violet-3);
  padding-left: 2rem;
  padding-right: 2rem;
  padding-top: 20px;
  padding-bottom: 10px;
}
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

ul li {
  margin: 0;
  margin-bottom: 0.1rem;
  position: relative;
}

ul li a {
  display: block;
  background-color: transparent;
  padding: 0.1rem 1.5rem;
  margin-left: -1.5rem;
  margin-right: -1rem;
  color: #fff;
}

ul li a.router-link-active {
  text-decoration: underline;
  font-style: italic;
}

ul li a:hover,
ul li a:focus {
  /* background-color: var(--color-teal-4); */
  /* color: #eee; */
  background-color: var(--color-indigo-2);
  color: var(--color-indigo-6);
  text-decoration: none;
}

.person-view {
  padding-bottom: 60px;
  padding-top: 20px;
}

.list-choose h2 {
  margin: 0;
  padding-left: 0;
  margin-bottom: 0.1rem;
}

@media (min-width: 850px) {
  .page-people {
    display: grid;
    grid-template-columns: auto 1fr;
  }
  .list-choose {
    padding-top: 50px;
    padding-bottom: 50px;
    grid-row: 1;
    grid-column: 1;
  }
  .person-view {
    grid-row: 1;
    grid-column: 2;
  }
  ul li a {
    padding: 0.2rem 1.5rem;
  }
}
</style>
