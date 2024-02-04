<template>
  <Header />
  <div class="container">
    <Balance />
    <IncomeExpense />
    <TransactionList :transactions="transactions" />
    <AddTransaction />
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
import Balance from "./components/Balance.vue";
import IncomeExpense from "./components/IncomeExpense.vue";
import TransactionList from "./components/TransactionList.vue";
import AddTransaction from "./components/AddTransaction.vue";

import { ref } from "vue";

const transactions = ref([
  { id: 1, text: "flower", amount: -19.0 },
  { id: 2, text: "salary", amount: 299.97 },
  { id: 3, text: "book", amount: -10 },
  { id: 4, text: "camera", amount: 150 },
]);
</script>
