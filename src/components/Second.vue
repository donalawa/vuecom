<template>
  <div class="child">
      {{ title }}
  </div>
</template>

<script>

export default {
    data(){
        return {
            title: ''
        }
    },
    methods: {
        changeGreeting(){
            this.greeting = 'Changed From Child';
            this.$emit('newChange', this.greeting);
        }
    },
    created(){
        this.$root.$on('newtitle', val => {
            this.title = val;
        })
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
