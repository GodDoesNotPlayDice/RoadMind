Para instalar depende si se usa framework o vanilla.

## Framework
```bash
npm install tailwindcss @tailwindcss/vite
```


`vite.config.ts`
```js
import { defineConfig } from 'vite'import tailwindcss from '@tailwindcss/vite'export default defineConfig({  plugins: [    tailwindcss(),  ],})
```

`index.css`
```css
@import "tailwindcss";
```

## Vanilla (CDN)

```html
  <script src="https://cdn.tailwindcss.com"></script>
```

