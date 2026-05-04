## 🧪 Casos de Teste

> 🔗 **Sistema sob teste (SUT):** [SauceDemo](https://www.saucedemo.com/) – site fictício para prática de automação e testes manuais.

## CT-01 – Login com credenciais válidas

**ID:** CT-01  
**Módulo:** Login  
**Versão:** v1.0  
**Prioridade:** Alta  
**Severidade:** Alta  
**Tipo de teste:** Funcional 

**Pré-condição:** Usuário cadastrado

### Passos:
1. Acessar a aplicação SauceDemo
2. Inserir o usuário `standard_user`
3. Inserir a senha `secret_sauce`
4. Clicar em `Login`

### Resultado esperado:
Usuário deve ser redirecionado para a página de produtos

### Resultado obtido:
Usuário foi redirecionado para a página de produtos (Swag Labs), com listagem de itens e botões "Add to cart" visíveis

### Status:
Aprovado

### Observação:
Fluxo de autenticação executado com sucesso conforme esperado

---

## CT-02 – Login com senha inválida

**ID:** CT-02  
**Módulo:** Login  
**Versão:** v1.0  
**Prioridade:** Alta  
**Severidade:** Média  
**Tipo de teste:** Funcional / Negativo

**Pré-condição:** Usuário cadastrado

### Passos:
1. Acessar a aplicação SauceDemo
2. Inserir o usuário `standard_user`
3. Inserir a senha inválida `123456`
4. Clicar em `Login`

### Resultado esperado:
Sistema deve exibir mensagem de erro informando que as credenciais são inválidas

### Resultado obtido:
Mensagem de erro foi exibida com destaque em vermelho:  
"Epic sadface: Username and password do not match any user in this service"

### Status:
Aprovado

### Observação:
Sistema apresentou comportamento esperado ao bloquear acesso com credenciais inválidas

---

## CT-03 – Login com campos vazios

**ID:** CT-03  
**Módulo:** Login  
**Versão:** v1.0  
**Prioridade:** Alta  
**Severidade:** Média  
**Tipo de teste:** Funcional / Validação  

**Pré-condição:** Usuário na tela de login

### Passos:
1. Acessar a aplicação SauceDemo
2. Não preencher usuário nem senha
3. Clicar em `Login`

### Resultado esperado:
Sistema deve exibir mensagem informando que os campos de usuário e senha são obrigatórios

### Resultado obtido:
Mensagem de erro exibida com destaque em vermelho:
"Epic sadface: Username is required"

### Status:
Reprovado

### Observação:
O sistema informa apenas a ausência do usuário, não indicando que o campo de senha também é obrigatório.

---

## CT-04 – Login com usuário bloqueado

**ID:** CT-04  
**Módulo:** Login  
**Versão:** v1.0  
**Prioridade:** Alta  
**Severidade:** Média  
**Tipo de teste:** Funcional / Regra de negócio  

**Pré-condição:** Usuário bloqueado disponível (`locked_out_user`)  

### Passos:
1. Acessar a aplicação SauceDemo
2. Inserir o usuário `locked_out_user`
3. Inserir a senha `secret_sauce`
4. Clicar em "Login"

### Resultado esperado:
Sistema deve impedir o acesso e exibir mensagem informando que o usuário está bloqueado

### Resultado obtido:
Mensagem exibida com destaque em vermelho:  
"Epic sadface: Sorry, this user has been locked out."

### Status:
Aprovado

### Observação:
Sistema se comportou conforme esperado, bloqueando o acesso e exibindo mensagem clara ao usuário

---

## CT-05 – Fluxo completo com usuário problemático

**ID:** CT-05  
**Módulo:** Login / Produtos / Carrinho / Checkout  
**Versão:** v1.0  
**Prioridade:** Alta  
**Severidade:** Média  
**Tipo de teste:** Funcional / Exploratório  

**Pré-condição:** Usuário `problem_user` disponível  

### Passos:
1. Acessar a aplicação SauceDemo  
2. Inserir o usuário `problem_user`  
3. Inserir a senha `secret_sauce`  
4. Clicar em "Login"  
5. Navegar pela lista de produtos  
6. Selecionar um produto  
7. Adicionar o produto ao carrinho  
8. Acessar o carrinho  
9. Clicar em "Checkout"  
10. Preencher o campo "First Name"  
11. Tentar preencher o campo "Last Name"  
12. Preencher o campo "Zip Code"  
13. Clicar em "Continue"  

### Resultado esperado:
Usuário deve conseguir navegar por todo o fluxo da aplicação, incluindo visualização correta dos produtos e finalização do checkout sem erros.

### Resultado obtido:
Usuário acessou a aplicação, porém foram identificadas inconsistências:

- Imagens dos produtos exibidas incorretamente na listagem (BUG-002)  
- Falha no campo "Last Name", que corrompe o valor do campo "First Name" e impede a continuidade no checkout (BUG-004)  

### Status:
Reprovado  

### Observação:
Os defeitos identificados ocorrem exclusivamente com o perfil `problem_user`.  
Com o usuário `standard_user`, as imagens são exibidas corretamente e o fluxo de checkout funciona normalmente, incluindo o preenchimento dos campos.

---

## CT-06 – Fluxo completo com usuário válido (fluxo feliz)

**ID:** CT-06  
**Módulo:** Login / Produtos / Carrinho / Checkout  
**Versão:** v1.0  
**Prioridade:** Alta  
**Severidade:** Alta  
**Tipo de teste:** Funcional / E2E (End-to-End)  

**Pré-condição:** Usuário `standard_user` disponível  

### Passos:
1. Acessar a aplicação SauceDemo  
2. Inserir o usuário `standard_user`  
3. Inserir a senha `secret_sauce`  
4. Clicar em "Login"  
5. Verificar carregamento da lista de produtos  
6. Adicionar um produto ao carrinho (ex.: "Sauce Labs Backpack")  
7. Acessar o carrinho  
8. Verificar se o produto foi adicionado corretamente  
9. Clicar em "Checkout"  
10. Preencher o campo "First Name"  
11. Preencher o campo "Last Name"  
12. Preencher o campo "Zip Code"  
13. Clicar em "Continue"  
14. Verificar exibição do resumo da compra  
15. Validar valores (item total, taxa e total geral)  
16. Clicar em "Finish"  

### Resultado esperado:
Usuário deve conseguir completar todo o fluxo da aplicação com sucesso, desde o login até a finalização da compra, com:

- Produtos exibidos corretamente  
- Item adicionado ao carrinho  
- Formulário de checkout funcionando corretamente  
- Valores calculados corretamente  
- Confirmação de pedido exibida ao final  

### Resultado obtido:
Usuário conseguiu navegar por todo o fluxo sem erros:

- Login realizado com sucesso  
- Produto adicionado ao carrinho corretamente  
- Campos do checkout preenchidos sem inconsistências  
- Valores exibidos corretamente no resumo  
- Mensagem final exibida: "Thank you for your order!"  

### Status:
Aprovado  

### Observação:
Este teste valida o fluxo principal da aplicação (happy path), servindo como linha de base para os cenários exploratórios e negativos (como o CT-05).  
Garante que as funcionalidades críticas estão operando corretamente em condições normais de uso.

