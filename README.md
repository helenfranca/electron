## Aplicação Electron - Puro

[Vídeo Base](https://www.youtube.com/watch?v=TBECQe6AteU)

[Documentação Electron](https://www.electronjs.org/docs/tutorial/first-app)

### Passos:

Dentro da pasta que irá desenvolver o projeto, dê o comando:
```
npm init
```
Crie os arquivos:
```
your-app/
├── package.json
├── main.js
└── index.html
```

Altere o package.json
```
{
  "name": "your-app",
  "version": "0.1.0",
  "main": "main.js",
  "scripts": {
    "start": "electron ."
  }
}
```

Instale o Electron
```
npm install --save-dev electron
```

No arquivo *main.js* insira o código:
```
const { app, BrowserWindow } = require('electron')

function createWindow () {
  // Create the browser window.
  let win = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      nodeIntegration: true
    }
  })

  // and load the index.html of the app.
  win.loadFile('index.html')
}

app.whenReady().then(createWindow)
```

Rodar Aplicação
```
npm start
```

### Para gerar o Executável
Instale o electron-packager
```
npm install electron-packager -g
```
Feito isso, rode o seguinte comando:

```
electron-packager . <nome-do-app>
```
O arquivo executável irá para dentro da pasta do projeto

Em casos de dúvidas, consulte a documentação.

#### O modo de geração do executável neste exemplo serve para qualquer SO.