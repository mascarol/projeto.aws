# ANEXO A: DIRETRIZES CONCEITUAIS DE ARQUITETURA EM NUVEM

Este documento estabelece os fundamentos teóricos que serviram de base para a análise de viabilidade económica e tecnológica na infraestrutura da Abstergo Industries.

## 💾 Modelos de Armazenamento Adotados

1. **Armazenamento de Objetos (Object Storage)**
   * **Conceito:** Armazenamento de dados não estruturados onde cada arquivo é tratado como um objeto individual contendo dados, metadados e uma chave identificadora única.
   * **Aplicação:** Utilizado no projeto através do **Amazon S3** para a criação de repositórios eficientes de logs, mídias e cópias de segurança.

2. **Armazenamento em Blocos (Block Storage)**
   * **Conceito:** Divisão dos dados em blocos independentes e customizáveis, oferecendo o menor índice de latência e o maior desempenho para leitura e escrita (I/O).
   * **Aplicação:** Utilizado no projeto através do **Amazon EBS** para sustentar os sistemas operativos e volumes de dados das instâncias EC2.

3. **Armazenamento de Ficheiros (File Storage)**
   * **Conceito:** Sistemas de ficheiros partilhados em rede que utilizam protocolos tradicionais (como NFS), permitindo o acesso simultâneo de múltiplos servidores.
   * **Aplicação:** Mapeado para cenários futuros de colaboração através do **Amazon EFS**.

---

## 🏗️ Pilares de Otimização Financeira
* **Ciclo de Vida Autónomo:** Migração automática de dados quentes (frequentes) para dados frios (arquivos) com base no tempo de inatividade.
* **Elasticidade Ativa (Serverless):** Ajuste em tempo real da capacidade computacional, garantindo que a empresa pague estritamente pelo processamento consumido.
* **Redundância Incremental:** Eliminação de cópias completas repetitivas, armazenando apenas as alterações estruturais dos volumes de dados.