# Prefeitura Z — perfis de desempenho e memória 0.4.16

Jogador e Admin agora oferecem três perfis em **Ajustes → Perfil de desempenho**:

- **PZ_Optimization**: mantém configuração automática e busca versões compatíveis no repositório oficial do autor antes de jogar.
- **Tempo + Every Texture Optimized**: baixa os itens oficiais pela Steam, prepara o Java do Tempo 1.2.1 para B42.21 e instala as texturas **Well Balanced** do ETO. Os arquivos são conferidos por SHA-256. Uma mudança não reconhecida no pacote exige nova validação.
- **Sem otimizador adicional**: remove os componentes reconhecidos do PZ_Optimization e não inclui o Java do Tempo no próximo processo. Horse, física e correções de visibilidade continuam independentes.

Escolha um perfil e use **Aplicar perfil agora**, com Steam aberta e jogo fechado, ou clique em **Jogar**. **Salvar ajustes** guarda a escolha para a próxima preparação; sozinho, não instala nem remove arquivos.

Ao sair do PZ_Optimization, o launcher remove suas classes e scripts aprovados, sua correção exclusiva de salas e os caches AOT conhecidos. Também retira seus argumentos Java e suas preferências gerenciadas. Não se limita a gravar `enabled=false`. Backups de recuperação e pacotes de download inativos podem permanecer nas pastas de suporte; eles não são carregados no jogo. Arquivos alterados ou desconhecidos interrompem a troca e são preservados.

As texturas são aplicadas somente no cliente, com registro dos originais. Ao sair desse perfil, os originais são restaurados e arquivos antes ausentes são removidos. Alterações posteriores não são sobrescritas automaticamente. O ETO não é adicionado à lista do servidor nem ativado simultaneamente em duas variantes.

## Memória independente do otimizador

Em **Ajustes → Memória do jogo**, escolha **Automática** ou **3, 4, 6, 8, 10 ou 12 GB**. A opção funciona nos três perfis, inclusive sem otimizador adicional. O limite manual é conferido contra a RAM física e livre antes de iniciar. Se faltar folga, a preparação pede para reduzir o limite, selecionar Automática ou fechar outros aplicativos.

Em um PC de 8 GB com RAM livre suficiente, a seleção automática chega a 4 GB de Java. O valor pode diminuir se a memória disponível estiver menor. Esse limite não inclui toda a memória nativa, texturas, Windows e outros aplicativos. Não representa garantia de desempenho de todo o modpack em qualquer PC.

## Tempo no multiplayer

O Tempo realiza suas otimizações no cliente. O Lua precisa ser carregado pela lista de mods enviada pelo servidor; a parte Java é opcional por jogador e não deve ser instalada no dedicado.

1. Atualize os launchers dos jogadores e administradores para **0.4.16** antes de incluir Tempo no servidor. Versões antigas não controlam as opções individuais do Tempo.
2. Instale o painel **2.1.8** no computador do dedicado, mantendo configurações, bridge, convites e certificados.
3. Com dedicado, AutoRestart e supervisão parados, abra **Integração**, confira as pastas e clique em **Preparar Tempo no multiplayer**.
4. O painel acrescenta apenas `Tempo_PerfKit` em `Mods` e `3736629791` em `WorkshopItems`, com backup. Inicie pelo painel normalmente e aguarde os downloads da Steam.
5. Cada jogador escolhe seu perfil no launcher. Nos demais perfis, as opções funcionais do Tempo são desativadas; sua página de opções pode continuar aparecendo por ele pertencer à lista do servidor.

O launcher conserva o limite original de 510 zumbis 3D e 20 animações com blending, e deixa cache de tooltip, relatórios contínuos e atribuição de desempenho desligados. Não promete aumento fixo de FPS.

## Preservação e validação

Continuam a atualização com nome personalizado, ausência de `.bak` ao lado do EXE, contas separadas entre Jogador e Admin, proteção local e verificação de assinatura dos downloads. Nenhuma regra de autenticação ou privilégio Admin foi flexibilizada.

Foram concluídas 535 verificações: 240 do Jogador, 95 do Admin, 156 do painel, 32 dos novos perfis e memória e 12 da preparação do Tempo no INI. O teste dos perfis instalou e restaurou 6.140 texturas em cópia isolada, simulou falha e edição posterior e verificou o carregamento das classes Tempo junto com Horse, física e visibilidade na JVM real com `-Xverify:all`.

Não foi feita alteração no dedicado remoto. A homologação em partida com o modpack completo, inclusive no computador do outro administrador e em hardware de 8 GB, continua necessária.

Créditos e distribuição oficial: [PZ_Optimization / xD3I](https://github.com/xD3I/PZ_Optimization), [Tempo / Vyper](https://steamcommunity.com/workshop/filedetails/?id=3736629791), [Every Texture Optimized / maceleet](https://steamcommunity.com/sharedfiles/filedetails/?id=3119788162). Os mods são baixados de suas origens; este pacote não redistribui as texturas do ETO.
