# Simulador de Investimentos e Alocação de Ativos

Este repositório contém o projeto prático do **Simulador de Investimentos em Excel**, desenvolvido como desafio do curso. A ferramenta permite planejar a independência financeira e a alocação de ativos personalizada de acordo com o perfil de investidor do usuário.

---

## 📌 1. Perguntas que a Ferramenta Responde

A planilha foi estruturada para responder a **5 perguntas fundamentais** sobre planejamento financeiro e investimentos:

1. **Qual é o aporte mensal necessário para atingir a meta financeira?**  
   * **Onde aparece:** Na aba de Simulação Principal / Painel de Metas (Célula de Resultado do Aporte Mensal).
2. **Quanto tempo levará para alcançar o patrimônio desejado com o aporte atual?**  
   * **Onde aparece:** No painel resumo de Metas e Prazos (Célula com tempo estimado em meses/anos).
3. **Qual será o patrimônio acumulado ao final do período projetado?**  
   * **Onde aparece:** No destaque de Valor Futuro Acumulado e no gráfico de evolução patrimonial.
4. **Como o aporte mensal deve ser distribuído entre as classes de ativos (Renda Fixa, Ações, FIIs, Internacional, etc.)?**  
   * **Onde aparece:** Na tabela de Alocação de Ativos por Perfil e no gráfico de rosca/pizza de distribuição.
5. **Qual é a rentabilidade média ponderada da carteira ajustada ao perfil selecionado?**  
   * **Onde aparece:** No indicador de Taxa Esperada da Carteira (Painel de Métricas).

---

## 🧮 2. Aplicação das Funções `VF` e `PROCV`

### **Função `VF` (Valor Futuro)**
A função `VF` é utilizada para calcular o patrimônio final acumulado com base em taxa de juros constante, número de períodos e depósitos regulares.
* **Sintaxe no projeto:** `=VF(taxa_mensal; nper; -aporte_mensal; -patrimonio_inicial)`
* **Aplicação:** Permite projetar o efeito dos juros compostos ao longo do tempo sobre os aportes periódicos.

### **Função `PROCV` (Procura Vertical)**
A função `PROCV` atua na dinamização do modelo de acordo com o **Perfil de Investidor** selecionado na caixa de seleção (Validação de Dados).
* **Sintaxe no projeto:** `=PROCV(Perfil_Selecionado; Tabela_Perfis; Coluna_Percentual; FALSO)`
* **Aplicação:** Ao alterar o perfil (ex: *Conservador*, *Moderado*, *Arrojado*), o `PROCV` busca automaticamente os percentuais de distribuição e as taxas de retorno esperadas para cada classe de ativos na tabela de parâmetros.

---

## 🏷️ 3. Intervalos Nomeados Criados

Para garantir clareza nas fórmulas, facilitando a leitura e a manutenção, foram definidos os seguintes **Intervalos Nomeados**:

* **`Perfil_Selecionado`**: Célula com a lista suspensa para seleção do perfil (Conservador, Moderado, Arrojado).
* **`Tabela_Perfis`**: Matriz contendo a alocação percentual por perfil de investidor.
* **`Aporte_Mensal`**: Valor investido periodicamente pelo usuário.
* **`Taxa_Carteira`**: Taxa de retorno ponderada da carteira selecionada.
* **`Meta_Patrimonio`**: Valor final desejado para alcançar a independência financeira.

---

## 📊 4. Percentuais por Perfil e Origem das premissas

A divisão da carteira varia segundo o apetite de risco de cada perfil. Todos os perfis somam **100% de alocação**:

| Classe de Ativo | Conservador | Moderado | Arrojado |
| :--- | :---: | :---: | :---: |
| **Renda Fixa / Pós-fixado** | 70% | 40% | 20% |
| **Ações Locais (Brasil)** | 10% | 25% | 35% |
| **Fundos Imobiliários (FIIs)** | 15% | 20% | 25% |
| **Ativos Internacionais** | 5% | 15% | 20% |
| **Total** | **100%** | **100%** | **100%** |

* **Origem dos dados:** Os percentuais e rentabilidades históricas baseiam-se em conceitos clássicos de *Asset Allocation* (Alocação de Ativos) e nos parâmetros de referência sugeridos no curso, ajustados para manter um portfólio equilibrado entre preservação de capital e rendimento real.

---

## 🛠️ 5. Melhorias em Relação à Ferramenta do Expert

Buscando evoluir o modelo original disponibilizado pelo instrutor/expert, foram implementadas as seguintes melhorias:

1. **Design e UX Aprimorados:** Layout moderno com Modo Escuro/Clean, paleta de cores harmoniosa e hierarquia visual para fácil visualização das respostas das 5 perguntas.
2. **Alertas e Travas de Validação:** Implementação de validação de dados para evitar inputs incorretos (ex: valores negativos ou soma de alocação diferente de 100%).
3. **Ponderação Dinâmica de Rentabilidade:** A taxa de juros utilizada no `VF` ajusta-se automaticamente com base na proporção exata investida em cada classe de ativo do perfil selecionado.
4. **Gráficos Dinâmicos Interativos:** Inclusão de gráfico de alocação que atualiza suas fatias automaticamente ao mudar o perfil.

---

## 📸 Evidências de Funcionamento (Prints)

> **Dica para o aluno:** Tire prints da sua planilha preenchida e adicione nesta seção.

### **Simulação 1: Perfil Conservador**
![Simulação Conservador](https://via.placeholder.com/800x400?text=Print+Simulacao+Perfil+Conservador)
*Demonstração do cálculo com foco em Renda Fixa e menor volatilidade.*

### **Simulação 2: Perfil Arrojado**
![Simulação Arrojado](https://via.placeholder.com/800x400?text=Print+Simulacao+Perfil+Arrojado)
*Mesmo valor de entrada, porém demonstrando a nova divisão do aporte voltada a Renda Variável e maior projeção final de Valor Futuro.*

---

## 📋 Checklist de Submissão

- [x] A planilha abre sem erros de fórmula (`#N/D`, `#VALOR!`, etc.).
- [x] Trocar o perfil na lista altera automaticamente a divisão do aporte.
- [x] A soma das porcentagens de cada perfil totaliza **100%**.
- [x] Os dados de salário e investimentos são totalmente figurativos/exemplos.
- [x] Repositório público com nome sem acentos e em minúsculas (ex: `simulador-investimentos-excel`).