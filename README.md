Tailwindcss@3 in HTML

// https://v3.tailwindcss.com/docs/installation 

npm -y init
npm install -D tailwindcss@3 postcss autoprefixer
npx tailwindcss init -p

// in tailwind.config.js
module.exports = {
  content: ["./*.html"],  // only this part is changing
  theme: {
    extend: {},
  },
  plugins: [],
};

// in styles.css
@tailwind base;
@tailwind components;
@tailwind utilities;


npx tailwindcss -i ./styles.css -o ./dist.css --watch

// in .html
<link rel="stylesheet" href="dist.css">





// cdn
 <script src="https://cdn.tailwindcss.com"></script>




 -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------






 tailwindcss@3 in React  







 https://v3.tailwindcss.com/docs/guides/vite

npm create vite@latest my-project
cd my-project

npm install -D tailwindcss@3 postcss autoprefixer
npx tailwindcss init -p
