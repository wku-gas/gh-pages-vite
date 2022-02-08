# Deploy vite react app to GitHub Pages

The steps are generally very similar to [the tutorial for deploying CRA app to GitHub Pages](https://github.com/gitname/react-gh-pages)

1. Create a react app using vite
````
    npm init vite@latest my-vite-react-app -- --template react
````
2. Do a `git init`
3. Add `gh-pages` dev dependency
````
    npm i -D gh-pages
````
4. Add the following to `"scripts"` in `package.json`
````
  "scripts": {
    ...,
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist"
  },  
````

Here, `dist` would be the default build folder for vite

5. Create a new repository at GitHub (for example `my-vite-app`)
6. Add git remote origin
````
    git remote add origin git@github.com:<github user>/<repo>.git
    git remote add origin git@github.com:wku-stengg/my-vite-app.git
````
7. add `base` field in `vite.config.js`, assuming using project site
````
    base: '/<repo>/'
    base: '/my-vite-app/'
````
8. Deploy by using `npm run deploy`
9. You should be able to access the react app at 
````
https://<github user>.github.io/<repo>/
https://wku-stengg.github.io/my-vite-app/
````