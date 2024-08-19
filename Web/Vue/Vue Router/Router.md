
# Package Manager

Si tiene un proyecto existente que utiliza un administrador de paquetes JavaScript
```bash
npm install vue-router@4
```

Si no puede instalarlo desde la creación del proyecto
```bash
npm create vue@latest
```

# Estructura

```scaffolding
src/
├── router/
	├── index.ts
```

**router**: se crea la carpeta router para agregar un `index.ts` que nos servirá como barril para agregar las rutas de navegación.

## Index.ts
Dentro del `index` tenemos que llamar al `createRouter` y `createWebHistory` de `vue-router`.

`createRouter`: se compone por `history` y `routes`, donde `history` es el tipo de historial que se va a utilizar y `routes` es un arreglo de rutas.

`createWebHistory`: es una función que crea un historial de navegación basado en la API de historial de navegación HTML5.

```typescript
import { createRouter, createWebHistory } from 'vue-router';
import HomePage from '@/modules/landing/pages/HomePage.vue'
  

const router = createRouter({
history: createWebHistory(import.meta.env.BASE_URL),
routes: [
		{
			path: '/',
			name: 'home',
			component: HomePage
		},
		{
			path: '/features',
			name: 'features',
			component: () => import('@/modules/landing/pages/FeaturesPages.vue')
		},
		{
			path: '/pricing',
			name: 'pricing',
			component: () => import('@/modules/landing/pages/PricingPage.vue')
		},
		{
			path: '/contact',
			name: 'contact',
			component: () => import('@/modules/landing/pages/ContactPage.vue')
		}
	]
})


export default router

```

## Diferencias entre `createWebHistory` y `createWebHashHistory`
`
`createWebHistory`: es una función que crea un historial de navegación basado en la API de historial de navegación HTML5.

`createWebHashHistory`: es una función que crea un historial de navegación basado en la API de historial de navegación HTML5, pero con un hash en la URL, el uso principal se debe a cuando no puedes cambiar la configuración del servidor.


## App.vue
En el `app.vue` nosotros solo tenemos que usar `router-view` y `router-link` para poder navegar entre las rutas.

```vue
<template>
	<router-link to="/">Home</router-link>
	<router-link to="/features">Features</router-link>
	<router-link to="/pricing">Pricing</router-link>
	<router-link to="/contact">Contact</router-link>
	<div>
		<router-view />
	</div>
</template>
  ```


`router-link`: este componente tiene `to` al cual se le puede pasar varios parametros, como lo son, `name`, `path`, `params` y `query`.


## Rutas padres y rutas hijas
Las rutas padres e hijas son útiles cuando se necesita tener una estructura de rutas anidadas.

```scaffolding
src/
├── modules/
	├── auth/
	  ├── layouts/
      ├── AuthLayout.vue
    ├── pages/
      ├── LoginPage.vue
      ├── RegisterPage.vue
	├── landing/
	  ├── layouts/
      ├── LandingLayout.vue
    ├── pages/
      ├── HomePage.vue
      ├── FeaturesPages.vue
      ├── PricingPage.vue
      ├── ContactPage.vue

```


```typescript
import HomePage from '@/modules/landing/pages/HomePage.vue'
import { createRouter, createWebHistory } from 'vue-router'

const router = createRouter({
	history: createWebHistory(import.meta.env.BASE_URL),
	routes: [
		{
			path: '/',
			name: 'LandingPage',
			component: () => import('@/modules/landing/layouts/LandingLayout.vue'),
			children: [
				{
					path: '/',
					name: 'home',
					component: HomePage
				},
				{

					path: '/features',
					name: 'features',
					component: () => import('@/modules/landing/pages/FeaturesPages.vue')
				},
				{
					path: '/pricing',
					name: 'pricing',
					component: () => import('@/modules/landing/pages/PricingPage.vue')
				},
				{
					path: '/contact',
					name: 'contact',
					component: () => import('@/modules/landing/pages/ContactPage.vue')
				}
			]
		},
		{
			path: '/auth',
			redirect: '/login',
			component: () => import('@/modules/auth/layouts/AuthLayout.vue'),
			children: [
			{
				path: '/login',
				component: () => import('@/modules/auth/pages/LoginPage.vue')
			},
			{
				path: '/register',
				component: () => import('@/modules/auth/pages/RegisterPage.vue')
			}
			]
		}
	]
})

  

export default router
```

## 404
El 404 se hace colocando el siguiente `path` por que es el último que se va a leer.

```typescript
{
	path: '/:pathMatch(.*)*',
	name: 'NotFound404',
	component: NotFound404
}
```

## Argumentos por URL
Se le agrega un `arg` entra después del slash y se define los `props`, estos props se pueden procesar para ser sanitizados.
```ts
{
path: '/pokemon/:id',
name: 'pokemon',
props: (route) => {
	const id = +route.params.id
	return isNaN(id) ? { id: 1 } : { id }
},
component: () => import('@/modules/pokemons/pages/PokemonPage.vue')
}
```


## Router
Existen dos tipos de `router`

**`useRouter()`**:  es un hook que se utiliza para obtener el router actual.
**`useRoute()`**: es un hook que se utiliza para obtener la ruta actual.

## Guards
Los guards se declaran de la siguiente manera.

```scaffolding
src/
├── modules/
	├── auth/
		├── guards/
		  ├── is-authenticated.guard.ts
```

`is-authenticated.guard.ts`
```typescript
import type {
RouteLocationNormalizedGeneric,
RouteLocationNormalizedLoadedGeneric,
NavigationGuardNext
} from 'vue-router'

const isAuthenticatedGuard = (
	to: RouteLocationNormalizedGeneric,
	from: RouteLocationNormalizedLoadedGeneric,
	next: NavigationGuardNext
) => {

const isAuthenticated = localStorage.getItem('isAuthenticated')
localStorage.setItem('lastPath', to.path)
if (!isAuthenticated) {
	console.log('User is not authenticated. Redirecting to login page...')
return next({
	name: 'login'
})
}
console.log('User is authenticated. Proceeding...')
return next()
}

  

export default isAuthenticatedGuard
```

Primero se ha de importar los tipos de `vue-router`
```ts
import type {
RouteLocationNormalizedGeneric,
RouteLocationNormalizedLoadedGeneric,
NavigationGuardNext
} from 'vue-router'
```
Y así declarar `isAuhenticatedGuard` que recibe tres parametros, `to`, `from` y `next`.

`to`: es la ruta a la que se quiere ir.
`from`: es la ruta de la que se viene.
`next`: es una función que se ejecuta para poder continuar con la navegación.

```ts
const isAuthenticatedGuard = (
	to: RouteLocationNormalizedGeneric,
	from: RouteLocationNormalizedLoadedGeneric,
	next: NavigationGuardNext
)
```

Podemos hacer uso del `localStorage` para poder guardar la información de la autenticación, ojo que esto tiene que ser validado en el **backend**.

```ts
const onLogin = () => {
	localStorage.setItem('isAuthenticated', true)
	const lastPath = localStorage.getItem('lastPath') ?? '/'
	router.replace(lastPath)
}
```


```ts
const isAuthenticatedGuard = (
	to: RouteLocationNormalizedGeneric,
	from: RouteLocationNormalizedLoadedGeneric,
	next: NavigationGuardNext
) => {

const isAuthenticated = localStorage.getItem('isAuthenticated')
localStorage.setItem('lastPath', to.path)
if (!isAuthenticated) {
	console.log('User is not authenticated. Redirecting to login page...')
return next({
	name: 'login'
})
}
```

