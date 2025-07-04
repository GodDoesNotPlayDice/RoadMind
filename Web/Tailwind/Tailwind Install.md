Para instalar depende si se usa framework o vanilla.

## Framework
```bash
pnpm install tailwindcss @tailwindcss/vite
```

```bash
npm install tailwindcss @tailwindcss/vite
```

`vite.config.ts`
```ts
import tailwindcss from '@tailwindcss/vite'
export default defineConfig({  plugins: [ tailwindcss(),  ],})
```

`index.css`
```css
@import "tailwindcss";
```
## Vanilla (CDN)

```html
  <script src="https://cdn.tailwindcss.com"></script>
```

