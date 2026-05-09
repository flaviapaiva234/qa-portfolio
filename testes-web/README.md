# 🌐 Testes em Aplicação Web

Este diretório apresenta a execução prática de testes manuais na aplicação [SauceDemo](https://www.saucedemo.com/), simulando o fluxo real de trabalho de um QA.

---

## 🎯 Objetivo

Validar o comportamento do sistema em diferentes cenários, identificando falhas funcionais, inconsistências visuais, problemas de usabilidade e degradação de performance ao longo do fluxo da aplicação.

---

## 🧪 Tipos de testes realizados

- Testes funcionais  
- Testes de login  
- Testes de validação de campos  
- Testes exploratórios  
- Testes de performance (não funcionais)  
- Análise de comportamento do sistema  

---

## 🔍 Cenários testados

- Login com dados válidos  
- Login com senha inválida  
- Login com campos vazios  
- Login com usuário bloqueado  
- Fluxo completo com usuário problemático  
- Fluxo completo com usuário válido (happy path)  
- Fluxo de navegação até o carrinho  
- Fluxo de checkout  
- Teste de performance degradada com `performance_glitch_user`  

---

## 📂 Estrutura do diretório

- `casos-de-teste.md` → Casos de teste detalhados  
- `bugs.md` → Relatório de bugs identificados  
- `evidencias/` → Imagens utilizadas como prova dos bugs  

---

## 🔗 Rastreabilidade

Os testes e bugs estão diretamente relacionados, permitindo rastrear falhas desde a execução até sua documentação:

- CT-03 → BUG-001 (validação incompleta)
- CT-05 → BUG-002 (imagens incorretas)
- CT-05 → BUG-003 (ausência de seletor de quantidade — classificado como possível melhoria)
- CT-05 → BUG-004 (falha crítica no checkout)
- CT-06 → Validação do fluxo completo sem erros (happy path)
- CT-07 → BUG-005 (lentidão perceptível na navegação)

---

## 🐞 Principais problemas identificados

- Inconsistência visual na listagem de produtos  
- Falha de validação de campos obrigatórios  
- Erro crítico no fluxo de checkout (impede finalização da compra)  
- Ausência de controle de quantidade (analisado como possível melhoria)  
- Lentidão perceptível na navegação e carregamento da interface  

---

## 💡 Análise de QA

Durante os testes, foram identificados comportamentos que inicialmente pareciam bugs, mas após validação foram classificados como limitações do sistema.

Essa análise reforça a importância do pensamento crítico em QA, evitando a classificação incorreta de defeitos (falsos positivos) e melhorando a qualidade dos resultados.

Além dos testes funcionais, também foram explorados cenários relacionados à experiência do usuário e performance da aplicação.

---

## 📌 Observação

Este projeto simula o dia a dia de um QA, incluindo:

- Execução de testes  
- Identificação de falhas  
- Documentação estruturada  
- Organização de evidências  
- Rastreabilidade entre testes e bugs  
- Análise funcional e não funcional
