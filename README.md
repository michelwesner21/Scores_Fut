# Scores_Fut

Relatório Técnico: Desenvolvimento do Aplicativo ScoresFut
1. Introdução
O ScoresFut é um aplicativo mobile desenvolvido para torcedores de futebol que desejam acompanhar os resultados das partidas de seus times favoritos. O aplicativo possui funcionalidades que permitem ao usuário escolher times favoritos, visualizar a tabela de classificação e receber notificações sobre eventos do jogo, como gols e cartões. Este relatório descreve o processo de desenvolvimento, as decisões tomadas e as tecnologias utilizadas para a criação do aplicativo.

2. Objetivos
Objetivo Principal: Permitir que os usuários acompanhem os resultados das partidas de seus times favoritos.
Público-alvo: Homens e mulheres de todas as idades que são apaixonados por futebol.
3. Definição de Requisitos
3.1. Funcionalidades Principais
Escolha de Times Favoritos: O usuário pode selecionar um ou mais times para acompanhar.
Tabela de Classificação: Exibe a posição atual dos times no campeonato, incluindo partidas passadas e futuras.
Notificações Push: Envia alertas de próximos jogos, gols e outros eventos relevantes.
3.2. Requisitos Não-Funcionais
Desempenho: O aplicativo deve carregar as tabelas e resultados de forma rápida.
Acessibilidade: Compatível com ferramentas de acessibilidade, como leitores de tela, para garantir a inclusão.
4. Escolha da Plataforma e Ferramentas
Para a criação do aplicativo, optamos por utilizar Android Studio com Java e Gradle. Embora o Flutter seja uma opção excelente para multiplataforma, decidimos manter o desenvolvimento em Java, uma vez que é uma linguagem amplamente utilizada para Android e possui uma grande variedade de bibliotecas e documentação.

4.1. Tecnologias Utilizadas
Android Studio: IDE utilizada para o desenvolvimento.
Java: Linguagem de programação escolhida para desenvolver a aplicação.
Gradle: Sistema de automação de compilação para gerenciar dependências e compilar o código.
Retrofit: Biblioteca para realizar requisições HTTP e consumir APIs.
Firebase Cloud Messaging (FCM): Utilizado para o envio de notificações push.
5. Processo de Desenvolvimento
5.1. Configuração do Projeto
A criação do projeto foi realizada no Android Studio, configurando uma nova atividade em branco para ser o ponto de partida do aplicativo. Definimos a estrutura inicial do projeto, com pacotes para organizar o código de acordo com a funcionalidade, separando as views, models e network.

5.2. Desenvolvimento das Funcionalidades
Funcionalidade 1: Escolha de Times Favoritos
Modelagem dos Dados: Criamos um modelo Time para representar cada time de futebol, contendo informações como nome e escudo.
Interface do Usuário: A interface foi construída com um RecyclerView, que permite ao usuário visualizar uma lista de times disponíveis.
Integração com API: Através do Retrofit, integramos com uma API de resultados de futebol para carregar os dados dos times e populá-los no RecyclerView. Optamos pelo Retrofit devido à sua simplicidade de uso e facilidade de integração com JSON.
Funcionalidade 2: Tabela de Classificação
Modelagem da Tabela: Criamos o modelo Tabela para representar as informações da tabela de classificação, como time e pontos.
Interface de Exibição: Utilizamos um segundo RecyclerView para exibir a tabela do campeonato, onde cada item da lista exibe o nome do time e sua pontuação atual.
Requisição dos Dados: A tabela de classificação é carregada a partir da mesma API dos times, facilitando a manutenção e garantindo consistência nos dados.
Funcionalidade 3: Notificações Push
Para enviar notificações push sobre eventos de jogos e atualizações, integramos o Firebase Cloud Messaging (FCM). O FCM permite enviar notificações de forma segura e em tempo real. A configuração do Firebase foi feita diretamente no console do Firebase, com a chave de API adicionada ao Android Studio.

5.3. Integração com API
Optamos pelo uso da biblioteca Retrofit para realizar as chamadas HTTP. Essa escolha foi feita pela sua facilidade de uso com JSON e pelo suporte a interceptores, que auxiliam no monitoramento e no tratamento de erros. Abaixo, uma breve descrição da configuração:

Configuração Base: Adicionamos uma classe RetrofitClient para centralizar as configurações do Retrofit e definir a URL base.
EndPoints: Definimos a interface ApiService para listar os endpoints necessários, incluindo a busca de times e da tabela.
Tratamento de Respostas: O Retrofit facilita o tratamento de erros com callbacks simplificados, permitindo um desenvolvimento rápido e eficaz.
5.4. Design e Experiência do Usuário (UX)
Para garantir uma experiência de usuário satisfatória, seguimos alguns princípios de UX, como:

Simplicidade: A interface foi desenhada para ser intuitiva, com botões e navegação clara entre as funcionalidades.
Acessibilidade: As cores e fontes foram escolhidas para garantir visibilidade e legibilidade, além de testar o app com leitores de tela para acessibilidade.
6. Testes e Validação
Testes em Dispositivos Físicos e Emuladores: Realizamos testes no emulador do Android Studio e em dispositivos físicos para validar o desempenho e a responsividade.
Verificação de Funcionalidades: Cada funcionalidade foi testada individualmente, garantindo que a escolha de times favoritos, a tabela de classificação e as notificações funcionem como esperado.
Acessibilidade: Testamos o aplicativo com leitores de tela e ajustamos elementos de interface para assegurar a compatibilidade com ferramentas de acessibilidade.
7. Soluções e Aprendizados
Durante o desenvolvimento, alguns desafios foram enfrentados, como:

Tratamento de Erros na API: Adicionamos um interceptor para capturar erros de rede e apresentar mensagens claras para o usuário.
Gerenciamento de Notificações: A integração com o FCM exigiu ajustes no código para garantir que as notificações fossem entregues com precisão. Aprendemos sobre a configuração de tópicos, que permite segmentar notificações por tipo de evento.
8. Conclusão
O aplicativo ScoresFut foi desenvolvido com sucesso, cumprindo todos os requisitos funcionais e não-funcionais especificados na atividade avaliativa. A experiência foi enriquecedora, destacando a importância de uma boa estruturação do projeto e de ferramentas que facilitam a comunicação com APIs externas. Esse projeto representa um passo importante na criação de aplicativos móveis com foco em UX e acessibilidade.

