<main>
  <h1>Apresentação</h1>
  <div>Esse tutorial ensina como instalar o typebot localmente pelo windows sem simular um abiente ubuntu e a como configurar um debugger para o mesmo.A pasta detalhes.txt conta como fiz isso.</div><br>
  <div><i>PS:Alguns arquivos são modificados do projeto original para que os breakpoints do debugger sejam reconhecidos.</i></div>
  <h1>Requisitos</h1>
  <div>Requer VsCode, Google chrome e Docker Desktop Aberto</div>
  <h1>Limitações</h1>
  <div>Apesar de usar o vscode para startar o debugger a debugação em si só funciona pelo chrome dev tools</div>
  <h1>Instalação local</h1>
  <div class="code"> - git clone https://github.com/DAVIAMERICO242/typebot_debugger</div><br>
  <div class="code"> - cd typebot.io</div><br>
  <div class="code"> - copy .env.example .env</div><br>
  <div class="code"> - npm i -g pnpm</div><br>
  <div class="code"> - corepack enable pnpm </div><br>
  <div class="code"> - npm i -g bun</div><br>
  <div class="code"> - npm i -g turbo</div><br>
  <div class="warning"><b>Caso o bun, turbo nao sejam reconhecidos no terminal se deve criar uma variavel ambiente path no windows no diretório relativo ...\AppData\Roaming\npm (procure por %appdata% no buscador do windows que achará) </b></div>   <br>
  <div class="code"> - chcp 65001 </div><br>
  <div class="code"> - pnpm i </div><br>
  <div class="code"> - pnpm dev </div><br>
  <div><i>O frontend será visivel em localhost:3000 (pnpm dev irá rodar o projeto sem nenhum tipo de debug)</i></div>
  <h1>Configurar debugger</h1>
  <div><i>Nesse projeto escolhi a porta 9992 pro debugger no backend (viewer), 9990 por frontend (builder) e 9994 pro chat api.</i></div><br>
  <div> <b>1</b> - Abrir o vs code em typebot.io e configurar o seguinte launch.json:</div><br>

   ```json
  {
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Next.js: debug server-side",
      "type": "node-terminal",
      "request": "launch",
      "command": "npm run dev"
    },
    {
      "name": "Next.js: debug client-side",
      "type": "chrome",
      "request": "launch",
      "url": "http://localhost:3000"
    },
    {
      "name": "Next.js: debug full stack",
      "type": "node",
      "request": "launch",
      "program": "${workspaceFolder}/node_modules/.bin/next",
      "runtimeArgs": ["--inspect"],
      "skipFiles": ["<node_internals>/**"],
      "serverReadyAction": {
        "action": "debugWithEdge",
        "killOnServerStop": true,
        "pattern": "- Local:.+(https?://.+)",
        "uriFormat": "%s",
        "webRoot": "${workspaceFolder}"
      }
    }
  ]
}
 ```
<br>
<div><b>2</b> - Rodar no vscode a pasta raiz do projeto com esse launch.json configurado no modo DEBUG </div><br>
<div><b>3</b> - Acessar chrome://inspect > open dedicated devtools for node > adicionar o localhost com a porta de debug (9990,9992 ou 9994 dependendo do que vc quer debugar) </div><br>
<div><b>4</b> - Apos isso ir em fontes>adicionar pasta </div><br>
<div><b>5</b> - Adicione a pasta raiz do typebot (deve ficar como pasta inicial typebot.io) </div><br>
<div><b>5</b> - Agora voce pode usar os breakpoints sem problemas em fontes. </div><br>




  

</main>
