Título: OverEngineering

descrição: projeto educacional para aplicação de ensinamentos do dia a dia corporativo

objetivo: Simular sistema de banco, com funções como: sacara, depositar, entre outros. Em primeiro momento será desenvolvido somente através de terminal, através de Java e Maven.
As funções a serem implementadas estão em : [modelagem](modeling/main.readme)

```mermaid
flowchart TB
    %% Direcao Top to Bottom para melhor leitura
    %% (Pode trocar para LR se preferir horizontal)

    %% --- Carregar Dinheiro ---
    subgraph CD[Funcao: Carregar Dinheiro]
        CD1([Inicio]) --> CD2[Autenticar operador]
        CD2 --> CD3{Autorizacao valida?}
        CD3 -- Nao --> CDX[Exibir erro] --> CDF([Fim])
        CD3 -- Sim --> CD4[Selecionar funcao Carregar Dinheiro]
        CD4 --> CD5[Abrir compartimento de cedulas]
        CD5 --> CD6[Inserir valor e quantidade de cedulas]
        CD6 --> CD7{Valores corretos?}
        CD7 -- Nao --> CD8[Solicitar correcao] --> CD6
        CD7 -- Sim --> CD9[Confirmar operacao]
        CD9 --> CD10[Atualizar saldo no sistema]
        CD10 --> CD11[Emitir comprovante]
        CD11 --> CD12[Fechar compartimento e encerrar sessao]
        CD12 --> CDF([Fim])
    end

    %% --- Saque ---
    subgraph SQ[Funcao: Saque]
        SQ1([Inicio]) --> SQ2[Inserir cartao]
        SQ2 --> SQ3[Digitar senha]
        SQ3 --> SQ4{Senha valida?}
        SQ4 -- Nao --> SQX[Exibir erro] --> SQF([Fim])
        SQ4 -- Sim --> SQ5[Selecionar opcao Saque]
        SQ5 --> SQ6[Informar valor desejado]
        SQ6 --> SQ7{Saldo suficiente?}
        SQ7 -- Nao --> SQY[Exibir mensagem saldo insuficiente] --> SQF([Fim])
        SQ7 -- Sim --> SQ8[Dispensar cedulas]
        SQ8 --> SQ9[Atualizar saldo da conta]
        SQ9 --> SQ10[Emitir comprovante]
        SQ10 --> SQF([Fim])
    end

