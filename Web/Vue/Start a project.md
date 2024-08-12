`vue.js`
```bash
npm create vue@latest
```

`tailwind.css`
```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

`index.css`
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

`tailwind.config.js`
```
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx,vue}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```