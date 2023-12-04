# Настройки для проектов React:

1. Добавить в package.json две строчки:                                    
    "homepage": "https://Alekcandrovich.github.io/название проекта/",                               
    и "lint:js": "eslint src/**/*.{js,jsx}"                              
////////////////////////////////////

  "name": "car-rental-test",    
  "version": "0.1.0",    
  "private": true,    

// "homepage": "https://Alekcandrovich.github.io/car-rental-test/",    
  
  "dependencies": {    
    "@testing-library/jest-dom": "^5.17.0",    
    "@testing-library/react": "^13.4.0",    
    "@testing-library/user-event": "^13.5.0",    
    "react": "^18.2.0",    
    "react-dom": "^18.2.0",    
    "react-scripts": "5.0.1",    
    "web-vitals": "^2.1.4"    
  },    
  "scripts": {    
    "start": "react-scripts start",    
    "build": "react-scripts build",    
    "test": "react-scripts test",    
    "eject": "react-scripts eject",    
    
// "lint:js": "eslint src/**/*.{js,jsx}"    
  },    
/////////////////////    
  
2. Добавить в корень проекта файлы настройки для    
   редактора - .editorconfig     
   и форматировщика - .prettierrc.json    

3. Деплой проекта:    
   в GitHub во вкладке "Actions" перейти по ссылке "set up a workflow yourself"    
   и создать файл deploy.yml со следующим содержимым:    
///////////////////    
     name: Build and deploy to GitHub Pages    

on:    
  push:    
    branches: [main]    

jobs:    
  build-and-deploy:    
    runs-on: ubuntu-latest    
    steps:    
      - name: Checkout 🛎️    
        uses: actions/checkout@v2.3.1    

      - name: Install, lint, build 🔧    
        run: |    
          npm install    
          npm run lint:js    
          npm run build    

      - name: Deploy 🚀    
        uses: JamesIves/github-pages-deploy-action@4.1.0    
        with:    
          branch: gh-pages    
          folder: build    

/////////////////////
