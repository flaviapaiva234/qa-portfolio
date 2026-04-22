# 🐞 Relatório de Bugs

---

## BUG-001 – Validação incompleta de campos obrigatórios no login

**Relacionado ao caso de teste:** CT-03 – Login com campos vazios  

**Ambiente:**
- Aplicação: SauceDemo  
- URL: https://www.saucedemo.com/  
- Navegador: Chrome  
- Data do teste: 22/04/2026  

**Severidade:** Média  
**Prioridade:** Média
**Tipo de defeito:** Validação / UX

---

### Passos para reprodução:
1. Acessar a página de login
2. Não preencher os campos de usuário e senha
3. Clicar no botão "Login"

---

### ❌ Resultado atual:
Mensagem exibida:  
"Epic sadface: Username is required"

---

### ✅ Resultado esperado:
Sistema deve informar que ambos os campos (usuário e senha) são obrigatórios

---

### 🎯 Impacto:
Usuário pode não entender que também precisa preencher a senha, gerando confusão no fluxo de login

---

###  Evidência:
<img width="947" height="676" alt="image" src="https://github.com/user-attachments/assets/306bc7b7-5c31-47ac-afe2-c4180e6b09e7" />

---

###  Observação:
A validação ocorre apenas para o campo de usuário, ignorando o campo de senha quando ambos estão vazios
