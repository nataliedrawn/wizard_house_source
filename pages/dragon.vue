<template>
  <House
    img="dragon.jpeg"
    img-alt="dragon"
    house="dragon"
    colors="red, gold, and black"
    motto="Have fun, work hard"
    :bio="bio"
  >
  </House>
</template>

<script>
  import House from "../components/house"

  export default {
    name: "dragon",
    components: {House},
    data() {
      return {
        bio: `House Dragon is for those who are strong and courageous! Dragons are often mysterious and
guarded. Thought to be incredibly fierce. Although House Dragon is full of power, peace, and prosperity,
you might find yourself a little hot tempered when things don't go your way.
        <br>
        <br>
        You are often very successful and have a great sense of fearlessness. Mentally and physically, you
are very strong and strong willed. You protect those who you consider your family and friends with everything
you've got`
      }
    }
  }
</script>
