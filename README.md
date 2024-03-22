## ElectronJS + NextJS Template 

Um template ElectronJS com NextJS no Front-End para tornar as suas aplicações Desktop + Reactivas.

## Primeiros passos

Clone este repositorio, abra o seu terminal digite:

```bash
npm install 
# em seguida
npm run dev
```

O Electron construira a sua aplicação em um ambiente de desenvolvimento e escutara a sua aplicação NextJs na porta 3000 [http://localhost:3000](http://localhost:3000).

Você pode começar a editar a página modificando `app/page.tsx`. A página é atualizada automaticamente conforme você edita o arquivo.

## Compilando a aplicação

Estamos usando o (electron-builder) para lidar com isso para nós.

Comece a criar um arquivo chamado (electron-builder.yaml) na raiz do seu projeto.

```bash
appId: "io.github.rbfraphael.electron-next"
productName: "Electron Next.JS"
copyright: "Copyright (c) 2024 Nilton667"
win:
  target: ["dir", "portable", "zip"]
  icon: "resources/icon.ico" # O diretório exato do seu icon
linux:
  target: ["dir", "appimage", "zip"]
  icon: "resources/icon.png" # O diretório exato do seu icon
mac:
  target: ["dir", "dmg", "zip"]
  icon: "resources/icon.icns" # O diretório exato do seu icon
```

- Depois de especificar corretamente as opções necessárias no electron-builder.yaml arquivo, basta executar npm run buildem seu terminal. 

- Os arquivos estáticos Next.JS serão gerados e exportados para o out/diretório, então o aplicativo Electron será compilado e salvo no dist/diretório.

- [electron-builder Documentação](https://www.electron.build)

## Notas Do Author

- O app route do nextJS não é compativel com Electron então se for utiliza-lo podera ter um comportamento inesperado.

- É uma boa praticada separar as paginas por componentes em vez de usar o page route, Assim o electron carregara toda a sua aplicação logo no primeiro carregamento.

- Se notar alguma anormalia não relatada aqui sinta-se a vontande para abrir um tikect (Problemas) que eu terei muito gosto em resolver com você.