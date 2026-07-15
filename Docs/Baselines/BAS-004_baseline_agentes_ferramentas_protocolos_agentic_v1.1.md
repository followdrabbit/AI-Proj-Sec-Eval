# BAS-004 — Baseline de Controles Técnicos para Agentes, Ferramentas e Protocolos Agentic

| Campo | Valor |
|---|---|
| **Código** | BAS-004 |
| **Nome** | Baseline de Controles Técnicos para Agentes, Ferramentas e Protocolos Agentic |
| **Tipo documental** | Baseline técnico |
| **Classificação da informação** | Uso Interno |
| **Status** | Minuta para revisão |
| **Versão** | 1.1 |
| **Data** | 13/07/2026 |
| **Owner institucional** | Segurança da Informação / Segurança de IA |
| **Custodiante técnico** | Arquitetura de Segurança da Informação / IAM-PAM / AppSec |
| **Quantidade de controles** | 48 |

## 1. Objetivo

Estabelecer recomendações técnicas mínimas, verificáveis e auditáveis para agentes de IA, ferramentas, capabilities, tool calling, function calling, actions, plugins, skills, computer use, automações locais, integrações agentic e protocolos de interoperabilidade como MCP. O documento segue a estrutura de recomendações dos CIS Benchmarks e contém somente controles técnicos. Fluxos de aprovação, homologação, exceção, RACI, contratação e resposta processual estão fora do escopo.

## 2. Escopo

Aplica-se a agentes conversacionais e operacionais, planners, executors, orquestradores multiagente, tools, functions, plugins, actions, skills, clientes e servidores MCP, registries, prompts, resources, computer use, browser agents, terminal agents, IDE agents e tecnologias equivalentes. Este baseline não deve ser aplicado isoladamente: BAS-001, BAS-002 e BAS-003 permanecem aplicáveis, e os demais baselines especializados devem ser combinados cumulativamente conforme a arquitetura avaliada.

## 3. Modelo de classificação

### 3.1 Profile Applicability

- **Level 1:** configuração técnica fundamental para qualquer implementação agentic ou MCP no escopo.
- **Level 2:** defesa em profundidade para agentes autônomos, ações materiais, ambientes críticos, múltiplos tenants, computer use ou integrações privilegiadas. Pressupõe conformidade com os controles Level 1 aplicáveis.

### 3.2 Criticidade

| Criticidade | Critério |
|---|---|
| **Crítica** | A ausência permite execução indevida, elevação de privilégio, vazamento, comprometimento do host, bypass de autorização ou ação material não contida. |
| **Alta** | A ausência enfraquece significativamente isolamento, integridade, rastreabilidade, contenção ou controle da autonomia. |
| **Média** | Controle de hardening cuja ausência normalmente exige outra falha para produzir impacto material. Esta versão não contém recomendações de criticidade Média. |
| **Baixa** | Otimização técnica com impacto limitado. Esta versão não contém recomendações de criticidade Baixa. |

## 4. Regras de interpretação

1. BAS-001, BAS-002 e BAS-003 são pré-requisitos quando aplicáveis aos componentes cobertos por este documento.
2. Cada recomendação deve ser avaliada de forma independente.
3. Um controle é **Conforme** somente quando todos os critérios descritos em **Audit** forem atendidos.
4. Implementação parcial deve ser registrada como **Não Conforme**; não existe conformidade parcial neste baseline.
5. Quando uma recomendação não se aplicar tecnicamente, a justificativa deve indicar a capability, integração ou comportamento inexistente.
6. Aprovações, pareceres, prompts e instruções ao modelo não substituem enforcement técnico.

## Sumário

- [1. Identidades agentic e contexto de execução](#1-identidades-agentic-e-contexto-de-execucao)
  - [1.1 Certifique-se de que cada agente possua identidade técnica exclusiva e não reutilizada](#11-certifique-se-de-que-cada-agente-possua-identidade-tecnica-exclusiva-e-nao-reutilizada)
  - [1.2 Certifique-se de que credenciais não sejam compartilhadas entre agentes, usuários e operadores](#12-certifique-se-de-que-credenciais-nao-sejam-compartilhadas-entre-agentes-usuarios-e-operadores)
  - [1.3 Certifique-se de que a identidade efetiva do solicitante acompanhe toda ação executada pelo agente](#13-certifique-se-de-que-a-identidade-efetiva-do-solicitante-acompanhe-toda-acao-executada-pelo-agente)
  - [1.4 Certifique-se de que planejamento e execução utilizem contextos de privilégio segregados](#14-certifique-se-de-que-planejamento-e-execucao-utilizem-contextos-de-privilegio-segregados)
  - [1.5 Certifique-se de que credenciais do agente sejam temporárias e vinculadas à execução](#15-certifique-se-de-que-credenciais-do-agente-sejam-temporarias-e-vinculadas-a-execucao)
  - [1.6 Certifique-se de que execução anônima ou com privilégio implícito esteja desabilitada](#16-certifique-se-de-que-execucao-anonima-ou-com-privilegio-implicito-esteja-desabilitada)
- [2. Registro, integridade e schemas de tools](#2-registro-integridade-e-schemas-de-tools)
  - [2.1 Certifique-se de que o agente somente possa invocar tools explicitamente allowlisted](#21-certifique-se-de-que-o-agente-somente-possa-invocar-tools-explicitamente-allowlisted)
  - [2.2 Certifique-se de que definições de tools e capabilities utilizem versões imutáveis](#22-certifique-se-de-que-definicoes-de-tools-e-capabilities-utilizem-versoes-imutaveis)
  - [2.3 Certifique-se de que entradas de tools sejam validadas por schema estrito](#23-certifique-se-de-que-entradas-de-tools-sejam-validadas-por-schema-estrito)
  - [2.4 Certifique-se de que saídas de tools sejam validadas antes de retornarem ao agente](#24-certifique-se-de-que-saidas-de-tools-sejam-validadas-antes-de-retornarem-ao-agente)
  - [2.5 Certifique-se de que registro e descoberta dinâmica de tools estejam desabilitados por padrão](#25-certifique-se-de-que-registro-e-descoberta-dinamica-de-tools-estejam-desabilitados-por-padrao)
  - [2.6 Certifique-se de que cada tool declare metadados técnicos mínimos e efeitos colaterais](#26-certifique-se-de-que-cada-tool-declare-metadados-tecnicos-minimos-e-efeitos-colaterais)
- [3. Autorização determinística e limites de ação](#3-autorizacao-deterministica-e-limites-de-acao)
  - [3.1 Certifique-se de que toda ação material seja autorizada por mecanismo independente do modelo](#31-certifique-se-de-que-toda-acao-material-seja-autorizada-por-mecanismo-independente-do-modelo)
  - [3.2 Certifique-se de que o sistema-alvo valide a autorização da ação](#32-certifique-se-de-que-o-sistema-alvo-valide-a-autorizacao-da-acao)
  - [3.3 Certifique-se de que permissões de tools utilizem default deny e menor privilégio por ação e recurso](#33-certifique-se-de-que-permissoes-de-tools-utilizem-default-deny-e-menor-privilegio-por-acao-e-recurso)
  - [3.4 Certifique-se de que ações irreversíveis ou de alto impacto exijam confirmação humana explícita](#34-certifique-se-de-que-acoes-irreversiveis-ou-de-alto-impacto-exijam-confirmacao-humana-explicita)
  - [3.5 Certifique-se de que valores, volumes e frequência de ações possuam limites técnicos](#35-certifique-se-de-que-valores-volumes-e-frequencia-de-acoes-possuam-limites-tecnicos)
  - [3.6 Certifique-se de que ações mutáveis possuam idempotência e proteção contra replay](#36-certifique-se-de-que-acoes-mutaveis-possuam-idempotencia-e-protecao-contra-replay)
- [4. Segurança de clientes, servidores e registries MCP](#4-seguranca-de-clientes-servidores-e-registries-mcp)
  - [4.1 Certifique-se de que somente clientes e servidores MCP allowlisted possam estabelecer sessão](#41-certifique-se-de-que-somente-clientes-e-servidores-mcp-allowlisted-possam-estabelecer-sessao)
  - [4.2 Certifique-se de que clientes e servidores MCP utilizem autenticação mútua](#42-certifique-se-de-que-clientes-e-servidores-mcp-utilizem-autenticacao-mutua)
  - [4.3 Certifique-se de que metadados do registry MCP possuam integridade verificável](#43-certifique-se-de-que-metadados-do-registry-mcp-possuam-integridade-verificavel)
  - [4.4 Certifique-se de que autorização MCP seja aplicada por capability, resource e operação](#44-certifique-se-de-que-autorizacao-mcp-seja-aplicada-por-capability-resource-e-operacao)
  - [4.5 Certifique-se de que sessões e namespaces MCP estejam isolados por tenant e contexto](#45-certifique-se-de-que-sessoes-e-namespaces-mcp-estejam-isolados-por-tenant-e-contexto)
  - [4.6 Certifique-se de que versões de protocolo e schemas MCP sejam fixadas e desconhecidos falhem de forma segura](#46-certifique-se-de-que-versoes-de-protocolo-e-schemas-mcp-sejam-fixadas-e-desconhecidos-falhem-de-forma-segura)
- [5. Proteção contra instruções e capabilities adversariais](#5-protecao-contra-instrucoes-e-capabilities-adversariais)
  - [5.1 Certifique-se de que saídas de tools, resources e prompts MCP sejam tratadas como conteúdo não confiável](#51-certifique-se-de-que-saidas-de-tools-resources-e-prompts-mcp-sejam-tratadas-como-conteudo-nao-confiavel)
  - [5.2 Certifique-se de que instruções de controle e dados externos permaneçam em canais separados](#52-certifique-se-de-que-instrucoes-de-controle-e-dados-externos-permanecam-em-canais-separados)
  - [5.3 Certifique-se de que descrições de tools, prompts e resources sejam inspecionadas contra instruções ocultas](#53-certifique-se-de-que-descricoes-de-tools-prompts-e-resources-sejam-inspecionadas-contra-instrucoes-ocultas)
  - [5.4 Certifique-se de que o agente valide o vínculo entre capability, endpoint e sistema-alvo](#54-certifique-se-de-que-o-agente-valide-o-vinculo-entre-capability-endpoint-e-sistema-alvo)
  - [5.5 Certifique-se de que pacotes e implementações de tools tenham integridade verificada antes do carregamento](#55-certifique-se-de-que-pacotes-e-implementacoes-de-tools-tenham-integridade-verificada-antes-do-carregamento)
  - [5.6 Certifique-se de que conteúdo externo não possa ampliar tools, escopos ou privilégios do agente](#56-certifique-se-de-que-conteudo-externo-nao-possa-ampliar-tools-escopos-ou-privilegios-do-agente)
- [6. Sandbox, host, navegador e computer use](#6-sandbox-host-navegador-e-computer-use)
  - [6.1 Certifique-se de que agentes com execução de código ou computer use operem em ambiente isolado](#61-certifique-se-de-que-agentes-com-execucao-de-codigo-ou-computer-use-operem-em-ambiente-isolado)
  - [6.2 Certifique-se de que o acesso do agente ao filesystem utilize allowlist de caminhos e operações](#62-certifique-se-de-que-o-acesso-do-agente-ao-filesystem-utilize-allowlist-de-caminhos-e-operacoes)
  - [6.3 Certifique-se de que o tráfego de saída do agente utilize allowlist de destinos](#63-certifique-se-de-que-o-trafego-de-saida-do-agente-utilize-allowlist-de-destinos)
  - [6.4 Certifique-se de que comandos, executáveis e intérpretes disponíveis ao agente sejam allowlisted](#64-certifique-se-de-que-comandos-executaveis-e-interpretes-disponiveis-ao-agente-sejam-allowlisted)
  - [6.5 Certifique-se de que automação de navegador seja restrita a domínios e ações permitidos](#65-certifique-se-de-que-automacao-de-navegador-seja-restrita-a-dominios-e-acoes-permitidos)
  - [6.6 Certifique-se de que credenciais e sessões do host não sejam acessíveis ao runtime agentic](#66-certifique-se-de-que-credenciais-e-sessoes-do-host-nao-sejam-acessiveis-ao-runtime-agentic)
- [7. Memória, delegação e comunicação entre agentes](#7-memoria-delegacao-e-comunicacao-entre-agentes)
  - [7.1 Certifique-se de que memória agentic seja segregada por usuário, tenant, agente e sessão](#71-certifique-se-de-que-memoria-agentic-seja-segregada-por-usuario-tenant-agente-e-sessao)
  - [7.2 Certifique-se de que memórias possuam TTL e limites de volume configurados](#72-certifique-se-de-que-memorias-possuam-ttl-e-limites-de-volume-configurados)
  - [7.3 Certifique-se de que gravações em memória sejam validadas e saneadas](#73-certifique-se-de-que-gravacoes-em-memoria-sejam-validadas-e-saneadas)
  - [7.4 Certifique-se de que segredos e credenciais não sejam persistidos em memória do agente](#74-certifique-se-de-que-segredos-e-credenciais-nao-sejam-persistidos-em-memoria-do-agente)
  - [7.5 Certifique-se de que mensagens entre agentes sejam autenticadas, íntegras e não reutilizáveis](#75-certifique-se-de-que-mensagens-entre-agentes-sejam-autenticadas-integras-e-nao-reutilizaveis)
  - [7.6 Certifique-se de que delegações mantenham limites imutáveis de autoridade](#76-certifique-se-de-que-delegacoes-mantenham-limites-imutaveis-de-autoridade)
- [8. Observabilidade agentic e comportamento fail-safe](#8-observabilidade-agentic-e-comportamento-fail-safe)
  - [8.1 Certifique-se de que toda cadeia de ação do agente seja registrada de ponta a ponta](#81-certifique-se-de-que-toda-cadeia-de-acao-do-agente-seja-registrada-de-ponta-a-ponta)
  - [8.2 Certifique-se de que um identificador de correlação una usuário, agente, modelo, tool e sistema-alvo](#82-certifique-se-de-que-um-identificador-de-correlacao-una-usuario-agente-modelo-tool-e-sistema-alvo)
  - [8.3 Certifique-se de que exista mecanismo técnico de interrupção imediata das ações do agente](#83-certifique-se-de-que-exista-mecanismo-tecnico-de-interrupcao-imediata-das-acoes-do-agente)
  - [8.4 Certifique-se de que execuções possuam limites de iterações, tempo, tokens e chamadas de tools](#84-certifique-se-de-que-execucoes-possuam-limites-de-iteracoes-tempo-tokens-e-chamadas-de-tools)
  - [8.5 Certifique-se de que indisponibilidade de autorização, registry ou validação resulte em falha fechada](#85-certifique-se-de-que-indisponibilidade-de-autorizacao-registry-ou-validacao-resulte-em-falha-fechada)
  - [8.6 Certifique-se de que padrões anômalos de falha ou negação suspendam novas ações](#86-certifique-se-de-que-padroes-anomalos-de-falha-ou-negacao-suspendam-novas-acoes)

## 1. Identidades agentic e contexto de execução

Controles para identidade exclusiva, propagação do subject, credenciais temporárias e segregação entre planejamento e execução.

### 1.1 Certifique-se de que cada agente possua identidade técnica exclusiva e não reutilizada

**Control ID:** BAS-004.1.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes, orquestradores agentic, workers de execução e runtimes que acessem dados, tools ou sistemas corporativos.

**Description**

Cada agente implantado deve utilizar identidade técnica exclusiva por aplicação e ambiente. A identidade deve ser distinguível de identidades humanas, não pode ser compartilhada com outro agente e deve permanecer associada ao identificador e à versão do agente nos registros de autenticação.

**Rationale**

Identidades compartilhadas impedem atribuição de ações, ampliam o impacto do comprometimento e tornam inviável revogar somente o agente afetado.

**Impact**

A implementação aumenta a quantidade de identidades, roles e políticas a serem mantidas.

**Audit**

1. Enumerar todos os agentes e workers ativos em cada ambiente.
2. Comparar o inventário com as identidades técnicas configuradas e confirmar relação de um para um entre agente/aplicação/ambiente e identidade.
3. Confirmar que a identidade aparece nos logs de autenticação e que não é utilizada por processos não relacionados.
4. Reprovar se dois agentes independentes ou ambientes distintos utilizarem a mesma conta, principal, client ID, role ou chave.

**Remediation**

Criar identidade técnica exclusiva para cada agente e ambiente, migrar permissões mínimas e revogar credenciais compartilhadas.

**Evidence**

Inventário de agentes, exportação de identidades e correlação de autenticações por agente e ambiente.

**Mappings**

CIS Controls v8 5, 6 e 8; NIST SP 800-53 AC-2, IA-4, IA-5; NIST AI RMF GOVERN

---

### 1.2 Certifique-se de que credenciais não sejam compartilhadas entre agentes, usuários e operadores

**Control ID:** BAS-004.1.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes que utilizem API keys, tokens, certificados, secrets, sessões ou credenciais de sistema operacional.

**Description**

Credenciais atribuídas ao agente não podem ser utilizadas por pessoas, outros agentes, pipelines ou tarefas administrativas. Credenciais humanas, pessoais ou de operador não podem ser armazenadas ou reutilizadas pelo runtime agentic.

**Rationale**

O compartilhamento transfere privilégios entre contextos, dificulta rotação e permite que ações do agente sejam atribuídas incorretamente a uma pessoa.

**Impact**

Pode exigir criação de credenciais e políticas específicas para integrações legadas.

**Audit**

1. Listar os secrets e credenciais referenciados pelo agente.
2. Consultar consumidores, bindings ou acessos de cada credencial e confirmar que somente o principal esperado a utiliza.
3. Pesquisar credenciais pessoais, tokens de usuário e sessões interativas nos arquivos, variáveis e cofres do agente.
4. Reprovar se uma credencial possuir consumidores de naturezas distintas ou se o agente executar com sessão pessoal de usuário.

**Remediation**

Substituir credenciais compartilhadas por identidades de workload, revogar tokens pessoais e restringir cada secret ao principal técnico correspondente.

**Evidence**

Exportação de consumers/bindings do cofre, configuração do runtime e varredura sem tokens pessoais.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-2, IA-5; Zero Trust principles

---

### 1.3 Certifique-se de que a identidade efetiva do solicitante acompanhe toda ação executada pelo agente

**Control ID:** BAS-004.1.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes que operem em nome de usuário, sistema, serviço, fila, evento ou processo de negócio.

**Description**

Cada plano, chamada de tool e ação em sistema-alvo deve transportar um subject imutável que identifique o solicitante original, além da identidade técnica do agente. Quando não houver solicitante humano, o subject deve identificar o sistema ou evento originador. O subject não pode ser definido ou alterado pelo modelo.

**Rationale**

Sem identidade originadora, o agente pode executar com privilégio próprio desvinculado da autoridade do solicitante, inviabilizando autorização e investigação.

**Impact**

Integrações podem precisar adotar token exchange, delegation claims ou cabeçalhos assinados.

**Audit**

1. Iniciar execuções por dois usuários com permissões diferentes e por um processo sistêmico.
2. Rastrear cada chamada até o sistema-alvo e confirmar presença da identidade do agente e do subject originador.
3. Tentar alterar o subject por prompt, parâmetro de tool ou mensagem intermediária; o valor deve permanecer derivado de contexto autenticado.
4. Reprovar se a ação chegar ao sistema-alvo somente com a identidade do agente ou se o modelo puder escolher o subject.

**Remediation**

Implementar propagação de identidade autenticada por token exchange ou claims assinadas e impedir que prompts e tools sobrescrevam o subject.

**Evidence**

Capturas de token/claims mascaradas, logs ponta a ponta e resultados de teste com usuários de permissões distintas.

**Mappings**

CIS Controls v8 6 e 8; NIST SP 800-53 AC-3, AC-4, IA-2; Zero Trust principles

---

### 1.4 Certifique-se de que planejamento e execução utilizem contextos de privilégio segregados

**Control ID:** BAS-004.1.4
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Agentes com etapa de planejamento, reflexão, roteamento ou geração de plano separada da execução de tools.

**Description**

O componente que gera ou revisa o plano não deve possuir credenciais capazes de executar ações materiais. Somente o executor controlado pode acessar tools, e deve receber uma representação estruturada e validada da ação, não texto livre do planejamento.

**Rationale**

Comprometimento do modelo de planejamento ou prompt injection não deve conceder acesso direto aos sistemas-alvo.

**Impact**

A segregação adiciona componentes e pode aumentar latência e complexidade de integração.

**Audit**

1. Revisar arquitetura, identidades e bindings dos componentes de planejamento e execução.
2. Confirmar que a identidade do planner não possui permissão de invocar tools materiais ou acessar sistemas-alvo.
3. Tentar chamar uma tool diretamente a partir do planner; a operação deve ser negada.
4. Reprovar se o mesmo processo, identidade ou token puder planejar e executar sem um ponto intermediário de validação.

**Remediation**

Separar planner e executor em processos ou identidades distintas, remover credenciais do planner e validar planos estruturados antes da execução.

**Evidence**

Diagrama de componentes, matrizes de acesso e teste negativo de invocação pelo planner.

**Mappings**

CIS Controls v8 4, 5 e 6; NIST SP 800-53 AC-5, AC-6, SC-2

---

### 1.5 Certifique-se de que credenciais do agente sejam temporárias e vinculadas à execução

**Control ID:** BAS-004.1.5
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Agentes com acesso a sistemas críticos, dados sensíveis, produção ou ações privilegiadas.

**Description**

Credenciais de execução devem ser emitidas sob demanda, possuir tempo de vida limitado e ser vinculadas ao agente, ambiente, subject, escopo e identificador da execução. Tokens estáticos ou de longa duração não atendem ao controle para ações materiais.

**Rationale**

Credenciais persistentes roubadas permitem uso fora do contexto e por período prolongado, mesmo após o término da execução.

**Impact**

Pode exigir federação, STS, workload identity ou broker de credenciais.

**Audit**

1. Capturar metadados de tokens emitidos para amostra de execuções.
2. Confirmar TTL definido, audience restrita, subject/agente, escopo e execution ID.
3. Após o encerramento ou expiração, tentar reutilizar o token; a operação deve ser negada.
4. Reprovar se o agente armazenar chave estática com acesso material ou token reutilizável entre execuções não relacionadas.

**Remediation**

Substituir chaves estáticas por credenciais federadas ou temporárias, limitar audience/escopo e revogar tokens ao finalizar a execução.

**Evidence**

Claims de tokens mascaradas, configuração de emissão e teste de reutilização bloqueada.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 IA-5, AC-12; Zero Trust principles

---

### 1.6 Certifique-se de que execução anônima ou com privilégio implícito esteja desabilitada

**Control ID:** BAS-004.1.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Runtimes agentic, endpoints de agentes, workers, filas, schedulers e interfaces de tool calling.

**Description**

Toda execução deve ser iniciada por identidade autenticada e contexto de autorização explícito. Anonymous access, credenciais padrão, execução como conta do host ou herança automática de privilégios do operador devem permanecer desabilitados.

**Rationale**

Execuções sem identidade ou com privilégio implícito podem acessar recursos sem responsabilização e escapar de políticas por subject.

**Impact**

Integrações antigas ou tarefas locais podem precisar de identidade técnica dedicada.

**Audit**

1. Enumerar endpoints, filas, triggers e formas de iniciar o agente.
2. Confirmar que nenhuma rota aceita execução anônima ou sem principal resolvido.
3. Executar tentativa sem credencial, com credencial inválida e a partir de usuário local comum; todas devem ser negadas.
4. Reprovar se o agente herdar automaticamente a sessão do host, IDE, navegador ou operador sem política explícita.

**Remediation**

Exigir autenticação em todos os triggers, criar identidades técnicas para tarefas locais e desabilitar herança implícita de sessões e contas do host.

**Evidence**

Configuração dos endpoints/triggers e resultados de tentativas anônimas bloqueadas.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-3, IA-2; OWASP API Security

---

## 2. Registro, integridade e schemas de tools

Controles para allowlist, versionamento, metadados e validação estrita de entradas e saídas de tools e capabilities.

### 2.1 Certifique-se de que o agente somente possa invocar tools explicitamente allowlisted

**Control ID:** BAS-004.2.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes com tool calling, function calling, plugins, actions, skills, conectores, comandos ou capabilities.

**Description**

O runtime deve carregar tools a partir de allowlist explícita por agente e ambiente. Toda tool não listada deve ser negada, mesmo que seja descoberta, sugerida por conteúdo externo ou conhecida pelo modelo. Wildcards e carregamento arbitrário por nome ou URL não atendem ao controle.

**Rationale**

Tools não aprovadas podem ampliar a superfície de ação, acessar dados indevidos ou executar código sem avaliação.

**Impact**

Novas capacidades exigirão cadastro técnico antes do uso.

**Audit**

1. Exportar a lista efetiva de tools disponível ao agente.
2. Comparar com a allowlist configurada e confirmar correspondência exata.
3. Solicitar por prompt uma tool inexistente ou não aprovada; a chamada deve ser rejeitada antes da resolução.
4. Reprovar se o agente aceitar tool por nome arbitrário, URL, pacote, extensão ou descoberta não cadastrada.

**Remediation**

Configurar allowlist por agente/ambiente, remover wildcards e bloquear resolução ou carregamento de tools não cadastradas.

**Evidence**

Configuração da allowlist, exportação das tools efetivas e teste negativo com tool não permitida.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 CM-7, AC-6; OWASP GenAI Security Project

---

### 2.2 Certifique-se de que definições de tools e capabilities utilizem versões imutáveis

**Control ID:** BAS-004.2.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Tools, plugins, functions, skills, actions e capabilities mantidos em código, registry ou plataforma.

**Description**

Cada definição deve possuir identificador e versão imutáveis. O agente não pode usar aliases mutáveis como latest, current ou default em produção. Alteração de nome, descrição, schema, endpoint, permissões ou efeitos deve gerar nova versão.

**Rationale**

Mudanças silenciosas alteram o comportamento permitido sem modificar a configuração do agente e impedem reproduzir ações.

**Impact**

O versionamento pode exigir coexistência temporária de versões e atualização explícita dos agentes.

**Audit**

1. Consultar as versões das tools configuradas nos agentes produtivos.
2. Confirmar ausência de aliases mutáveis e presença de versão explícita.
3. Alterar uma definição em ambiente de teste e verificar que a versão anterior permanece imutável.
4. Reprovar se uma publicação puder substituir conteúdo de versão já referenciada por agente produtivo.

**Remediation**

Adotar versionamento imutável, pin de versão por agente e impedir sobrescrita de artefatos publicados.

**Evidence**

Exportação do registry, histórico de versões e teste de imutabilidade.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 CM-2, CM-3, SI-7

---

### 2.3 Certifique-se de que entradas de tools sejam validadas por schema estrito

**Control ID:** BAS-004.2.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Toda tool ou capability que receba argumentos gerados ou selecionados por modelo.

**Description**

A entrada deve ser validada contra schema fechado que defina tipos, formatos, enumerações, limites, campos obrigatórios, tamanho máximo e rejeição de propriedades adicionais. Texto livre não pode ser repassado diretamente a comandos, SQL, paths, URLs ou APIs sensíveis.

**Rationale**

Argumentos produzidos pelo modelo podem conter injeções, valores fora de faixa ou parâmetros não previstos que alterem a operação.

**Impact**

Schemas estritos podem exigir normalização e atualização quando a interface evoluir.

**Audit**

1. Revisar schemas de todas as tools materiais.
2. Testar campo adicional, tipo incorreto, valor fora da enumeração, tamanho acima do limite e caracteres de controle.
3. Confirmar que todos os casos são rejeitados antes da chamada ao sistema-alvo.
4. Reprovar se a validação ocorrer somente após construir comando, query ou requisição final.

**Remediation**

Definir schemas fechados, limites e validação antes da execução. Substituir texto livre por parâmetros estruturados e APIs parametrizadas.

**Evidence**

Schemas, logs de validação e conjunto de payloads inválidos rejeitados.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 SI-10; OWASP Injection Prevention

---

### 2.4 Certifique-se de que saídas de tools sejam validadas antes de retornarem ao agente

**Control ID:** BAS-004.2.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Tools que retornem dados, status, arquivos, referências, mensagens ou conteúdo utilizado em novas decisões do agente.

**Description**

A resposta deve ser validada por schema, tamanho, tipo, status e campos esperados. Conteúdo inesperado, campos extras, HTML/script, instruções ou payloads acima do limite devem ser removidos ou bloquear a resposta. Erros não podem ser convertidos silenciosamente em sucesso.

**Rationale**

Saídas comprometidas ou malformadas podem injetar instruções no agente, causar decisões incorretas ou ocultar falhas.

**Impact**

A validação pode descartar campos úteis que não estejam formalizados no contrato.

**Audit**

1. Revisar os contratos de resposta das tools.
2. Simular resposta com campo extra, status conflitante, conteúdo ativo, instrução embutida e tamanho excessivo.
3. Confirmar bloqueio ou saneamento antes de a resposta entrar no contexto do modelo.
4. Reprovar se resposta não validada for concatenada diretamente ao prompt ou memória.

**Remediation**

Criar schemas de saída, validar status e payload, remover conteúdo ativo e limitar tamanho antes de retornar ao agente.

**Evidence**

Schemas de resposta e resultados de testes com payloads malformados ou adversariais.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 SI-10, SI-11; OWASP GenAI Security Project

---

### 2.5 Certifique-se de que registro e descoberta dinâmica de tools estejam desabilitados por padrão

**Control ID:** BAS-004.2.5
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Plataformas que suportem plugins, skills, registries, marketplace, MCP discovery ou registro em tempo de execução.

**Description**

O agente não deve registrar, instalar ou habilitar novas tools durante a execução. Discovery deve consultar registry controlado e retornar somente capabilities previamente vinculadas ao agente. Registro dinâmico por usuário, documento, URL, repositório ou resposta do modelo deve ser negado.

**Rationale**

Registro dinâmico permite que conteúdo adversarial introduza uma capability não avaliada ou substitua uma existente.

**Impact**

Reduz flexibilidade para agentes que criam integrações ad hoc.

**Audit**

1. Revisar configurações de plugin/skill discovery e permissões de registro.
2. Tentar registrar tool durante uma sessão do agente e por identidade de runtime; a operação deve ser negada.
3. Publicar capability não vinculada no registry e confirmar que ela não é descoberta pelo agente.
4. Reprovar se o modelo, usuário ou documento puder adicionar tool à sessão sem mudança técnica controlada.

**Remediation**

Desabilitar auto-install e registro em runtime, restringir permissões de registry e vincular explicitamente capabilities por agente.

**Evidence**

Configuração da plataforma, políticas do registry e testes de registro/descoberta bloqueados.

**Mappings**

CIS Controls v8 2, 4 e 6; NIST SP 800-53 CM-7, AC-6; Supply chain security principles

---

### 2.6 Certifique-se de que cada tool declare metadados técnicos mínimos e efeitos colaterais

**Control ID:** BAS-004.2.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Todas as tools e capabilities disponíveis a agentes.

**Description**

A definição deve conter ID, versão, endpoint ou executor, sistema-alvo, operações permitidas, recursos acessados, escopos necessários, classificação dos dados, efeitos colaterais, reversibilidade, idempotência, limites e owner técnico. Definições incompletas não podem ser publicadas no registry.

**Rationale**

Sem metadados, o runtime não consegue aplicar políticas proporcionais ao efeito e revisores não conseguem determinar o impacto real da capability.

**Impact**

Exige manutenção de schemas e atualização quando a implementação muda.

**Audit**

1. Exportar todas as definições do registry.
2. Validar presença e preenchimento dos campos obrigatórios.
3. Tentar publicar definição sem efeito colateral, owner ou escopo; a publicação deve falhar.
4. Reprovar se ferramentas materiais estiverem descritas apenas por texto livre sem atributos estruturados.

**Remediation**

Definir schema obrigatório do registry, bloquear publicação incompleta e atualizar tools existentes com metadados técnicos.

**Evidence**

Schema do registry, exportação das definições e teste de publicação incompleta bloqueada.

**Mappings**

CIS Controls v8 1, 2 e 4; NIST SP 800-53 CM-8, CM-7; NIST AI RMF MAP

---

## 3. Autorização determinística e limites de ação

Controles para separar inferência de autorização, aplicar menor privilégio, confirmação contextual, limites e proteção contra replay.

### 3.1 Certifique-se de que toda ação material seja autorizada por mecanismo independente do modelo

**Control ID:** BAS-004.3.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Tools que criem, alterem, excluam, transmitam, aprovem, executem ou comprometam recursos, dados ou transações.

**Description**

Antes da execução, um policy enforcement point determinístico deve autorizar subject, agente, tool, operação, recurso, contexto e limites. Texto do prompt, decisão do modelo, chain-of-thought, score ou confirmação inferida não constituem autorização.

**Rationale**

Modelos podem ser manipulados, errar ou interpretar instruções de forma inesperada; permitir que a inferência autorize ações elimina a separação entre decisão probabilística e controle de acesso.

**Impact**

Pode exigir integração com IAM, policy engine ou serviço de autorização.

**Audit**

1. Selecionar amostra de ações materiais e identificar o ponto de autorização externo ao modelo.
2. Executar a mesma ação com subject permitido e não permitido.
3. Confirmar que o caso não permitido é bloqueado antes de atingir o sistema-alvo, independentemente do texto produzido pelo modelo.
4. Reprovar se uma instrução no prompt, system prompt ou output do modelo puder dispensar a autorização.

**Remediation**

Adicionar policy enforcement determinístico antes da execução e remover qualquer caminho que trate a decisão do modelo como autorização.

**Evidence**

Arquitetura de autorização, políticas e testes positivos/negativos com subjects distintos.

**Mappings**

CIS Controls v8 6; NIST SP 800-53 AC-3, AC-6; Zero Trust principles

---

### 3.2 Certifique-se de que o sistema-alvo valide a autorização da ação

**Control ID:** BAS-004.3.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes que chamem APIs, bancos, filas, e-mail, sistemas de negócio, infraestrutura ou endpoints externos.

**Description**

O sistema-alvo deve validar a identidade e a autorização recebidas; a tool ou agente não pode ser o único componente que decide o acesso. Credenciais onipotentes usadas pela tool para executar qualquer solicitação não atendem ao controle.

**Rationale**

Se o sistema-alvo confiar integralmente na tool, o comprometimento da camada agentic permite bypass de controles de negócio e acesso amplo.

**Impact**

Sistemas legados podem precisar de proxy, facade ou policy enforcement adicional.

**Audit**

1. Revisar o mecanismo de autenticação e autorização no sistema-alvo.
2. Tentar chamar diretamente o endpoint-alvo com parâmetros equivalentes e subject sem permissão.
3. Confirmar que o próprio sistema-alvo ou proxy de enforcement nega a operação.
4. Reprovar se a tool utilizar credencial ampla e o alvo aceitar qualquer operação sem validar subject, recurso e ação.

**Remediation**

Implementar autorização no alvo ou proxy confiável, reduzir permissões da credencial da tool e transmitir claims verificáveis do subject.

**Evidence**

Configuração do alvo, políticas e teste direto de operação não autorizada bloqueada.

**Mappings**

CIS Controls v8 6 e 16; NIST SP 800-53 AC-3, AC-4; OWASP API Security

---

### 3.3 Certifique-se de que permissões de tools utilizem default deny e menor privilégio por ação e recurso

**Control ID:** BAS-004.3.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes e tools com acesso a sistemas corporativos.

**Description**

Políticas devem permitir apenas operações, recursos, tenants, campos e ambientes necessários ao caso de uso. Permissões genéricas, administrativas, wildcard ou equivalentes devem ser negadas. Operações não declaradas devem falhar por padrão.

**Rationale**

Permissões amplas transformam qualquer falha de modelo ou tool em comprometimento de alto impacto.

**Impact**

Pode exigir criação de roles e APIs mais granulares.

**Audit**

1. Exportar permissões efetivas de cada identidade de tool e agente.
2. Pesquisar wildcards, roles administrativas e acesso a recursos fora do escopo declarado.
3. Executar ação não listada e acesso a recurso de outro escopo; ambos devem ser negados.
4. Reprovar se a política depender de lista de negação sobre uma permissão ampla.

**Remediation**

Substituir permissões amplas por allowlists de ações e recursos, criar roles específicas e aplicar negação padrão.

**Evidence**

Matriz de permissões, policies exportadas e testes de ações/recursos fora do escopo.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-3, AC-6; Least privilege principles

---

### 3.4 Certifique-se de que ações irreversíveis ou de alto impacto exijam confirmação humana explícita

**Control ID:** BAS-004.3.4
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Exclusão, pagamento, transferência, aprovação, concessão de acesso, publicação externa, envio massivo, mudança de produção ou ação equivalente.

**Description**

A confirmação deve apresentar operação, alvo, parâmetros críticos, efeito, identidade executora e possibilidade de reversão. Deve ser coletada imediatamente antes da execução, por interface autenticada, e vinculada ao hash da ação. Confirmações genéricas ou anteriores ao plano final não atendem ao controle.

**Rationale**

O agente pode planejar ação incorreta ou ser manipulado; confirmação contextual reduz execução involuntária de operações materiais.

**Impact**

Introduz intervenção humana e reduz autonomia em operações sensíveis.

**Audit**

1. Selecionar ações classificadas como irreversíveis ou de alto impacto.
2. Confirmar que a interface exibe todos os parâmetros críticos e solicita confirmação após o plano final.
3. Alterar um parâmetro após a confirmação; a autorização deve ser invalidada e nova confirmação exigida.
4. Reprovar se confirmação do tipo “autorizar agente” cobrir múltiplas ações futuras ou se puder ser simulada pelo modelo.

**Remediation**

Adicionar confirmação autenticada por ação, vincular ao hash dos parâmetros e invalidar a confirmação em qualquer alteração.

**Evidence**

Capturas da confirmação, registros de hash e testes de alteração posterior bloqueada.

**Mappings**

CIS Controls v8 6; NIST SP 800-53 AC-3, AU-10; Human-in-the-loop safety principles

---

### 3.5 Certifique-se de que valores, volumes e frequência de ações possuam limites técnicos

**Control ID:** BAS-004.3.5
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Agentes capazes de realizar transações, alterações em lote, envio de mensagens, criação de recursos, consumo financeiro ou operações repetitivas.

**Description**

Devem existir limites por execução, período, subject, agente, tool e recurso para quantidade, valor, tamanho, taxa e custo. Valores acima do limite devem ser bloqueados antes da execução e não podem ser divididos automaticamente pelo agente para contornar o teto.

**Rationale**

Sem limites, uma decisão incorreta ou loop pode causar fraude, custo excessivo, indisponibilidade ou alteração massiva.

**Impact**

Limites podem bloquear operações legítimas de grande porte e exigir caminho técnico separado.

**Audit**

1. Revisar limites configurados por operação material.
2. Executar ação exatamente no limite e acima dele, além de múltiplas ações menores cuja soma exceda o teto do período.
3. Confirmar que o excesso é bloqueado antes de atingir o alvo e que não pode ser contornado por paralelismo.
4. Reprovar se o limite existir apenas em instrução de prompt ou monitoramento posterior.

**Remediation**

Configurar quotas e limites transacionais no enforcement point ou sistema-alvo, com agregação por período e proteção contra divisão/paralelismo.

**Evidence**

Configuração dos limites e resultados de testes no limite, acima do limite e por soma acumulada.

**Mappings**

CIS Controls v8 4 e 13; NIST SP 800-53 AC-10, SC-5; Abuse prevention principles

---

### 3.6 Certifique-se de que ações mutáveis possuam idempotência e proteção contra replay

**Control ID:** BAS-004.3.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Tools que criem, alterem, enviem, aprovem, executem ou gerem efeitos externos.

**Description**

Cada ação deve usar identificador idempotente único vinculado à execução e aos parâmetros. Reenvio, retry, repetição de mensagem ou reutilização do identificador com parâmetros diferentes deve ser rejeitado ou retornar o resultado original sem repetir o efeito.

**Rationale**

Retries de runtime, falhas de rede ou loops do agente podem duplicar pagamentos, mensagens, tickets, recursos ou alterações.

**Impact**

O sistema-alvo ou proxy precisará armazenar chaves e resultados por período definido.

**Audit**

1. Executar a mesma ação duas vezes com a mesma chave e parâmetros; somente um efeito deve ocorrer.
2. Reutilizar a chave com parâmetros diferentes; a operação deve ser rejeitada.
3. Simular timeout após o alvo concluir a ação e permitir retry; não deve haver duplicação.
4. Reprovar se a proteção depender somente de o modelo “lembrar” que já executou.

**Remediation**

Implementar idempotency key e replay cache no alvo ou proxy, vinculando chave, subject, operação e parâmetros.

**Evidence**

Logs e registros do alvo mostrando uma única execução nos testes de repetição e timeout.

**Mappings**

CIS Controls v8 8 e 16; NIST SP 800-53 SC-23, AU-10; Reliable distributed systems principles

---

## 4. Segurança de clientes, servidores e registries MCP

Controles para autenticação, integridade, autorização granular, isolamento e compatibilidade segura de componentes MCP.

### 4.1 Certifique-se de que somente clientes e servidores MCP allowlisted possam estabelecer sessão

**Control ID:** BAS-004.4.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Ambientes que utilizem MCP ou protocolo equivalente para expor tools, resources, prompts ou contextos.

**Description**

Clientes e servidores devem ser cadastrados por identificador, versão, ambiente e endpoint. Sessões com componente não cadastrado, endpoint diferente ou identidade desconhecida devem ser negadas antes da descoberta de capabilities.

**Rationale**

Shadow MCP ou servidor não avaliado pode expor tools maliciosas, dados indevidos ou capturar contexto do agente.

**Impact**

Novos componentes precisarão ser registrados antes de uso.

**Audit**

1. Exportar allowlists de clientes e servidores MCP.
2. Tentar conectar cliente não cadastrado a servidor aprovado e cliente aprovado a servidor não cadastrado.
3. Confirmar que ambos os casos falham antes da enumeração de tools/resources.
4. Reprovar se qualquer endpoint MCP puder ser fornecido por usuário, prompt, arquivo de configuração local não controlado ou descoberta pública.

**Remediation**

Criar registry/allowlist de clientes e servidores, bloquear endpoints arbitrários e exigir vínculo explícito por ambiente.

**Evidence**

Configuração da allowlist e testes de conexão com componentes não cadastrados.

**Mappings**

CIS Controls v8 1, 2 e 13; NIST SP 800-53 CM-8, AC-4; MCP security principles

---

### 4.2 Certifique-se de que clientes e servidores MCP utilizem autenticação mútua

**Control ID:** BAS-004.4.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Conexões MCP por rede, IPC, bridge, proxy ou transporte equivalente.

**Description**

O cliente deve autenticar o servidor e o servidor deve autenticar o cliente por certificados, workload identity, tokens com audience ou mecanismo equivalente. Confiar somente em host, porta, nome do processo ou canal local não atende ao controle em ambientes compartilhados.

**Rationale**

Sem autenticação mútua, um componente malicioso pode personificar servidor ou cliente e interceptar contexto, tools ou credenciais.

**Impact**

Pode exigir PKI, federação de identidade ou broker de tokens.

**Audit**

1. Inspecionar o mecanismo de autenticação em cada transporte MCP.
2. Tentar conexão com certificado/token inválido em ambos os sentidos.
3. Confirmar validação de audience, emissor, validade e identidade esperada.
4. Reprovar se qualquer lado aceitar sessão apenas porque o outro está na mesma máquina ou rede.

**Remediation**

Habilitar mTLS, workload identity ou tokens mutuamente validados e remover confiança baseada somente em localização.

**Evidence**

Configuração de autenticação e testes com credenciais inválidas de cliente e servidor.

**Mappings**

CIS Controls v8 6 e 12; NIST SP 800-53 IA-3, SC-8, SC-23

---

### 4.3 Certifique-se de que metadados do registry MCP possuam integridade verificável

**Control ID:** BAS-004.4.3
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Registries, catálogos ou manifests que publiquem servidores, capabilities, tools, resources e prompts MCP.

**Description**

Entradas do registry devem ser assinadas ou protegidas por mecanismo equivalente de integridade e possuir histórico imutável. O cliente deve verificar a integridade antes de usar endpoint, chave, schema, descrição ou versão. Alteração não autorizada deve impedir o consumo.

**Rationale**

A adulteração do registry pode redirecionar agentes para servidor malicioso ou substituir definição segura por capability contaminada.

**Impact**

Exige gestão de chaves, assinatura e trilhas de versão.

**Audit**

1. Selecionar entradas de registry e verificar assinatura/hash e histórico de alteração.
2. Alterar endpoint ou schema em cópia de teste sem assinatura válida.
3. Confirmar que o cliente rejeita a entrada adulterada e não estabelece sessão.
4. Reprovar se o cliente confiar em conteúdo do registry sem verificação de integridade.

**Remediation**

Assinar manifests/entradas, proteger o registry contra alterações diretas e validar assinatura ou hash no cliente.

**Evidence**

Entradas assinadas, histórico de alterações e teste com manifest adulterado rejeitado.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 SI-7, CM-3; Supply chain security principles

---

### 4.4 Certifique-se de que autorização MCP seja aplicada por capability, resource e operação

**Control ID:** BAS-004.4.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Servidores MCP que exponham múltiplas tools, resources, prompts, tenants ou operações.

**Description**

A autorização deve avaliar separadamente cada capability e recurso. Autenticar o cliente ou permitir acesso ao servidor não pode conceder acesso a todas as tools/resources. O servidor deve aplicar menor privilégio por subject, agente, ambiente e operação.

**Rationale**

Permissão ampla no servidor transforma qualquer tool ou resource exposto em superfície acessível ao agente.

**Impact**

Pode exigir políticas mais granulares e claims adicionais.

**Audit**

1. Exportar policies do servidor MCP e mapear capabilities por identidade.
2. Com cliente autenticado, tentar acessar capability não permitida e resource de outro escopo.
3. Confirmar negação pelo servidor antes da execução ou leitura.
4. Reprovar se a autorização ocorrer somente no cliente ou se o servidor usar uma permissão única para todas as capabilities.

**Remediation**

Implementar autorização no servidor por capability/resource/operação e reduzir escopos concedidos aos clientes.

**Evidence**

Policies exportadas e testes de acesso negado a capability e resource fora do escopo.

**Mappings**

CIS Controls v8 6; NIST SP 800-53 AC-3, AC-6; Zero Trust principles

---

### 4.5 Certifique-se de que sessões e namespaces MCP estejam isolados por tenant e contexto

**Control ID:** BAS-004.4.5
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Servidores MCP compartilhados por múltiplos usuários, agentes, aplicações, tenants ou ambientes.

**Description**

Estado de sessão, cache, subscriptions, handles, arquivos temporários, resources e resultados não podem ser reutilizados entre contexts. Identificadores de sessão devem ser imprevisíveis e sempre vinculados a subject, agente, tenant e ambiente.

**Rationale**

Falhas de isolamento podem expor dados, tools ou resultados de outra sessão ou tenant.

**Impact**

Pode aumentar consumo de recursos e exigir particionamento lógico ou físico.

**Audit**

1. Criar sessões simultâneas para dois tenants/subjects e armazenar estado distinto.
2. Tentar reutilizar session ID, handle, resource URI ou cache entre as sessões.
3. Confirmar que nenhum dado ou estado cruza a fronteira.
4. Reprovar se session ID isolado for suficiente sem validação adicional de subject/tenant.

**Remediation**

Particionar estado e caches, vincular cada objeto ao contexto autenticado e validar o vínculo em toda leitura ou operação.

**Evidence**

Arquitetura de sessão e resultados de testes de reutilização cruzada bloqueada.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-4, SC-4; Multi-tenant isolation principles

---

### 4.6 Certifique-se de que versões de protocolo e schemas MCP sejam fixadas e desconhecidos falhem de forma segura

**Control ID:** BAS-004.4.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Clientes, servidores, gateways, bridges e proxies MCP.

**Description**

Cada integração deve declarar versões de protocolo, transportes e schemas suportados. Mensagens, capabilities, campos ou versões desconhecidos devem ser rejeitados; negociação não pode habilitar automaticamente comportamento experimental ou mais permissivo.

**Rationale**

Compatibilidade permissiva pode interpretar campos de forma diferente, ignorar restrições ou habilitar capabilities não avaliadas.

**Impact**

Atualizações exigirão mudança coordenada entre componentes.

**Audit**

1. Consultar versões e schemas configurados em cliente e servidor.
2. Enviar versão não suportada, campo adicional crítico e capability desconhecida.
3. Confirmar rejeição com erro explícito e ausência de fallback permissivo.
4. Reprovar se unknown fields forem ignorados quando puderem alterar autorização, endpoint ou execução.

**Remediation**

Fixar versões suportadas, habilitar validação estrita e configurar fail closed para mensagens e capabilities desconhecidas.

**Evidence**

Configurações de versão/schema e testes com versão/campos não suportados.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 CM-2, SI-10; Secure protocol design principles

---

## 5. Proteção contra instruções e capabilities adversariais

Controles contra prompt injection indireto, tool poisoning, model misbinding, target substitution e autoelevação de autoridade.

### 5.1 Certifique-se de que saídas de tools, resources e prompts MCP sejam tratadas como conteúdo não confiável

**Control ID:** BAS-004.5.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes que incorporem resultados de tools, resources, prompts MCP ou conteúdo externo ao contexto do modelo.

**Description**

O runtime deve marcar a origem, delimitar o conteúdo e impedir que instruções presentes nesses dados alterem system/developer instructions, policies, tools disponíveis, subject ou autorização. Conteúdo de tool/resource deve ser interpretado como dado, salvo capability específica e allowlisted para retornar instruções.

**Rationale**

Um sistema-alvo ou documento comprometido pode inserir instruções que induzam o agente a executar novas ações ou exfiltrar dados.

**Impact**

Pode reduzir a capacidade de workflows que dependem de instruções dinâmicas e exigir canais separados.

**Audit**

1. Criar resposta de tool e resource contendo instrução para ignorar policy, chamar outra tool ou revelar segredo.
2. Executar o agente e confirmar que o conteúdo é tratado como dado e não altera tools, autorização ou objetivo.
3. Verificar marcação de provenance no contexto.
4. Reprovar se texto retornado por tool puder modificar instruções de maior precedência ou iniciar ação adicional sem validação.

**Remediation**

Separar canais de dados e instruções, adicionar provenance/delimitadores e bloquear promoção de instrução oriunda de tools/resources não autorizados.

**Evidence**

Prompts de teste, traces do contexto e comprovação de que a instrução adversarial não foi executada.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SI-10; OWASP GenAI Security Project — Prompt Injection

---

### 5.2 Certifique-se de que instruções de controle e dados externos permaneçam em canais separados

**Control ID:** BAS-004.5.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes que processem documentos, páginas, mensagens, tickets, e-mails, APIs ou resultados de busca.

**Description**

System/developer instructions, policies e schemas devem ser fornecidos por canal controlado e imutável. Dados externos devem ser delimitados e não concatenados ao mesmo campo de instrução. Templates não podem permitir que conteúdo externo feche delimitadores ou injete novos blocos de controle.

**Rationale**

Misturar dados e controle facilita prompt injection e confusão de precedência.

**Impact**

Pode exigir refatoração de templates e uso de APIs estruturadas.

**Audit**

1. Revisar templates e mensagens enviadas ao modelo.
2. Inserir conteúdo que tente fechar delimitadores, criar nova mensagem de sistema ou modificar schema.
3. Confirmar que o conteúdo permanece no campo de dados e não altera instruções controladas.
4. Reprovar se texto externo for interpolado diretamente em system/developer message ou configuração de tool.

**Remediation**

Utilizar mensagens/campos estruturados, escaping robusto e delimitação não controlável pelo conteúdo externo.

**Evidence**

Templates, payloads capturados e resultados de testes de escape/injeção.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SI-10; OWASP GenAI Security Project

---

### 5.3 Certifique-se de que descrições de tools, prompts e resources sejam inspecionadas contra instruções ocultas

**Control ID:** BAS-004.5.3
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Registries e servidores que forneçam descrições, exemplos, prompts, resource metadata ou texto utilizado pelo modelo para seleção de capability.

**Description**

Conteúdo descritivo deve ser normalizado e inspecionado para texto oculto, caracteres de controle, Unicode confusável, links, instruções de exfiltração, override de políticas e conteúdo não relacionado à função. Apenas texto aprovado e versionado deve ser apresentado ao modelo.

**Rationale**

Tool poisoning pode manipular a escolha e os argumentos do modelo por meio da descrição, mesmo quando o código da tool é legítimo.

**Impact**

Pode exigir revisão manual e limitar descrições dinâmicas ou multilíngues.

**Audit**

1. Selecionar descrições e prompts do registry e executar normalização/inspeção.
2. Inserir texto invisível, caractere de controle e instrução de exfiltração em definição de teste.
3. Confirmar bloqueio antes da publicação ou exposição ao modelo.
4. Reprovar se descrição for aceita sem normalização e inspeção de conteúdo adversarial.

**Remediation**

Normalizar Unicode, remover conteúdo invisível/ativo, aplicar scanner de instruções adversariais e exigir definição versionada aprovada.

**Evidence**

Definições analisadas e resultados de publicação de conteúdos ocultos/adversariais bloqueados.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 SI-7, SI-10; Tool poisoning mitigations

---

### 5.4 Certifique-se de que o agente valide o vínculo entre capability, endpoint e sistema-alvo

**Control ID:** BAS-004.5.4
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Tools ou servidores que possam resolver dinamicamente endpoint, recurso, modelo, tenant ou sistema de destino.

**Description**

A definição aprovada deve vincular capability a endpoint, identidade do servidor, sistema-alvo e namespace. Redirecionamentos, resolução DNS, aliases, parâmetros ou respostas não podem substituir o destino por componente diferente sem nova validação.

**Rationale**

Model misbinding e target substitution permitem que uma capability aparentemente legítima execute contra sistema ou tenant incorreto.

**Impact**

Reduz flexibilidade de roteamento e pode exigir verificação de identidade do destino após resolução.

**Audit**

1. Mapear capability para endpoint e identidade esperados.
2. Simular redirect, DNS alterado, alias ou parâmetro que aponte a outro destino.
3. Confirmar que o runtime valida a identidade final e bloqueia destino não vinculado.
4. Reprovar se a validação ocorrer somente sobre o nome lógico antes da resolução.

**Remediation**

Fixar e validar endpoint/audience/certificado/sistema-alvo, bloquear redirects não allowlisted e conferir o destino final antes da execução.

**Evidence**

Manifest da capability, configurações de endpoint e testes de substituição de destino bloqueada.

**Mappings**

CIS Controls v8 12 e 16; NIST SP 800-53 SC-8, SC-23, SI-7; Model misbinding mitigations

---

### 5.5 Certifique-se de que pacotes e implementações de tools tenham integridade verificada antes do carregamento

**Control ID:** BAS-004.5.5
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Tools distribuídas como pacotes, containers, scripts, binários, extensões, skills ou funções implantáveis.

**Description**

O runtime ou pipeline deve verificar assinatura, digest ou hash allowlisted do artefato e de suas dependências antes do carregamento. Artefato não assinado, com hash divergente ou proveniência ausente deve ser bloqueado.

**Rationale**

Ataques à supply chain podem substituir uma tool aprovada por código malicioso mantendo nome e descrição.

**Impact**

Exige publicação imutável, assinatura e gestão de confiança.

**Audit**

1. Selecionar artefatos de tools em produção e comparar digest/assinatura com o registry aprovado.
2. Alterar um artefato em ambiente de teste sem atualizar assinatura/hash.
3. Confirmar que implantação ou carregamento é bloqueado.
4. Reprovar se o runtime resolver pacote por nome/faixa de versão sem validar integridade.

**Remediation**

Assinar artefatos, fixar digests e verificar integridade/proveniência antes de implantar ou carregar a tool.

**Evidence**

Digests/assinaturas, políticas de verificação e teste com artefato adulterado bloqueado.

**Mappings**

CIS Controls v8 2 e 16; NIST SP 800-53 SI-7; SLSA and software supply chain principles

---

### 5.6 Certifique-se de que conteúdo externo não possa ampliar tools, escopos ou privilégios do agente

**Control ID:** BAS-004.5.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes que leiam páginas, documentos, e-mails, mensagens, recursos MCP, tickets ou entradas de usuários.

**Description**

A seleção de tools e escopos deve ser limitada pela configuração técnica anterior à leitura do conteúdo. Nenhum dado externo pode habilitar capability adicional, aumentar limite, alterar role, solicitar novo token ou modificar política de autorização.

**Rationale**

Prompt injection pode instruir o agente a obter mais privilégios ou habilitar ferramentas para cumprir objetivo malicioso.

**Impact**

Pode impedir workflows que pretendam instalar capabilities sob demanda; esses casos exigem processo técnico separado fora da execução.

**Audit**

1. Fornecer conteúdo com instruções para habilitar tool, solicitar credencial elevada, trocar role ou aumentar limite.
2. Confirmar que a lista efetiva de tools, scopes e limites permanece inalterada.
3. Verificar que qualquer tentativa é registrada como violação ou conteúdo não confiável.
4. Reprovar se o modelo puder acionar API de administração, registry ou IAM para ampliar a própria autoridade.

**Remediation**

Separar plano administrativo do runtime, remover capabilities de autoelevação e tornar toolset/escopos imutáveis durante a execução.

**Evidence**

Configuração antes/depois da sessão e traces demonstrando que tentativas de ampliação foram rejeitadas.

**Mappings**

CIS Controls v8 6 e 16; NIST SP 800-53 AC-6, CM-7; OWASP GenAI Security Project

---

## 6. Sandbox, host, navegador e computer use

Controles de isolamento para código, terminal, filesystem, rede, navegador, desktop e credenciais do host.

### 6.1 Certifique-se de que agentes com execução de código ou computer use operem em ambiente isolado

**Control ID:** BAS-004.6.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes que executem comandos, código, scripts, navegador, desktop, IDE, automação ou ferramentas locais.

**Description**

A execução deve ocorrer em container, VM, sandbox ou ambiente equivalente isolado do host e de outros workloads, com identidade, filesystem, rede e processos próprios. O agente não pode possuir acesso administrativo ao host nem reutilizar a sessão interativa do usuário.

**Rationale**

Código ou ação gerada pelo modelo pode comprometer o endpoint, extrair credenciais e movimentar-se para outros sistemas.

**Impact**

O isolamento aumenta consumo de recursos e pode limitar integração com aplicações locais.

**Audit**

1. Revisar o ambiente de execução e fronteiras de isolamento.
2. Tentar acessar processos, filesystem, credenciais e dispositivos do host fora do sandbox.
3. Confirmar bloqueio e ausência de privilégio administrativo.
4. Reprovar se o agente executar diretamente na sessão do usuário ou como administrador do host.

**Remediation**

Mover execução para sandbox/container/VM, remover privilégios do host e restringir mounts, devices, capabilities e IPC.

**Evidence**

Configuração do sandbox e resultados de testes de acesso ao host bloqueado.

**Mappings**

CIS Controls v8 4, 10 e 16; NIST SP 800-53 SC-2, SC-39; Sandbox principles

---

### 6.2 Certifique-se de que o acesso do agente ao filesystem utilize allowlist de caminhos e operações

**Control ID:** BAS-004.6.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes com capacidade de ler, criar, alterar, mover ou excluir arquivos.

**Description**

O runtime deve limitar leitura e escrita a diretórios específicos por execução. Paths absolutos fora da allowlist, traversal, links simbólicos, mounts inesperados, arquivos de credenciais e diretórios do sistema devem ser bloqueados. Escrita deve ocorrer em área descartável quando possível.

**Rationale**

Acesso amplo permite exfiltração, alteração de código, persistência e destruição de dados locais.

**Impact**

Pode restringir automações que dependem de múltiplos diretórios ou compartilhamentos.

**Audit**

1. Exportar mounts, roots e policies de filesystem do agente.
2. Testar path traversal, symlink, acesso a home, chaves, configurações e diretórios de sistema.
3. Confirmar que todos os acessos fora da allowlist são negados.
4. Reprovar se a tool aceitar path arbitrário validado apenas por extensão ou prefixo textual.

**Remediation**

Implementar sandbox de filesystem, canonicalização de path, bloqueio de symlinks/mounts e allowlist separada de leitura e escrita.

**Evidence**

Configuração de paths e resultados dos testes de traversal e acesso a arquivos sensíveis.

**Mappings**

CIS Controls v8 3, 4 e 10; NIST SP 800-53 AC-3, MP-2; Path traversal prevention

---

### 6.3 Certifique-se de que o tráfego de saída do agente utilize allowlist de destinos

**Control ID:** BAS-004.6.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes locais ou remotos com acesso de rede, navegador, HTTP client, package manager ou comandos.

**Description**

Egress deve ser permitido somente para domínios, IPs, portas e serviços necessários. DNS, redirects, proxies e resolução final devem ser validados. Acesso a metadata service, rede interna não requerida, localhost do host e Internet irrestrita deve ser bloqueado.

**Rationale**

Egress amplo permite exfiltração, download de payload, command-and-control, SSRF e acesso a serviços internos.

**Impact**

Pode exigir manutenção de allowlists e proxies para dependências externas.

**Audit**

1. Exportar políticas de egress e destinos permitidos.
2. Tentar acessar domínio não cadastrado, endereço IP direto, metadata service, serviço interno e destino por redirect.
3. Confirmar bloqueio no enforcement de rede.
4. Reprovar se o controle depender somente de instrução do modelo ou filtro de URL na aplicação.

**Remediation**

Aplicar egress proxy/firewall por allowlist, bloquear ranges internos/metadata e validar o destino final após DNS/redirect.

**Evidence**

Policies de rede e resultados de testes de destinos proibidos.

**Mappings**

CIS Controls v8 12 e 13; NIST SP 800-53 SC-7; SSRF prevention

---

### 6.4 Certifique-se de que comandos, executáveis e intérpretes disponíveis ao agente sejam allowlisted

**Control ID:** BAS-004.6.4
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Agentes com terminal, shell, execução de código, automação de IDE ou acesso a processos.

**Description**

O ambiente deve disponibilizar somente comandos e intérpretes necessários, com argumentos validados. Shell genérico, package manager, downloaders, ferramentas de rede, escalonamento de privilégio e execução arbitrária devem permanecer indisponíveis salvo caso de uso explicitamente restrito.

**Rationale**

Comandos amplos permitem que prompt injection se converta em execução arbitrária, persistência ou exfiltração.

**Impact**

Reduz flexibilidade de automação e pode exigir wrappers específicos.

**Audit**

1. Enumerar binários, commands e interpreters acessíveis ao agente.
2. Tentar executar shell não permitido, instalar pacote, baixar binário e iniciar processo arbitrário.
3. Confirmar bloqueio antes da execução.
4. Reprovar se a tool expuser comando livre ou “execute script” sem linguagem/subconjunto e argumentos restritos.

**Remediation**

Substituir shell genérico por wrappers estruturados, remover binários desnecessários e aplicar allowlist de comandos e argumentos.

**Evidence**

Inventário do ambiente e resultados de tentativas de comandos não permitidos.

**Mappings**

CIS Controls v8 2, 4 e 10; NIST SP 800-53 CM-7, AC-6; Command injection prevention

---

### 6.5 Certifique-se de que automação de navegador seja restrita a domínios e ações permitidos

**Control ID:** BAS-004.6.5
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Agentes com browser automation, computer use ou interação visual com aplicações web.

**Description**

O navegador deve utilizar perfil isolado, domínios allowlisted, downloads controlados e bloqueio de extensões, pop-ups, protocolos externos e navegação para origens não permitidas. Ações sensíveis como envio, compra, aprovação e upload devem possuir enforcement independente da percepção visual do agente.

**Rationale**

Páginas maliciosas podem redirecionar, exibir instruções adversariais, roubar sessões ou induzir cliques em ações críticas.

**Impact**

Pode limitar navegação dinâmica e exigir integração por API em vez de interface visual.

**Audit**

1. Revisar perfil, policies e domínios do navegador agentic.
2. Tentar navegar para domínio não permitido, acionar protocolo externo, instalar extensão e baixar executável.
3. Testar página que simule botão ou instrução adversarial para ação sensível.
4. Reprovar se o agente puder usar sessão pessoal existente ou executar ação crítica apenas por reconhecimento visual.

**Remediation**

Criar perfil descartável, aplicar allowlist de domínios e downloads, desabilitar extensões/protocolos e mover ações críticas para APIs autorizadas.

**Evidence**

Configuração do navegador e resultados de testes de navegação, download e ação sensível.

**Mappings**

CIS Controls v8 4, 9 e 10; NIST SP 800-53 SC-7, SI-3; Browser isolation principles

---

### 6.6 Certifique-se de que credenciais e sessões do host não sejam acessíveis ao runtime agentic

**Control ID:** BAS-004.6.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes executados em endpoint, IDE, desktop, navegador, terminal ou infraestrutura compartilhada.

**Description**

Cookies, tokens SSO, chaves SSH, cofres locais, credential managers, variáveis do usuário, clipboard e sessões de aplicações do host devem permanecer inacessíveis. Credenciais necessárias devem ser injetadas no sandbox com escopo e TTL limitados.

**Rationale**

Acesso às sessões do host permite que o agente assuma a identidade do usuário em serviços não previstos e exfiltre credenciais.

**Impact**

Pode impedir uso transparente de aplicações já autenticadas e exigir broker de credenciais.

**Audit**

1. Executar o agente e tentar ler cookies, credential manager, chaves SSH, variáveis e clipboard do host.
2. Confirmar que esses recursos não estão montados nem disponíveis no sandbox.
3. Verificar que credenciais necessárias são específicas, temporárias e não reutilizam a sessão interativa.
4. Reprovar se o agente controlar navegador/IDE com perfil pessoal ou acessar diretórios de credenciais do usuário.

**Remediation**

Isolar perfil e storage do agente, remover mounts do host e fornecer credenciais temporárias por broker ou workload identity.

**Evidence**

Configuração de mounts/perfis e resultados de tentativas de acesso a credenciais do host.

**Mappings**

CIS Controls v8 5, 6 e 10; NIST SP 800-53 IA-5, AC-6; Endpoint isolation principles

---

## 7. Memória, delegação e comunicação entre agentes

Controles para segregação e saneamento de memória, proteção de segredos, mensagens autenticadas e limites imutáveis de delegação.

### 7.1 Certifique-se de que memória agentic seja segregada por usuário, tenant, agente e sessão

**Control ID:** BAS-004.7.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes com short-term memory, long-term memory, vector memory, checkpoints ou histórico persistente.

**Description**

Cada registro de memória deve ser vinculado a subject, tenant, agent ID, ambiente e escopo de sessão. Consultas devem aplicar todos os filtros antes da recuperação. Compartilhamento entre agentes ou usuários deve ser explícito e ocorrer em namespace separado.

**Rationale**

Memória compartilhada indevidamente pode expor dados, instruções e decisões de outro usuário ou tenant.

**Impact**

A segregação aumenta namespaces e metadados.

**Audit**

1. Criar memórias distintas para dois usuários/tenants e dois agentes.
2. Executar consultas cruzadas e confirmar ausência de resultados de outro contexto.
3. Tentar omitir um filtro ou alterar identificador no cliente; o backend deve continuar aplicando todos os vínculos.
4. Reprovar se o isolamento depender somente do prompt ou de filtro enviado pelo modelo.

**Remediation**

Particionar memória, persistir metadados de contexto e aplicar filtros de autorização no backend antes da busca.

**Evidence**

Schema de memória e resultados de testes de recuperação cruzada bloqueada.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-4, SC-4; Multi-tenant isolation principles

---

### 7.2 Certifique-se de que memórias possuam TTL e limites de volume configurados

**Control ID:** BAS-004.7.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Agentes que armazenem histórico, preferências, resumos, planos, resultados ou contexto persistente.

**Description**

Memórias temporárias e persistentes devem possuir TTL explícito, tamanho máximo por item, quantidade máxima por subject/agente e política de substituição. Retenção indefinida por ausência de configuração não é permitida.

**Rationale**

Memória ilimitada acumula dados sensíveis, instruções obsoletas e conteúdo adversarial, além de aumentar custo e superfície de vazamento.

**Impact**

Informações antigas podem deixar de estar disponíveis e precisar ser regeneradas.

**Audit**

1. Enumerar stores de memória e suas políticas.
2. Confirmar TTL e quotas explícitos para cada tipo.
3. Criar item com expiração curta e verificar remoção e impossibilidade de recuperação após o prazo.
4. Reprovar se qualquer store depender de limpeza manual ou possuir retenção infinita não justificada tecnicamente.

**Remediation**

Configurar TTL, quotas e lifecycle por tipo de memória e remover itens vencidos existentes.

**Evidence**

Configurações de lifecycle e teste de expiração/limite.

**Mappings**

CIS Controls v8 3; NIST SP 800-53 SI-12, MP-6; Data minimization principles

---

### 7.3 Certifique-se de que gravações em memória sejam validadas e saneadas

**Control ID:** BAS-004.7.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes que persistam conteúdo derivado de usuários, tools, páginas, documentos ou outros agentes.

**Description**

Antes da persistência, o conteúdo deve ser classificado, limitado, associado à provenance e inspecionado contra instruções adversariais, dados proibidos e metadados inconsistentes. O modelo não pode gravar diretamente em memória confiável sem validação intermediária.

**Rationale**

Conteúdo adversarial persistido pode contaminar execuções futuras e manter prompt injection além da sessão original.

**Impact**

A validação adiciona latência e pode reduzir a quantidade de informação retida.

**Audit**

1. Inserir conteúdo contendo instrução persistente, segredo sintético e provenance ausente.
2. Solicitar gravação em memória e confirmar bloqueio ou saneamento antes da persistência.
3. Iniciar nova sessão e verificar que o conteúdo bloqueado não influencia o agente.
4. Reprovar se qualquer output do modelo ou tool puder ser gravado como memória confiável sem validação.

**Remediation**

Adicionar camada de validação e classificação antes da escrita, separar memória não confiável e bloquear conteúdo proibido ou sem provenance.

**Evidence**

Traces de escrita e resultados de testes com conteúdo adversarial não persistido.

**Mappings**

CIS Controls v8 3 e 16; NIST SP 800-53 SI-10; OWASP GenAI Security Project

---

### 7.4 Certifique-se de que segredos e credenciais não sejam persistidos em memória do agente

**Control ID:** BAS-004.7.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Memórias, histories, checkpoints, scratchpads, summaries, caches e stores de contexto.

**Description**

Tokens, chaves, senhas, cookies, certificados privados e valores equivalentes devem ser detectados e removidos antes da persistência. A memória deve armazenar referência opaca ao secret quando necessário, nunca o valor. Logs de memória e backups também devem permanecer livres desses dados.

**Rationale**

Segredos em memória podem ser recuperados por outro prompt, usuário, agente, administrador ou backup.

**Impact**

Falsos positivos podem remover strings legítimas semelhantes a secrets.

**Audit**

1. Inserir secrets sintéticos de formatos suportados e induzir o agente a memorizá-los.
2. Consultar memória, logs e checkpoint; nenhum valor completo deve estar presente.
3. Confirmar que somente referência opaca seja persistida quando necessária.
4. Reprovar se masking ocorrer somente na interface e o valor original permanecer no storage.

**Remediation**

Aplicar secret scanning antes da escrita, substituir valores por referências e expurgar memórias/backups existentes.

**Evidence**

Resultados de secret scanning e consultas aos stores sem valores sensíveis.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 IA-5, SC-28; Secret management principles

---

### 7.5 Certifique-se de que mensagens entre agentes sejam autenticadas, íntegras e não reutilizáveis

**Control ID:** BAS-004.7.5
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Arquiteturas multiagente, filas, buses, handoffs, delegações ou colaboração entre agentes.

**Description**

Cada mensagem deve identificar agente emissor, destinatário, subject, execução, timestamp, nonce e escopo delegado, com autenticação e integridade verificáveis. Mensagens expiradas, duplicadas, alteradas ou destinadas a outro agente devem ser rejeitadas.

**Rationale**

Um agente ou atacante pode personificar outro, alterar tarefas ou repetir instruções para gerar efeitos duplicados.

**Impact**

Exige assinatura, tokens ou canal autenticado e controle de replay.

**Audit**

1. Capturar mensagem válida e alterar payload, emissor, destinatário ou escopo.
2. Reenviar a mensagem e tentar entregá-la a outro agente.
3. Confirmar rejeição em todos os casos e aceitação somente da mensagem original no prazo.
4. Reprovar se mensagens internas forem confiadas apenas por estarem na mesma fila ou rede.

**Remediation**

Assinar ou autenticar mensagens, incluir nonce/expiração e validar destinatário, execution ID e escopo antes do processamento.

**Evidence**

Formato de mensagem e resultados de testes de adulteração, replay e destinatário incorreto.

**Mappings**

CIS Controls v8 6 e 8; NIST SP 800-53 SC-8, SC-23, AU-10

---

### 7.6 Certifique-se de que delegações mantenham limites imutáveis de autoridade

**Control ID:** BAS-004.7.6
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Agentes que deleguem subtarefas a outros agentes, workers, modelos ou serviços.

**Description**

A delegação deve incluir escopo máximo de tools, recursos, dados, tempo, custo e ações, sempre igual ou menor que a autoridade do delegante. O agente delegado não pode ampliar limites, redelegar com maior privilégio ou remover condições impostas.

**Rationale**

Cadeias de delegação podem diluir restrições e criar agente secundário com autoridade superior à origem.

**Impact**

Pode limitar autonomia e exigir enforcement central em cada handoff.

**Audit**

1. Criar cadeia de delegação com pelo menos dois níveis.
2. Tentar solicitar tool, recurso ou limite não pertencente ao delegante.
3. Confirmar que o enforcement rejeita a ampliação e preserva as restrições originais em todos os níveis.
4. Reprovar se os limites forem transmitidos apenas em texto ou puderem ser reescritos pelo agente delegado.

**Remediation**

Representar autoridade em claims/policies imutáveis, calcular interseção de escopos em cada delegação e bloquear redelegação acima do limite.

**Evidence**

Traces de delegação, claims de autoridade e testes de ampliação bloqueada.

**Mappings**

CIS Controls v8 6; NIST SP 800-53 AC-3, AC-6; Delegation of authority principles

---

## 8. Observabilidade agentic e comportamento fail-safe

Controles específicos para rastreabilidade de ações, correlação, kill switch, limites de execução e falha fechada.

### 8.1 Certifique-se de que toda cadeia de ação do agente seja registrada de ponta a ponta

**Control ID:** BAS-004.8.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes que selecionem tools, executem ações, deleguem tarefas ou acessem MCP.

**Description**

O trace deve registrar solicitante, agente e versão, modelo, plano ou decisão resumida, tool/capability e versão, argumentos saneados, policy decision, confirmação humana quando aplicável, sistema-alvo, resultado, erro e timestamps. Registros devem permitir reconstruir a sequência sem depender de chain-of-thought privada.

**Rationale**

Sem trilha completa não é possível investigar ação indevida, provar autorização ou identificar componente comprometido.

**Impact**

A coleta aumenta volume de telemetria e requer mascaramento de dados sensíveis.

**Audit**

1. Executar workflow com múltiplas tools e delegação.
2. Reconstruir a sequência apenas pelos registros disponíveis.
3. Confirmar presença dos campos obrigatórios e correlação entre decisões, autorização e resultado.
4. Reprovar se houver lacuna entre seleção da tool e efeito no alvo ou se logs exigirem conteúdo sensível não mascarado.

**Remediation**

Instrumentar runtime, policy engine, MCP e systems targets com eventos correlacionados e campos mínimos, aplicando mascaramento.

**Evidence**

Trace completo de execução de teste e validação dos campos obrigatórios.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 AU-2, AU-3, AU-12; NIST AI RMF MEASURE

---

### 8.2 Certifique-se de que um identificador de correlação una usuário, agente, modelo, tool e sistema-alvo

**Control ID:** BAS-004.8.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Execuções agentic distribuídas por múltiplos serviços, filas, MCP, APIs e systems targets.

**Description**

Um correlation/execution ID imutável deve ser gerado no início e propagado por todas as chamadas, mensagens e logs. Componentes podem adicionar span IDs, mas não substituir o ID raiz. Eventos sem correlação válida devem ser rejeitados ou marcados como erro técnico.

**Rationale**

Sem correlação, eventos de uma mesma execução ficam fragmentados e ações paralelas podem ser atribuídas ao contexto incorreto.

**Impact**

Exige suporte de propagação nos componentes e schemas de evento.

**Audit**

1. Executar fluxo que atravesse runtime, policy engine, MCP, tool e sistema-alvo.
2. Consultar logs de todos os componentes e confirmar o mesmo execution ID.
3. Tentar enviar mensagem com ID diferente ou ausente; o componente deve rejeitar ou gerar erro explícito sem vinculá-la à execução.
4. Reprovar se o ID puder ser escolhido pelo modelo ou reutilizado entre execuções independentes.

**Remediation**

Gerar execution ID no entry point confiável, propagá-lo em headers/claims/mensagens e validar consistência em cada componente.

**Evidence**

Consulta correlacionada ponta a ponta e teste com ID ausente/divergente.

**Mappings**

CIS Controls v8 8; NIST SP 800-53 AU-3, AU-12; Distributed tracing principles

---

### 8.3 Certifique-se de que exista mecanismo técnico de interrupção imediata das ações do agente

**Control ID:** BAS-004.8.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes com tools, autonomia, execução prolongada, filas ou processos assíncronos.

**Description**

Deve existir kill switch capaz de impedir novas ações, revogar credenciais temporárias, cancelar jobs e bloquear chamadas pendentes sem depender da cooperação do modelo. O mecanismo deve atuar por agente, versão, tenant e globalmente conforme a arquitetura.

**Rationale**

Um agente comprometido ou em loop precisa ser contido mesmo que continue gerando ações e ignorando instruções.

**Impact**

A interrupção pode deixar operações parciais e exigir recuperação técnica.

**Audit**

1. Iniciar execução contínua com múltiplas ações e acionar o kill switch durante o fluxo.
2. Confirmar que novas tools são negadas, jobs são cancelados e credenciais deixam de funcionar.
3. Verificar que reinício do runtime não reativa automaticamente a execução bloqueada.
4. Reprovar se a contenção consistir apenas em enviar uma mensagem de parada ao modelo.

**Remediation**

Implementar bloqueio no enforcement point, revogação de credenciais e cancelamento de jobs/filas, com persistência do estado de suspensão.

**Evidence**

Resultado de teste de kill switch e logs de revogação/cancelamento.

**Mappings**

CIS Controls v8 6, 8 e 13; NIST SP 800-53 IR-4, AC-12; Safety shutdown principles

---

### 8.4 Certifique-se de que execuções possuam limites de iterações, tempo, tokens e chamadas de tools

**Control ID:** BAS-004.8.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Agentes autônomos, loops de reflexão, planners, workers e workflows de longa duração.

**Description**

Cada execução deve possuir limites máximos de duração, passos/iterações, tokens, chamadas totais e por tool, paralelismo e custo. Ao atingir qualquer limite, o runtime deve interromper novas ações e retornar estado explícito de limite excedido.

**Rationale**

Loops, deadlocks ou objetivos impossíveis podem gerar custo, indisponibilidade e repetição de ações.

**Impact**

Execuções complexas legítimas podem precisar de limites maiores definidos por perfil técnico.

**Audit**

1. Consultar limites configurados por tipo de agente.
2. Executar cenário que exceda cada limite individualmente.
3. Confirmar interrupção antes de nova chamada e registro do motivo.
4. Reprovar se o limite existir somente em prompt ou alerta posterior sem enforcement técnico.

**Remediation**

Configurar limites no runtime/orquestrador, impedir aumento pelo modelo e interromper a execução ao atingir qualquer teto.

**Evidence**

Configurações e logs de testes de tempo, iteração, token, tool call e custo excedidos.

**Mappings**

CIS Controls v8 4 e 13; NIST SP 800-53 SC-5, SI-17; Resource exhaustion prevention

---

### 8.5 Certifique-se de que indisponibilidade de autorização, registry ou validação resulte em falha fechada

**Control ID:** BAS-004.8.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes dependentes de IAM, policy engine, registry de tools/MCP, scanner, schema validator ou serviço de confirmação.

**Description**

Quando qualquer controle necessário estiver indisponível, expirado ou inconsistente, novas ações materiais devem ser negadas. O runtime não pode reutilizar decisão indefinidamente, remover validação ou continuar com configuração local desatualizada além do TTL definido.

**Rationale**

Falha aberta converte indisponibilidade de um controle em execução sem autorização ou com capability obsoleta.

**Impact**

A disponibilidade do agente pode ser reduzida durante falhas de dependências de segurança.

**Audit**

1. Simular indisponibilidade individual de policy engine, registry e validator.
2. Executar ação material e confirmar bloqueio antes da chamada ao alvo.
3. Verificar expiração de caches e que configuração antiga não é usada além do TTL.
4. Reprovar se o runtime continuar com “modo degradado” que dispense autorização ou validação.

**Remediation**

Configurar fail closed, TTL limitado para caches e circuit breaker que bloqueie ações materiais durante indisponibilidade.

**Evidence**

Resultados de testes de indisponibilidade e configurações de TTL/fail closed.

**Mappings**

CIS Controls v8 4, 6 e 13; NIST SP 800-53 AC-3, SC-7; Fail-safe defaults

---

### 8.6 Certifique-se de que padrões anômalos de falha ou negação suspendam novas ações

**Control ID:** BAS-004.8.6
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Agentes que possam repetir chamadas, explorar alternativas ou operar em alta frequência.

**Description**

O runtime deve detectar e interromper execução após limiar configurado de negações de policy, falhas de autenticação, validações de schema, tentativas de tool inexistente, acesso a destinos proibidos ou erros repetidos. A suspensão deve impedir que o agente tente variantes para contornar o controle.

**Rationale**

Agentes podem entrar em loop de tentativa e erro, enumerar permissões ou adaptar parâmetros até encontrar bypass.

**Impact**

Pode interromper execuções legítimas durante falhas transitórias ou dados inconsistentes.

**Audit**

1. Revisar limiares por tipo de violação.
2. Executar sequência de tentativas negadas até atingir o limite.
3. Confirmar suspensão da execução e bloqueio de novas variantes ou tools.
4. Reprovar se o agente puder reiniciar automaticamente ou criar subtarefa para continuar as tentativas.

**Remediation**

Configurar contadores por execution ID/subject/agente, suspender ao atingir o limite e impedir reinício ou delegação automática.

**Evidence**

Configuração de detecção e logs de execução suspensa após tentativas repetidas.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 SI-4, AC-7; Abuse detection principles

---
