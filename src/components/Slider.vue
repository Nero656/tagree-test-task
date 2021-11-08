<template>
  <div class="slider">
    <div v-for="(item, id) in slides">
      <Slide v-if="page === item.id"
             :id=item.id
             :title=item.title
             :info=item.info
             :image=item.image
             :toolName="item.toolName"
      >
      </Slide>
    </div>

    <div class="page">
      <h2 class="pageActive">0{{page}}| <span class="pages">0{{slides.length}}</span> </h2>
    </div>

    <span class="slideBtn">
      <button @click="slideBack" class="leftButton">↼</button>
      <button @click="slideNext" class="rightButton">⇀</button>
    </span>
  </div>
</template>

<script>
import Slide from "./Slide"

export default {
  name: "Slider",

  components: {
    Slide
  },
  data: () => ({
    page: 1,
    slides: [],
  }),
  mounted() {
    this.slides.push({
          id: 1,
          title: "Возьми STIHL – почувствуй мощь!",
          info: "Единственное условие – регистрация продукта, которая займет меньше минуты и будет сделана" +
              "прямо в магазине в момент Вашей покупки!",
          image: "../images/promo-01.png",
          toolName: "Бензопилы"
        },
        {
          id: 2,
          title: "Возьми STIHL – почувствуй мощь!",
          info: "Промо-текст, почувствуй помощь",
          image: "../images/promo-02.png",
          toolName: "МОТОКОСЫ"
        }
    )
  },
  methods: {
    slideNext() {
      this.page++

      if (this.page > this.slides.length) {
        this.page = 1;
      }
    },
    slideBack() {
      this.page--

      if (this.page < 1) {
        this.page = this.slides.length;
      }
    }
  }
}
</script>

<style scoped>

.slider {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  min-height: 100%;
  z-index: 100;
}
.slideBtn{
  position: absolute;
  display: flex;
  bottom: 0;
  right: 0;
  z-index: 110;
  height: 5%;
  width: 20%;
  background-color:#F1EBE8;
}

.page{
  position: absolute;
  right: 5px;
  transform: rotate(100grad);
  bottom: 7.5%;
  color: #F1EBE8;
  z-index: 110;
}

.pageActive{
  color: #121212;
  font-size: 40px;
}

.pages{
  font-size: 30px;
  color: #F1EBE8;
}

button{
  transition: 0.5s;
  margin-left: 5px;
  height: 100%;
  width: 10%;
  outline: none;
  font-size: 30px;
  background-color: #F1EBE8;
}

.leftButton:hover{
  padding-right: 10px;
}
.rightButton:hover{
  padding-left: 10px;
}

</style>
