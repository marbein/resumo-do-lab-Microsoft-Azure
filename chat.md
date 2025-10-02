# ☁️ Formação Microsoft AZ-900 Certification  

Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab na DIO, voltado para a certificação **Microsoft Azure Fundamentals (AZ-900)**.  

---

## 📑 Sumário  
- [Módulo 1 - Conceito de Nuvem](#módulo-1---conceito-de-nuvem)  
  - [Introdução à Computação em Nuvem](#tópico-1---introdução-à-computação-em-nuvem)  
  - [Benefícios da Computação em Nuvem](#tópico-2---benefícios-da-computação-em-nuvem)  
  - [Tipos de Serviço de Nuvem](#tópico-3---tipos-de-serviço-de-nuvem)  
- [Módulo 2 - Componentes de Arquitetura do Azure](#módulo-2---componentes-de-arquitetura-do-azure)  
  - [Arquitetura e Serviços do Azure](#tópico-1---arquitetura-e-serviços-do-azure)  
  - [Computação e Rede no Azure](#tópico-2---computação-e-rede-no-azure)  
  - [Armazenamento do Azure](#tópico-3---armazenamento-do-azure)  
  - [Identidade, Acesso e Segurança](#tópico-4---identidade-acesso-e-segurança)  
- [Módulo 3 - Gerenciamento e Governança](#módulo-3---gerenciamento-e-governança)  
  - [Gerenciamento de Custos](#tópico-1---gerenciamento-de-custos-na-azure)  
  - [Governança e Conformidade](#tópico-2---primeiros-passos-com-governança-e-conformidade-na-azure)  
  - [Ferramentas de Gerenciamento e Implantação](#tópico-3---ferramentas-de-gerenciamento-e-implantação)  
  - [Ferramentas de Monitoramento](#tópico-4---ferramentas-de-monitoramento-do-azure)  
- [📚 Referências](#-referências)  

---

## Módulo 1 - Conceito de Nuvem  

### Tópico 1 - Introdução à Computação em Nuvem  
> **Computação em Nuvem**: Recursos virtualizados disponibilizados por provedores de nuvem.  

- **Modelos de Nuvem:**  
  - ☁️ **Pública:** Infraestrutura de hardware de propriedade do provedor (ex: Microsoft Azure).  
  - 🏢 **Privada:** Infraestrutura exclusiva de uma organização, local (on-premises) ou hospedada.  
  - 🔄 **Híbrida:** Combina nuvem pública e privada, permitindo movimentação entre ambientes.  

- **Modelos de Custo:**  
  | Modelo | Descrição | Exemplo |
  |--------|-----------|---------|
  | **CapEx** | Investimentos em bens de capital, longo prazo | Comprar servidores físicos |
  | **OpEx** | Custos operacionais do dia a dia | Pagar assinatura do Azure |

---

### Tópico 2 - Benefícios da Computação em Nuvem  
- 🔄 **Escalabilidade:** Ajustar recursos conforme a demanda.  
- ⚡ **Elasticidade:** Aumentar ou reduzir recursos automaticamente.  
- 🔒 **Segurança:** Provedor oferece ferramentas, cliente implementa.  
- ✅ **Alta Disponibilidade (SLA):**  

| SLA (%)   | Tempo Máximo de Inatividade/Mês |
|-----------|---------------------------------|
| 99%       | 7h 12min                        |
| 99.9%     | 43min                           |
| 99.95%    | 21min                           |

- 📊 **Previsibilidade:** Controle de custos, performance e confiabilidade.  
- 🛠️ **Gerenciabilidade:** Portal, CLI, PowerShell, APIs.  
- 🧭 **Governança:** Políticas, compliance e boas práticas.  

---

### Tópico 3 - Tipos de Serviço de Nuvem  
| Modelo | Cliente Gerencia | Exemplo |
|--------|------------------|---------|
| **IaaS** (Infraestrutura como Serviço) | SO, apps, dados | VM no Azure |
| **PaaS** (Plataforma como Serviço) | Apps e dados | Azure Functions |
| **SaaS** (Software como Serviço) | Apenas uso/configuração | Microsoft 365 |

- **Modelo de Responsabilidade Compartilhada:**  
  <img width="819" height="442" alt="responsabilidade compartilhada" src="https://github.com/user-attachments/assets/35fe9c36-4d47-4ab9-954f-8b81f5d6b848" />  

---

## Módulo 2 - Componentes de Arquitetura do Azure  

### Tópico 1 - Arquitetura e Serviços do Azure  
- 🌍 **Regiões:** 60 regiões em +140 países.  
- 🏢 **Zonas de Disponibilidade:** Alta disponibilidade e resiliência.  
- 🔗 **Pares de Regiões:** Estratégia de Disaster Recovery.  
- 📦 **Grupo de Recursos:** Pasta lógica para organizar e gerenciar recursos.  
- 🧾 **Assinaturas:** Limites de cobrança e controle de acesso.  
- 🗂️ **Grupos de Gerenciamento:** Organização centralizada de assinaturas.  

---

### Tópico 2 - Computação e Rede no Azure  
- 💻 **Máquinas Virtuais (VMs):** IaaS personalizável.  
- 🖥️ **Área de Trabalho Virtual:** Virtualização de desktops.  
- 📦 **Contêineres e Kubernetes (AKS):** Execução de microserviços.  
- ⚡ **Azure Functions:** Serverless, executado sob demanda.  
- 🌐 **Rede Virtual (VNet):** Conexão entre recursos, VPN Gateway, ExpressRoute e DNS.  

---

### Tópico 3 - Armazenamento do Azure  
- 📦 **Tipos de Armazenamento:** Blob, Disco, Arquivos, Filas, Tabelas.  
- 🔄 **Redundância:**  
  | Tipo | Local de Replicação | Cópias |
  |------|---------------------|--------|
  | LRS  | Datacenter único | 3 |
  | ZRS  | Zonas de Disponibilidade | 3 |
  | GRS  | Região primária + secundária | 6 |
  | GZRS | ZRS + replicação secundária | 6 |

- 📂 **Camadas de Acesso:**  
  - Frequente, Esporádico, Frio, Arquivo Morto.  
- 🚚 **Migração:** AzCopy, Data Box, Gerenciador de Armazenamento.  

---

### Tópico 4 - Identidade, Acesso e Segurança  
- 🔑 **Microsoft Entra ID:** Identidade e acesso.  
- 🔒 **Autenticação Multifator (MFA).**  
- 👥 **Autenticação B2B/B2C.**  
- ⚖️ **Acesso Condicional.**  
- 🛡️ **Defender for Cloud:** Monitoramento e proteção.  
- 🔐 **Modelo Zero Trust:** Sempre verificar, nunca confiar.  

---

## Módulo 3 - Gerenciamento e Governança  

### Tópico 1 - Gerenciamento de Custos na Azure  
- 💰 **Fatores de custo:** tipo de recurso, consumo, região, tráfego, assinatura.  
- 🛒 **Marketplace Azure.**  
- 🧮 **Calculadoras:**  
  - **Preço:** Estimativa de custos.  
  - **TCO:** Comparação on-premises x Azure.  
- 🏷️ **Tags:** Pares chave-valor para organizar recursos.  

---

### Tópico 2 - Primeiros Passos com Governança e Conformidade  
- 📜 **Azure Policy:** Padronização e compliance.  
- 🔒 **Bloqueio de Recursos:** Previne exclusão acidental.  
- 📊 **Microsoft Purview:** Governança e auditoria de dados.  
- ✅ **Portal de Confiança do Serviço:** Transparência em conformidade.  

---

### Tópico 3 - Ferramentas de Gerenciamento e Implantação  
- 🛠️ **Ferramentas:** Portal, CLI, PowerShell, Cloud Shell.  
- 🌍 **Azure Arc:** Governança híbrida e multinuvem.  
- 📄 **ARM Templates:** Infraestrutura como Código (IaC).  
- 🖊️ **Bicep/Terraform:** Automação de infraestrutura.  

---

### Tópico 4 - Ferramentas de Monitoramento do Azure  
- 🤖 **Assistente do Azure:** Recomendações de otimização.  
- 🟢 **Integridade do Serviço:** Status do Azure e dos recursos.  
- 📈 **Azure Monitor:** Telemetria e análise de performance.  

---

## 📚 Referências  
- [📘 Documentação Oficial do Microsoft Azure](https://learn.microsoft.com/azure)  
- [📘 Microsoft Learn - AZ-900](https://learn.microsoft.com/certifications/exams/az-900)  
