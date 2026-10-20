# Atualização automática — launcher 0.4.10 / painel 2.1.4

Repositório escolhido pelo usuário: https://github.com/Sirrakx/PrefeituraZ-Launcher.

## Correções incorporadas no fonte

GameLayout.Jar procura primeiro `projectzomboid.jar` na raiz e depois `java/projectzomboid.jar`. O hash B42.21 continua obrigatório. O resolvedor é compartilhado pelo seletor do dedicado, validação de versão, registro/restauração de backups, ferramentas Java incorporadas, login, física, Horse e diagnóstico. Não duplica o JAR. Um JAR presente porém incorreto na raiz não é ocultado pelo arquivo em java.

ServerProtection.Values deixou de impor somente DoLuaChecksum. False, true, ausência e linha comentada são preservados nos dois perfis. SteamVAC e os outros pares permanecem iguais. TLS, autenticação, convites e revogação continuam com a implementação existente. No dedicado remoto nenhuma opção foi aplicada nesta rodada.

## Experiência do jogador

A primeira instalação desta geração é manual: os EXEs antigos não continham um atualizador. Depois de instalar a 0.4.10, o jogador mantém o mesmo atalho. O launcher verifica sozinho ao abrir e novamente antes de Jogar. Se houver uma versão nova para sua edição e revisão do jogo, baixa, verifica assinatura RSA/SHA-256 e tamanho, guarda o EXE anterior, troca e reabre. O jogo não é iniciado durante a troca. Não precisa clicar em Verificar atualização.

O endereço está incorporado:

`https://github.com/Sirrakx/PrefeituraZ-Launcher/releases/download/channel-stable/updates.json`

A publicação desse canal é necessária para ativar o serviço real. Enquanto não existir ou estiver indisponível, a aplicação informa e mantém a versão instalada. Um manifesto sem assinatura válida, expirado ou com sequência regressiva é recusado. Um arquivo novo com hash/tamanho divergente não substitui o instalado. O download aceita somente HTTPS, inclusive nos redirecionamentos.

A nova aplicação confirma que abriu a interface. Se o processo novo encerrar sem confirmar, o auxiliar restaura o EXE anterior e o reabre. Se continuar aberto sem confirmação, preserva o backup e escreve update-error.txt, sem matar o processo. Os testes de substituição usam executáveis de fixture; não substituíram um launcher de produção.

O painel 2.1.4 também verifica ao abrir, mas adia a troca enquanto dedicado, AutoRestart/Watchdog, hosts do painel ou acesso Admin estiverem ativos. Use manutenção e desative o host Admin antes de atualizar o painel. Não interrompe um dedicado para atualizar.

## PZ_Optimization

Antes de preparar o jogo, se o recurso estiver habilitado, consulta a release mais recente no repositório oficial do autor. Seleciona somente a revisão B42.21/4a0e9546ec, uma release normal e o ZIP oficial, com SHA-256 informado pelo GitHub ou inequivocamente pelo texto da release. Baixa automaticamente uma versão diferente da instalada para validação.

Antes de gravar, compara as classes utilizadas por Horse, física, visibilidade, correção de salas e reconstrução de regiões com as variantes suportadas nesta geração. Se forem compatíveis, instala com backup, remove arquivos que o autor retirou (também com backup), reaplica a correção de salas e retira o cache AOT antigo do próximo início. As novas classes entram na conferência de integridade. O estado é protegido com DPAPI e o pacote de origem volta a ser conferido por hash. O backup fica em `%LOCALAPPDATA%/PrefeituraZLauncher/optimizer-backups`.

Se a atualização mudar uma classe que ainda não sabemos combinar, não a força: mantém a versão instalada e registra o motivo. Para essa versão passar, precisamos adaptar a integração e publicar um novo launcher. Isso evita substituir silenciosamente uma correção por outra. O SHA-256 comprova origem/integridade do pacote consultado, não ausência de bugs: não existe garantia de estabilidade de uma atualização de terceiro apenas por ela ser recente.

Não executa install.ps1, shell ou instalador remoto. Os scripts incluídos no pacote do autor podem ser gravados como parte de seu conteúdo, mas o launcher instala os arquivos por seu próprio mecanismo de transação. O PZ_Optimization não é instalado no dedicado. Na verificação desta rodada, a release mais recente continuava sendo d1bbdcf, já integrada.

Fontes do autor: [release consultada](https://github.com/xD3I/PZ_Optimization/releases/tag/b42.21-20261019-0042-d1bbdcf) e [limitações](https://github.com/xD3I/PZ_Optimization/blob/master/docs/guide/limitations.md). O autor limita as classes a uma revisão exata e informa restrições de multiplayer/combinação de mods.

## Publicação inicial pelo dono

1. Na pasta de publicação, confira os arquivos. O proprietário autorizou expressamente a publicação dos EXEs com a senha geral de entrada incorporada em 20/10/2026. Essa senha é extraível do recurso de conexão; a autorização não inclui credenciais administrativas. Senha RCON, convites, certificados, contas e a chave privada não devem ser enviados.
2. Faça um commit inicial com somente README público no repositório vazio, para existir uma branch de destino.
3. Crie a release de arquivos `v0.4.10-b42-2.1.4`. Anexe `PrefeituraZ-Launcher.exe`, `PrefeituraZ-Admin.exe`, `PrefeituraZ-Servidor.exe` e o ZIP de instalação do painel. O painel dentro do ZIP usa o nome original PrefeituraZ-Launcher.exe.
4. Gere o manifesto com New-UpdateManifest.ps1 (instrução abaixo) depois de congelar os três executáveis. Não recompile depois de assinar sem gerar o manifesto novamente.
5. Crie a release `channel-stable` e anexe o arquivo assinado com o nome exato `updates.json`. Publique o canal por último, após os arquivos estarem acessíveis. O endereço fixo do launcher passa a resolver.
6. Faça uma abertura de teste do cliente atualizado e um teste de download/troca com uma versão de homologação antes de distribuir a todos.

## Próximas versões

Compile/teste os três executáveis. Crie uma nova release com tag própria, envie os arquivos, gere um manifesto com sequência crescente e atualize o asset updates.json de channel-stable por último. As URLs dos executáveis são da release específica, não /latest, para o manifesto apontar sempre para os bytes assinados. O arquivo possui validade de 60 dias; renovar o canal mesmo se não houver nova versão antes de expirar. Canal expirado não força a execução de arquivo novo nem remove o instalado.

Exemplo no computador publicador, com Windows PowerShell:

```powershell
& '.\tools\New-UpdateManifest.ps1' -Player 'C:\Entrega\PrefeituraZ-Launcher.exe' -Admin 'C:\Entrega\PrefeituraZ-Admin.exe' -Server 'C:\Entrega\PrefeituraZ-Servidor.exe' -ReleaseTag 'v0.4.10-b42-2.1.4' -Output 'C:\Entrega\updates.json'
```

O script confirma a edição e versão de cada EXE, calcula hashes/tamanhos e assina. O número de sequência padrão é o horário UTC em segundos; não reutilize sequência menor. Initialize-UpdateSigning.ps1 prepara a chave uma única vez e recusa sobrescrever uma chave pública existente sem a privada correspondente.

A chave privada está protegida com DPAPI do usuário Windows, em `%LOCALAPPDATA%/PrefeituraZPublisher/signing-key.bin`. Ela não está nos executáveis nem no repositório. Preserve um backup protegido dessa chave e do perfil Windows: perdê-la pode exigir distribuir outro bootstrap. Não exporte a chave privada para a pasta pública. Os EXEs incorporam somente a chave pública. Não foi criado token GitHub ou nova credencial de acesso ao repositório.

## Evidências locais e limites

- Testes de assinatura, chave incorreta, validade, HTTPS, sequência, hash, concorrência, versão/revisão e reversão passaram.
- O auxiliar real substituiu e iniciou uma fixture assinada; também reverteu ao executável anterior quando outra fixture encerrou sem confirmação.
- O pacote real d1bbdcf passou as barreiras de compatibilidade e foi aplicado integralmente numa fixture, com retirada de arquivo obsoleto, preservação da correção de salas e reversão completa.
- Layout java, registro/restauração de backup e preservação de DoLuaChecksum foram testados. A suíte Horse/AutoRestart passou também com JAR em java.
- Regressões de conta/áudio, integridade, integração e Horse passaram sem alterar o jogo/dedicado de produção.

Publicado e verificado em 20/10/2026: release v0.4.10-b42-2.1.4 e canal channel-stable. Os quatro downloads públicos conferiram por SHA-256; cliente, Admin e painel consultaram o endpoint real, aceitaram assinatura/sequência e confirmaram a versão atual em estado isolado. A troca de versão e a reversão foram testadas com executáveis de fixture. Não foi aplicada alteração no servidor remoto. A estabilidade em partida de uma futura versão de terceiro não pode ser certificada antes de ela existir; classes incompatíveis serão adiadas. Som/HP do Horse e sessão completa em PC de 8 GB mantêm as pendências de homologação anteriores.
