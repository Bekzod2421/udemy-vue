<template>
  <div class="logo">{{ title }}</div>
  Lorem ipsum dolor, sit amet consectetur adipisicing elit. Excepturi
  necessitatibus distinctio voluptatum molestias placeat. Possimus, autem?
  Commodi, porro ratione, facilis magni optio dolore eligendi voluptate possimus
  temporibus eum corrupti? Consequuntur.
  <a href="#">vue</a>
  <mark ref="mark"> Marked text </mark>
  <button @click.right="color">OK</button>
  <br />
  <div class="text" v-if="show">
    <Model :bek="bek" @ochir="myShow">
      <ul class="menu">
        <li><a href="#">menu1</a></li>
        <li><a href="#">menu2</a></li>
        <li><a href="#">menu3</a></li>
        <li><a href="#">menu4</a></li>
      </ul>
      <template v-slot:logo>
        <img alt="Vue logo" src="./assets/logo.png" />
      </template>
    </Model>
  </div>
  <button @click="myShow">None</button>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <div @click.ctrl="prodShow">Product Show</div>
  <div @click="serShow">Service Show</div>
  <div class="myprod" v-if="pShow">
    <Prod @och="prodShow">
      <div class="item" v-for="prod in prod">
        <div class="title">Product {{ prod }}</div>
        <img src="./assets/logo.png" alt="" />
        <div class="price">1001</div>
      </div>
    </Prod>
  </div>
  <teleport to=".bek" v-if="sShow">
    <Prod @och="serShow">
      <div class="item" v-for="prod in prod">
        <div class="title">Service {{ prod }}</div>
        <img src="./assets/logo.png" alt="" />
        <div class="price">buy</div>
      </div>
    </Prod>
  </teleport>
</template>

<script>
import Model from "./components/Modal.vue";
import Prod from "./components/Prod.vue";
// import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    Model,
    Prod,
  },
  data() {
    return {
      title: "My Vue CLI",
      version: 1.0,
      bek: "salom",
      show: true,
      pShow: false,
      prod: 6,
      sShow: false,
    };
  },
  methods: {
    color() {
      console.log(this.$refs.mark);
      this.$refs.mark.classList.add("active");
    },
    myShow() {
      this.show = !this.show;
    },
    prodShow() {
      this.pShow = !this.pShow;
    },
    serShow() {
      this.sShow = !this.sShow;
    },
  },
};
</script>

<style>
.logo {
  color: red;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
