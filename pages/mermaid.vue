<template>
  <House
    img="mermaid.jpeg"
    img-alt="mermaid"
    house="mermaid"
    colors="blue, green, and aqua"
    motto="Let the sea set you free"
    :bio="bio"
  >
  </House>
</template>

<script>
  import House from "../components/house"

  export default {
    name: "mermaid",
    components: {House},
    data() {
      return {
        bio: `House Mermaid is a house filled with dualities. Mermaids are ocean spirits, gentle one moment
and destructive the next! House Mermaid is transformative, and full of passionate people. A bit on
the introverted side, House Mermaid is for those who are friendly, intuitive pleasure seekers.
        <br>
        <br>
        You are fluid and changeable, just like water. But also powerful and emotional. A bit mysterious, a
bit seductive, you are a person of transformation who craves freedom and never wants to be caged
in. You love spending tim ein the ocean, or any body of water, as well as relaxing on the beach.`
      }
    }
  }
</script>
