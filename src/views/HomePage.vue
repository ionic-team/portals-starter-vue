<script lang="ts">
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar,
} from "@ionic/vue";
import { getInitialContext } from "@ionic/portals";

const initialContext = {
  showHeader: false,
  ...getInitialContext<any>(),
};

export default {
  data() {
    return {
      initialContext,
    };
  },
};
</script>

<template>
  <ion-page>
    <ion-header :translucent="true" v-if="initialContext.showHeader">
      <ion-toolbar>
        <ion-title>Blank</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense" v-if="initialContext.showHeader">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>

      <div id="container">
        <pre>{{ JSON.stringify(initialContext, null, 2) }}</pre>
      </div>
    </ion-content>
  </ion-page>
</template>

<style scoped></style>
