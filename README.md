# Prefeitura Z Launcher

Launchers oficiais da comunidade Prefeitura Z para Windows e Project Zomboid B42.22.

Na 0.4.31, cada edição consulta seu canal incorporado no EXE. Não é necessário manter PrefeituraZ-Updates.json ao lado dele; arquivos externos antigos são ignorados. A versão também recupera registros de texturas desatualizados com backup e reversão e corrige a identificação da versão no diagnóstico. Clientes antigos que não consultam o canal precisam substituir o EXE uma vez.

A opção **Usar Steam Relay**, em **Conta e áudio**, é opcional e começa desmarcada. A escolha é salva automaticamente. Use o modo direto normalmente e ative o Relay quando precisar desse caminho de conexão.

## Downloads

- [Launcher para jogadores](https://github.com/Sirrakx/PrefeituraZ-Launcher/releases/download/v0.4.31-b42-2.1.8/PrefeituraZ-Launcher.exe)
- [Launcher Admin](https://github.com/Sirrakx/PrefeituraZ-Launcher/releases/download/v0.4.31-b42-2.1.8/PrefeituraZ-Admin.exe)
- [Launcher Controle](https://github.com/Sirrakx/PrefeituraZ-Launcher/releases/download/v0.4.31-b42-2.1.8/PrefeituraZ-Controle.exe)
- [ZIP Windows 0.4.31 com as três edições](https://github.com/Sirrakx/PrefeituraZ-Launcher/releases/download/v0.4.31-b42-2.1.8/PrefeituraZ-0.4.31-PZO-Windows.zip)
- [Painel do dedicado 2.1.8 — ZIP](https://github.com/Sirrakx/PrefeituraZ-Launcher/releases/download/v0.4.16-b42-2.1.8/PrefeituraZ-Servidor-2.1.8-Windows.zip)

Instale a geração com atualização automática uma vez, substituindo o executável antigo com o launcher fechado. Depois, mantenha o mesmo atalho: o launcher verifica o canal assinado ao abrir e antes de iniciar o jogo. Confere assinatura e SHA-256 e usa uma cópia interna temporária para recuperação.

A versão 0.4.29 acompanha automaticamente o Lua oficial do Workshop e as releases estáveis oficiais do motor PZO ao preparar o jogo. Confere origem, tamanho, SHA-256 e a API da ponte, aplica o pacote com backup e preserva a memória escolhida. Há recuperação local quando a consulta ou instalação falha. Jogador/Admin incluem o endereço do canal assinado; o Controle mantém seu canal exclusivo. [Como atualizar, recuperação e limites](ATUALIZADOR-0.4.31.md).

A edição Admin exige convite individual e conta autorizada; baixar esse executável não concede privilégios no servidor.

O painel reconhece projectzomboid.jar na raiz ou em java e preserva o valor existente de DoLuaChecksum. Atualizações do painel exigem dedicado e auxiliares parados. Para instalar o painel, use o ZIP completo.

[Detalhes técnicos e publicação de próximas versões](GUIA-ATUALIZACAO.md).
Versões 0.4.11 / 2.1.5: código ofuscado e ícone exclusivo do Admin, com testes de conta, atualização e administração. [Detalhes da proteção e medições](OFUSCACAO-0.4.11.md).

Versões 0.4.12 / 2.1.6: atualizam o EXE com nome personalizado e não deixam .bak ao lado do aplicativo. [Instalação e comportamento das versões anteriores](ATUALIZADOR-0.4.12.md).

Versão 0.4.13: jogador e Admin lembram contas independentes. Cadastre uma conta em cada edição na primeira abertura. O painel permanece na 2.1.6. [Detalhes da separação das contas](ATUALIZADOR-0.4.13.md).

Versão 0.4.14: corrige o encerramento ao abrir o jogo causado pela verificação de origem do PZ_Optimization com o pacote Horse. [Detalhes e validação](ATUALIZADOR-0.4.14.md).

Painel 2.1.7: a nova aba **Contas do jogo** consulta contas existentes, concede o cargo Admin e redefine senhas, inclusive da conta admin. As alterações exigem dedicado online e confirmação do resultado no banco. [Uso e instalação](PAINEL-2.1.7.md).

Versão 0.4.15: reconhece classes aprovadas de uma instalação parcial, verifica acesso aos arquivos antes de gravar e informa o destino de falhas no Windows. [Detalhes e recuperação](ATUALIZADOR-0.4.15.md).

Versoes 0.4.16 / 2.1.8: tres perfis de desempenho, remocao real do PZ_Optimization, Tempo + texturas equilibradas e memoria automatica ou manual independente. [Uso e validacao](ATUALIZADOR-0.4.16.md). [Preparacao do Tempo no dedicado](PAINEL-2.1.8.md).


A 0.4.29 corrige a abertura na B42.22 com integrações Java. Três rodadas de testes nas três edições e testes de abertura real aprovados. Os problemas de partida do mod AVCS e animações de cavalos estão em investigação separada no modpack/servidor.
