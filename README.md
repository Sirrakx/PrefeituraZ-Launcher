# Prefeitura Z Launcher

Launchers oficiais da comunidade Prefeitura Z para Windows e Project Zomboid B42.21.

## Downloads

- [Launcher para jogadores](https://github.com/Sirrakx/PrefeituraZ-Launcher/releases/download/v0.4.14-b42-2.1.6/PrefeituraZ-Launcher.exe)
- [Launcher Admin](https://github.com/Sirrakx/PrefeituraZ-Launcher/releases/download/v0.4.14-b42-2.1.6/PrefeituraZ-Admin.exe)
- [Painel do dedicado 2.1.6 — ZIP](https://github.com/Sirrakx/PrefeituraZ-Launcher/releases/download/v0.4.14-b42-2.1.6/PrefeituraZ-Servidor-2.1.6-Windows.zip)

Instale a geração com atualização automática uma vez, substituindo o executável antigo com o launcher fechado. Depois, mantenha o mesmo atalho: o launcher verifica o canal assinado ao abrir e antes de iniciar o jogo. Confere assinatura e SHA-256 e usa uma cópia interna temporária para recuperação.

O PZ_Optimization é consultado no repositório oficial do autor e atualizado automaticamente quando a versão do jogo e as integrações forem compatíveis. Uma atualização incompatível é adiada e informada no log.

A edição Admin exige convite individual e conta autorizada; baixar esse executável não concede privilégios no servidor.

O painel reconhece projectzomboid.jar na raiz ou em java e preserva o valor existente de DoLuaChecksum. Atualizações do painel exigem dedicado e auxiliares parados. Para instalar o painel, use o ZIP completo.

[Detalhes técnicos e publicação de próximas versões](GUIA-ATUALIZACAO.md).
Versões 0.4.11 / 2.1.5: código ofuscado e ícone exclusivo do Admin, com testes de conta, atualização e administração. [Detalhes da proteção e medições](OFUSCACAO-0.4.11.md).

Versões 0.4.12 / 2.1.6: atualizam o EXE com nome personalizado e não deixam .bak ao lado do aplicativo. [Instalação e comportamento das versões anteriores](ATUALIZADOR-0.4.12.md).

Versão 0.4.13: jogador e Admin lembram contas independentes. Cadastre uma conta em cada edição na primeira abertura. O painel permanece na 2.1.6. [Detalhes da separação das contas](ATUALIZADOR-0.4.13.md).

Versão 0.4.14: corrige o encerramento ao abrir o jogo causado pela verificação de origem do PZ_Optimization com o pacote Horse. [Detalhes e validação](ATUALIZADOR-0.4.14.md).
