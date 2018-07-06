<!-- eslint-disable -->
<template>
  <div class="hello">
    <Block ref="one"/>
    <button @click="clickHandler">{{rev ? "<":">"}}</button>
    <Block ref="two"/>
  </div>
</template>

<script>
  import Block from './Block';

  export default {
    name: 'HelloWorld',
    components: {
      Block
    },
    data () {
      return {
        rev:false
      }
    },
    methods: {
      clickHandler: function () {
        var oneTodos = this.$refs.one.todos;
        var twoTodos = this.$refs.two.todos;

        if (oneTodos.length == 0 || twoTodos.length == 0)
          this.rev = !this.rev;

        if (this.rev)
          oneTodos.push(twoTodos.pop());
        else
          twoTodos.push(oneTodos.pop());

        this.$refs.one.st =  "background-color:" + getRandomColorString();
        this.$refs.two.st =  "background-color:" + getRandomColorString();
      }
    }
  }

  var getRandomColorString = () => ("#" + Math.floor(Math.random() * 255 * 255 * 255).toString(16));

</script>

<style scoped>
</style>
