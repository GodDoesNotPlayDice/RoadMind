El ciclo de vida de Vue funciona cuando se hace `on` en algo. Por ejemplo, si se hace `onMounted` en un componente, se ejecutará cuando el componente se monte. 

## Lifecycle Hooks
Lista de hooks de  que se pueden usar en Vue:

**`onMounted()`**: Se ejecuta cuando el componente se monta.
**`onUpdate()`**: Se ejecuta cuando el componente se actualiza.
**`onUnmounted()`**: Se ejecuta cuando el componente se desmonta.
**`onBeforeMount()`**: Se ejecuta antes de montar el componente.
**`onBeforeUpdate()`**: Se ejecuta antes de actualizar el componente.
**`onBeforeUnmount()`**: Se ejecuta antes de desmontar el componente.
**`onErrorCaptured()`**: Se ejecuta cuando hay un error en el componente.
**`onRenderTracked()`**: Se ejecuta cuando se rastrea el renderizado.
**`onRenderTriggered()`**: Se ejecuta cuando se activa el renderizado.
**`onActivated()`**: Se ejecuta cuando el componente se activa.
**`onDeactivated()`**: Se ejecuta cuando el componente se desactiva.
**`onServerPrefetch()`**: Se ejecuta cuando se hace prefetch en el servidor.


## Router + KeepAlive
Para mantener un componente vivo en el router, se puede usar `keep-alive` en el router-view, de esta forma se mantendrá el estado del componente pero esto requiere el constante uso de la memoria.

```vue
<router-view v-slot="{ Component }">
	<keep-alive>
		<Component :is="Component" />
	</keep-alive>
</router-view>
```