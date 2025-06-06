# 📃 Requisitos do Sistema — iMilk

## 🧑‍💼 Regras de Negócio (RN)

1. O sistema **deverá permitir apenas doadoras com cadastro validado e exames atualizados** cadastrarem ofertas de leite.
2. O leite **deverá estar armazenado sob congelamento e em recipientes esterilizados**, com data de coleta informada.
3. O sistema **não poderá permitir agendamento de coleta** para ofertas fora do raio máximo de X km (configurável por banco).
4. Cada coleta **deverá envolver apenas uma doadora por viagem**, salvo exceções controladas pelo banco de leite.
5. Coletas **não realizadas em até 24 horas** após o pedido devem retornar automaticamente ao status "disponível".
6. O banco de leite **deverá confirmar e avaliar a integridade** do leite recebido antes de disponibilizá-lo.
7. O sistema **bloqueará automaticamente perfis** (mãe ou motorista) com 3 ocorrências de irregularidades.
8. O chat **deverá ser monitorado** e conter somente mensagens relacionadas à logística da doação.
9. Toda doação **deverá gerar um relatório final** contendo: número do pedido, volume transportado, tempo de coleta e destino.

---

## ✅ Requisitos Funcionais (RF)

1. O sistema deve permitir o cadastro de perfis: mãe doadora, banco de leite e motorista/coletor.
2. O sistema deve permitir o login com autenticação por e-mail e senha.
3. O sistema deve permitir que mães registrem ofertas de leite com dados como: quantidade, data de coleta, validade e tipo.
4. O sistema deve permitir que bancos de leite visualizem ofertas de leite disponíveis próximas à sua localização.
5. O sistema deve permitir que bancos de leite realizem pedidos de coleta.
6. O sistema deve selecionar automaticamente um motorista/coletor disponível para a rota.
7. O sistema deve permitir o rastreamento em tempo real do motorista/coletor por parte da mãe e do banco de leite.
8. O sistema deve atualizar automaticamente o status da coleta (agendada, em andamento, entregue).
9. O sistema deve permitir comunicação via mensagens entre mães, bancos e motoristas.
10. O sistema deve gerar relatórios sobre volume de leite doado, número de coletas, tempo médio e número de mães ativas.
11. O sistema deve exibir campanhas de incentivo com metas e estatísticas de doações.

---

## ☑️ Requisitos Não Funcionais (RNF)

1. A interface deve ser responsiva e funcionar em dispositivos móveis e desktop.
2. O sistema deve estar disponível pelo menos 99% do tempo.
3. Os dados devem ser salvos em um banco de dados persistente e seguro.
4. As informações sensíveis devem ser criptografadas e estar em conformidade com a LGPD.
5. O tempo de resposta das ações principais (cadastro, pedido, coleta) deve ser inferior a 2 segundos.
6. O sistema deve realizar backups automáticos diários e registrar logs de auditoria.
7. O aplicativo deve funcionar com GPS e notificações em tempo real, mesmo em conexões móveis instáveis.
8. O sistema deve ser escalável para suportar várias regiões e rotas simultaneamente.
