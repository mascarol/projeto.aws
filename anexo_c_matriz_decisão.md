# ANEXO C: MATRIZ DE DECISÃO ARQUITETURAL

Este documento serve como guia técnico oficial para orientar os engenheiros de dados e arquitetos de soluções da Abstergo Industries na escolha do modelo de armazenamento ideal para novos projetos, mitigando custos com provisionamento incorreto (overprovisioning).

---

## 🛠️ Matriz de Comparison de Armazenamento AWS

| Serviço AWS | Tipo de Armazenamento | Protocolo / Formato | Principal Vantagem | Quando Usar na Abstergo? |
| :--- | :--- | :--- | :--- | :--- |
| **Amazon EBS** | Blocos (Block Storage) | Discos Rígidos Virtuais (HDD/SSD) | Altíssima performance, throughput customizável e baixíssima latência para a instância conectada. | Volumes de sistema operativo para instâncias EC2 e servidores de bases de dados relacionais pesadas. |
| **Amazon S3** | Objetos (Object Storage) | Estrutura de Chave, Valor e Metadados | Escalabilidade praticamente infinita, durabilidade de 99,999999999% e políticas nativas de ciclo de vida. | Construção de Data Lakes, repositório de mídias (imagens/vídeos), arquivos de logs brutos e backups de retenção longa. |
| **Amazon EFS** | Arquivos (File Storage) | NFS (Network File System) | Elasticidade automática (cresce e diminui sozinho) e suporte a acesso simultâneo de múltiplos clientes. | Diretórios partilhados de rede, sistemas de arquivos para clusters de servidores e ambientes de desenvolvimento colaborativo. |

---

## 📌 Diretriz de Governança
Fica estipulado que nenhuma aplicação corporativa poderá utilizar armazenamento em bloco (EBS) para retenção de arquivos estáticos ou históricos, devendo estes ser obrigatoriamente direcionados ao Amazon S3 para conformidade com a política de redução de custos da empresa.