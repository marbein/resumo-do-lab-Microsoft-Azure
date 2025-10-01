# Formação Microsoft AZ-900 Certification

### Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab na DIO

## Introdução a Computação em Nuvem 

- **Definição de computação de nuvem:** Recursos virtualizados disponibolizados por provedores.  
    
- **Definição de nuvem:**
  - **Publica:** Nele, toda a infraestrutura de hardware (servidores, armazenamento, rede) é de propriedade e operada por um provedor de nuvem terceirizado, como Microsoft (Azure).  
  - **Privada:** Os recursos de computação são de uso exclusivo de uma única empresa ou organização. A infraestrutura pode estar fisicamente localizada no datacenter da própria organização (on-premises) ou ser hospedada por um provedor terceirizado, mas o hardware é totalmente dedicado.  
  - **Hibrida:** A nuvem híbrida é uma abordagem que combina uma nuvem privada com uma ou mais nuvens públicas. Ela permite que dados e aplicações se movam entre os dois ambientes, criando um ambiente unificado, flexível e otimizado.
   
- **Definição:**
  - **CapEx:** Refere-se aos investimentos em bens de capital que a empresa utilizará por um longo período, geralmente mais de um ano. Pense nisso como grandes compras que melhoram ou expandem a capacidade da empresa.
    
  - **OpeX:** São os custos do dia a dia necessários para manter o negócio funcionando. São despesas recorrentes e consumidas no curto prazo.  

## Módulo 1 - Benefícios da Computação em Nuvem  

- **Alta Disponibilidade:** Recursos,serviços sempre disponivel - SLA -> 99% = 7.2h; 99.9% = 43.8 minutos; 99.95% = 21.9 minutos; se nao disponivel no prazo é compensado por credito em sua conta.   Um mês com 30 dias tem 43.200 minutos. Um SLA de 99.9% garante que o serviço estará disponível por 99.9% desse tempo, permitindo um máximo de 0.1% de inatividade (43.2 minutos).  

- **Escabilidade:** Capacidade de ajustar recurso para atender demanda, exemplo adicionar disco ( aumentar tamanho HD servidor), RAM, processador, etc.

- **Elasticidade:** Se houver um aumento de demanda, recursos impantados pode ser expandido automaticamente ou manualmente.

- **Confiabilidade:** Devido ao desing descentralizado, a nuvem da suporte a uma infraestrutura confiavel e resiliente, permitindo implantacao de recursos em varias regiões.

- **Previsibilidade:** Capacidade de prever e controlar três aspectos principais de suas operações na nuvem: Custo, Performance e Confiabilidade, com o microsoft azure well-architected framework.

- **Segurança:** Nuvem (provedor) oferece varias ferramentas de segurança , mas implementação (nuvem) de muita deles devem ser realizada pelo cliente.

- **Governança:** É o conjunto de mecanismos, processos e ferramentas que permitem a uma organização manter o controle sobre seus recursos e assinaturas na nuvem. O objetivo é garantir que o uso do Azure esteja alinhado com as políticas corporativas, os requisitos regulatórios e as melhores práticas de gerenciamento, sem impedir a agilidade que a nuvem oferece.

- **Gerenciabilidade:** Opeçoes de capacidade de gerenciamento de recursos, Por meio: Portal, Interface Linha de comando, APIs, PowerShell.

## Tipos de Serviço de Nuvem  

- **Iass:** Infraestrutura como serviços - Aluguel da infraestrutura básica, cliente gerencia Sistema Operacional, Aplicações, Dados.

- **Paas:** Plataforma como serviço - Plataforma para desenvolver e rodar apps, cliente gerencia Apenas suas Aplicações e Dados.	

- **SaaS:** Software como serviço - Software pronto para uso (ex: Office 365), cliente gerencia apenas o uso e as configurações do software.

- **Modelo De Responsibilidade Compartilhada:** É um conceito fundamental na computação em nuvem que define a divisão de responsabilidades de segurança entre o provedor de nuvem (Microsoft Azure) e o cliente. Entender este modelo é crucial para garantir que seus dados, aplicativos e infraestrutura estejam devidamente protegidos.  
  <img width="819" height="442" alt="image" src="https://github.com/user-attachments/assets/35fe9c36-4d47-4ab9-954f-8b81f5d6b848" />  

## Módulo 2 -  Componentes de Arquitetura do Azure  

- **Regiões:** Azure oferece abrangencia global, em 60 regioes e mais de 140 paises.
    - Composta por 3 ou mais datacenters proximos;  
    - Oferecem flexibilidade e escala para reduzir latencia;  
    - Preservam a residencia dos dados com uma oferta abrangente de conformidade;

  - **Zonas de Disponibilidade:** Projetadas para oferecer alta disponibilidade, resiliência e proteção contra falhas em datacenters.
      - Cada Zona de Disponibilidade é uma localização fisicamente separada dentro de uma Região. Elas possuem sua própria fonte de energia, refrigeração e rede independentes.  
      - Proteção contra Falhas: O isolamento garante que uma falha em uma única zona (como um problema de energia, inundação ou falha de rede) não afete a disponibilidade dos recursos nas outras zonas.  
      - Conexão de Baixa Latência: Apesar de serem fisicamente separadas, as zonas dentro de uma mesma região são conectadas por uma rede privada de fibra óptica de altíssima velocidade e baixa latência.  
      - Resiliência para Aplicações: Ao distribuir os componentes de uma aplicação (como máquinas virtuais, bancos de dados e balanceadores de carga) entre múltiplas Zonas de Disponibilidade, você cria uma arquitetura altamente disponível.  

- **Pares de Regioes:** Projetado para oferecer uma estratégia robusta de recuperação de desastres (Disaster Recovery - DR). Cada Região do Azure é emparelhada com outra região dentro da mesma área de soberania de dados (geografia). Pense nisso como um "parceiro de backup" para uma região inteira.  

- **Região soberanas do Azure:**  
    - **Serviços Governamentais dos EUA:** Atende necessidade de segurança e conformidade das agencias federeais, dos EUA.  
    - **Azure China:** Intancia fisicamente separada dos serviços de nuvem do azure operada peça 21vianet.

- **Recursos do Azuere:**
  - Maquinas Virtuais;
  - Contas de Armazenamento;
  - Redes Virtuais;
  - Serviços de Aplicativo;
  - Banco de dados SQL;
  - Funções;
           
- **Gupo de recursos:** Pense nele como uma pasta onde você armazena todos os componentes que compõem uma aplicação, um ambiente de trabalho específico ou um projeto. Em vez de gerenciar dezenas de recursos individualmente, você os coloca dentro de um Grupo de Recursos para gerenciá-los como uma unidade única.  
    - Os recursos podem exister em apenas um grupo de recursos;  
    - Os recursos podem existir em diferentes regiões;  
    - Os recursos podem ser movidos para diferentes grupos de recursos;  
    - OS aplicativos podem ultizar varios grupos de recursos;  

- **Assinatura do Azure:** Para cada conta do Azure podem ter quantas assinaturas puder, cada assinatura responde a uma unica conta.  
  - **Limite de cobrança:** Gera relatorio de cobrança e fatura separado para cada assinatura.  
  - **Limite de controle de acesso:** gerencia e controla o acesso aos recursos que os usuarios podem provisionar com assinatura especificas.
 
- **Grupos de Gerenciamento:** Organiza suas assinaturas (subscriptions), permitindo que você aplique políticas, controles de acesso e iniciativas de conformidade de forma centralizada e em larga escala.
    - Os grupos de gerenciamento podem incluir varias assinaturas do Azure;
    - As assinaturas herdam as condicoes aplicadas ao grupo de gerenciamento;
      
- **Serviço de computação Azure:** Serviço sob demanda fornece recursos de computação, como discos, processadores, memoria, rede e OS.

- **Maquinas virtuais do Azure:**  
    - São emulacoes de software de computadores fisicos;  
    - Inclui processador virtual, memoria, armazenamento e rede;  
    - Oferta Iaas que oferece personalização e controle total;  

- **Cojunto de dimensionamento de VMs:** Oferece uma oportunidade de balanceamento de carga para dimensionar os recursos automaticamente.

- **Conjuntos de disponivilidade de VM:** É uma configuração para garantir a alta disponibilidade de aplicações executadas em máquinas virtuais (VMs). Trata-se de um agrupamento lógico de duas ou mais VMs dentro de um mesmo datacenter do Azure, que as distribui de forma inteligente para protegê-las contra falhas de hardware e atualizações planejadas pela Microsoft.  

- **Area de trabalho virtual do Azure:** É uma virtualização de area de trbalho e aplicativo executada em nuvem.  

- **Serviços de conteineres do Azeure:** É um ambiente leve e virtualizado que nao exige o gerenciamento do OS e pode responder a alteracoes sob demanda.  
    - **Instancia de Conteriner Azure:** PaaS que executa um conteiner ou pod de conteineres dno azure, sem necessidade de uma VM;  
    - **Aplicativo de Conteriner Azure:** PaaS, como instancias de conterineres que pode balancer a carga e escalar;  
    - **Serviço de kubernetes do Azure:** Serviço de osquestração para contineres com arquiteturas distribuidas e grande volumes de conteineres;  

- **Azure Functions:** PaaS que da suporte a operecao de computacao sem servidor, evento é executado quando chamado sem exigir uma infraestrutura de servidor.  

-  **Comparar opçoes de computação Azure:**  
    - **Maquinas virtuais:**  
        - Servidor em nuvem suporte em ambientes Windows ou Linux;  
        -  Util para migração lift-and-shift para nuvem;  
        -  Pacote de OS completo;  
    -  **Area de trabalho virtual:**  
        -  Fornece uma area de trabalho do windows baseada em nuvem;  
        -  App dedicado para conexao e uso de qualquer navegador;  
        -  Logon de varios usuario no mesmo computador;  
    - **Conterineres:**  
        - Ambiente leve em miniatura adequado para execução de microserviço;  
        - Projetado para escabilidade e resiliencia por meio da orquestração;  
        - Varios conteineres podem ficar em um OS do host;  

- **Serviços de Aplicativos do Azure:** Uma plataforma totalmente gerenciada para croar, implantar e dimensionar aplicativos WEB e APIs rapidamente.  
    - Trabalha com .NET, .NET Core, Nodes.js, Java, Python ou php;  
    - PaaS;  

- **Serviço de rede do Azure:** A rede vistual do azure(VNet) permirte que os recursos Azure se comuniquem uns com outros com a internet e com redes locais.  
    - **Gateway de VPN:** É usada para enviar trafego criptografado entre uma rede virtual do Azure e uma no local pela internet publica;
    - **ExpressRoute:** Estende redes locais para o Azure por meio de um conexao privada facilitada por um provedor de conectividade;
    - **DNS do Azure:** É um serviço de hospedagem para domínios DNS que fornece a resolução de nomes de domínio para endereços IP, utilizando a infraestrutura global e robusta do Microsoft Azure;  
 
- **Contas de Armazenamento:**  
    - Nome exclusivo;  
    - Determinar os serviços de armazenamento e as opçoes de redundancia;
      
- **Redundancia de armazenamento:**  
    - **LRS:** É a opção mais básica e de menor custo. O Azure mantém três cópias dos seus dados de forma síncrona dentro de uma única instalação física (um único datacenter) na região primária. Cada cópia está em um rack de armazenamento e domínio de falha diferente.  
    - **ZRS:** Mantém três cópias dos seus dados de forma síncrona, mas distribuídas entre três Zonas de Disponibilidade diferentes dentro da mesma região primária. Cada Zona de Disponibilidade é um datacenter fisicamente separado com energia, refrigeração e rede independentes.  
    - **GRS:** É a evolução do LRS. Ele primeiro copia seus dados três vezes dentro de um único datacenter na região primária (como o LRS) e, em seguida, replica esses dados de forma assíncrona para um único datacenter na região secundária, onde também são mantidas três cópias. Total de seis cópias.  
    - **GZRS:** Combina o melhor dos dois mundos. Ele replica seus dados entre três Zonas de Disponibilidade na região primária (como o ZRS) e também replica os dados de forma assíncrona para um único local na região secundária.  

- **Serviço de Armazenamento:**  
    - **Blob do Azure:** Otimizado para armazenamento de quantidade massiva de dados nao estruturado, como texto ou dados binario;  
    - **Disco do Azure:** Fornece discos para maquinas virtuais, aplicativos e outros serviços;  
    - **Fila do Azure:** Serviço de armazenamento de mensagens que fornece armazenamento e recuperação para grande quantidades de mensagens;  
    - **Arquivos do Azure:** Configura um compartilhamento de arquivos de rede altamente disponivel que pode ser ultilizado usando o protoloco bloco de mensagens do servidor;  
    - **Tabelas do Azure:** Fornece uma opção de chave/atributo para armazenamento de dados estruturado nao relacionais com um design sem esquema;  

- **Pontos de extremidade publicos do serviço de Armazenamento:** são os nomes de host dos serviços, que permitem acesso público à conta de armazenamento na Internet.  
    - Serviço Blob     -      privatelink.**blob**.core.windows.net  
    - Data Lake Storage  -    privatelink.**dfs**.core.windows.net  
    - Serviço de arquivos  -  privatelink.**file**.core.windows.net  
    - Serviço Fila       -    privatelink.**queue**.core.windows.net  
    - Serviço Tabela     -    privatelink.**table**.core.windows.net  

- **Camadas de acesso de Armazenamento do Azure:**  
    - Frequente: Otimizado para uso de dados com acesso frequencia;  
    - Esporadico: Otimizado para uso de dados com menos frequencia por pelo menos 30 dias;  
    - Frio: Otimizado para uso de dados com pouca frequencia por pelo menos 90 dias;  
    - Arquivo morto: Otimizado para uso de dados raramente frequencia por pelo menos 180 dias com requisitos de latencia flexivel;  

- **Migrações para Azure:** Migrar uma infraestrutura On-premises para nuvem Azure.  
    - Plataforma unificada;  
    - Intervalo de ferramentas intregras e automomas;  
    - Avaliação e Migração de legado;  
      
- **Azure Data Box:** Usados para transferir grandes dados de um data-center on-premises para um nuvem da Azure.  
    - Armazena date 80TB;  
    - Move um backups de recuperacão;  
    - Proteje seus dados em um caixa robusta;

- **AzCopy:** É um utilitário de linha de comando que você pode usar para copiar blobs ou arquivos de ou para uma conta de armazenamento, somente para um lado.

- **Gerenciador de Armazenamento do Azure:** Mesma ultilidade do **AzCopy**, com interface grafica do usuario.

- **Sincronização de arquivos do Azure:** É um serviço para centralizar os compartilhamentos de arquivos de uma organização nos Arquivos do Azure, mantendo a flexibilidade, o desempenho e a compatibilidade de um servidor de arquivos do Windows, bidirecional.

- **Microsoft Entra ID:** É o serviço de gerencimaneto de identidades e acesso baseado em nuvem do Microsoft Azure.
    -   Garantir Autenticação;  
    -   Logon Unico(SSO);  
    -   Gerenciamento de aplicativos;  
    -   Negocios para Negocios(B2B) (login com gmail,linkid, etc;  
    -   Gerenciamento de dispositivos;  

- **Microsoft Entra Domain Services:** É um serviço de domínio gerenciado que permite a empresas usar recursos de autenticação e diretório, como ingresso no domínio, políticas de grupo, LDAP e autenticação Kerberos, para máquinas virtuais e aplicativos no Azure, sem a necessidade de implantar e gerenciar controladores de domínio tradicionais.  

- **Autenticação e Autorização:**  
    - Autenticação: Identifica a pessoa ou serviço buscando acesso a um recurso, solicitando credencial de acesso.  
    - Autorização: Determina o nivel de acesso a uma pessoa ou serviço, define quais dados eles podem acessar.  

- **Autentincação Multifator:** Fornce segurança adicional para identidades, exigindo dois ou mais elementos para autenticação.  

- **Autenticação B2B:** É o processo de verificar a identidade de usuários, sistemas e aplicativos de empresas parceiras para garantir que apenas pessoas e serviços autorizados acessem recursos e dados compartilhados, exemplo cadastro ou long usando gmail.   

- **Autenticação B2C:** Fornece a identidade de empresa para cliente como um serviço. Seus clientes podem usar as próprias identidades de conta social, empresarial ou local preferenciais para obter acesso de logon único a seus aplicativos e APIs.  

- **Acesso Condicional:** Em sua definição mais simples, as políticas de Acesso Condicional são instruções se-então, se um usuário quiser acessar um recurso, então ele deverá concluir uma ação. Por exemplo: se um usuário quiser acessar um aplicativo ou serviço como o Microsoft 365, ele deverá executar a autenticação multifator para obter acesso.  

- **Controle de acessso baseado em função:** É um método de segurança que gerencia quem pode acessar quais recursos em um sistema, atribuindo permissões de acesso a funções (cargos) específicas, em vez de indivíduos. Em vez de conceder permissões personalizadas, os usuários recebem uma ou mais funções, e as permissões são associadas a essas funções.

- **Cofiança Zero:** É um modelo de segurança que pressupõe violação e verifica cada solicitação como se tivesse se originado de uma rede descontrolada.

- **Microsoft Defender para Nuvem:** É um serviço de monitoramento que fornce proteção contra ameaças nos datacenters azure e locais.

- 
