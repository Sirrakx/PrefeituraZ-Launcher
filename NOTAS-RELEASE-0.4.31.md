Prefeitura Z 0.4.31 — Steam Relay opcional no launcher

Em Conta e áudio, logo abaixo da conta, há a opção Usar Steam Relay.

- Desmarcada por padrão: usa conexão direta.
- Marcada: usa Steam Relay ao entrar na Prefeitura Z.
- A escolha é salva automaticamente e recuperada ao reabrir o launcher.
- Cada edição mantém suas próprias preferências. Memória, FPS e perfil de desempenho permanecem independentes.

Para jogadores que já entram normalmente, basta continuar com a opção desmarcada. Quem precisa do Relay pode marcá-la uma vez no launcher; não precisa navegar pelos menus do jogo a cada entrada.

O modo Relay abre o mesmo fluxo nativo de conexão usado no menu Entrar, preservando a conta salva e a autenticação do servidor. A escolha não é ativada automaticamente após uma falha. O modo direto mantém a consulta nativa de detalhes do servidor.

O diagnóstico passa a incluir conexao.txt, com etapas e tempos da tentativa. Nenhuma senha, nome de conta ou mensagem livre do servidor é incluída nesse resumo. A coleta continua manual pelo botão Salvar diagnóstico.

Inclui as correções da candidata 0.4.30: canal de atualização incorporado sem PrefeituraZ-Updates.json externo, identificação correta da versão e recuperação transacional dos registros de texturas antigos.

Compatibilidade: B42.22. O painel do dedicado permanece 2.1.8. O conteúdo Lua no disco e o checksum multiplayer não mudam por causa desta opção; não requer alteração do dedicado para usar o Relay.

O jogador afetado confirmou que conseguiu conectar usando Steam Relay. A opção reproduz esse caminho no launcher; a causa da diferença entre os caminhos de rede ainda não foi determinada.
