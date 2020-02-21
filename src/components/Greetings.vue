<template>
  <div class="child">
      <slot name="first"></slot>
      <slot name="third">Default Value</slot>
      <p>Child</p>
      <h1>{{ greeting }}</h1>
      <button @click="changeGreeting">change greeting</button>
      <slot name="second"></slot>
      <slot></slot>
  </div>
</template>

<script>

export default {
    props: ['greeting'],
    methods: {
        changeGreeting(){
            this.greeting = 'Changed From Child';
            this.$emit('newChange', this.greeting);
            this.$root.$emit('newtitle',this.greeting)
        }
    }
}

</script>

<style scoped>
    .child {
        width: 200px;
        height: 700px;
        background-color: rosybrown;
        border: 2px solid black;
    }
</style>
