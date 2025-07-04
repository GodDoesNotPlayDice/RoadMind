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
  import { computed, ref } from "vue";

  const counter = ref(0);

  const squareCounter = computed(() => counter.value * counter.value);
</script>

```


# Componente + v-bind

```vue
<template>
  <h1>My Counter App</h1>

  <MyCounter :value="10" />
</template>

<script setup lang="ts">
  import MyCounter from "./components/MyCounter.vue";
</script>

```


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
  import { computed, ref } from "vue";

  interface MyCounterProps {
    value: number;
  }

  const props = defineProps<MyCounterProps>();

  const counter = ref(props.value ?? 20);

  const squareCounter = computed(() => counter.value * counter.value);
</script>

```


# Componente pre SFC

```vue
<template>
  <div>
    <p>Counter: {{ counter }}</p>

    <p>Square: {{ squareCounter }}</p>
  </div>

  <button @click="counter++">Increment</button>

  <button @click="counter--">Decrement</button>
</template>

<script lang="ts">
  import { computed, defineComponent, ref } from "vue";

  export default defineComponent({
    props: {
      value: {
        type: Number,

        default: 20,

        required: true,
      },
    },

    setup(props) {
      const counter = ref(props.value);

      const squareCounter = computed(() => counter.value * counter.value);

      return {
        counter,

        squareCounter,
      };
    },
  });
</script>
```



# SFC 

```vue
<template>
  <div>
    <p>Counter: {{ counter }}</p>

    <p>Square: {{ squareCounter }}</p>
  </div>

  <button @click="counter++">Increment</button>

  <button @click="counter--">Decrement</button>
</template>

<script src="./MyCounterTs.ts" lang="ts"></script>

```

```ts
import { computed, defineComponent, ref } from "vue";

export default defineComponent({
  props: {
    value: {
      type: Number,

      default: 20,

      required: true,
    },
  },

  setup(props) {
    const counter = ref(props.value);

    const squareCounter = computed(() => counter.value * counter.value);

    return {
      counter,

      squareCounter,
    };
  },
});

```