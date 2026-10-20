# Prefeitura Z — launcher 0.4.12 / painel 2.1.6

## Nome livre do executável

O atualizador usa o caminho do EXE que foi aberto, em vez de exigir um nome PrefeituraZ fixo. Exemplos aceitos: `Meu jogo.exe`, `Admin - João.exe` e nomes com espaços, acentos e extensão `.EXE` em maiúsculas. O arquivo conserva seu nome depois de atualizar. Continuam obrigatórios assinatura, edição correta (jogador/Admin/servidor), revisão do jogo, versão mais nova, tamanho e SHA-256. O destino precisa ser um EXE existente e não pode ser um link de arquivo/pasta. Uma alteração concorrente do executável é recusada.

## Sem .bak ao lado do launcher

O novo auxiliar não cria `.bak`, `.back` ou `.previous-...` na pasta do aplicativo. Durante a troca, mantém uma cópia temporária em `%LOCALAPPDATA%/PrefeituraZLauncher/updates/recovery/<id>/previous.exe`; o painel usa PrefeituraZServerSetup. Essa cópia é removida depois da confirmação de abertura, ou depois de restaurar a versão anterior se a nova encerrar sem confirmar. Em falha que impeça concluir a recuperação ou remover o arquivo, pode conservar a cópia internamente para diagnóstico; não a move para a Área de Trabalho.

O arquivo de entrada temporário usado pela substituição atômica é criado na mesma pasta do destino e removido ao concluir a troca. O backup interno é copiado separadamente: a Área de Trabalho pode estar em uma unidade diferente da pasta de dados do Windows. A atualização não exige que a cópia de recuperação esteja na mesma unidade do EXE.

## Instalação inicial e versões anteriores

Para receber os dois comportamentos imediatamente, feche o launcher e substitua o EXE pela 0.4.12. Depois disso poderá renomeá-lo à vontade mantendo a extensão `.exe`.

Quem atualizar da 0.4.10/0.4.11 pelo mecanismo antigo poderá receber uma última cópia `.bak`, pois essa primeira troca ainda é feita pelo auxiliar da versão anterior. Essas versões também ainda exigem o nome original antes da troca. A mudança no novo EXE não altera retroativamente o auxiliar antigo. Arquivos `.bak` já existentes não são apagados automaticamente.

O painel 2.1.6 deve ser aplicado durante manutenção, com dedicado, AutoRestart/Watchdog e host Admin parados. Configurações, convites e certificados devem ser preservados. Nenhuma alteração foi aplicada no servidor remoto nesta entrega.

## Validação

Os executáveis finais continuam ofuscados. Foram testados nomes personalizados com espaços e acentos, nome preservado após a troca, ausência de arquivos auxiliares na pasta do launcher e exclusão da cópia interna após sucesso e reversão. Os auxiliares reais das três edições atualizaram e restauraram executáveis de fixture. Os testes de assinatura, adulteração, sequência, revisão do jogo e edição, integridade, contas, áudio, administração/TLS e integração continuaram passando.

O ícone Admin da Prefeitura Z e a ofuscação da 0.4.11 foram mantidos. A senha geral de entrada permanece incorporada conforme autorização do proprietário; não se torna secreta pela ofuscação.
