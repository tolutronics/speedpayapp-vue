<template>
  <ion-app>
    <ion-router-outlet />
  </ion-app>
</template>

<script lang="ts">
import { IonApp, IonRouterOutlet } from "@ionic/vue";
import { defineComponent, ref } from "vue";
import { CapacitorUpdater } from "@capgo/capacitor-updater";
import { App } from "@capacitor/app";
import { SplashScreen } from "@capacitor/splash-screen";

export default defineComponent({
  name: "App",
  components: {
    IonApp,
    IonRouterOutlet,
  },

  setup() {
    let version: any;
    App.addListener("appStateChange", async (state) => {
      if (state.isActive) {
        // Do the download during user active app time to prevent failed download
        version = await CapacitorUpdater.download({
          url: "https://github.com/Cap-go/demo-app/releases/download/0.0.4/dist.zip",
        });
        console.log("thi version===>", version);
      }
      if (!state.isActive && version !== "") {
        // Do the switch when user leave app
        SplashScreen.show();
        try {
          await CapacitorUpdater.set(version);
        } catch (err) {
          SplashScreen.hide(); // in case the set fail, otherwise the new app will have to hide it
        }
      }
    });
  },
});
</script>
