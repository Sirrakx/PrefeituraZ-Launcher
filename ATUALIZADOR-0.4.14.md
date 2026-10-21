# Prefeitura Z — correção de inicialização 0.4.14

## Jogo encerrava e o launcher voltava

O jogo iniciava o Java, mas o PZ_Optimization confundia o JAR das classes integradas do cavalo com o JAR original do Project Zomboid ao verificar `IsoAnimal`. Isso ativava o reparo de instalação do otimizador e encerrava o processo antes de abrir a janela. Nesta máquina, a tentativa de reinício pelo PowerShell também era recusada pelo Windows.

Os pacotes de classes verificados do Horse, da física e da visibilidade agora seguem a convenção `pzopt.jar` em subpastas identificadas pelo conteúdo. Essa é a convenção usada pelo verificador do otimizador para distinguir pacotes de override do JAR base. A precedência das classes, os hashes esperados, as listas de arquivos e a validação do JAR original continuam ativos. Nenhum código do otimizador, hash da classe original ou regra do Windows foi desativado.

A compatibilidade das próximas versões automáticas do otimizador também confere a implementação desse verificador. Se ela mudar, a atualização é adiada para revisão, preservando a versão instalada. Um novo teste Java usa o classpath completo com cavalo, física e visibilidade para verificar a origem dos recursos que o otimizador considera originais.

O launcher também informa quando o processo do jogo encerra em menos de 15 segundos, com o código de saída, e orienta a gerar o diagnóstico em Suporte. Isso evita tratar uma falha precoce silenciosa como uma partida concluída.

## Atualização

Jogador e Admin atualizam para a **0.4.14** pelo canal assinado. Para instalar manualmente, feche o launcher e substitua o EXE correspondente. Contas continuam separadas por edição, convites e preferências são preservados, nomes personalizados continuam aceitos e não é criado `.bak` ao lado do aplicativo.

O painel permanece na **2.1.6** com os mesmos bytes. Não é necessário atualizar o dedicado por esta correção dos clientes.

## Aviso do Windows ao executar um BAT no servidor

Um aviso de segurança do Windows sobre um BAT baixado é diferente do conflito de classes acima. Não foram alteradas políticas do Windows nem aprovados avisos automaticamente. Confira o arquivo indicado e a origem do pacote na máquina do dedicado; um aviso persistente requer essa conferência no servidor remoto. Não houve acesso ou mudança no dedicado nesta entrega.

## Validação

Além das suítes dos EXEs finais ofuscados, foi reproduzida a falha da 0.4.13 e conferida a abertura real do jogo corrigido até o menu, com PZ_Optimization ativo e os pacotes integrados no classpath. Os resultados detalham quais testes foram feitos sem conexão ao dedicado; a abertura do menu não representa teste de uma partida multiplayer completa.
