<template>
  <v-layout justify-center>
    <v-flex
      xs12
      sm10
      md8
    >
      <h2 class="mt-12">{{question.title}}</h2>
      <div class="d-flex flex-column justify-center">
        <v-btn
          rounded
          class="my-2"
          v-for="(answer, index) in question.answers"
          :key="index"
          v-text="answer.name"
          color="rgba(255,255,255,.5)"
          light
          @click="clicked(answer.value)"
        >
        </v-btn>
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {
    name: "question",
    props: [
      'question'
    ],
    methods: {
      clicked(val) {
        this.$emit('selected', val)
      }
    }
  }
</script>

<style lang="stylus" scoped>

</style>
