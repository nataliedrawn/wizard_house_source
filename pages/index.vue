<template>
  <v-layout
    justify-center
  >
    <v-flex
      xsm12
      sm10
      md8
    >
      <div class="d-flex flex-column justify-center align-center content"></div>
      <v-card flat color="rgba(0,0,0,0.15)">
        <v-container>
          <div class="card-content">
            <div class="question">
              WHAT ARTISTIC ISLE WIZARD<br>
              HOUSE DO YOU BELONG IN?
            </div>
            <div class="houses">
              House Pegasus | House Dragon | House Kitsune | House Mermaid
            </div>
            <template v-if="['md', 'lg', 'xl'].includes($vuetify.breakpoint.name)">
              <v-btn color="blue" x-large nuxt to="/questions">Start</v-btn>
            </template>
            <template v-else>
              <v-btn color="blue" nuxt to="/questions">Start</v-btn>
            </template>
          </div>
        </v-container>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {}
</script>

<style scoped lang="stylus">
  .content
    height 100%
  .card-content
    display flex
    flex-direction column
    justify-content center
    align-items center
    text-align center

  .question
    font-size 50px
    line-height .9em

    &::before
      border-top 1px solid white
      content ''
      display block
      width 50%
      margin-left 25%
      margin-bottom .25em

  .houses
    font-size 20px
    padding-top 1em
    padding-bottom: 1em;

  @media screen and (max-width: 500px)
    .question
      font-size 20px

      &:before
        margin-left 15%
        width 70%

    .houses
      font-size 10px

</style>
