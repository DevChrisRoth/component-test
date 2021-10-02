<template>
  <div id="app">
    <rns-chimp title="Ordered" type="warning" />
    <rns-chimp title="test" type="error" />
    <rns-alert title="Daten wurden erfolgreich gespeichert!" type="success" />
    <rns-iButton  title="Icon button"  iconClass="bi bi-bookmark" type="simple"  style="margin: 20px 2px; "/>
    <rns-iButton  title="Icon button"  iconClass="bi bi-arrow-counterclockwise" type="secondary"  style="margin: 20px 0; "/>
    <rns-button title="Save data" @click="save()"  iconClass="bi bi-trash" type="secondary" />
    <rns-notification  :bootVisible="notiVisible" title="Daten erfolgreich gespeichert!" desc="Ihre persönlichen Daten wurden erfolgreich gespeichert." type="success"/>
    <rns-dropdown   title="Personal Menu" :dData="dData"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "./components/HelloWorld.vue";
@Component({
  components: {
    HelloWorld
  },
})
export default class App extends Vue {
  imgUrlLink!: string;
  imgUrl!: string;
  notiVisible =  "false";
  title = "Testtitle";
  navbarActions: any | any = [
    {
      link: "http://localhost:8080",
      icon: "bi bi-chevron-up",
      text: "Alternativtext",
    },
  ];
  dData = [
    {
      title: "Home",
      icon: "bi bi-bookmark"
    },
    {
      title: "Delete",
      icon: "bi bi-trash"
    },
    {
      title: "New Event",
      icon: "bi bi-new"
    }
  ]
  save(){
    console.log(this.notiVisible)
    this.notiVisible = "true";
  }
}
</script>

<style lang="scss">
@import "./assets/index.scss";
body {
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0;
  margin: 0;
}

</style>
