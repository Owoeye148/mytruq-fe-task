<template>
  <ion-page>
    <Header />
    <ion-content :fullscreen="true">
      <div id="container">
        <div class="hero">
          <h2>Festivals and Shows</h2>
          <h1>Live Concerts</h1>
          <button>BUY TICKET</button>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonPage } from '@ionic/vue';
import Header from '../Components/Header.vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Home',
  components: {
    IonContent,
    IonPage,
    Header
  }
});
</script>

<style scoped>

/* .toolbar-container {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
} */



ion-content {
  background-color: black;
}

#container {
  /* text-align: center; */
  display: flex;
  justify-content: flex-end;
  background-image: url("https://images03.nicepage.com/c461c07a441a5d220e8feb1a/c8445170c45c5bebb617b93b/zxmin.jpg");
  background-repeat: no-repeat;
  background-size: 100%;
  height: 100vh;
  position: absolute;
  left: 0;
  right: 0;
  top: 8%;
}

.hero {
  margin-top: 15%;
  margin-right: 20%;
}

.hero h2 {
  color: rgb(248, 248, 248);
  font-weight: 600;
}

.hero h1 {
  color: rgb(183, 183, 11);
}

.hero button {
  background: rgba(169,3,41,1);
  background: -moz-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
  background: -webkit-gradient(left top, right top, color-stop(0%, rgba(169,3,41,1)), color-stop(44%, rgba(143,2,34,1)), color-stop(100%, rgba(109,0,25,1)));
  background: -webkit-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
  background: -o-linear-gradient(left, rgba(169,3,41,1) 0%, rgba(143,2,34,1) 44%, rgba(109,0,25,1) 100%);
  color:#ffffff;
  padding: 1em 2em;
  border-radius: 50px;
}
</style>