## 🧪 Casos de Teste

> 🔗 **Sistema sob teste (SUT):** [SauceDemo](https://www.saucedemo.com/) – site fictício para prática de automação e testes manuais.

### CT01 – Login com credenciais válidas

**Aplicação:** SauceDemo  
**Ambiente:** Produção  
**Pré-condição:** Usuário cadastrado

**Passos:**
1. Acessar a aplicação
2. Inserir o usuário `standard_user`
3. Inserir a senha `secret_sauce`
4. Clicar em `Login`

**Resultado esperado:**
Usuário deve ser redirecionado para a página de produtos

**Resultado obtido:**
Usuário foi redirecionado para a página de produtos e a lista de itens foi exibida com sucesso

**Status:** Aprovado

---

### CT02 – Login com senha inválida

**Pré-condição:** Usuário cadastrado

**Passos:**
1. Acessar a aplicação SauceDemo
2. Inserir o usuário `standard_user`
3. Inserir a senha inválida `123456`
4. Clicar em `Login`

**Resultado esperado:**
Sistema deve exibir mensagem de erro informando que as credenciais são inválidas

**Resultado obtido:**
Mensagem de erro foi exibida com destaque em vermelho:  
"Epic sadface: Username and password do not match any user in this service"

**Status:** Aprovado

---

## CT03 – Login com campos vazios

**Passos:**
1. Acessar a aplicação SauceDemo
2. Não preencher usuário nem senha
3. Clicar em `Login`

**Resultado esperado:**
Sistema deve exibir mensagem informando que os campos de usuário e senha são obrigatórios

**Resultado obtido:**
Mensagem de erro exibida com destaque em vermelho:
"Epic sadface: Username is required"

**Status:** Reprovado

**Observação:**
O sistema informa apenas a ausência do usuário, não indicando que o campo de senha também é obrigatório.
