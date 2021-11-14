<template>
  <div class="flight d-flex flex-column flex-sm-row">
    <div class="d-flex align-stretch flex-column">
      <div class="my-auto ml-4">
        <span class="text-h6">{{ formatCompany() }}</span>
      </div>
      <div class="d-none d-sm-flex mt-auto ml-4 mb-4">
        <button class="info-btn mr-4">Детали перелета</button>
        <button class="info-btn mr-4">Условия тарифа</button>
        <span>невозвратный</span>
      </div>
    </div>
    <div class="ml-sm-auto side">
      <div class="d-flex flex-column px-10 py-5">
        <div class="mx-auto">
          <span class="text-h5 mx-auto" v-text="flight.price"></span>
          <span class="text-h6"> {{ formatCurrency() }}</span>
        </div>
        <v-btn color="primary" block> Выбрать </v-btn>
        <small class="mx-auto py-4">Цена за всех пассажиров</small>
        <div class="d-flex justify-space-around">
          <small class="align-self-center text--black">Нет багажа</small>
          <button class="baggage-btn ml-4">
            <small class="px-2">+ Добавить багаж</small>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Flight",
  props: ["flight", "airlines"],
  methods: {
    formatCompany() {
      return this.airlines[this.flight.validating_carrier];
    },
    formatCurrency() {
      switch (this.flight.currency) {
        case "KZT":
          return "₸";
        case "RUB":
          return "₽";
        default:
          return "";
      }
    },
  },
};
</script>

<style scoped>
.flight {
  background: #ffffff;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.15);
  border-radius: 4px;
  min-height: 20px;
}

.side {
  background: #f5f5f5;
  border-radius: 0px 4px 4px 0px;
}

.baggage-btn {
  text-align: center;
  color: #5763b3;
  background: #eaf0fa;
  border-radius: 2px;
}

.info-btn {
  color: #7284e4;
  text-decoration: underline 1px dashed #7284e4;
}
</style>
