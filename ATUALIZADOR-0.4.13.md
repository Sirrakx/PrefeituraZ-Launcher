# Prefeitura Z — launcher 0.4.13 / painel 2.1.6

## Contas independentes para jogador e Admin

Cada edição agora lembra seu próprio usuário e senha pessoal do servidor. Cadastre a conta de jogador em **Conta e áudio** do launcher de jogador e a conta administrativa na mesma tela do launcher Admin. Salvar, substituir, desmarcar a opção de lembrar ou esquecer a conta afeta somente a edição aberta. As contas continuam disponíveis depois de fechar, reabrir, atualizar ou renomear o EXE.

O armazenamento usa arquivos separados em `%LOCALAPPDATA%/PrefeituraZLauncher/accounts/player.bin` e `admin.bin`. Os verificadores de senha continuam protegidos por DPAPI do usuário do Windows, com destino do servidor e edição vinculados à proteção, e acesso restrito ao usuário atual e SYSTEM. Copiar o arquivo de uma edição sobre o da outra não faz o launcher aceitar aquela conta.

Na primeira abertura da 0.4.13, informe a conta em cada edição uma vez. O arquivo antigo compartilhado não informa se continha uma conta de jogador ou administrativa; por isso não é importado automaticamente nem apagado. Convites de administração remota, permissões no servidor, configurações do jogo e preferências de áudio são preservados. Baixar ou usar a edição Admin não concede permissões no jogo.

## Atualização e nome do aplicativo

A atualização automática assinada continua ativa. A 0.4.12 já pode atualizar para a 0.4.13 preservando nomes personalizados e sem deixar `.bak` ao lado do EXE. A cópia interna de recuperação temporária é removida após a confirmação de abertura ou restauração bem-sucedida. Cópias antigas existentes não são removidas automaticamente.

Quem ainda usa 0.4.10/0.4.11 pode substituir manualmente o EXE com o launcher fechado para evitar o último `.bak` criado pelo atualizador antigo. Depois, pode renomear o aplicativo mantendo `.exe`.

O painel do dedicado permanece na **2.1.6**, com os mesmos bytes da entrega anterior. Não há atualização necessária do servidor por causa da separação das contas.

## Validação

Os dois EXEs finais são ofuscados. Os testes verificam armazenamento DPAPI, ACL, preservação da conta da outra edição ao salvar e esquecer, recusa de cofre copiado entre edições e ausência de importação automática do arquivo legado. As suítes de atualização, interface, proteção e demais integrações também são executadas em instalações de teste. Nenhuma conta real, partida ou servidor remoto é usada para esses testes.
