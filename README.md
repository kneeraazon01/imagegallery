# ImageGallery
Building a image gallery site with reactjs and tailwindcss


## Steps
 
### npx create-react-app react-tailwindcss && cd react-tailwindcss
### npm install tailwindcss postcss-cli autoprefixer@9.8.6 -D
### npx tailwind init tailwind.js --full > full is optional
### touch postcss.config.js
## Add this to the postcss.config.js

const tailwindcss = require('tailwindcss');
module.exports = {
    plugins: [
        tailwindcss('./tailwind.js'),
        require('autoprefixer')
    ],
};

## Add this to  tailwind.css file in src

@tailwind base;

@tailwind components;

@tailwind utilities;

or 

@import "tailwindcss/base";

@import "tailwindcss/components";

@import "tailwindcss/utilities";


## Modify Scripts in package.json as follows

"scripts": {
  "start": "npm run watch:css && react-scripts start",
  "build": "npm run watch:css && react-scripts build",
  "test": "react-scripts test",
  "eject": "react-scripts eject",
  "watch:css": "postcss src/assets/tailwind.css -o src/assets/main.css"
}

## now add the main.css from src to index.js and you are good to go

import './assets/main.css'
