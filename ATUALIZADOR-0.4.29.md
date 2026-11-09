Prefeitura Z 0.4.29 — abertura na B42.22

- Corrige o encerramento do jogo na inicialização causado pela assinatura do projectzomboid.jar ao carregar as integrações Java.
- Reconhece a linha de comando real do launcher, inclusive "-cp" e a pasta de dados entre aspas.
- Prepara uma cópia privada do JAR para as integrações; preserva o JAR original do jogo.
- Atualiza a base para B42.22 e PZO 1.9.9. PZ_Optimization fica indisponível enquanto aguarda versão compatível.
- Mantém os canais de atualização separados para Jogador/Admin e Controle.

Validação: três rodadas completas nas três edições, mais 33 verificações dos argumentos de abertura. Teste pelo botão Jogar confirmado até a entrada no mundo do servidor Prefeitura Z.

Problemas conhecidos: a partida dos veículos no mod AVCS e as animações dos cavalos estão em investigação separada no modpack/servidor. Esta atualização corrige a abertura do launcher e não declara resolvidos esses problemas de gameplay.

Instalação manual: extraia o ZIP completo em uma pasta e abra a edição desejada. Mantenha PrefeituraZ-Updates.json junto dos executáveis Jogador/Admin para receber o canal estável. O Controle mantém seu próprio canal incorporado.

Compatibilidade: jogo B42.22. A entrada do painel de servidor 2.1.8 é preservada no canal; este pacote não atualiza o servidor Linux.
