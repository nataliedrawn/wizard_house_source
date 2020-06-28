<template>
  <House
    img="pegasus.jpeg"
    img-alt="pegasus"
    house="pegasus"
    colors="white, silver, and blue"
    motto="Believe in your Dreams"
    :bio="bio"
  >
  </House>
</template>

<script>
  import House from "../components/house"

  export default {
    name: "pegasus",
    components: {House},
    data() {
      return {
        bio: `House Pegasus is filled with people who are good hearted and gentle.
        Named for a beautiful and kind flying house of the sky, House Pegasus is for the helpers.
        You may be a little naive, but you are always there for the people who mean the mose
        tho you, as well as the people you meet along the way! After all, a stranger is just a
        friend you haven't met yet!
        <br>
        <br>
        You are also innately talented, possess a sense of freedom, and are an excellent communicator
        you have a high flying imagination, and you are balanced, stable, and in harmony with the world
        around you.`
      }
    }
  }
</script>

<style lang="stylus" scoped>

</style>
