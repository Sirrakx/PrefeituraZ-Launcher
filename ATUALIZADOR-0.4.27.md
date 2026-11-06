# Prefeitura Z 0.4.27 — migração para PZO

As edições Jogador, Admin e Controle usam Project Zomboid Optimizer (PZO) 1.8.1, de prop11, na revisão B42.21 conferida pelo launcher. O JAR, a DLL e os arquivos Lua são conferidos por SHA-256. Atualizações upstream são fixadas até uma nova validação do launcher.

## Instalar e limpar o PZOpt

Com o jogo fechado e a Steam aberta, atualize o launcher e selecione PZO nos ajustes. Use **Aplicar perfil agora** ou **Jogar**, e aguarde a preparação terminar. A memória escolhida e as integrações existentes são preservadas.

A preparação retira os componentes ativos conhecidos do PZOpt da instalação selecionada, configurações antigas, argumentos Java e caches conhecidos do launcher. Os arquivos retirados ficam em backup de recuperação e não são carregados pelo jogo. Saves e outros mods são preservados. Arquivos compartilhados com alterações desconhecidas interrompem a migração para diagnóstico.

O alcance é a instalação e a pasta de dados usadas pelo launcher, além do cache conhecido. Não é uma busca por cópias em todos os discos, outros usuários Windows ou outras instalações. Cada jogador precisa executar a nova versão e concluir a preparação para que a limpeza aconteça.

## Atualização automática e edições

Jogador/Admin usam `channel-stable/updates.json`; mantenha `PrefeituraZ-Updates.json` ao lado do EXE. Se seu sidecar antigo tiver `manifestUrl` vazio, substitua-o pelo arquivo desta release uma vez. O Controle usa `updates-controle.json` em seu canal fixo para continuar recebendo a edição Controle.

O painel do dedicado permanece 2.1.8. O lado Lua `MPOptimizer`/Workshop 3787481250 precisa estar na lista de mods do servidor para ser ativado em uma sessão multiplayer. Esta entrega não modifica a configuração remota do servidor.

## Validação e limites

Três rodadas nas três edições: 51 suítes e 858 verificações numeradas, incluindo remoção, rollback com falha injetada, reaplicação, integridade, limites de memória, caminhos com espaços, atualizador assinado e navegação do Controle. A ponte própria preserva a pasta de dados e impede que o PZO reescreva os argumentos gerenciados ou instale versões externas sem validação. Os arquivos oficiais JAR/DLL são mantidos intactos.

Um ensaio gráfico pela edição Jogador abriu uma partida Solo isolada e confirmou PZO Java/Lua, Horse e PrefeituraZHorse carregados, com movimento e renderização. Admin/Controle passaram nos testes automatizados, sem uma sessão gráfica independente de cada edição. O ensaio neste PC exigiu desativar a voz apenas na cópia de teste devido a um bloqueio FMOD de microfone; essa alteração não é distribuída.

Conexão ao servidor, estabilidade prolongada do modpack multiplayer e benchmark comparativo não fazem parte dessa evidência.

Créditos: [PZO / prop11](https://github.com/prop11/PZO-Launcher), [Workshop MPOptimizer](https://steamcommunity.com/sharedfiles/filedetails/?id=3787481250).
