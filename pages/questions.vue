<template>
  <v-layout justify-center column>
    <v-flex xs12 sm10 md4>
      <Question :question="questions[location]" @selected="answered"></Question>
    </v-flex>
  </v-layout>
</template>

<script>
  import Question from "../components/question"
  import {includes, maxBy} from 'lodash'

  export default {
    name: "questions",
    components: {Question},
    data() {
      return {
        location: 0,
        mermaid: 0,
        dragon: 0,
        pegasus: 0,
        kitsune: 0,
        questions: [
          {
            title: "Where would you choose to live?",
            answers: [
              {name: "In a mansion in the sky", value: "pegasus"},
              {name: "In a remote castle", value: "dragon"},
              {name: "In the forrest, among nature", value: "kitsune"},
              {name: "By the sea", value: "mermaid"},
            ]
          },
          {
            title: "Do you enjoy telling people what to do?",
            answers: [
              {name: "Yes", value: "dragon"},
              {name: "No", value: "mermaid"},
              {name: "In a peaceful manner", value: "pegasus"},
              {name: "By tricking them into doing it", value: "kitsune"},
            ]
          },
          {
            title: "How will you celebrate your next birthday?",
            answers: [
              {name: "I'll have to think about that", value: "kitsune"},
              {name: "By inviting friends over", value: "mermaid"},
              {name: "Party lavishly with lots of people", value: "pegasus"},
              {name: "I don't really care much", value: "dragon"},
            ]
          },
          {
            title: "What trait would you say describes you best?",
            answers: [
              {name: "Gentle & good hearted", value: "pegasus"},
              {name: "Passionate", value: "mermaid"},
              {name: "Wise & intelligent", value: "kitsune"},
              {name: "fierce & courageous", value: "dragon"},
            ]
          },
          {
            title: "Someone needs your help! you:",
            answers: [
              {name: "immediately stop what you are doing to see how you can assist", value: "pegasus"},
              {name: "think about what would be the best option for everyone involved", value: "kitsune"},
              {name: "run straight into the danger to save them", value: "dragon"},
              {name: "are friendly at first, but end up luring them to a dark fate anyway", value: "mermaid"},
            ]
          },
          {
            title: "There are four bottles in front of you filled with some sort of liquid. You must drink one. Which do you choose?",
            answers: [
              {
                name: "a deep red bottle with a yellow ribbon around the top, filled with a dark liquid",
                value: "dragon"
              },
              {name: "a blue glass bottle, filled with a greenish liquid", value: "mermaid"},
              {name: "a ceramic bottle with black markings around the outside", value: "kitsune"},
              {name: "a white shiny bottle, glowing with silver sparkles", value: "pegasus"},
            ]
          },
          {
            title: "What is your favorite color?",
            answers: [
              {name: "blue", value: "mermaidpegasus"},
              {name: "green", value: "mermaid1"},
              {name: "yellow", value: "dragon1"},
              {name: "orange", value: "kitsune1"},
              {name: "red", value: "kitsunedragon"},
              {name: "purple", value: "mermaid2"},
              {name: "silver", value: "pegasus1"},
              {name: "gold", value: "dragon2"},
              {name: "black", value: "dragon3"},
              {name: "white", value: "pegasus2"},
              {name: "brown", value: "kitsune2"},
            ]
          },
        ]
      }
    },
    methods: {
      answered(value) {
        if (includes(value, 'kitsune')) {
          this.kitsune += 1
        }
        if (includes(value, 'dragon')) {
          this.dragon += 1
        }
        if (includes(value, 'pegasus')) {
          this.pegasus += 1
        }
        if (includes(value, 'mermaid')) {
          this.mermaid += 1
        }
        if (this.location === this.questions.length - 1) {
          let data = [
            ['kitsune', this.kitsune],
            ['dragon', this.dragon],
            ['mermaid', this.mermaid],
            ['pegasus', this.pegasus]
          ]
          return this.goto(maxBy(data, i => i[1])[0])
        }
        this.location += 1
      },
      goto(destination) {
        this.$router.push(`/${destination}`)
      }
    }
  }
</script>

<style lang="stylus" scoped>

</style>
