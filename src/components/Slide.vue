<template>
  <div class="slideContent">
    <div class="slideText">
      <h1 class="title">{{ title }}</h1>
      <span class="text">
        <hr>
        <p>{{ info }}</p>
      </span>
      <button class="moreInfo">Узнать больше</button>
    </div>
    <div class="slideTool">
      <img
          class="image"
          v-bind:src="image"
          :alt=toolName
          height="50%"
      />
        <h1 class="toolName">{{ toolName }}</h1>
    </div>
  </div>
</template>


<script>
export default {
  name: "slide",
  props: {
    id: {
      type: Int32Array,
      default: null
    },
    title: {
      type: String,
      default: null
    },
    info: {
      type: String,
      default: null
    },
    image: {
      type: String,
      default: null,
    },
    toolName: {
      type: String,
      default: null
    }
  }
}
</script>

<style scoped>

hr {
  color: #F37A1F;
  height: 0;
  width: 50px;
  margin-top: 20px;
  margin-right: 0;
}

.slideContent {
  display: flex;
  min-height: 100vh;
}

.title {
  box-sizing: border-box;
  margin: auto;
  width: 70%;
  font-size: 72px;
}

.text {
  display: flex;
  box-sizing: border-box;
  margin-left: 25%;
  font-size: 18px;
  width: 50%;
}

.slideText {
  align-self: center;
}

.slideTool {
  display: flex;
  background-color: #d28154;
  width: 45%;
  right: 0;
}

.image {
  align-self: center;
  transform: translateX(-47%);
  z-index: 110;
}

.toolName{
  position: absolute;
  color: #FFFFFF;
  bottom: 30%;
  font-size: 130px;
  transform: translateX(-45%) rotate(100grad);
  z-index: 109;
}

.moreInfo {
  color: #F5F5F5;
  background: #121212;
  padding: 10px 10px 10px 10px;
  transition: all 0.5s ease;
}

.moreInfo:hover{
  background-color: #F37A1F;
}
/*.moreInfo:before {*/
/*  content:'';*/
/*  position: absolute;*/
/*  margin-top: -10px;*/
/*  margin-left: -10px;*/
/*  color: #F5F5F5;*/
/*  width: 0;*/
/*  height: 38px;*/
/*  background: #f37a1f;*/
/*  text-align: center;*/
/*  transition: all 2s ease;*/
/*}*/


/*.moreInfo:hover:before {*/
/*  width: 6.25%;*/
/*}*/




</style>
