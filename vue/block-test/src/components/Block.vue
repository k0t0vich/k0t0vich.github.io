<template>
  <div class="block">
    <ol>
      <li v-for="todo in todos" :style="st">
        {{ todo.text }}
      </li>
    </ol>
  </div>
</template>

<script>
    export default {
      name: "Block",
      data() {
          return {
            todos: [
              { text: '*' },
              { text: '*' },
              { text: '*' },
              { text: '*' },
              { text: '*' },
              { text: '*' },
              { text: '*' }
            ],
           st: "background-color:#7f7f7f"
          }
      },
      props: ['msg']
    }
</script>

<style scoped>
  li {
    border: #000066;
  }
</style>
