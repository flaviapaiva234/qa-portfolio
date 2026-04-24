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

## CT-05 – Login com usuário problemático

**ID:** CT-05  
**Módulo:** Login / Produtos / Carrinho  
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

### Resultado esperado:
Usuário deve acessar a aplicação com todos os elementos visuais e funcionalidades operando corretamente, incluindo imagens, adição de produtos e cálculo de valores

### Resultado obtido:
Usuário acessou a aplicação, porém foram identificadas inconsistências:
- imagens dos produtos exibidas incorretamente na listagem
- ausência de funcionalidade para seleção de quantidade
- valor total não exibido corretamente no carrinho

### Status:
Reprovado

### Observação:
Foram identificados múltiplos problemas na interface e no comportamento do sistema após login com usuário problemático

