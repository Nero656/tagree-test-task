<template>
  <div class="home">

    <Slider></Slider>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '../components/HelloWorld.vue'
import Slider from "../components/Slider";

export default {
  name: 'Home',

  components: {
    Slider,
    // HelloWorld
    // eslint-disable-next-line vue/no-unused-components
  }
}
</script>
