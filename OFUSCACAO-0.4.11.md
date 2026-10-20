# Prefeitura Z — proteção do código e ícone Admin

Cliente/Admin 0.4.11 e painel do dedicado 2.1.5, Windows/B42.21.

## Alterações

Os quatro executáveis produzidos pelo build passam por Obfuscar 2.2.50, obtido do NuGet oficial com SHA-256 fixado. São renomeados os tipos e métodos da implementação e ocultados textos literais do código. Campos e propriedades usados por JSON, contas, convites, preferências, backups e protocolo Admin conservam seus nomes. A API pequena usada pelo publicador e pelo diagnóstico permanece identificável. Os recursos incorporados são preservados por hash.

O ofuscador funciona somente durante a compilação. O jogador continua recebendo um EXE, sem instalar o ofuscador ou suas DLLs, sem serviço adicional e sem verificações contínuas novas. Mapas de nomes e executáveis sem proteção ficam somente na pasta privada de build. A assinatura das atualizações usa a mesma chave privada protegida no computador publicador.

O launcher Admin recebeu um ícone próprio: brasão Prefeitura Z com placa ADMIN em cobre/vermelho envelhecido. O ICO contém 16, 24, 32, 48, 64, 128 e 256 pixels com transparência e é usado pelo arquivo, janela e bandeja. O ícone dos jogadores foi preservado.

## Validação

As suítes foram executadas sobre os EXEs já ofuscados: conta/DPAPI e áudio, integridade, memória, atualização assinada e reversão, ciclo de janela/bandeja, diagnóstico, Horse, física, visibilidade, correção de salas e testes básicos. No painel: TLS real em loopback, autenticação, convites/revogação, integração, Horse/AutoRestart com JAR em java, layouts e preservação do checksum. Os auxiliares reais de cliente, Admin e painel passaram pelos testes de troca e reversão com executáveis de fixture.

Auditoria: cliente e Admin tiveram 139 tipos e 398 métodos renomeados cada; painel, 141 tipos e 338 métodos. Os 18 recursos do cliente, 19 do Admin e 8 do painel ficaram idênticos aos respectivos builds anteriores à ofuscação. Os ícones nativos sobreviveram à transformação.

Medição local do Admin, cinco aberturas/renderizações após aquecimento: mediana de 421 ms e pico de memória mediano de 77,50 MB antes; 433 ms e 77,66 MB depois. É uma medição de abertura da interface nesta máquina, não um teste de FPS ou de uma sessão com todo o modpack.

## Instalação e atualização

Quem já usa 0.4.10 recebe 0.4.11 pelo canal assinado ao abrir ou antes de Jogar. Quem usa uma geração anterior sem atualizador precisa substituir o EXE uma vez. No dedicado, faça a primeira instalação do painel 2.1.5 com servidor, AutoRestart/Watchdog e host Admin parados, preservando configurações, certificados e convites. Nenhuma alteração foi aplicada no dedicado remoto nesta entrega.

O resolvedor de projectzomboid.jar na raiz ou em java, o hash B42.21, a preservação de DoLuaChecksum, a política de memória, o atualizador do PZ_Optimization e as permissões Admin foram conservados.

## Limites

Ofuscação dificulta análise e modificação; não impede copiar o EXE ou recuperar a lógica. Não protege como segredo a senha geral incorporada por autorização do proprietário. Recursos Lua/Java e conteúdo de terceiros continuam extraíveis. A versão anterior já distribuída não recebe proteção retroativa. A chave privada de atualização, credenciais administrativas e mapas de nomes não são publicados.

Referências: [Obfuscar 2.2.50 no NuGet](https://www.nuget.org/packages/Obfuscar/2.2.50), [configuração e limites do autor](https://docs.lextudio.com/obfuscar/getting-started/configuration).
