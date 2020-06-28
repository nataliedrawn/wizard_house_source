<template>
  <House
    img="kitsune.jpeg"
    img-alt="kitsune"
    house="kitsune"
    colors="red, brown, and yellow"
    motto="Knowledge speaks, wisdom listens"
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
        bio: `House Kitsune is a fun-loving, intelligent house. filled with those who are incredibly loyal and
faithful! You're also a little bit of a prankster, so you lie to keep things interesting. You are wise
beyond you years, so your friends often seek you out for advice or to help them make decisions.
        <br>
        <br>
        You believe that if you can dream it, you an do it - so you spend time crafting anything you desire.
Your also a bit of a transformer yourself, finding that you might act different around different groups of people.
Sometimes this is for self protection, and sometimes it's just to have a bit of fun. You have a deep connection
to nature and love spending time outdoors.`
      }
    }
  }
</script>
