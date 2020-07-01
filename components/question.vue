<template>
  <v-layout justify-center>
    <v-flex
      xs12
      sm10
      md8
    >
      <h2 class="mt-12">{{question.title}}</h2>
      <div class="d-flex flex-column justify-center">
        <v-chip
          v-for="(answer, index) in question.answers"
          class="my-2"
          :key="index"
          v-text="answer.name"
          @click="clicked(answer.value)"
          color="rgba(255,255,255,.5)"
          :large="largeChips"
        ></v-chip>
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
  import {includes, map, some} from 'lodash'
  export default {
    name: "question",
    props: [
      'question'
    ],
    methods: {
      clicked(val) {
        this.$emit('selected', val)
      }
    },
    computed: {
      largeChips() {
        return some(map(this.question.answers, 'name'), n => n.length > 45) && includes(['xs', 'sm'], this.$vuetify.breakpoint.name)
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .v-chip
    white-space normal !important
</style>
