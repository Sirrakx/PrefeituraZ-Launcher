# Prefeitura Z — painel do dedicado 2.1.8

A aba **Integração** ganhou **Preparar Tempo no multiplayer**. A função inclui `Tempo_PerfKit` em `Mods` e `3736629791` em `WorkshopItems`, sem duplicar entradas, e guarda backup do INI. O Java do Tempo fica somente nos clientes que escolherem esse perfil.

Atualize os clientes para 0.4.16 primeiro. No computador do servidor, use **Parar e manter parado**, aguarde dedicado, AutoRestart e supervisão encerrarem e feche o painel antes de instalar a nova versão. Substitua o executável pelo pacote 2.1.8 e mantenha configurações, dados de convites, certificados e bridge. A função também confirma que os processos estão parados antes de escrever.

Selecione a instalação e a pasta Zomboid corretas em **Integração**, clique em **Preparar Tempo no multiplayer** e depois use **Iniciar** normalmente. A Steam baixa o mod pela rotina normal do dedicado. O ETO não é incluído no servidor; as texturas são individuais no cliente.

O preparo preserva as demais opções, incluindo `DoLuaChecksum` false, true ou ausente, mapas e acesso. Mantém o fluxo do AutoRestart e reconhece `projectzomboid.jar` tanto na raiz quanto em `java`. Não instala classes Java do Tempo no dedicado.

As funções de contas do jogo, convites, revogação, TLS, permissões, Horse e proteção mantêm o comportamento da 2.1.7. A capacidade dos alforjes continua 85.

O painel passou pelas 156 verificações existentes e por 12 novas verificações do INI: preservação das opções, listas já existentes ou ausentes, idempotência, entradas duplicadas e BOM UTF-8. Os testes usam instalações isoladas. A aplicação no dedicado remoto e a validação em partida permanecem a cargo da implantação.
