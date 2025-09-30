# resumo-do-lab-Microsoft-Azure
## Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab na DIO

### Introdução a Computação em Nuvem 

Aprendemos:  

- **Definição de computação de nuvem:** Recursos virtualizados disponibolizados por provedores.  
    
- **Definição de nuvem:**  
  - **Publica:** Nele, toda a infraestrutura de hardware (servidores, armazenamento, rede) é de propriedade e operada por um provedor de nuvem terceirizado, como Microsoft (Azure).  
  - **Privada:** Os recursos de computação são de uso exclusivo de uma única empresa ou organização. A infraestrutura pode estar fisicamente localizada no datacenter da própria organização (on-premises) ou ser hospedada por um provedor terceirizado, mas o hardware é totalmente dedicado.  
  - **Hibrida:** A nuvem híbrida é uma abordagem que combina uma nuvem privada com uma ou mais nuvens públicas. Ela permite que dados e aplicações se movam entre os dois ambientes, criando um ambiente unificado, flexível e otimizado.
   
- **Definição:**
  - **CapEx:** Refere-se aos investimentos em bens de capital que a empresa utilizará por um longo período, geralmente mais de um ano. Pense nisso como grandes compras que melhoram ou expandem a capacidade da empresa.
    
  - **OpeX:** São os custos do dia a dia necessários para manter o negócio funcionando. São despesas recorrentes e consumidas no curto prazo.  

### Benefícios da Computação em Nuvem  

- **Alta Disponibilidade:** Recursos,serviços sempre disponivel - SLA -> 99% = 7.2h; 99.9% = 43.8 minutos; 99.95% = 21.9 minutos; se nao disponivel no prazo é compensado por credito em sua conta.   Um mês com 30 dias tem 43.200 minutos. Um SLA de 99.9% garante que o serviço estará disponível por 99.9% desse tempo, permitindo um máximo de 0.1% de inatividade (43.2 minutos).  

- **Escabilidade:** Capacidade de ajustar recurso para atender demanda, exemplo adicionar disco ( aumentar tamanho HD servidor), RAM, processador, etc.

- **Elasticidade:** Se houver um aumento de demanda, recursos impantados pode ser expandido automaticamente ou manualmente.

- **Confiabilidade:** Devido ao desing descentralizado, a nuvem da suporte a uma infraestrutura confiavel e resiliente, permitindo implantacao de recursos em varias regiões.

- **Previsibilidade:** Capacidade de prever e controlar três aspectos principais de suas operações na nuvem: Custo, Performance e Confiabilidade, com o microsoft azure well-architected framework.

- **Segurança:** Nuvem (provedor) oferece varias ferramentas de segurança , mas implementação (nuvem) de muita deles devem ser realizada pelo cliente.

- **Governança:** É o conjunto de mecanismos, processos e ferramentas que permitem a uma organização manter o controle sobre seus recursos e assinaturas na nuvem. O objetivo é garantir que o uso do Azure esteja alinhado com as políticas corporativas, os requisitos regulatórios e as melhores práticas de gerenciamento, sem impedir a agilidade que a nuvem oferece.

- **Gerenciabilidade:** Opeçoes de capacidade de gerenciamento de recursos, Por meio: Portal, Interface Linha de comando, APIs, PowerShell.

### Tipos de Serviço de Nuvem  

- **Iass:** Infraestrutura como serviços - Aluguel da infraestrutura básica, cliente gerencia Sistema Operacional, Aplicações, Dados.

- **Paas:** Plataforma como serviço - Plataforma para desenvolver e rodar apps, cliente gerencia Apenas suas Aplicações e Dados.	

- **SaaS:** Software como serviço - Software pronto para uso (ex: Office 365), cliente gerencia apenas o uso e as configurações do software.

- **Modelo De Responsibilidade Compartilhada:** É um conceito fundamental na computação em nuvem que define a divisão de responsabilidades de segurança entre o provedor de nuvem (Microsoft Azure) e o cliente. Entender este modelo é crucial para garantir que seus dados, aplicativos e infraestrutura estejam devidamente protegidos.
  <img width="819" height="442" alt="image" src="https://github.com/user-attachments/assets/35fe9c36-4d47-4ab9-954f-8b81f5d6b848" />

  
