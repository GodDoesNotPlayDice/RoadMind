
```vue
<template>
  <div>
    <p>Counter: {{ counter }}</p>

    <p>Square: {{ squareCounter }}</p>
  </div>

  <button @click="counter++">Increment</button>

  <button @click="counter--">Decrement</button>
</template>

<script setup lang="ts">
  import { useCounter } from "@/composables/useCounter";

  const { counter, squareCounter } = useCounter(80);
</script>

```


```ts
import { computed, ref } from "vue";

export const useCounter = (iniValue: number) => {
  const counter = ref(iniValue ?? 10);

  const squareCounter = computed(() => counter.value * counter.value);

  const increment = () => {
    counter.value++;
  };

  const decrement = () => {
    counter.value--;
  };

  return {
    counter,
    squareCounter,
    increment,
    decrement,
  };
};

export type UseCounterReturn = ReturnType<typeof useCounter>;
```



