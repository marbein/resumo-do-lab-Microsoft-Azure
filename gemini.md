# Resumo de Estudos: Certificação Microsoft AZ-900 (Azure Fundamentals)

Este repositório contém um resumo consolidado dos principais conceitos abordados no exame de certificação AZ-900. O objetivo é servir como um guia de revisão rápido, visual e eficiente para a comunidade.

---

## 🧭 Sumário

- [Módulo 1: Conceitos de Nuvem](#-módulo-1-conceitos-de-nuvem)
  - [Tópico 1: Introdução à Computação em Nuvem](#tópico-1-introdução-à-computação-em-nuvem)
  - [Tópico 2: Benefícios da Computação em Nuvem](#tópico-2-benefícios-da-computação-em-nuvem)
  - [Tópico 3: Tipos de Serviço de Nuvem](#tópico-3-tipos-de-serviço-de-nuvem)
- [Módulo 2: Componentes de Arquitetura do Azure](#-módulo-2-componentes-de-arquitetura-do-azure)
  - [Tópico 1: Arquitetura e Serviços do Azure](#tópico-1-arquitetura-e-serviços-do-azure)
  - [Tópico 2: Computação e Rede no Azure](#tópico-2-computação-e-rede-no-azure)
  - [Tópico 3: Armazenamento do Azure](#tópico-3-armazenamento-do-azure)
  - [Tópico 4: Identidade, Acesso e Segurança](#tópico-4-identidade-acesso-e-segurança)
- [Módulo 3: Gerenciamento e Governança](#-módulo-3-gerenciamento-e-governança)
  - [Tópico 1: Gerenciamento de Custos no Azure](#tópico-1-gerenciamento-de-custos-no-azure)
  - [Tópico 2: Governança e Conformidade no Azure](#tópico-2-governança-e-conformidade-no-azure)
  - [Tópico 3: Ferramentas de Gerenciamento e Implantação](#tópico-3-ferramentas-de-gerenciamento-e-implantação)
  - [Tópico 4: Ferramentas de Monitoramento do Azure](#tópico-4-ferramentas-de-monitoramento-do-azure)
- [📚 Referências e Links Úteis](#-referências-e-links-úteis)

---

## ☁️ Módulo 1: Conceitos de Nuvem

### Tópico 1: Introdução à Computação em Nuvem

> **Computação em Nuvem** é a entrega de recursos de computação (servidores, armazenamento, redes, software) pela internet, disponibilizados por provedores.

- **Modelos de Nuvem:**
  - **Pública:** A infraestrutura pertence e é operada por um provedor (ex: Microsoft Azure). Os recursos são compartilhados por múltiplos clientes.
  - **Privada:** Os recursos são de uso exclusivo de uma única organização. Pode ser hospedada localmente (*on-premises*) ou por um terceiro.
  - **Híbrida:** Combina nuvem privada com uma ou mais nuvens públicas, permitindo que dados e aplicações se movam entre os ambientes.

- **Modelos Financeiros:**

| Modelo | **CapEx (Capital Expenditure)** | **OpEx (Operational Expenditure)** |
| :--- | :--- | :--- |
| **Definição** | Gasto inicial em ativos físicos. | Gasto contínuo em serviços. |
| **Exemplo** | Comprar servidores para um datacenter. | Pagar uma fatura mensal do Azure. |
| **Associação** | Modelo tradicional *on-premises*. | Modelo principal da nuvem. |


### Tópico 2: Benefícios da Computação em Nuvem

- **⚡ Alta Disponibilidade:** Garantia de que os serviços estão sempre em execução, medida pelo **SLA (Service Level Agreement)**.

| SLA | Tempo de Inatividade Máximo por Mês |
| :--- | :--- |
| `99%` | ~7.2 horas |
| `99.9%` | ~43.8 minutos |
| `99.95%`| ~21.9 minutos |
| `99.99%`| ~4.3 minutos |

- **📈 Escalabilidade:** Capacidade de aumentar ou diminuir recursos **verticalmente** (mais poder, ex: adicionar CPU/RAM a uma VM).
- **🤸 Elasticidade:** Capacidade de escalar recursos **horizontalmente** (mais instâncias, ex: adicionar/remover VMs) de forma automática.
- **🛡️ Confiabilidade:** A arquitetura descentralizada garante resiliência contra falhas.
- **🔮 Previsibilidade:** Capacidade de prever custos e desempenho com ferramentas como o *Microsoft Azure Well-Architected Framework*.
- **🔒 Segurança:** Responsabilidade compartilhada entre o provedor (segurança *da* nuvem) e o cliente (segurança *na* nuvem).
- **🏛️ Governança:** Ferramentas para alinhar o uso da nuvem às políticas corporativas.
- **🛠️ Gerenciabilidade:** Gerenciamento centralizado via Portal Azure, PowerShell, CLI e APIs.

### Tópico 3: Tipos de Serviço de Nuvem

| Tipo | **IaaS (Infraestrutura como Serviço)** | **PaaS (Plataforma como Serviço)** | **SaaS (Software como Serviço)** |
| :--- | :--- | :--- | :--- |
| **Descrição** | Aluguel da infraestrutura básica. | Plataforma para desenvolver e rodar apps. | Software pronto para uso. |
| **Você Gerencia**| S.O., Aplicações, Dados. | Apenas Aplicações e Dados. | Apenas o uso e as configurações. |
| **Exemplo Azure**| Máquinas Virtuais (VMs) | Serviço de Aplicativo, Azure SQL | Microsoft 365, Dynamics 365 |

- **Modelo de Responsabilidade Compartilhada:** Define a divisão de responsabilidades. Quanto mais você gerencia (IaaS), maior sua responsabilidade.

  ![Modelo de Responsabilidade Compartilhada](https://github.com/user-attachments/assets/35fe9c36-4d47-4ab9-954f-8b81f5d6b848)

---

## 🏗️ Módulo 2: Componentes de Arquitetura do Azure

### Tópico 1: Arquitetura e Serviços do Azure

- **Geografia do Azure:**
  - **Regiões:** Uma área geográfica contendo múltiplos datacenters.
  - **Zonas de Disponibilidade:** Datacenters fisicamente separados dentro de uma região, com energia, refrigeração e redes independentes. Protegem contra falhas em nível de datacenter.
  - **Pares de Regiões:** Uma região é emparelhada com outra na mesma geografia para recuperação de desastres.

- **Estrutura de Gerenciamento do Azure:**
> A estrutura organizacional do Azure permite aplicar governança e gerenciar o acesso de forma hierárquica e granular.

  ```mermaid
  graph TD
      A[🏢 Grupo de Gerenciamento] --> B[💳 Assinatura A];
      A --> C[💳 Assinatura B];
      B --> D[🗂️ Grupo de Recursos 1];
      B --> E[🗂️ Grupo de Recursos 2];
      D --> F[⚙️ Recurso VM];
      D --> G[⚙️ Recurso Rede];
  ```
  - **Grupos de Gerenciamento:** Aplicam governança (políticas, RBAC) a múltiplas assinaturas.
  - **Assinaturas:** Unidade de cobrança e limite de acesso aos recursos.
  - **Grupos de Recursos:** Contêiner lógico para agrupar recursos de uma solução.

### Tópico 2: Computação e Rede no Azure

- **Serviços de Computação:**
  - **Máquinas Virtuais (VMs):** Servidores virtuais (IaaS).
  - **Conjuntos de Dimensionamento de VMs:** Gerencia um grupo de VMs com balanceamento de carga e dimensionamento automático.
  - **Contêineres (ACI & AKS):** ACI para contêineres simples (PaaS), AKS para orquestração robusta com Kubernetes.
  - **Azure Functions:** Computação *Serverless* que executa código baseado em eventos.
  - **Serviços de Aplicativos:** Plataforma gerenciada (PaaS) para hospedar aplicações web e APIs.

- **Serviços de Rede:**
  - **Rede Virtual (VNet):** Rede privada e isolada no Azure.
  - **Gateway de VPN:** Conecta uma VNet a uma rede local pela internet pública (criptografado).
  - **ExpressRoute:** Conexão privada e dedicada entre seu datacenter e o Azure.

### Tópico 3: Armazenamento do Azure

- **Redundância de Armazenamento:**

| Sigla | Nome | Proteção Contra |
| :---- | :--- | :--- |
| **LRS** | Redundância Local | Falha de disco/rack |
| **ZRS** | Redundância de Zona | Falha de datacenter |
| **GRS** | Redundância Geográfica | Desastre regional |
| **GZRS**| Redundância de Zona Geográfica| Falha de datacenter **E** desastre regional |

- **Serviços de Armazenamento:**
  - **Blob do Azure:** Para dados não estruturados (imagens, vídeos, logs).
  - **Arquivos do Azure:** Compartilhamentos de arquivos de rede na nuvem (protocolo SMB).
  - **Disco do Azure:** Discos de bloco para VMs.

- **Camadas de Acesso (Blob):**
  - **Hot (Frequente):** Dados acessados frequentemente.
  - **Cool (Esporádico):** Dados com pouco acesso (mín. 30 dias).
  - **Cold (Frio):** Dados raramente acessados (mín. 90 dias).
  - **Archive (Arquivo Morto):** Dados de longo prazo, raramente acessados (mín. 180 dias).

### Tópico 4: Identidade, Acesso e Segurança

> **Microsoft Entra ID** (antigo Azure AD) é o serviço de gerenciamento de identidades e acesso do Azure.

- **Principais Recursos:**
  - **Autenticação e Autorização:** Verifica a identidade e define o que o usuário pode acessar.
  - **Autenticação Multifator (MFA):** Camada adicional de segurança que exige duas ou mais formas de verificação.
  - **Acesso Condicional:** Políticas "se-então" para impor controles de acesso (ex: SE o usuário está em uma rede desconhecida, ENTÃO exigir MFA).
  - **RBAC (Controle de Acesso Baseado em Função):** Concede permissões atribuindo funções (Leitor, Colaborador) a usuários em escopos específicos.
- **Modelos de Segurança:**
  - **Confiança Zero (Zero Trust):** Modelo que assume violação e verifica cada solicitação.
  - **Microsoft Defender para Nuvem:** Ferramenta para gerenciamento de postura de segurança e proteção contra ameaças.

---

## 🏛️ Módulo 3: Gerenciamento e Governança

### Tópico 1: Gerenciamento de Custos no Azure

- **Ferramentas de Planejamento:**
  - **Calculadora de Preços:** Estima o custo mensal dos serviços.
  - **Calculadora de Custo Total de Propriedade (TCO):** Estima a economia ao migrar para o Azure.
- **Ferramentas de Otimização:**
  - **Gerenciamento de Custos e Cobrança:** Analisa, gerencia e otimiza gastos. Permite criar **orçamentos** e **alertas**.
  - **Marcas (Tags):** Pares de chave-valor aplicados aos recursos para organização e rastreamento de custos. Tags **não são herdadas**.

### Tópico 2: Governança e Conformidade no Azure

- **Azure Policy:**
  > Cria e gerencia políticas para impor regras e garantir a conformidade dos recursos. Ex: "Permitir VMs apenas da série D".
- **Bloqueios de Recursos:**
  > Protegem recursos contra exclusão (`CanNotDelete`) ou modificação (`ReadOnly`) acidental. Bloqueios **são herdados**.
- **Microsoft Purview:** Solução de governança de dados para mapear e gerenciar dados em ambientes locais e multinuvem.
- **Portal de Confiança do Serviço:** Documentação sobre a conformidade da Microsoft com padrões e regulamentações.

### Tópico 3: Ferramentas de Gerenciamento e Implantação

- **Ferramentas de Interação:**
  - **Portal do Azure:** Interface web.
  - **Azure PowerShell / CLI:** Ferramentas de linha de comando para automação.
  - **Azure Cloud Shell:** Shell interativo no navegador.
- **Azure Arc:**
  > Estende o painel de gerenciamento do Azure para infraestruturas **fora** do Azure (on-premises, AWS, GCP), permitindo governança unificada.
- **Infraestrutura como Código (IaC):**
  > Prática de gerenciar infraestrutura via código (Modelos ARM, Bicep, Terraform) para automação e consistência.

### Tópico 4: Ferramentas de Monitoramento do Azure

- **Assistente do Azure (Azure Advisor):**
  > Consultor de nuvem que fornece recomendações para otimizar recursos em Custo, Segurança, Confiabilidade, Desempenho e Excelência Operacional.
- **Integridade do Serviço do Azure:**
  - **Status do Azure:** Visão global da saúde dos serviços Azure.
  - **Integridade do Serviço:** Visão personalizada da saúde dos serviços que **você** usa.
  - **Resource Health:** Saúde dos **seus recursos individuais**.
- **Azure Monitor:** Plataforma completa para coletar, analisar e agir com base em telemetria e logs de suas aplicações e infraestrutura.

---

## 📚 Referências e Links Úteis

- [Microsoft Learn: Roteiro de Aprendizagem AZ-900](https://learn.microsoft.com/pt-br/training/paths/microsoft-azure-fundamentals-describe-cloud-concepts/)
- [Calculadora de Preços do Azure](https://azure.microsoft.com/pt-br/pricing/calculator/)
- [Calculadora de Custo Total de Propriedade (TCO)](https://azure.microsoft.com/pt-br/pricing/tco/calculator/)
- [Documentação do Azure](https://learn.microsoft.com/pt-br/azure/)
- [Portal de Confiança do Serviço da Microsoft](https://servicetrust.microsoft.com/)
