# Prefeitura Z — correção de instalação interrompida 0.4.15

Uma primeira preparação podia falhar ao substituir um arquivo no Windows e deixar parte das classes do PZ_Optimization na instalação. Na tentativa seguinte, a versão 0.4.14 bloqueava qualquer classe que já existisse com a mensagem genérica de “outro mod Java”. A presença do arquivo, sozinha, não identificava um mod diferente.

A 0.4.15 compara SHA-256 antes de preparar. Aceita somente classes idênticas ao pacote aprovado, ao JAR original B42.21 ou à correção de salas conhecida da Prefeitura Z. Pode complementar uma instalação parcial sem build-info quando os arquivos existentes passam por essas verificações. O resultado continua sujeito à verificação completa de integridade. Classes desconhecidas, classpath adicional e arquivos alterados continuam bloqueados e preservados.

Antes de escrever o lote, o launcher verifica se os destinos existentes que precisam mudar estão disponíveis para gravação. Arquivos ocupados, somente leitura ou sem acesso interrompem a preparação com o destino e, quando disponível, o código de erro do Windows. Não são alterados atributos, permissões, políticas ou antivírus. Se uma falha posterior exigir recuperação e ela não puder concluir, o log informa o backup pendente.

O diagnóstico em **Suporte → Salvar diagnóstico** passa a listar as classes divergentes e seus hashes usando caminhos relativos. A mensagem deixa de afirmar que outro mod foi instalado sem evidência.

## Para quem recebeu o aviso

1. Feche o launcher e abra novamente para receber a **0.4.15** pelo canal assinado.
2. Clique em **Jogar** com o jogo fechado e aguarde a preparação. Os arquivos conhecidos da tentativa anterior podem ser reaproveitados.
3. Se aparecer arquivo ocupado, somente leitura ou sem permissão, confira o nome indicado e feche o programa que estiver usando esse arquivo. Se a causa não estiver clara, gere um novo diagnóstico em Suporte e envie à equipe. Não apague pastas de classes ou saves indiscriminadamente.

A retomada dos arquivos aprovados não garante a remoção de um bloqueio persistente de gravação no computador. O diagnóstico anterior não registrava o destino da falha, portanto essa causa específica precisa ser conferida no ambiente afetado.

Jogador e Admin usam a mesma correção e mantêm suas contas separadas. Atualização com nome personalizado e sem `.bak` ao lado do EXE permanece. O painel dedicado continua **2.1.7 com os mesmos bytes**. Horse, capacidade dos alforjes e otimizador incorporado não mudam.

## Validação

Foram simulados instalação nova, cópia parcial sem build-info, classe original, hotfix PRZ, classe desconhecida dentro e fora do pacote, pacote alterado, restauração após completar a instalação, arquivo ocupado e somente leitura. O pacote recuperado passou pela verificação completa de integridade. A consulta de divergências também foi conferida no ZIP de suporte.

Os testes usam cópias isoladas. Não houve acesso à máquina do jogador nem confirmação de uma partida nesse computador após a correção.
