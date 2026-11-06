# Prefeitura Z 0.4.28 — atualização automática do PZO

A versão 0.4.27 interrompia a preparação quando a Steam atualizava o Lua do PZO: os arquivos deixavam de corresponder ao manifesto fixo 1.8.1. A 0.4.28 acompanha o item oficial do Workshop e a release estável oficial do motor, sem exigir recompilar o launcher para cada atualização compatível do PZO.

## Funcionamento

Com o jogo fechado e a Steam aberta, use **Aplicar perfil agora** ou **Jogar**. A preparação sincroniza o Workshop `3787481250` / mod `MPOptimizer`, consulta a release estável de `prop11/PZO-Launcher`, baixa JAR/DLL quando necessário e confere origem, tamanho e SHA-256 publicado pelo GitHub. A consulta à release tem cache de cinco minutos. Mudanças Lua são acompanhadas mesmo quando o autor mantém o número de versão.

O pacote completo é aplicado com backup: motor, DLL, Lua e registro de integridade. A memória escolhida e a pasta de dados são preservadas. A ponte PRZ mantém os argumentos de inicialização sob controle do launcher, enquanto a atualização do PZO passa a ser conduzida pela preparação automática.

Uma inspeção de bytecode confere a API usada pela ponte sem executar as classes do pacote durante essa inspeção. Se a consulta, download ou compatibilidade dessa API falhar, o launcher tenta manter o último pacote completo guardado localmente. Há também um Lua de recuperação incluído; a primeira instalação do motor ainda exige download ou cache disponível. Uma instalação interrompida usa a recuperação transacional existente.

## Atualização do próprio launcher

Jogador e Admin agora têm o endereço do canal assinado incorporado. Na 0.4.28, a ausência de `PrefeituraZ-Updates.json` não desativa a consulta. O Controle continua com seu canal exclusivo. Um arquivo externo que desative explicitamente o canal continua sendo respeitado.

Quem já está em uma versão antiga com canal desativado ou ausente precisa instalar o ZIP completo uma vez. Publicar uma release não permite alcançar remotamente um EXE antigo que não consulta atualizações.

## Validação e limites

A entrega usa como recuperação PZO Java/DLL/Lua 1.8.2. A validação cobre atualização futura simulada sem recompilar o launcher, Lua alterado sem mudar a versão, remoção de arquivos obsoletos, rollback, metadados inválidos, origem de download, proteção dos hashes, cache corrompido e recuperação offline com componentes já disponíveis.

Os executáveis finais passaram em três rodadas nas três edições: 51 suítes e 993 verificações numeradas. A cópia isolada migrou de Java/Lua 1.8.1 para 1.8.2, confirmou o agente ativo e abriu o save Solo. O teste gráfico foi feito pela edição Jogador; Admin/Controle receberam a validação automatizada. A voz foi desativada somente na cópia de teste por causa do bloqueio FMOD já diagnosticado neste PC; esse ajuste não é distribuído.

As verificações de integridade não são uma homologação prévia de toda versão futura publicada pelo autor. O canal acompanha versões estáveis oficiais; betas são excluídos. Uma mudança incompatível na API da ponte pode exigir uma nova versão do launcher, enquanto o pacote anterior é mantido. A estabilidade do modpack multiplayer inteiro permanece uma verificação adicional no servidor.

O painel do dedicado permanece 2.1.8. A limpeza dos componentes ativos conhecidos do PZOpt continua restrita à instalação selecionada, pasta de dados e caches conhecidos, com backup e preservação de saves e outros mods.

Créditos: [PZO / prop11](https://github.com/prop11/PZO-Launcher), [Workshop MPOptimizer](https://steamcommunity.com/sharedfiles/filedetails/?id=3787481250).
