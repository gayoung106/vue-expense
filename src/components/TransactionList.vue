<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <li
      v-for="t in transactions"
      :key="t.id"
      :class="t.amount < 0 ? 'minus' : 'plus'"
    >
      {{ t.text }} <span>${{ t.amount }}</span>
      <button @click="deleteTransaction(t.id)" class="delete-btn">X</button>
    </li>
    <!-- <li class="minus">
      Cash <span>-$400</span> <button class="delete-btn">X</button>
    </li>
    <li class="plus">
      PayCheck <span>$800</span> <button class="delete-btn">X</button>
    </li> -->
  </ul>
</template>

<script setup>
import { defineProps } from "vue";

const emit = defineEmits(["transactionDeleted"]);

const props = defineProps({
  transactions: {
    type: Array,
    required: true,
  },
});

const deleteTransaction = (id) => {
  emit("transactionDeleted", id);
};
</script>
