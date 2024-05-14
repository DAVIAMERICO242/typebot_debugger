<main>
  <h1>Apresentação</h1>
  <div>Esse tutorial ensina como instalar o typebot localmente pelo windows sem simular um abiente ubuntu e configurar um debugger para o mesmo.</div>
  <div>Alguns arquivos são modificados para que os breakpoints do debugger sejam reconhecidos.</div>
  <h1>Instalação local</h1>
  <div class="code"> - git clone https://github.com/DAVIAMERICO242/typebot_debugger</div><br>
  <div class="code"> - cd typebot.io</div><br>
  <div class="code"> - copy .env.example .env</div><br>
  <div class="code"> - npm i pnpm</div><br>
  <div class="code"> - npm i bun</div><br>
  <div class="code"> - npm i turbo</div><br>
  <div class="warning"><b>Caso o bun, turbo nao sejam reconhecidos no terminal se deve criar uma variavel ambiente path no windows no diretório relativo ...\AppData\Roaming\npm (procure por %appdata% no buscador do windows que achará) </b></div>   <br>
  <div class="code"> - pnpm i </div><br>
  <div class="code"> - pnpm dev </div><br>
  <div><i>O frontend será visivel em localhost:3000 (pnpm dev irá rodar o projeto sem nenhum tipo de debug)</i></div>

  

</main>
