Título: OverEngineering

descrição: projeto educacional para aplicação de ensinamentos do dia a dia corporativo

objetivo: Simular sistema de banco, com funções como: sacara, depositar, entre outros. Em primeiro momento será desenvolvido somente através de terminal, através de Java e Maven.

DIAGRAMA(PlantUML):
```mermaid
sequenceDiagram
    participant Cliente
    participant Caixa
    Cliente->>Caixa: Inserir cartão
    Caixa-->>Cliente: Solicitar senha
