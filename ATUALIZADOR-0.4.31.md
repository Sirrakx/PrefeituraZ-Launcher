# Steam Relay opcional e atualização do launcher

Jogador/Admin mantêm o canal assinado incorporado; Controle mantém seu canal exclusivo. Arquivos PrefeituraZ-Updates.json externos são ignorados. Clientes antigos com consulta desativada ainda precisam substituir o EXE uma vez.

O novo checkbox fica em Conta e áudio, abaixo da conta. `useSteamRelay` é um booleano salvo junto das demais preferências internas, por edição. Ausência da chave significa desmarcado. O salvamento normal dos demais ajustes preserva a escolha.

Ao iniciar o jogo para o destino integrado, o launcher coloca a escolha nos argumentos JVM e prepara um JAR privado em PRZRuntime, cujo conteúdo é conferido contra o recurso incorporado. Não grava a opção no JSON do jogo nem muda o perfil de desempenho. O agente instalado nesse processo usa o evento OnMainMenuEnter da thread Lua e limita a escolha ao destino integrado da Prefeitura Z.

Com Relay selecionado, o fluxo abre ServerConnectPopup diretamente para o dedicado conhecido, como a entrada pelo menu nativo, e seleciona Usar Steam Relay. Com Relay desmarcado, permanece a consulta normal de BootstrapConnectPopup e o popup recebe a escolha desmarcada. A passagem de conta e verificador, doHash, authType, senha do servidor e parâmetros nativos de autenticação são preservados. Outros servidores e inicializações sem o destino integrado não recebem a opção.

Não há troca automática para Relay, watchdog de reconexão ou repetição de tentativas de autenticação. Essas propostas foram retiradas em favor da opção explícita solicitada pelo usuário.

Os arquivos Lua do jogo permanecem iguais no disco. O hook é carregado somente na JVM iniciada pelo launcher; não exige alterar o dedicado nem desativar checksum. O agente e ASM 9.9/licença ficam incorporados no EXE e são preparados automaticamente.

`conexao.txt` é incluído no ZIP de suporte a partir de códigos e tempos explicitamente permitidos. Texto arbitrário e credenciais são descartados. Nenhum envio automático foi adicionado.

Validação: RelayOptionTests verifica interface real, padrão desmarcado, persistência, preservação dos ajustes, ambas as classes de entrada, caminhos com espaços, destino isolado e reconstrução do cache. ConnectionRecoveryProbe usa a JVM/Kahlua do jogo, o BootstrapConnectPopup nativo e a integração de login de produção, cobrindo os modos direto e Relay, falha, cancelamento, callbacks atrasados, outros destinos e ausência de repetição de autenticação. Os testes da candidata 0.4.30 continuam no fluxo de validação.
