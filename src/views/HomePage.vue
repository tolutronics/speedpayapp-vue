<template>
  <ion-page>
    <ion-header class="ion-no-border">
      <ion-toolbar color="primary" class="ion-padding-start ion-padding-end">
        <ion-avatar slot="start" class="profile">
          <img src="@/assets/icons/male.png" />
        </ion-avatar>
        <ion-avatar slot="end" class="scan">
          <img src="@/assets/icons/scan.png" />
        </ion-avatar>
        <ion-avatar slot="end" class="notification">
          <img src="@/assets/icons/notification.gif" />
        </ion-avatar>
      </ion-toolbar>
    </ion-header>
    <ion-content color="primary" class="ion-padding">
      <ion-item class="balance" lines="none">
        <ion-avatar slot="start" class="refresh">
          <img src="@/assets/icons/refresh.png" />
        </ion-avatar>
        <ion-label>
          <div>
            <h6>Total balance</h6>
            <span><ion-icon :icon="eye"></ion-icon></span>
          </div>
          <h1><img src="@/assets/icons/naira.png" height="24" /> 2,00000</h1>
        </ion-label>
        <ion-button shape="round"> Top-up </ion-button>
      </ion-item>

      <ion-grid class="section">
        <ion-row>
          <ion-col size="12" class="sub-header"> Money Transfer</ion-col>
        </ion-row>
        <ion-row>
          <ion-col size="3" class="ion-text-center service-item">
            <ion-avatar>
              <img src="@/assets/icons/user.png" />
            </ion-avatar>
            <p>To SpeedPay</p>
          </ion-col>
          <ion-col size="3" class="ion-text-center service-item">
            <ion-avatar>
              <img src="@/assets/icons/bank.png" />
            </ion-avatar>
            <p>To Bank Account</p>
          </ion-col>
          <ion-col size="3" class="ion-text-center service-item">
            <ion-avatar>
              <img src="@/assets/icons/withdraw.png" />
            </ion-avatar>
            <p>Withdraw</p>
          </ion-col>
          <ion-col size="3" class="ion-text-center service-item">
            <ion-avatar>
              <img src="@/assets/icons/users.png" />
            </ion-avatar>
            <p>To Beneficiaries</p>
          </ion-col>
        </ion-row>
      </ion-grid>
      <ServicesComponent />
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { eye } from "ionicons/icons";
import ServicesComponent from "../components/servicesComponent.vue";
import commonIonicComponents from "@/shared/customIonicComponents";
export default defineComponent({
  name: "HomePage",
  components: {
    ...commonIonicComponents,
    ServicesComponent,
  },

  setup() {
    //notung
    return {
      eye,
    };
  },
});
</script>

<style scoped>
ion-avatar.notification {
  width: 30px;
  height: 30px;
  margin-left: 20px;
}
ion-avatar.refresh {
  width: 30px;
  height: 30px;
}
ion-avatar.scan {
  width: 30px;
  height: 30px;
}
ion-avatar.profile {
  width: 40px;
  height: 40px;
}
ion-item.balance {
  --background: var(--ion-color-secondary-contrast);
  box-shadow: 2px 2px 6px #e2e0e0;
  border-radius: 10px;
  --padding-bottom: 8px;
  --padding-top: 10px;
}
ion-item.balance > ion-label > div {
  display: flex;
}

ion-item.balance > ion-label > h1 {
  font-weight: 600;
  display: flex;
  /* height: 20px; */
  align-items: center;
}
ion-col.service-item {
  display: flex;
  flex-direction: column;
  align-items: center;
}
ion-col.service-item > p {
  font-size: 11px;
  font-weight: 600;
}
ion-col.service-item > ion-avatar {
  width: 30px;
  height: 30px;
}
ion-grid.section {
  background: #fff;
  border-radius: 10px;
}
</style>
