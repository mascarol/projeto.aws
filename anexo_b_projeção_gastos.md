# ANEXO B: PLANILHA DE PROJEÇÃO DE GASTOS MENSAIS

Este documento apresenta a estimativa de impacto financeiro e o Retorno sobre o Investimento (ROI) após a implementação do **Amazon S3 Intelligent-Tiering** na infraestrutura da Abstergo Industries.

## 📋 Premissas da Simulação
* **Volume total de dados analisado:** 10 TB (dados não estruturados).
* **Região AWS utilizada:** São Paulo (sa-east-1).
* **Comportamento dos dados:** Com base na análise de volumetria, constatou-se que 70% dos dados gerados tornam-se ociosos (sem qualquer tipo de acesso ou modificação) após 30 dias da sua criação.

---

## 📊 Tabela Comparativa de Custos

| Cenário de Armazenamento (Massa de 10 TB) | Custo por GB (Estimado) | Custo Mensal Total | Economia Gerada |
| :--- | :---: | :---: | :---: |
| **Cenário Atual:** 100% alocado na classe S3 Standard | \$0,023 / GB | \$230,00 | \$0,00 (Gargalo Financeiro) |
| **Cenário Otimizado:** 3 TB em S3 Standard + 7 TB em S3 Infrequent Access | \$0,023 (Std) / \$0,0125 (IA) | \$156,50 | **\$73,50 / mês (32% de redução)** |

## 🎯 Conclusão Analítica
A automação do ciclo de vida dos objetos reduz imediatamente o custo fixo de armazenamento da empresa. Projetando este cenário em escala anual, a Abstergo Industries atinge uma economia direta de **\$882,00 por ano** para cada bloco de 10 TB otimizado, sem acrescentar nenhuma complexidade operacional para a equipa de engenharia.