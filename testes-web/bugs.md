# 🐞 Relatório de Bugs

---

## BUG-001 – Validação incompleta de campos obrigatórios no login

**Relacionado ao caso de teste:** CT-03 – Login com campos vazios  

**Ambiente:**
- Aplicação: SauceDemo  
- URL: https://www.saucedemo.com/  
- Navegador: Chrome  
- Data do teste: 22/04/2026  

**Módulo:** Login  
**Severidade:** Média    
**Prioridade:** Média  
**Tipo de defeito:** Validação / UX


### Passos para reprodução:
1. Acessar a página de login
2. Não preencher os campos de usuário e senha
3. Clicar no botão "Login"


### ❌ Resultado atual:
Mensagem exibida:  
"Epic sadface: Username is required"


### ✅ Resultado esperado:
Sistema deve informar que ambos os campos (usuário e senha) são obrigatórios.


### Impacto:
Usuário pode não compreender que ambos os campos são obrigatórios, comprometendo a interação com o sistema.

### Evidência:
<img width="947" height="676" alt="image" src="https://github.com/user-attachments/assets/306bc7b7-5c31-47ac-afe2-c4180e6b09e7" />


### Observação:
A validação ocorre apenas para o campo de usuário, ignorando o campo de senha quando ambos estão vazios.

---

## BUG-002 – Imagens dos produtos exibidas incorretamente

**Relacionado ao caso de teste:** CT-05 – Fluxo de produtos com problem_user
**Usuário impactado:** problem_user

**Ambiente:**
- Aplicação: SauceDemo  
- URL: https://www.saucedemo.com/  
- Navegador: Chrome  
- Data do teste: 25/04/2026
  
**Módulo:** Produtos  
**Escopo afetado:** Listagem de produtos  
**Severidade:** Média  
**Prioridade:** Alta  
**Tipo de defeito:** Funcional / UI  


### Passos para reprodução:
1. Acessar a página de login
2. Inserir o usuário `problem_user`
3. Inserir a senha `secret_sauce`
4. Clicar no botão "Login"
5. Acessar a lista de produtos


### ❌ Resultado atual:
Imagens exibidas na listagem estão repetidas ou não correspondem aos produtos descritos.


### ✅ Resultado esperado:
Cada produto deve exibir a imagem correta correspondente à sua descrição.


### Impacto:
Usuário pode perder confiança na aplicação e tomar decisões incorretas de compra devido à inconsistência visual dos produtos.


### Evidência:
- Tela de produtos com imagens incorretas:
<img width="1318" height="685" alt="image" src="https://github.com/user-attachments/assets/6c7e9baa-5493-4d4c-b8c5-c83623eeac8d" />


- Tela do produto correto:
<img width="1321" height="680" alt="image" src="https://github.com/user-attachments/assets/dcf8426a-f1e3-47f5-b65d-05ba90403ca8" />



### Observação:
O problema ocorre apenas na listagem. Ao acessar o detalhe do produto, a imagem correta é exibida.
