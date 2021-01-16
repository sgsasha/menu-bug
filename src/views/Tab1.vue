<template>
  <ion-page>
    <ion-button @click="openMenu()">Open menu</ion-button>
    <ion-menu side="start" menu-id="first" content-id="main">
      <ion-header>
        <ion-toolbar color="primary">
          <ion-title>Actions</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content id="main">
        <!--This click works-->
        <ion-button @click="doAction()">Do action</ion-button>
        <ion-list>
          <!--This click does not work-->
          <ion-item button @click="doAction()">
            <ion-label>Do action</ion-label>
          </ion-item>
        </ion-list>
      </ion-content>
    </ion-menu>
  </ion-page>
</template>

<script lang="ts">
  import {
    IonContent,
    IonPage,
    IonHeader,
    IonToolbar,
    IonTitle,
    IonMenu,
    IonList,
    IonItem,
    IonLabel,
    IonButton,
    menuController
  } from '@ionic/vue';
  import { defineComponent } from 'vue';

  export default defineComponent({
    name: 'Tab1',
    components: {
      IonContent,
      IonPage,
      IonHeader,
      IonToolbar,
      IonTitle,
      IonMenu,
      IonList,
      IonItem,
      IonLabel,
      IonButton
    },
    methods: {
      doAction () {
        console.log("called");
      },
      openMenu () {
        menuController.open('first');
      },
    }
  })
</script>