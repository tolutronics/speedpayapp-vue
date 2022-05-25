<template>
  <ion-grid class="section">
    <ion-row>
      <ion-col size="12" class="sub-header"> Services</ion-col>
    </ion-row>
    <ion-row>
      <ion-col size="3" class="ion-text-center service-item">
        <ion-avatar>
          <img src="@/assets/icons/loan.png" />
        </ion-avatar>
        <p>Loan</p>
      </ion-col>
      <ion-col size="3" class="ion-text-center service-item">
        <ion-avatar>
          <img src="@/assets/icons/bank.png" />
        </ion-avatar>
        <p>Data Bundle</p>
      </ion-col>
      <ion-col size="3" class="ion-text-center service-item">
        <ion-avatar>
          <img src="@/assets/icons/withdraw.png" />
        </ion-avatar>
        <p>Airtime</p>
      </ion-col>
      <ion-col size="3" class="ion-text-center service-item">
        <ion-avatar>
          <img src="@/assets/icons/users.png" />
        </ion-avatar>
        <p>Electricity</p>
      </ion-col>
    </ion-row>
    <ion-row>
      <ion-col size="3" class="ion-text-center service-item">
        <ion-avatar>
          <img src="@/assets/icons/user.png" />
        </ion-avatar>
        <p>Insurance</p>
      </ion-col>
      <ion-col size="3" class="ion-text-center service-item">
        <ion-avatar>
          <img src="@/assets/icons/bank.png" />
        </ion-avatar>
        <p>Betting</p>
      </ion-col>
      <ion-col size="3" class="ion-text-center service-item">
        <ion-avatar>
          <img src="@/assets/icons/withdraw.png" />
        </ion-avatar>
        <p>Travel & Hotel</p>
      </ion-col>
      <ion-col size="3" class="ion-text-center service-item">
        <ion-avatar>
          <img src="@/assets/icons/users.png" />
        </ion-avatar>
        <p>School Payment</p>
      </ion-col>
    </ion-row>
  </ion-grid>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { eye } from "ionicons/icons";
import commonIonicComponents from "@/shared/customIonicComponents";
export default defineComponent({
  name: "servicesComponent",
  components: {
    ...commonIonicComponents,
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
