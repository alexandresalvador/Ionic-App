<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Veja quantos anos você tem!</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Login</ion-title>
        </ion-toolbar>
           </ion-header>
           
     <ion-item>
        <ion-label position="floating">Data :</ion-label>
        <ion-input type = "date" v-model="valorInput"></ion-input>
      </ion-item>
      <ion-button @click="validarIdade()"> Validar</ion-button>
      <ion-item>
        <ion-label> {{idade}}</ion-label>
      </ion-item>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButton, IonLabel, IonInput, IonItem } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Login',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonButton,
    IonLabel,
    IonInput,
    IonItem,
  },

 methods: {
    validarIdade() {
      const dataNasc = new Date(this.valorInput);
      const hoje = new Date();
      const idade = hoje.getFullYear() - dataNasc.getFullYear();
      this.idade = idade;
      console.log(`A sua idade é: ${idade}`);
    }
  },
  data() {
    return {
      valorInput: '',
      idade: 0,
    }
  },
});
 //function mudarTela(){
        // muda a tela pra home
      //  const texto = document.getElementsByTagName('h1')[0];
   // } 
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}

#card {
  background-color: rgb(223, 253, 89);
  width: 150px;
  height: 160px;
  
}
</style>