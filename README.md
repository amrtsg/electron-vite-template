# Electron + Vite + React Template

Quickstarter template using electron, vite and react for program development.

## Initial Template Setup
```
> npm create electron-vite //you will be prompted to pick react, vue, or vanilla.
> cd YOURPROJECTNAME
> npm i
> npm i vite-tsconfig-paths //This will create the vite.config.ts file
```
Then open vite.config.ts file and import ```import tsconfigPaths from 'vite-tsconfig-paths'``` and add ```tsconfigPaths(),``` under ```plugins: [``` in the file.

Now you can add your paths to ```tsconfig.json``` like so:
```
"paths": {
      "@/*": [
        "./src/*"
      ],
      "components/*": ["./src/components/*"],
    },
```

Now to remove the default menubar from the electron window, open electrons ```main.ts``` file and add the following line
```
function createWindow() {
  win = new BrowserWindow({
    icon: path.join(process.env.VITE_PUBLIC, 'electron-vite.svg'),
    autoHideMenuBar: true, //ADD THIS LINE HERE!
    webPreferences: {
      preload: path.join(__dirname, 'preload.mjs'),
    },
  })
```

## To run this project
```
> git clone https://github.com/amrtsg/electron-vite-template.git
> cd electron-vite
> npm i
> npm run dev
```