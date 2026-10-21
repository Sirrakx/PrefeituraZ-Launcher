# Validação da versão 0.4.15

Os executáveis finais ofuscados passaram **335 verificações**: 240 no Jogador e 95 no Admin. Incluem atualização assinada, contas separadas, interface, proteção local, ciclo de vida, diagnóstico, Horse, visibilidade, salas, física, layout e aplicação/restauração de ajustes.

Cada edição passou 18 verificações novas: instalação limpa; classe idêntica ao pacote; classe original extraída do JAR; hotfix de salas reconhecido; classe desconhecida bloqueada e preservada; log com destino e hash; relatório com caminhos relativos; classe desconhecida fora do pacote bloqueada; plano adulterado recusado; fixture de instalação parcial sem build-info; complemento do pacote; integridade completa do resultado; restauração ao estado anterior; arquivo somente leitura; arquivo ocupado; falha de substituição atômica com destino e código Windows; limpeza de temporários; comparação de classes dentro do ZIP de suporte.

Os testes de gravação e restauração usaram pastas descartáveis. Não foi iniciado jogo no computador afetado, removido arquivo desconhecido ou alterada configuração de segurança, atributo ou permissão do Windows para contornar um bloqueio.

Após ofuscação, os 18 recursos do Jogador e os 19 do Admin permaneceram idênticos por SHA-256; ícones foram preservados. Em cada executável foram renomeados 144 tipos e 413 métodos. Fontes e mapas privados não integram o pacote público.

O manifesto assinado foi conferido pelas três edições, com versão, papel, tamanho, hash e destino. O painel e ZIP 2.1.7 são os mesmos da entrega anterior. O addon Horse e o pacote incorporado do PZ_Optimization mantêm seus hashes.

Limite: um arquivo ainda bloqueado para gravação no computador do jogador continuará impedindo a aplicação; a nova mensagem identifica o destino. O diagnóstico 0.4.14 não continha o nome desse arquivo.

## Publicação e atualização automática

Os oito downloads públicos foram conferidos por SHA-256. O endpoint fixo retorna o manifesto esperado e as três edições aceitaram assinatura, sequência e versão atual. Jogador e Admin 0.4.14 baixaram a 0.4.15 pelo canal real e passaram troca/reversão em cópias isoladas. O helper real passou confirmação, recuperação após falha, preservação de nome personalizado e limpeza de temporários sem .bak ao lado do EXE. São 12 verificações adicionais do fluxo de atualização, além das 335 verificações das suítes.
