# UniMove

O **UniMove** é um projeto de um aplicativo de transporte voluntário de universitário para universitário, trazendo preços mais acessiveis para pessoas que tenham necessidade de deslocamento para universidades e faculdades. A ideia é fazer com que pessoas que já vão de carro para faculdade, se volutanriem para levar outros alunos, e ainda ganhar uma pequeno renda extra.


## Objetivo do Projeto

O objetivo do projeto é aplicar conceitos de desenvolvimento de aplicativos e organização de projetos, criando um aplicativo de transporte para alunos de faculdades e universidades.

Durante o desenvolvimento foram utilizados conceitos como:

* Criação de um aplicativo
* Sistema de Login e cadastro
* Organização de corridas 
* Busca de voluntários que já vão de carro para a instituição de ensino
* Controle de versão com GitHub
* Organização de tarefas com Kanban

## Tecnologias Utilizadas

* HTML5
* CSS3
* PHP
* MySQL
* Git
* GitHub
* Python

## Funcionalidades do Sistema

* Cadastro de usuários
* Login de usuários
* Possibilidade de combinar corridas
* Possibilidade de se cadastrar como motorista
* 
* Adição de produtos ao carrinho

## Metodologia

O projeto utiliza princípios de **metodologia ágil**, organizando o desenvolvimento através de:

* Histórias de usuário
* Kanban
* Organização de tarefas no GitHub Projects

## Nomes
* Alice Rocha 
* Felipe Maduro
* Igor Santos 
* Jean Guilherme 
* Luiz Pedro
* Pedro Cano
* Samuel Celli
* Theodoro Portapilla

## Diagrama

```mermaid

sequenceDiagram
    participant U as Usuário
    participant APP as App UniMove
    participant API as Backend
    participant DB as Banco de Dados
    participant M as Motorista

    %% Cadastro e Login
    U->>APP: Cadastro de novos usuários
    APP->>API: Envia dados
    API->>DB: Salva usuário
    DB-->>API: OK
    API-->>APP: Cadastro concluído

    U->>APP: Login no sistema
    APP->>API: Envia credenciais
    API->>DB: Valida login
    DB-->>API: OK
    API-->>APP: Acesso liberado

    %% Cadastro como motorista
    U->>APP: Solicitar cadastro como motorista
    APP->>API: Envia dados (CNH, veículo, etc.)
    API->>DB: Salva dados do motorista
    DB-->>API: OK
    API-->>APP: Cadastro como motorista aprovado
    APP-->>U: Usuário agora é motorista

    %% Definição de trajeto
    U->>APP: Definir origem e destino
    APP->>API: Envia localização
    API->>DB: Consulta rotas
    DB-->>API: Dados de rota
    API-->>APP: Exibe trajeto

    U->>APP: Estimar tempo da carona
    APP->>API: Solicita estimativa
    API-->>APP: Tempo estimado

    %% Buscar e solicitar corrida
    U->>APP: Buscar corrida
    APP->>API: Solicita motoristas
    API->>DB: Busca motoristas disponíveis
    DB-->>API: Lista
    API-->>APP: Exibe opções

    U->>APP: Solicitar carona
    APP->>API: Envia solicitação
    API-->>M: Notificação de corrida

    %% Aceite
    M->>API: Aceitar/Rejeitar solicitação
    API-->>APP: Atualiza status

    %% Chat
    U->>APP: Enviar mensagem
    APP->>API: Encaminha mensagem
    API-->>M: Recebe mensagem
    M->>API: Responde mensagem
    API-->>APP: Exibe resposta

    %% Pagamento
    U->>APP: Escolher pagamento
    APP->>API: Processar pagamento
    API->>DB: Registrar pagamento
    DB-->>API: Confirmação
    API-->>APP: Corrida confirmada

    %% Início da corrida
    M->>API: Iniciar corrida
    API-->>APP: Notifica início

    %% Durante corrida
    API-->>APP: Atualização de trajeto em tempo real
    APP-->>U: Visualizar rota

    %% Cancelamento (alternativo)
    U->>APP: Cancelar corrida
    APP->>API: Solicita cancelamento
    API-->>M: Notifica cancelamento

    %% Finalização
    M->>API: Finalizar corrida
    API-->>APP: Corrida encerrada

    %% Avaliação
    U->>APP: Avaliar motorista
    APP->>API: Envia avaliação
    API->>DB: Salva avaliação

    %% Histórico
    U->>APP: Visualizar histórico
    APP->>API: Solicita dados
    API->>DB: Busca histórico
    DB-->>API: Retorna dados
    API-->>APP: Exibe corridas

    %% Notificações
    API-->>APP: Envia notificações (status, mensagens, corrida)
