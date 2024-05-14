<head>
  <style>
    .code{
      background-color:gray;
    }
  </style>
</head>
<main>
  <h1>Apresentação</h1>
  <div>Esse tutorial ensina como instalar o typebot localmente pelo windows sem simular um abiente ubuntu e configurar um debugger para o mesmo.</div>
  <div>Alguns arquivos são modificados para que os breakpoints do debugger sejam reconhecidos.</div>
  <h1>Instalação local</h1>
  <div class="code">git clone https://github.com/DAVIAMERICO242/typebot_debugger</div>
  <div class="code">cd typebot.io</div>
  <div class="code">copy .env.example .env</div>
  <div class="code">npm i bun</div>
  <div class="code">npm i turbo</div>
  <div class="warning">Caso o bun e turbo nao sejam reconhecidos no terminal se deve criar uma variavel ambiente path no windows no diretório relativo ...\AppData\Roaming\npm (procure por %appdata% no buscador do windows que achará) </div>

</main>
