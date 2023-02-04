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
      <div className="container">
        <img className="logo" src="/assets/logo.svg" />
        <h3>Welcome to Portals</h3>
        <p>
          This is a web application that has the Portals plugin preinstalled. If
          you would like to learn more about how to interact with this web
          application from the Native application you can find reference
          material below.
        </p>
        <ol className="info-list">
          <li>
            <p>Passing Data to a Portal with Initial Context</p>
            <a
              href="https://ionic.io/docs/portals/for-ios/how-to/using-the-portals-plugin#initial-context"
            >
              iOS
            </a>
            <a
              href="https://ionic.io/docs/portals/for-android/how-to/using-the-portals-plugin#initial-context"
            >
              Android
            </a>
          </li>
          <li>
            <p>Communicating with Pub/Sub</p>
            <a
              href="https://ionic.io/docs/portals/for-ios/how-to/using-the-portals-plugin#communicating-via-pubsub"
            >
              iOS
            </a>
            <a
              href="https://ionic.io/docs/portals/for-android/how-to/using-the-portals-plugin#communicating-via-pubsub"
            >
              Android
            </a>
          </li>
          <li>
            <p>Define your own API for communication</p>
            <a
              href="https://ionic.io/docs/portals/for-ios/how-to/define-api-in-typescript"
            >
              iOS
            </a>
            <a
              href="https://ionic.io/docs/portals/for-android/how-to/define-api-in-typescript"
            >
              Android
            </a>
          </li>
        </ol>
        <h3>Initial Context</h3>
        <p>
          This application was preseeded with an Initial Context. This data was
          initially provided by the Native application
        </p>
        <pre>{{ JSON.stringify(initialContext, null, 2) }}</pre>
      </div>
    </ion-content>
  </ion-page>
</template>

<style scoped>
.container {
  margin: 50px 25px;
  line-height: 1.5em;
}

img.logo {
  margin: 0 auto 38px;
  display: block;
  width: 33%;
}

.info-list {
  padding: 15px;
  list-style: none;
}

.info-list li {
  display: flex;
  flex-flow: row wrap;
  margin: 8px 0;
}

.info-list p {
  margin: 0;
  width: 100%;
}

.info-list a {
  display: block;
  margin: 8px;
}

pre {
  color: #ffffff;
  background-color: #383a3e;
  font-family: "Courier New", Courier, monospace;
  margin: 0;
  padding: 16px 8px;
}
</style>
