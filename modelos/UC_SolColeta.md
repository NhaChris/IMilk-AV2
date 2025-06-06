## Caso de Uso: Solicitar Coleta de Leite Disponível

### 1. Nome
Solicitar Coleta de Leite Disponível

### 2. Atores Envolvidos
- Instituição (principal)
- Agente Logístico (secundário, notificado)
- Doadora (secundário, notificado)

### 3. Descrição
Este caso de uso descreve o processo em que uma instituição solicita, por meio do sistema, a coleta de leite humano previamente informado como disponível por uma doadora. O pedido é enviado para um agente logístico vinculado à instituição.

### 4. Pré-condições
- A instituição deve estar cadastrada e autenticada no sistema.
- Deve existir leite disponível registrado por doadoras.
- Deve haver pelo menos um agente logístico vinculado à instituição.

### 5. Fluxo Principal de Eventos
1. A instituição acessa o sistema e navega até a área de "Solicitações de Coleta".
2. O sistema exibe uma lista de doações disponíveis.
3. A instituição seleciona uma ou mais doações para coleta.
4. A instituição confirma a solicitação.
5. O sistema registra a solicitação e notifica o agente logístico responsável.

### 6. Fluxos Alternativos
- **A6.1**: Se não houver agentes logísticos disponíveis, o sistema exibe uma mensagem de erro e a solicitação não é concluída.
- **A6.2**: Caso os dados da doadora estejam desatualizados, o sistema solicita verificação antes da solicitação.

### 7. Pós-condições
- A solicitação de coleta fica registrada e visível para o agente logístico.
- A doação selecionada é marcada como "aguardando coleta".
- A doadora é notificada para se preparar para a coleta

### 8. Regras de Negócio
- Uma coleta só pode ser solicitada se o volume mínimo para transporte for atingido.
- A doação não pode estar marcada como "em avaliação" ou "em rota".

---

## 🎯 Diagrama de Caso de Uso

```plantuml
@startuml
actor "Instituição" as I
actor "Agente Logístico" as A
actor "Doadora" as D

usecase "Visualizar doações disponíveis" as UC1
usecase "Selecionar doações para coleta" as UC2
usecase "Confirmar solicitação de coleta" as UC3
usecase "Notificar agente logístico" as UC4
usecase "Notificar doadora" as UC5

I --> UC1
I --> UC2
I --> UC3
UC3 --> UC4 : <<include>>
UC3 --> UC5 : <<include>>
UC4 --> A
UC5 --> D

@enduml
