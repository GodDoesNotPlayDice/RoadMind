
**`MessageBox.vue`**
```vue
<template>
<!-- Emite mediante la funcion sendMessage-->
  <input
    type="text"
    placeholder="Type your message..."
    class="flex-1 border rounded-full px-4 py-2 focus:outline-none"
    v-model="message"
    @keypress.enter="sendMessage" 
  />

  <button
    class="bg-blue-500 text-white rounded-full p-2 ml-2 hover:bg-blue-600 focus:outline-none"
    @click="sendMessage"
  ></button>
</template>

<script setup lang="ts">
  import { ref } from "vue";
<!-- Emite el valor asignado el nombre de la emision y el tipo que este posee-->
  const emits = defineEmits<{
    (e: "sendMessage", message: string): void;
  }>();

  const message = ref<string>("");

  const sendMessage = () => {
    if (message.value.trim() === "") return;
<!-- Asignas el nombre del emit definido previo y el valor real a emitir -->
    emits("sendMessage", message.value);

    message.value = ""; // Clear the input after sending
  };
</script>

```

**`view.vue`**
```vue
<template>
  <div class="bg-gray-100 h-screen flex flex-col max-w-lg mx-auto">
    <div class="bg-blue-500 p-4 text-white flex justify-between items-center">
      <span>Usuario</span>
    </div>

    <ChatMessages :messages="messages" />

    <MessageBox @send-message="onMessage" />   <!-- toma el valor emitido y lo pasa a la funcion onMessage de UseChat-->
  </div>
</template>

<script lang="ts" setup>
  import ChatMessages from "@/components/chat/ChatMessages.vue";

  import MessageBox from "@/components/chat/MessageBox.vue";

  import { useChat } from "@/composables/useChat";

  const { messages, onMessage } = useChat();
</script>

```

**`useChat`**
```ts
export const useChat = () => {
  const messages = ref<ChatMessage[]>([]);

  const getHerResponse = async () => {
    const resp = await fetch("https://yesno.wtf/api");

    const data = (await resp.json()) as YesNoResponse;

    return data;
  };

  const onMessage = async (text: string) => {
    if (text.trim() === "") return;

    messages.value.push({
      id: new Date().getTime(),

      message: text,

      isMine: true,
    });

    if (text.endsWith("?")) {
      await sleep(1);

      const { answer, image } = await getHerResponse();

      messages.value.push({
        id: new Date().getTime() + 1,

        message: answer,

        isMine: false,

        img: image,
      });

      return;
    }
  };

  return {
    messages,

    onMessage,
  };
};

```