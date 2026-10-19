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
