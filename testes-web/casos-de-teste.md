## 🧪 Casos de Teste

### CT01 – Login com credenciais válidas

**Pré-condição:** Usuário cadastrado

**Passos:**
1. Acessar a aplicação SauceDemo
2. Inserir o usuário `standard_user`
3. Inserir a senha `secret_sauce`
4. Clicar em `Login`

**Resultado esperado:**
Usuário deve ser redirecionado para a página de produtos

**Resultado obtido:**
Usuário foi redirecionado para a página de produtos e a lista de itens foi exibida

**Status:** Aprovado

---

### CT02 – Login inválido
Passos:
1. Inserir usuário
2. Inserir senha incorreta
3. Clicar em entrar

Resultado esperado:
Mensagem de erro exibida
