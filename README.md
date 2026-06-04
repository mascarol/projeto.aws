# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

**Data:** 4 de junho de 2026  
**Empresa:** Abstergo Industries  
**Responsável:** Caroline Martins  

## Introdução
Este relatório apresenta o processo de viabilidade e implementação de ferramentas de infraestrutura em nuvem na empresa Abstergo Industries, realizado por Caroline Martins. O objetivo principal do projeto foi elencar 3 serviços estratégicos da AWS (Amazon Web Services) focados em armazenamento e banco de dados, com a finalidade de realizar uma diminuição de custos imediatos e otimização de recursos.

## Descrição do Projeto
O projeto de otimização foi dividido em 3 etapas distintas. Cada uma mapeia um gargalo financeiro atual da infraestrutura da empresa e propõe a substituição por um serviço gerenciado ou técnica nativa da AWS, conforme detalhado a seguir:

### Etapa 1: Otimização de Custos em Arquivamento e Dados Brutos
* **Nome da ferramenta:** Amazon S3 (Simple Storage Service) utilizando a classe **S3 Intelligent-Tiering**.
* **Foco da ferramenta:** Armazenamento de Objetos (Object Storage) com gerenciamento automatizado de ciclo de vida de dados não estruturados.
* **Descrição de caso de uso:** A Abstergo Industries armazena um volume massivo de logs de aplicações, mídias e backups cujos padrões de acesso mudam constantemente ou são desconhecidos. Em vez de pagar a tarifa cheia da classe *Standard* por dados ociosos, implementamos o *S3 Intelligent-Tiering*. A ferramenta monitora os padrões de uso e move automaticamente os objetos não acessados há mais de 30 dias para a camada de acesso infrequente (*Infrequent Access*), e após 90 dias para camadas de arquivo, reduzindo os custos de armazenamento em até 68% de forma imediata e sem impactar a performance de recuperação.

### Etapa 2: Redução de Desperdício Computacional e Licenciamento de Banco de Dados
* **Nome da ferramenta:** Amazon Aurora Serverless.
* **Foco da ferramenta:** Banco de Dados Relacional (SQL) elástico e totalmente gerenciado.
* **Descrição de caso de uso:** Atualmente, a empresa mantém servidores ligados 24/7 (ou paga licenças caras de bancos tradicionais) para sistemas internos que possuem picos de utilização apenas em horários comerciais. Ao migrar esses dados para o Amazon Aurora Serverless (compatível com MySQL/PostgreSQL), o banco passa a ajustar sua capacidade de computação de forma automática de acordo com a demanda em tempo real. Durante a madrugada ou fins de semana, o serviço reduz sua escala ao mínimo (ou desliga), cobrando estritamente pelo que foi processado e eliminando custos com provisionamento excessivo (*overprovisioning*).

### Etapa 3: Eficiência Financeira em Rotinas de Backup de Infraestrutura
* **Nome da ferramenta:** Amazon EBS (Elastic Block Store) - Mecanismo de **Snapshots Incrementais**.
* **Foco da ferramenta:** Armazenamento em Blocos (Block Storage) persistente para instâncias de computação.
* **Descrição de caso de uso:** Para garantir a segurança dos servidores EC2 da Abstergo Industries, eram feitas cópias diárias completas dos discos rígidos virtuais, gerando redundância e custos inflados de armazenamento. Substituímos essa rotina pela política de *Snapshots* do EBS. Por operarem de forma estritamente **incremental**, o primeiro backup armazena o volume total, mas as cópias diárias subsequentes salvam apenas os blocos de dados que sofreram alteração. Isso diminui o espaço consumido na nuvem de forma imediata e otimiza radicalmente os gastos com retenção de segurança e recuperação de desastres.

---

## Conclusão
A implementação das ferramentas e estratégias desenhadas para a Abstergo Industries trará um impacto financeiro positivo imediato através da eliminação de desperdício com espaço ocioso e provisionamento incorreto. Além do ganho financeiro, a empresa adota uma postura de arquitetura moderna baseada em serviços *serverless* e automação de ciclo de vida de dados, o que aumentará a eficiência, a resiliência e a produtividade das equipes de engenharia. 

Recomenda-se a continuidade do monitoramento através do AWS Cost Explorer e a futura expansão para soluções de Big Data analítico (como o Amazon Redshift) para extrair valor de negócio desses dados armazenados de forma econômica.

## Anexos

* [Anexo A: Diretrizes Conceituais de Arquitetura em Nuvem](anexo_a_diretrizes_arquitetura.md)
* [Anexo B: Planilha de Projeção de Gastos Mensais](anexo_b_projeção_gastos.md)
* [Anexo C: Matriz de Decisão Arquitetural](anexo_c_matriz_decisão.md)

---

Assinatura do Responsável pelo Projeto:

**Caroline Martins** *Engenheiro(a) de Dados em Formação - Abstergo Industries*
