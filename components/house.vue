<template>
  <v-layout justify-center align-content-center>
    <v-flex
      xs12
      sm10
      md8
    >
      <div class="d-flex flex-column align-center">
        <v-avatar size="300">
          <v-img :src="require(`~/static/${this.img}`)" :alt="imgAlt"></v-img>
        </v-avatar>
        <v-row class="mb-2">
          <span class="house">You Belong In House {{house}}</span>
        </v-row>
        <v-row>
          House colors: {{colors}}
        </v-row>
        <v-row>
          House motto: {{motto}}
        </v-row>
        <hr class="divider my-4">
        <v-row>
          <div class="bio" v-html="bio"></div>
        </v-row>
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {
    name: "house",
    props: [
      'house',
      'img',
      'imgAlt',
      'title',
      'colors',
      'motto',
      'bio'
    ],
  }
</script>

<style lang="stylus" scoped>
  .bio
    text-align center
  .house
    font-size 45px
    text-transform uppercase

  .divider
    width 25%
    color white

  @media screen and (max-width: 500px)
    .house
      font-size 25px
      padding-top 10px

    .divider
      width 50%
</style>
