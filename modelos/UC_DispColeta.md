# 📄 Caso de Uso: Disponibilização para Coleta de Leite Materno

---

## 🎯 Descrição
Este caso de uso descreve o fluxo pelo qual uma usuária com perfil de doadora informa que possui leite materno disponível para coleta. O sistema registra a quantidade, a localização da doadora e a disponibilidade para facilitar o agendamento com instituições parceiras (ex: bancos de leite ou hospitais).

---

## 👥 Atores
- **Doadora autenticada:** mulher previamente cadastrada e aprovada para doação.
- **Sistema:** aplicativo de doação de leite materno.
- **Instituição coletora:** hospital, banco de leite ou agente logístico vinculado à plataforma.

---

## 🎬 Pré-condições
- A doadora está autenticada na plataforma.
- A doadora foi previamente aprovada para doações (verificação de saúde).
- A doadora possui leite armazenado e adequado para doação.

---

## 🔁 Fluxo Principal
1. A doadora acessa a área logada do aplicativo.
2. Seleciona a opção **"Oferecer leite para coleta"**.
3. Preenche o formulário com as seguintes informações:
   - Quantidade disponível (em ml)
   - Data da coleta/extração
   - Condições de armazenamento (refrigerado ou congelado)
   - Horários disponíveis para coleta
4. Confirma os dados e envia a solicitação.
5. O sistema registra a solicitação e:
   - Associa à localização da doadora
   - Notifica as instituições coletoras parceiras mais próximas
6. A instituição interessada entra em contato ou agenda coleta automaticamente, se disponível.
7. A doadora recebe notificação com os detalhes do agendamento (data, hora, instituição, contato).

---

## 🔁 Fluxos Alternativos

- **3A. Dados incompletos ou inválidos:**  
  O sistema exibe mensagem de erro e impede envio até correção dos dados.

- **6A. Nenhuma instituição disponível:**  
  O sistema informa que a solicitação foi registrada e aguarda disponibilidade de coleta. A doadora será notificada assim que possível.

---

## ✅ Pós-condições
- A solicitação de coleta está registrada.
- A doadora foi notificada do agendamento ou que a solicitação está pendente.
- A instituição coletora foi informada da nova doação disponível.

---

## 🔒 Regras de Negócio
- Só podem oferecer leite para coleta doadoras previamente aprovadas.
- Leite armazenado deve ter sido extraído em até 15 dias, devidamente refrigerado/congelado.
- A quantidade mínima para coleta pode variar conforme regras da instituição (ex: ≥ 100 ml).
- A coleta deve ocorrer dentro da janela de validade do leite (segundo critérios da Anvisa ou banco de leite parceiro).

---
## 🎯 Diagrama de Caso de Uso
```@startuml
left to right direction
skinparam actorStyle awesome

actor "Doadora Autenticada" as D
actor "Sistema" as S
actor "Instituição Coletora" as I

usecase "Acessar área logada" as UC1
usecase "Oferecer leite para coleta" as UC2
usecase "Preencher informações da doação" as UC3
usecase "Confirmar envio da solicitação" as UC4
usecase "Registrar doação no sistema" as UC5
usecase "Notificar instituições coletoras" as UC6
usecase "Receber agendamento ou contato" as UC7
usecase "Notificar doadora com detalhes" as UC8

D --> UC1
UC1 --> UC2
UC2 --> UC3
UC3 --> UC4
UC4 --> UC5
UC5 --> UC6
I --> UC7
UC6 --> I
UC7 --> UC8
UC8 --> D

@enduml
```

---

## 📌 Observações
- Futuros recursos podem incluir agendamento via calendário integrado.
- A avaliação da qualidade do leite (triagem) será feita pela instituição no momento da coleta.
