# 📄 Caso de Uso: Cadastro de Usuário

---

## 🎯 Descrição
Este caso de uso descreve o fluxo para que um novo usuário (doadora ou instituição) possa se cadastrar no aplicativo de doação de leite materno. O cadastro é o primeiro passo necessário para acessar as funcionalidades da plataforma, como ofertar, solicitar ou gerenciar doações.

---

## 👥 Atores
- **Usuário não autenticado:** pessoa física (mãe doadora), agente logístico ou representante de uma instituição.
- **Sistema:** aplicativo de doação de leite materno.

---

## 🎬 Pré-condições
- O usuário possui acesso à internet.
- O aplicativo está instalado e funcionando corretamente.
- O usuário não possui uma conta previamente cadastrada com o mesmo e-mail ou CPF/CNPJ.

---

## 🔁 Fluxo Principal
1. O usuário acessa a tela inicial do aplicativo.
2. Seleciona a opção "Cadastrar-se".
3. Escolhe o tipo de perfil: Doadora, Instituição ou Agente de Coleta.
4. Preenche os campos obrigatórios:
   - Nome completo
   - CPF (ou CNPJ para instituições)
   - Data de nascimento
   - Endereço (CEP, cidade, estado)
   - E-mail
   - Telefone
   - Senha
5. (Para doadoras) Informa dados adicionais de saúde, como:
   - Período de amamentação
   - Atestado de saúde atualizado
   - Tipo sanguíneo (opcional)
6. (Para Agente Logísticos) Informa código providenciado por Instituição já cadastrada
7. O sistema valida os dados preenchidos.
8. Caso os dados estejam corretos, o sistema salva as informações no banco de dados e envia um e-mail de confirmação.
9. O usuário recebe uma mensagem de sucesso e pode fazer login.

---

## 🔁 Fluxo Alternativo
- **4A. Dados incompletos ou inválidos:**  
  O sistema exibe mensagens de erro específicas para cada campo com problema e impede a finalização do cadastro.

- **7A. E-mail ou CPF já cadastrado:**  
  O sistema informa que o e-mail ou o CPF já está em uso e oferece a opção de recuperação de senha.

---

## ✅ Pós-condições
- O novo usuário está registrado na base de dados.
- O e-mail de confirmação foi enviado.
- O usuário pode acessar a área logada após ativação (caso necessário).

---

## 🔒 Regras de Negócio
- Cada CPF/CNPJ pode ser associado a apenas um perfil.
- A senha deve conter 6 caracteres numéricos, não podendo ter mais de 2 números iguais seguidos
- Doadoras devem passar por uma etapa adicional de verificação de saúde antes de poder doar.

---

## 📌 Observações
- No futuro, poderá ser adicionado login via redes sociais.
- A integração com bancos de dados de saúde (como o SUS) pode ser avaliada para validação de doadoras.
