# IBM Guardium Data Protection no NotebookLM

- **Contexto e Objetivos**
> Elaboração de um NotebookLM contendo materiais e informações sobre a solução de Segurança da Informação e Proteção de Dados que venho trabalhando em um grande cliente.

- **Curadoria de Fontes**
> https://www.ibm.com/products/guardium  
> https://www.ibm.com/docs/en/gdp/12.x   
> https://www.youtube.com/watch?v=AQbnPD10hJM  

- **Engenharia de Prompts e "Cicatrizes"**
<img width="898" height="732" alt="image" src="https://github.com/user-attachments/assets/b539677c-679d-48d4-882e-07c57ce95f32" />  
<img width="900" height="730" alt="image" src="https://github.com/user-attachments/assets/55677bd8-7a3e-4a86-913a-0a06cb2a4b80" />  
<img width="902" height="736" alt="image" src="https://github.com/user-attachments/assets/76756832-03bc-4915-b972-c2b9b21e8643" />  

- **Miniguia de Estudo (Entrega Final)**
<img width="907" height="861" alt="image" src="https://github.com/user-attachments/assets/f6529795-f807-47b9-bf17-92a3863b5700" />  

### Componentes e Arquitetura
*   **Agregador (Aggregator)**: Appliance que coleta e funde informações de múltiplos coletores para fornecer uma visão holística de todo o ambiente e gerar relatórios de nível empresarial.
*   **Central Manager (CM)**: O ponto central de administração que controla e monitora todo o ecossistema Guardium, incluindo coletores e agregadores, a partir de um único console.
*   **Coletor (Collector)**: Unidade responsável pela captura e análise em tempo real das atividades do banco de dados, aplicando políticas de segurança e gerando alertas.
*   **Edge Gateway**: Arquitetura moderna baseada em **Kubernetes** que processa e filtra o tráfego localmente próximo às fontes de dados, reduzindo a latência e os custos de largura de banda.
*   **GIM (Guardium Installation Manager)**: Ferramenta que automatiza a implantação, atualização e gerenciamento do ciclo de vida dos agentes (como o S-TAP) nos servidores de banco de dados.
*   **S-TAP (Software TAP)**: Agente leve instalado no servidor de banco de dados que intercepta a comunicação entre o motor do banco e seus clientes, enviando os dados para um coletor.

### Mecanismos de Monitoramento e Interceptação
*   **A-TAP (Application TAP)**: Agente de nível de aplicação utilizado para monitorar tráfego de banco de dados **criptografado** (como Oracle ou DB2) onde a decriptação ocorre dentro do processo do banco.
*   **CAS (Change Audit System)**: Agente que captura informações de auditoria de mudanças em arquivos de configuração, binários e variáveis de ambiente no servidor do banco de dados.
*   **K-TAP (Kernel TAP)**: Módulo de nível de kernel que "gancha" as comunicações de rede e locais (como memória compartilhada) para garantir visibilidade total do tráfego.
*   **Universal Connector**: Framework **sem agentes** que utiliza plugins para ingerir logs de auditoria nativos de fontes de nuvem (como AWS S3, Azure ou Snowflake) e normalizá-los para o Guardium.

### Módulos e Funcionalidades Principais
*   **Active Threat Analytics (ATA)**: Painel que utiliza **Inteligência Artificial** para detectar vetores de ataque avançados, como injeção de SQL, vazamento de dados e abuso de contas privilegiadas.
*   **Audit Process Builder**: Ferramenta de automação que gerencia todo o ciclo de auditoria, incluindo a geração de relatórios, distribuição para partes interessadas e captura de assinaturas eletrônicas.
*   **Compliance Hub**: Dashboard centralizado que oferece uma visão em tempo real da postura de conformidade da organização em relação a regulamentações como **GDPR, LGPD e PCI DSS**.
*   **Discovery and Classification (DDC)**: Funcionalidade que identifica dados sensíveis conhecidos e desconhecidos em repositórios estruturados e não estruturados através de varreduras automatizadas.
*   **Long-Term Log Retention (LTLR)**: Recurso que permite o armazenamento de logs de auditoria por longos períodos (7 a 10 anos) em armazenamento de objetos de baixo custo, mantendo-os pesquisáveis via SQL.
*   **Risk Spotter**: Motor de avaliação de risco dinâmico que analisa resultados de vulnerabilidades e dados de monitoramento para pontuar o nível de risco de usuários e instâncias de banco de dados.
*   **Vulnerability Assessment (VA)**: Módulo que detecta configurações incorretas, senhas fracas e falta de patches de segurança, comparando-os com benchmarks da indústria (como CIS e STIG).

### Ações de Política e Segurança
*   **Selective Audit**: Ação que registra comandos SQL específicos ou ações de usuários para fins de trilha de auditoria.
*   **Terminate**: Comando que encerra imediatamente uma sessão de banco de dados caso ocorra uma violação de política, prevenindo a exfiltração de dados.
*   **Masking/Redaction (Mascaramento)**: Técnica que oculta dados sensíveis em tempo real (ex: substituindo por asteriscos), permitindo que a aplicação funcione sem expor informações privadas.
*   **Quarentena**: Bloqueio temporário de um usuário ou sessão suspeita até que a atividade seja revisada por um analista de segurança.

<img width="5363" height="7336" alt="NotebookLM Mind Map" src="https://github.com/user-attachments/assets/ce0cad3c-a379-4630-97bd-fa3250036729" />
