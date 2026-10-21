# Prefeitura Z — painel do dedicado 2.1.7

A nova aba **Contas do jogo** permite consultar o cargo de uma conta existente, torná-la Admin e redefinir sua senha, inclusive da conta `admin`. Não precisa informar a senha anterior. O jogador precisa ter entrado nesse servidor uma vez para a conta existir.

## Como usar

1. Confira em **Integração** a pasta Zomboid usada pelo dedicado. Ela deve conter o perfil e o banco de contas desse servidor.
2. Com o servidor online e respondendo ao painel, abra **Contas do jogo**, informe o nome exato de login e clique em **Consultar conta**.
3. Use **Tornar Admin** para conceder o cargo. Para trocar a senha, preencha e confirme a nova senha e clique em **Redefinir senha**. Cada alteração pede confirmação indicando conta e perfil.

Reconecte a conta promovida para conferir as ferramentas administrativas. Depois de redefinir uma senha, atualize o login salvo em **Conta e áudio** no launcher dessa conta. Jogador e Admin continuam guardando logins separados.

A tela administra permissões dentro do jogo. Convites TLS para iniciar, parar e reiniciar o dedicado continuam na aba **Proteção e admins** e não concedem permissão para modificar contas por acesso remoto.

## Funcionamento e proteção

As alterações usam os comandos nativos `setaccesslevel` e `setpassword`, enviados ao RCON local. Uma consulta SQLite somente para leitura confere a existência da conta antes da ação e a persistência do resultado depois. Uma resposta textual positiva, sozinha, não informa sucesso: a B42 pode responder à troca de senha mesmo quando a conta não existe.

O helper usa o Java e o JDBC da instalação B42.21 validada, procura o JAR na raiz ou em `java` e consulta somente o perfil selecionado. Não há consulta periódica de contas: ela roda ao usar os controles. O painel não escreve diretamente no banco. Senhas ficam mascaradas, não são passadas pela linha de comando do Java nem gravadas pelo painel; respostas com o verificador de senha são descartadas e ocultadas dos consoles. A auditoria registra a ação e o usuário, sem a senha.

Se os scripts conhecidos de inicialização impuserem `-adminpassword`, a redefinição de `admin` será bloqueada com orientação para revisar essa configuração. Isso evita que a senha anterior volte no próximo início. O painel não altera esses scripts por conta própria.

São preservados AutoRestart, Watchdog, convites, certificados, configurações, checksum existente e integrações. Os launchers Jogador e Admin permanecem **0.4.14 com os mesmos bytes**; o addon Horse permanece 0.1.2.

## Instalação

Para atualizar o painel automaticamente, mantenha o dedicado parado em manutenção e encerre seus auxiliares, incluindo o host de acesso remoto. Abra o painel: o canal assinado oferece a 2.1.7 quando não há componentes ativos.

Para atualizar manualmente, com dedicado e auxiliares parados e painel fechado, extraia o ZIP **PrefeituraZ-Servidor-2.1.7-Windows.zip** na pasta do dedicado, substituindo os arquivos do painel e bridge. Preserve as pastas e configurações existentes. Nenhuma conta é promovida ou tem sua senha alterada só por instalar a atualização.

## Validação

As suítes do executável final incluem comandos, injeção, RCON real em loopback, autenticação recusada, conta ausente, confirmação em banco SQLite descartável, campos mascarados e bloqueio de ações duplicadas. Também foram exercitados os métodos nativos da B42 em outro banco isolado: parser, senha criptografada, separação por mundo, persistência do cargo e logs sem credenciais.

Os testes não alteram contas do servidor remoto, não iniciam uma partida e não substituem a conferência operacional após instalar nessa máquina.
