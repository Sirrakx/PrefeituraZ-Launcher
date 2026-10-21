# Validação do painel 2.1.7

O executável final ofuscado passou 156 verificações: contas (33), atualização (19), proteção e administração TLS (24), integração de cavalos com JAR em java (18), integração geral (17), layout e preservação de checksum (28) e funcionamento anterior do painel (17).

Outras 7 verificações exercitaram o código nativo da B42.21 em banco descartável: parser com espaços e Unicode, confirmação e criptografia da senha, persistência com authType, separação por mundo, persistência do cargo, resposta de conta inexistente e log sem senha ou verificador.

As consultas reais pelo JDBC incorporado deixaram o banco de teste idêntico por SHA-256. Foram testados autenticação RCON recusada, conta ausente, comandos inválidos, respostas sem persistência, operação duplicada, servidor ambíguo e senha admin imposta pelo script de inicialização. Os campos de senha são mascarados e alterações ficam bloqueadas até o dedicado responder.

Os 10 recursos incorporados permaneceram idênticos antes e depois da ofuscação. Foram renomeados 163 tipos e 399 métodos; o ícone nativo foi preservado. Fonte, mapa de nomes e chave de assinatura não fazem parte da entrega.

O manifesto foi validado pelos três executáveis, conferindo assinatura, edição, versão, hash, tamanho e destino. O painel dentro do ZIP é idêntico ao EXE identificado pelo manifesto. Os executáveis Jogador e Admin 0.4.14 e seu ícone têm os mesmos bytes da entrega anterior.

Não houve alteração de contas reais, inicialização do dedicado remoto ou teste de uma sessão multiplayer remota. A instalação e a primeira operação precisam ser conferidas na máquina do dedicado.

## Canal público e migração

Os oito arquivos publicados foram baixados novamente e conferidos por SHA-256. O endpoint fixo do canal retorna o manifesto assinado esperado; os três executáveis consultaram o canal real e confirmaram assinatura, sequência e versão atual. O painel 2.1.6 baixou a 2.1.7 pelo canal público e passou troca e reversão em cópia isolada. O helper real também passou atualização com confirmação, recuperação após falha, preservação de nome personalizado e limpeza dos temporários, sem .bak ao lado do EXE. Os manifestos anteriores de 0.4.10 até 0.4.14 foram conservados.
