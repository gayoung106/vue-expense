<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <li
      v-for="t in transactions"
      :key="t.id"
      :class="t.amount < 0 ? 'minus' : 'plus'"
    >
      {{ t.text }} <span>${{ t.amount }}</span>
      <button class="delete-btn">X</button>
    </li>
    <!-- <li class="minus">
      Cash <span>-$400</span> <button class="delete-btn">X</button>
    </li>
    <li class="plus">
      PayCheck <span>$800</span> <button class="delete-btn">X</button>
    </li> -->
  </ul>
</template>

<script>
export default {
  setup() {
    const transactions = [
      { id: 1, text: "flower", amount: -19.0 },
      { id: 2, text: "salary", amount: 299.97 },
      { id: 3, text: "book", amount: -10 },
      { id: 4, text: "camera", amount: 150 },
    ];

    return {
      transactions,
    };
  },
};
</script>
