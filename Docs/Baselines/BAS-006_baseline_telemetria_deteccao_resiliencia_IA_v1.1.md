# BAS-006 — Baseline de Controles Técnicos para Telemetria, Detecção e Resiliência de Inteligência Artificial

| Campo | Valor |
|---|---|
| **Código** | BAS-006 |
| **Tipo documental** | Baseline técnico |
| **Classificação da informação** | Uso Interno |
| **Status** | Minuta para revisão |
| **Versão** | 1.1 |
| **Data** | 13/07/2026 |
| **Owner institucional** | Segurança da Informação / Segurança de IA |
| **Custodiante técnico** | Arquitetura de Segurança / SOC / SRE / Engenharia de Plataforma |
| **Quantidade de controles** | 48 |

## 1. Objetivo

Estabelecer recomendações técnicas mínimas, verificáveis e auditáveis para geração e proteção de telemetria, correlação ponta a ponta, detecção de ameaças, identificação de anomalias, contenção, continuidade, recuperação e desativação segura de soluções de Inteligência Artificial. O documento segue a estrutura de recomendações dos CIS Benchmarks e contém somente controles técnicos. Triagem, escalonamento, comunicação, gestão de incidentes, governança, exceções, RACI e demais processos estão fora do escopo.

## 2. Escopo

Aplica-se a aplicações, gateways, modelos, providers, RAG, agentes, MCP, tools, pipelines, sistemas downstream, collectors, brokers, SIEM, APM, data lakes, dashboards, mecanismos de contenção e componentes de continuidade. Este baseline não deve ser aplicado isoladamente: BAS-001 a BAS-005 permanecem aplicáveis, e os demais baselines especializados devem ser combinados cumulativamente conforme a arquitetura e as capacidades avaliadas.

## 3. Modelo de classificação

### 3.1 Profile Applicability

- **Level 1:** configuração técnica fundamental para qualquer solução de IA no escopo.
- **Level 2:** defesa em profundidade para soluções críticas, sensíveis, externas, reguladas ou com alto impacto. Pressupõe conformidade com todos os controles Level 1 aplicáveis.

### 3.2 Criticidade

| Criticidade | Critério |
|---|---|
| **Crítica** | A ausência permite execução ou ação sem trilha, perda de evidência, vazamento não detectado, bypass de contenção, falha insegura ou incapacidade de recuperação. |
| **Alta** | A ausência reduz significativamente correlação, detecção, visibilidade, confiabilidade operacional ou resistência a falhas. |
| **Média** | Controle de hardening cuja ausência normalmente exige outra falha para produzir impacto material. Esta versão não contém recomendações de criticidade Média. |
| **Baixa** | Otimização técnica com impacto limitado. Esta versão não contém recomendações de criticidade Baixa. |

## 4. Regras de interpretação

1. BAS-001 a BAS-005 são pré-requisitos quando aplicáveis aos componentes cobertos por este documento.
2. Cada recomendação deve ser avaliada de forma independente.
3. Um controle é **Conforme** somente quando todos os critérios descritos em **Audit** forem atendidos.
4. Implementação parcial deve ser registrada como **Não Conforme**; não existe conformidade parcial neste baseline.
5. Quando uma recomendação não se aplicar tecnicamente, a justificativa deve indicar o componente, capacidade ou fluxo inexistente.
6. Dashboards, relatórios, procedimentos ou declarações não substituem geração de eventos, enforcement, teste de falha ou mecanismo técnico verificável.

## Sumário

- [1. Geração de eventos e integridade temporal](#1-geracao-de-eventos-e-integridade-temporal)
  - [1.1 Certifique-se de que toda requisição material de IA gere evento de início e de término](#11-certifique-se-de-que-toda-requisicao-material-de-ia-gere-evento-de-inicio-e-de-termino)
  - [1.2 Certifique-se de que timestamps de eventos utilizem UTC e fonte de tempo sincronizada](#12-certifique-se-de-que-timestamps-de-eventos-utilizem-utc-e-fonte-de-tempo-sincronizada)
  - [1.3 Certifique-se de que cada evento possua identificador único e não reutilizável](#13-certifique-se-de-que-cada-evento-possua-identificador-unico-e-nao-reutilizavel)
  - [1.4 Certifique-se de que eventos registrem o modelo, provider, deployment e versão efetivamente utilizados](#14-certifique-se-de-que-eventos-registrem-o-modelo-provider-deployment-e-versao-efetivamente-utilizados)
  - [1.5 Certifique-se de que decisões de segurança e resultados sejam registrados com valores enumerados](#15-certifique-se-de-que-decisoes-de-seguranca-e-resultados-sejam-registrados-com-valores-enumerados)
  - [1.6 Certifique-se de que o schema de eventos seja versionado e compatível com validação automática](#16-certifique-se-de-que-o-schema-de-eventos-seja-versionado-e-compativel-com-validacao-automatica)
- [2. Correlação e contexto ponta a ponta](#2-correlacao-e-contexto-ponta-a-ponta)
  - [2.1 Certifique-se de que trace_id seja propagado por todas as camadas do fluxo de IA](#21-certifique-se-de-que-traceid-seja-propagado-por-todas-as-camadas-do-fluxo-de-ia)
  - [2.2 Certifique-se de que request_id, response_id e job_id sejam únicos e relacionados](#22-certifique-se-de-que-requestid-responseid-e-jobid-sejam-unicos-e-relacionados)
  - [2.3 Certifique-se de que a identidade originadora e a identidade técnica sejam registradas separadamente](#23-certifique-se-de-que-a-identidade-originadora-e-a-identidade-tecnica-sejam-registradas-separadamente)
  - [2.4 Certifique-se de que tenant, conta, ambiente, região e classificação de dados estejam presentes nos eventos](#24-certifique-se-de-que-tenant-conta-ambiente-regiao-e-classificacao-de-dados-estejam-presentes-nos-eventos)
  - [2.5 Certifique-se de que recuperações RAG registrem fontes e objetos efetivamente utilizados](#25-certifique-se-de-que-recuperacoes-rag-registrem-fontes-e-objetos-efetivamente-utilizados)
  - [2.6 Certifique-se de que tool calls e chamadas MCP sejam correlacionadas à decisão que as originou](#26-certifique-se-de-que-tool-calls-e-chamadas-mcp-sejam-correlacionadas-a-decisao-que-as-originou)
- [3. Proteção, minimização e integridade dos registros](#3-protecao-minimizacao-e-integridade-dos-registros)
  - [3.1 Certifique-se de que segredos e credenciais não sejam registrados em texto claro](#31-certifique-se-de-que-segredos-e-credenciais-nao-sejam-registrados-em-texto-claro)
  - [3.2 Certifique-se de que prompts, outputs e documentos não sejam armazenados integralmente por padrão](#32-certifique-se-de-que-prompts-outputs-e-documentos-nao-sejam-armazenados-integralmente-por-padrao)
  - [3.3 Certifique-se de que eventos sejam criptografados em trânsito e em repouso](#33-certifique-se-de-que-eventos-sejam-criptografados-em-transito-e-em-repouso)
  - [3.4 Certifique-se de que o acesso a logs de IA aplique menor privilégio e segregação por função](#34-certifique-se-de-que-o-acesso-a-logs-de-ia-aplique-menor-privilegio-e-segregacao-por-funcao)
  - [3.5 Certifique-se de que eventos críticos sejam protegidos contra alteração e exclusão](#35-certifique-se-de-que-eventos-criticos-sejam-protegidos-contra-alteracao-e-exclusao)
  - [3.6 Certifique-se de que consultas, exportações e alterações de configuração de logging sejam auditadas](#36-certifique-se-de-que-consultas-exportacoes-e-alteracoes-de-configuracao-de-logging-sejam-auditadas)
- [4. Coleta, transporte e integração com SIEM](#4-coleta-transporte-e-integracao-com-siem)
  - [4.1 Certifique-se de que emissores mantenham buffer persistente quando o coletor estiver indisponível](#41-certifique-se-de-que-emissores-mantenham-buffer-persistente-quando-o-coletor-estiver-indisponivel)
  - [4.2 Certifique-se de que perda de telemetria crítica provoque estado seguro em operações de alto impacto](#42-certifique-se-de-que-perda-de-telemetria-critica-provoque-estado-seguro-em-operacoes-de-alto-impacto)
  - [4.3 Certifique-se de que eventos inválidos sejam colocados em quarentena e não descartados silenciosamente](#43-certifique-se-de-que-eventos-invalidos-sejam-colocados-em-quarentena-e-nao-descartados-silenciosamente)
  - [4.4 Certifique-se de que entrega de eventos possua confirmação, controle de duplicidade e sequência](#44-certifique-se-de-que-entrega-de-eventos-possua-confirmacao-controle-de-duplicidade-e-sequencia)
  - [4.5 Certifique-se de que a saúde do pipeline de telemetria seja monitorada independentemente da aplicação](#45-certifique-se-de-que-a-saude-do-pipeline-de-telemetria-seja-monitorada-independentemente-da-aplicacao)
  - [4.6 Certifique-se de que eventos críticos estejam disponíveis no SIEM dentro do limite de latência definido](#46-certifique-se-de-que-eventos-criticos-estejam-disponiveis-no-siem-dentro-do-limite-de-latencia-definido)
- [5. Detecções técnicas de segurança para IA](#5-deteccoes-tecnicas-de-seguranca-para-ia)
  - [5.1 Certifique-se de que o uso de modelo, provider, rota ou capability não permitida seja detectado](#51-certifique-se-de-que-o-uso-de-modelo-provider-rota-ou-capability-nao-permitida-seja-detectado)
  - [5.2 Certifique-se de que exposição de dados sensíveis, segredos e credenciais em prompts ou outputs seja detectada](#52-certifique-se-de-que-exposicao-de-dados-sensiveis-segredos-e-credenciais-em-prompts-ou-outputs-seja-detectada)
  - [5.3 Certifique-se de que tentativas de prompt injection, jailbreak e prompt leakage sejam detectadas por múltiplos sinais](#53-certifique-se-de-que-tentativas-de-prompt-injection-jailbreak-e-prompt-leakage-sejam-detectadas-por-multiplos-sinais)
  - [5.4 Certifique-se de que ações agentic anômalas ou sem autorização sejam detectadas](#54-certifique-se-de-que-acoes-agentic-anomalas-ou-sem-autorizacao-sejam-detectadas)
  - [5.5 Certifique-se de que poisoning e recuperação indevida em RAG sejam detectados](#55-certifique-se-de-que-poisoning-e-recuperacao-indevida-em-rag-sejam-detectados)
  - [5.6 Certifique-se de que servidores, tools, resources e prompts MCP desconhecidos ou alterados sejam detectados](#56-certifique-se-de-que-servidores-tools-resources-e-prompts-mcp-desconhecidos-ou-alterados-sejam-detectados)
- [6. Anomalias de comportamento, custo e desempenho](#6-anomalias-de-comportamento-custo-e-desempenho)
  - [6.1 Certifique-se de que picos de tokens, requisições e custo sejam detectados por aplicação e identidade](#61-certifique-se-de-que-picos-de-tokens-requisicoes-e-custo-sejam-detectados-por-aplicacao-e-identidade)
  - [6.2 Certifique-se de que loops, retries excessivos e tempestades de chamadas sejam detectados](#62-certifique-se-de-que-loops-retries-excessivos-e-tempestades-de-chamadas-sejam-detectados)
  - [6.3 Certifique-se de que mudanças não esperadas de modelo, prompt, policy e configuração sejam detectadas](#63-certifique-se-de-que-mudancas-nao-esperadas-de-modelo-prompt-policy-e-configuracao-sejam-detectadas)
  - [6.4 Certifique-se de que taxa de falha dos guardrails e validadores seja monitorada](#64-certifique-se-de-que-taxa-de-falha-dos-guardrails-e-validadores-seja-monitorada)
  - [6.5 Certifique-se de que latência, erro, saturação e disponibilidade sejam medidos por camada](#65-certifique-se-de-que-latencia-erro-saturacao-e-disponibilidade-sejam-medidos-por-camada)
  - [6.6 Certifique-se de que drift de entrada, saída e desempenho do modelo seja detectado](#66-certifique-se-de-que-drift-de-entrada-saida-e-desempenho-do-modelo-seja-detectado)
- [7. Contenção técnica e comportamento seguro](#7-contencao-tecnica-e-comportamento-seguro)
  - [7.1 Certifique-se de que exista kill switch técnico para agentes e serviços de IA de alto impacto](#71-certifique-se-de-que-exista-kill-switch-tecnico-para-agentes-e-servicos-de-ia-de-alto-impacto)
  - [7.2 Certifique-se de que modelo, provider, tool, MCP server ou fonte RAG possam ser bloqueados individualmente](#72-certifique-se-de-que-modelo-provider-tool-mcp-server-ou-fonte-rag-possam-ser-bloqueados-individualmente)
  - [7.3 Certifique-se de que rollback para configuração conhecida e íntegra possa ser executado sem reconstrução manual](#73-certifique-se-de-que-rollback-para-configuracao-conhecida-e-integra-possa-ser-executado-sem-reconstrucao-manual)
  - [7.4 Certifique-se de que circuit breakers interrompam chamadas quando falhas ultrapassarem limites](#74-certifique-se-de-que-circuit-breakers-interrompam-chamadas-quando-falhas-ultrapassarem-limites)
  - [7.5 Certifique-se de que retries sejam limitados, espaçados e idempotentes](#75-certifique-se-de-que-retries-sejam-limitados-espacados-e-idempotentes)
  - [7.6 Certifique-se de que fallback preserve restrições de segurança e não amplie privilégios](#76-certifique-se-de-que-fallback-preserve-restricoes-de-seguranca-e-nao-amplie-privilegios)
- [8. Recuperação, continuidade e desativação técnica](#8-recuperacao-continuidade-e-desativacao-tecnica)
  - [8.1 Certifique-se de que configurações, policies, schemas e dashboards críticos possuam backup versionado](#81-certifique-se-de-que-configuracoes-policies-schemas-e-dashboards-criticos-possuam-backup-versionado)
  - [8.2 Certifique-se de que restauração de configurações e telemetria seja testada em ambiente isolado](#82-certifique-se-de-que-restauracao-de-configuracoes-e-telemetria-seja-testada-em-ambiente-isolado)
  - [8.3 Certifique-se de que componentes críticos de enforcement e observabilidade não possuam ponto único de falha](#83-certifique-se-de-que-componentes-criticos-de-enforcement-e-observabilidade-nao-possuam-ponto-unico-de-falha)
  - [8.4 Certifique-se de que objetivos técnicos de recuperação sejam medidos por testes de falha](#84-certifique-se-de-que-objetivos-tecnicos-de-recuperacao-sejam-medidos-por-testes-de-falha)
  - [8.5 Certifique-se de que credenciais, tokens e sessões possam ser revogados centralmente](#85-certifique-se-de-que-credenciais-tokens-e-sessoes-possam-ser-revogados-centralmente)
  - [8.6 Certifique-se de que a desativação técnica remova rotas, credenciais, dados operacionais e mecanismos de execução](#86-certifique-se-de-que-a-desativacao-tecnica-remova-rotas-credenciais-dados-operacionais-e-mecanismos-de-execucao)

## 1. Geração de eventos e integridade temporal

Define os requisitos mínimos para que execuções, decisões e falhas produzam eventos completos, temporalmente confiáveis e validáveis.

### 1.1 Certifique-se de que toda requisição material de IA gere evento de início e de término

**Control ID:** BAS-006.1.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Aplicações, gateways, runtimes, modelos, agentes, pipelines RAG e serviços de IA em homologação ou produção.

**Description**

Cada requisição deve gerar um evento de início antes do processamento e um evento de término após sucesso, bloqueio, erro, timeout ou cancelamento. Ambos devem conter o mesmo request_id ou identificador correlacionável. Requisições assíncronas devem registrar também o identificador do job e cada transição de estado.

**Rationale**

Sem eventos de início e término não é possível distinguir requisição não iniciada, processamento em andamento, falha silenciosa, perda de resposta ou execução concluída sem registro.

**Impact**

A instrumentação aumenta volume de telemetria e pode exigir ajuste de capacidade de coleta e retenção.

**Audit**

1. Executar amostras de requisições com sucesso, bloqueio, erro, timeout e cancelamento.
2. Confirmar que cada amostra produziu evento de início e evento de término com o mesmo request_id.
3. Confirmar que o evento de término contém result_status explícito e não depende da ausência de erro para representar sucesso.
4. Reprovar se qualquer caminho de execução terminar sem evento final ou se o início for registrado somente após o processamento.

**Remediation**

Instrumentar os pontos de entrada e saída do fluxo, registrar todos os estados finais e garantir que exceções não tratadas sejam convertidas em evento de término com falha.

**Evidence**

Eventos correlacionados de início e término para todos os cenários de teste e consulta demonstrando ausência de requisições órfãs.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 AU-2, AU-12, SI-4; NIST AI RMF MEASURE

---

### 1.2 Certifique-se de que timestamps de eventos utilizem UTC e fonte de tempo sincronizada

**Control ID:** BAS-006.1.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Todos os componentes que gerem, transformem, transportem ou armazenem eventos de IA.

**Description**

Eventos devem registrar timestamp em UTC com precisão mínima de milissegundos e offset explícito. Hosts, containers, funções, gateways, bancos e coletores devem utilizar fonte de tempo corporativa ou serviço confiável sincronizado. O desvio máximo permitido entre componentes do mesmo fluxo é de 2 segundos.

**Rationale**

Relógios divergentes impedem ordenar ações, calcular latência, correlacionar evidências e determinar a sequência real de um incidente.

**Impact**

Componentes legados podem exigir configuração de NTP/chrony ou conversão de formatos locais para UTC.

**Audit**

1. Consultar a configuração de sincronização de tempo de cada componente e confirmar estado saudável.
2. Comparar timestamps gerados simultaneamente por aplicação, gateway, provider e coletor.
3. Calcular o maior desvio observado; o valor deve ser igual ou inferior a 2 segundos.
4. Reprovar se houver timestamp sem timezone, em horário local, ou componente sem sincronização ativa.

**Remediation**

Configurar sincronização de tempo, padronizar UTC em todos os emissores e rejeitar ou marcar eventos cujo timestamp não possa ser validado.

**Evidence**

Configurações de NTP/chrony ou serviço equivalente, amostra de eventos e relatório de desvio temporal.

**Mappings**

CIS Controls v8 8; NIST SP 800-53 AU-8; ISO/IEC 27002 8.17

---

### 1.3 Certifique-se de que cada evento possua identificador único e não reutilizável

**Control ID:** BAS-006.1.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Eventos produzidos por aplicações, gateways, RAG, agentes, MCP, providers, pipelines e controles de segurança.

**Description**

Cada evento deve possuir event_id globalmente único, gerado por mecanismo que evite colisão entre instâncias e ambientes. O mesmo event_id não pode ser reutilizado em retry, reprocessamento, exportação ou transformação; cópias devem preservar o event_id original e adicionar identificador próprio de transporte quando necessário.

**Rationale**

Identificadores duplicados podem sobrescrever evidências, confundir deduplicação e permitir que eventos distintos sejam tratados como uma única ocorrência.

**Impact**

A adoção pode exigir alteração do schema e dos parsers atuais.

**Audit**

1. Coletar todos os eventos de uma janela representativa em múltiplas instâncias e ambientes.
2. Contar event_id distintos e confirmar igualdade com a quantidade total de eventos.
3. Reprocessar uma amostra e confirmar preservação do event_id original sem criação de evento sem identidade própria.
4. Reprovar se o identificador for sequencial local sem namespace, reutilizável ou ausente.

**Remediation**

Gerar UUID v4/v7, ULID ou identificador equivalente com namespace suficiente e tornar o campo obrigatório no schema e no pipeline de coleta.

**Evidence**

Consulta de unicidade, schema do evento e resultado de teste de reprocessamento.

**Mappings**

CIS Controls v8 8; NIST SP 800-53 AU-3, AU-12

---

### 1.4 Certifique-se de que eventos registrem o modelo, provider, deployment e versão efetivamente utilizados

**Control ID:** BAS-006.1.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Chamadas a modelos próprios, gerenciados, externos, locais, roteados ou com fallback.

**Description**

O evento de execução deve registrar provider_id, model_id, model_version ou digest, deployment_id e route_id efetivos após qualquer decisão de roteamento ou fallback. Alias mutável sem resolução para versão concreta não atende ao controle.

**Rationale**

Sem a versão efetiva não é possível atribuir comportamento, investigar regressões, bloquear componente comprometido ou reproduzir a resposta.

**Impact**

Providers que ocultem versão podem exigir captura do deployment e do identificador de release disponibilizado pelo serviço.

**Audit**

1. Executar chamadas para cada rota, incluindo fallback e mudança de modelo.
2. Confirmar que os eventos registram os valores efetivos retornados pela camada de roteamento e não apenas os valores solicitados.
3. Comparar os metadados do evento com a configuração do deployment e confirmar correspondência.
4. Reprovar se o evento contiver somente alias como latest, default ou auto sem versão resolvida.

**Remediation**

Instrumentar a camada que conhece o destino efetivo, resolver aliases para identificadores imutáveis e incluir os campos obrigatórios no evento final.

**Evidence**

Eventos de cada rota e fallback, exportação dos deployments e comparação entre versão executada e registrada.

**Mappings**

CIS Controls v8 1, 2 e 8; NIST SP 800-53 CM-2, AU-3; NIST AI RMF GOVERN

---

### 1.5 Certifique-se de que decisões de segurança e resultados sejam registrados com valores enumerados

**Control ID:** BAS-006.1.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Guardrails, DLP, filtros, authorization engines, gateways, validadores de input/output, tools e políticas de segurança.

**Description**

Cada decisão deve registrar policy_id, rule_id, decision e decision_reason. O campo decision deve aceitar somente valores enumerados, como allow, block, redact, mask, quarantine, require_human, throttle ou error. O resultado técnico deve ser registrado separadamente em result_status, como success, denied, failed, timeout ou cancelled.

**Rationale**

Texto livre e ausência de distinção entre decisão e resultado impedem correlação confiável, métricas e reconstrução do enforcement aplicado.

**Impact**

Políticas existentes podem precisar de IDs estáveis e adaptação do schema de eventos.

**Audit**

1. Acionar pelo menos uma condição para cada ação suportada pela plataforma.
2. Confirmar que decision, decision_reason, policy_id e rule_id são preenchidos no ponto de enforcement.
3. Validar o schema e confirmar rejeição de valores fora da enumeração.
4. Reprovar se bloqueio, erro e falha forem representados pelo mesmo valor ou somente por mensagem textual.

**Remediation**

Definir enumerações canônicas, atribuir IDs estáveis às políticas e regras e alterar os emissores para registrar decisão e resultado em campos separados.

**Evidence**

Schema com enumerações, eventos de teste de cada decisão e validação de valores inválidos rejeitados.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 AU-3, AU-12, SI-4

---

### 1.6 Certifique-se de que o schema de eventos seja versionado e compatível com validação automática

**Control ID:** BAS-006.1.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Schemas de eventos, parsers, transformadores, conectores e consumidores de telemetria de IA.

**Description**

Todo evento deve declarar schema_name e schema_version. O schema deve definir tipos, obrigatoriedade, enumerações e limites de tamanho. Mudança incompatível deve gerar nova versão principal; campos novos opcionais podem gerar versão secundária. Eventos inválidos não podem ser aceitos silenciosamente.

**Rationale**

Mudanças não controladas quebram parsers, descartam campos e criam lacunas de detecção sem erro aparente.

**Impact**

A versionagem exige manutenção de compatibilidade e atualização coordenada de emissores e consumidores.

**Audit**

1. Obter os schemas publicados e verificar versionamento semântico ou regra equivalente documentada tecnicamente.
2. Enviar evento sem campo obrigatório, com tipo incorreto e com valor fora da enumeração; todos devem ser rejeitados ou desviados para quarentena.
3. Confirmar que consumidores aceitam as versões suportadas e alertam versão desconhecida.
4. Reprovar se o parser ignorar falhas de validação ou se eventos não declararem versão.

**Remediation**

Publicar schemas versionados em registry, habilitar validação na origem e na ingestão e encaminhar eventos inválidos para quarentena com alerta.

**Evidence**

Schemas, histórico de versões, configuração do validador e eventos inválidos em quarentena.

**Mappings**

CIS Controls v8 4, 8 e 16; NIST SP 800-53 CM-3, AU-12, SI-10

---

## 2. Correlação e contexto ponta a ponta

Estabelece identificadores e metadados necessários para reconstruir o fluxo entre aplicações, modelos, RAG, agentes, MCP e sistemas downstream.

### 2.1 Certifique-se de que trace_id seja propagado por todas as camadas do fluxo de IA

**Control ID:** BAS-006.2.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Fluxos que atravessem aplicação, gateway, orquestrador, provider, RAG, agente, MCP, tool, fila ou sistema downstream.

**Description**

Um trace_id imutável deve ser criado no primeiro ponto confiável do fluxo e propagado por todas as chamadas síncronas e assíncronas. Cada componente deve registrar o mesmo trace_id e um span_id próprio. O modelo, o usuário e conteúdo não confiável não podem definir ou sobrescrever esses valores.

**Rationale**

Sem correlação ponta a ponta, eventos ficam isolados e não é possível reconstruir a sequência completa da requisição e das ações resultantes.

**Impact**

Integrações com terceiros podem exigir mapeamento entre identificadores locais e o trace_id corporativo.

**Audit**

1. Executar fluxo completo com RAG, modelo e ação downstream quando aplicável.
2. Consultar logs de cada camada e confirmar o mesmo trace_id e span_id distintos.
3. Tentar fornecer trace_id por prompt, header externo ou parâmetro de tool; o valor deve ser ignorado ou substituído no ponto confiável.
4. Reprovar se qualquer etapa crítica não puder ser associada ao trace original.

**Remediation**

Adotar contexto distribuído assinado ou protegido, propagar o trace_id por headers, mensagens e jobs e impedir sobrescrita por entrada não confiável.

**Evidence**

Consulta ponta a ponta por trace_id, diagrama de propagação e teste de tentativa de sobrescrita.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 AU-6, AU-12; OpenTelemetry

---

### 2.2 Certifique-se de que request_id, response_id e job_id sejam únicos e relacionados

**Control ID:** BAS-006.2.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Chamadas síncronas, streaming, batch, filas, jobs assíncronos e respostas parciais.

**Description**

Cada requisição deve possuir request_id único; cada resposta final ou segmento de streaming deve possuir response_id; operações assíncronas devem possuir job_id. Os eventos devem relacionar explicitamente esses identificadores ao trace_id e entre si. Retry deve gerar nova tentativa identificável sem apagar a requisição original.

**Rationale**

Sem identificadores separados, respostas podem ser atribuídas à requisição errada e retries podem ocultar loops ou duplicações.

**Impact**

A alteração pode aumentar a quantidade de campos e exigir atualização dos consumidores.

**Audit**

1. Executar chamadas simples, streaming, retry e job assíncrono.
2. Confirmar unicidade dos IDs e relacionamento com trace_id.
3. Verificar que cada retry possui attempt_number ou identificador equivalente e não reutiliza silenciosamente a mesma ocorrência.
4. Reprovar se uma resposta não puder ser ligada a uma requisição ou se múltiplas respostas finais usarem o mesmo response_id.

**Remediation**

Gerar identificadores independentes por entidade, registrar relações pai-filho e incluir número da tentativa nos eventos.

**Evidence**

Amostras de eventos síncronos, streaming e assíncronos, consulta de unicidade e correlação.

**Mappings**

CIS Controls v8 8; NIST SP 800-53 AU-3, AU-6, AU-12

---

### 2.3 Certifique-se de que a identidade originadora e a identidade técnica sejam registradas separadamente

**Control ID:** BAS-006.2.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Requisições iniciadas por usuários, aplicações, workloads, agentes, eventos ou processos automatizados.

**Description**

Eventos devem registrar subject_id da identidade originadora autenticada e actor_id da identidade técnica que executou a operação. Quando houver delegação, on_behalf_of deve refletir o subject validado. Nenhum desses campos pode ser obtido de texto de prompt ou parâmetro controlado pelo modelo.

**Rationale**

A mistura de identidades impede determinar quem solicitou, qual componente executou e com quais privilégios a ação ocorreu.

**Impact**

Pode exigir token exchange, claims assinadas ou integração adicional com IAM.

**Audit**

1. Executar requisições por usuários distintos, workload e agente.
2. Confirmar que subject_id e actor_id permanecem distintos e correspondem às identidades autenticadas.
3. Tentar alterar subject_id/on_behalf_of via input ou tool; os eventos devem manter o valor confiável.
4. Reprovar se ações forem registradas somente com conta de serviço ou se o usuário puder escolher a identidade registrada.

**Remediation**

Capturar identidades do contexto autenticado, propagar claims protegidas e registrar separadamente solicitante, executor e delegação.

**Evidence**

Eventos de usuários e workloads, claims mascaradas e teste de tentativa de falsificação de identidade.

**Mappings**

CIS Controls v8 5, 6 e 8; NIST SP 800-53 AC-3, IA-2, AU-3

---

### 2.4 Certifique-se de que tenant, conta, ambiente, região e classificação de dados estejam presentes nos eventos

**Control ID:** BAS-006.2.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Ambientes multi-tenant, múltiplas contas/subscriptions/projects, regiões, zonas ou classificações de informação.

**Description**

Eventos devem registrar tenant_id, account_or_project_id, environment, region e data_classification aplicáveis à execução. Campos não aplicáveis devem utilizar valor explícito not_applicable; valores vazios não são permitidos para eventos materiais.

**Rationale**

Ausência de contexto de isolamento dificulta detectar acesso cruzado, uso em região indevida e processamento incompatível com a classificação do dado.

**Impact**

Pode ser necessário enriquecer eventos no gateway ou coletor quando o componente emissor não conhece todos os campos.

**Audit**

1. Selecionar eventos de todos os ambientes, tenants e regiões ativos.
2. Confirmar preenchimento dos cinco campos com valores válidos ou not_applicable.
3. Comparar os valores com a configuração de deployment e a classificação da requisição.
4. Reprovar se produção e não produção não puderem ser distinguidos ou se tenant/conta estiverem ausentes em ambiente compartilhado.

**Remediation**

Adicionar os campos ao schema, enriquecer no ponto confiável e bloquear ingestão de eventos materiais com contexto obrigatório ausente.

**Evidence**

Eventos por ambiente/tenant, tabela de valores válidos e comparação com configuração de deployment.

**Mappings**

CIS Controls v8 1, 3 e 8; NIST SP 800-53 AC-4, AU-3, SC-7

---

### 2.5 Certifique-se de que recuperações RAG registrem fontes e objetos efetivamente utilizados

**Control ID:** BAS-006.2.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Soluções com RAG, busca semântica, bases de conhecimento, memória recuperável ou contexto externo.

**Description**

Cada recuperação deve registrar rag_source_id, index_id, document_id, chunk_id ou referência equivalente, source_version, authorization_decision e score utilizado na seleção. O evento deve indicar quais itens foram incluídos no contexto final, e não apenas quais foram candidatos.

**Rationale**

Sem referência ao contexto efetivo não é possível investigar vazamento, poisoning, resposta incorreta ou exclusão não propagada.

**Impact**

O volume de metadados pode aumentar e alguns providers podem exigir captura na camada de orquestração.

**Audit**

1. Executar consultas que recuperem múltiplas fontes e itens autorizados e negados.
2. Confirmar que o evento distingue candidatos, itens selecionados e itens bloqueados.
3. Comparar document_id/chunk_id e versão com o índice consultado.
4. Reprovar se apenas a consulta ou o texto final forem registrados sem identificar as fontes utilizadas.

**Remediation**

Instrumentar o retriever e o context builder, persistir referências imutáveis de fontes e registrar decisão de autorização e inclusão no contexto.

**Evidence**

Eventos de retrieval, manifestos do índice e reconstrução do contexto a partir das referências registradas.

**Mappings**

CIS Controls v8 3 e 8; NIST SP 800-53 AU-3, AC-4; OWASP LLM Top 10 LLM08

---

### 2.6 Certifique-se de que tool calls e chamadas MCP sejam correlacionadas à decisão que as originou

**Control ID:** BAS-006.2.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes, tool calling, function calling, MCP clients/servers e automações acionadas por IA.

**Description**

Cada chamada deve registrar agent_id, agent_version, tool_id ou capability_id, server_id quando MCP, tool_call_id, autorização aplicada, parâmetros redigidos, resultado e trace_id. O evento de execução deve referenciar o evento de planejamento ou decisão que solicitou a ação.

**Rationale**

Ações sem ligação à decisão e à autorização permitem execução invisível, investigação incompleta e dificuldade para identificar excessive agency.

**Impact**

A instrumentação pode exigir correlação entre orquestrador, gateway MCP e sistema-alvo.

**Audit**

1. Executar tools permitidas, negadas, com erro e com confirmação humana.
2. Rastrear cada tool_call_id do plano até o sistema-alvo e o resultado final.
3. Confirmar registro da autorização e, quando aplicável, do approval_id sem incluir conteúdo sensível desnecessário.
4. Reprovar se existir ação no sistema-alvo sem evento agentic correspondente ou chamada sem identidade da tool/capability.

**Remediation**

Adicionar identificadores estáveis de agente, tool e servidor, propagar trace_id e registrar eventos antes e depois da autorização e execução.

**Evidence**

Eventos ponta a ponta de tool/MCP, logs do sistema-alvo e correlação por tool_call_id.

**Mappings**

CIS Controls v8 6, 8 e 13; NIST SP 800-53 AC-3, AU-12, SI-4; MITRE ATLAS

---

## 3. Proteção, minimização e integridade dos registros

Protege os registros contra exposição, alteração, exclusão e uso excessivo de conteúdo sensível.

### 3.1 Certifique-se de que segredos e credenciais não sejam registrados em texto claro

**Control ID:** BAS-006.3.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Logs de aplicação, gateway, provider, RAG, agentes, MCP, pipelines, erros e traces.

**Description**

Chaves de API, tokens, cookies, authorization headers, senhas, certificados privados, connection strings e valores de secret stores devem ser removidos antes da emissão do evento. Redação deve ocorrer na origem e novamente na ingestão como defesa em profundidade.

**Rationale**

Segredos em logs são replicados para múltiplos sistemas, possuem retenção longa e podem permitir comprometimento amplo.

**Impact**

Regras agressivas podem ocultar valores legítimos e demandar ajuste de padrões.

**Audit**

1. Executar requisições contendo segredos de teste em headers, parâmetros, prompt e mensagens de erro.
2. Pesquisar os valores exatos em logs locais, buffers, APM, filas, SIEM e exports.
3. Confirmar que nenhum valor completo aparece e que a redação ocorre antes do transporte.
4. Reprovar se o segredo estiver presente mesmo em fonte intermediária ou log de debug.

**Remediation**

Implementar filtros na origem e na ingestão, desabilitar logging de headers sensíveis e remover ou rotacionar segredos já expostos.

**Evidence**

Casos de teste com segredos, consultas negativas em todas as camadas e configuração de redaction.

**Mappings**

CIS Controls v8 3, 6 e 8; NIST SP 800-53 IA-5, AU-9; OWASP Logging Cheat Sheet

---

### 3.2 Certifique-se de que prompts, outputs e documentos não sejam armazenados integralmente por padrão

**Control ID:** BAS-006.3.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Eventos de inferência, traces, APM, debug, RAG e ferramentas de observabilidade.

**Description**

O padrão deve registrar metadados, classificação, tamanho, hashes e referências em vez do conteúdo integral. Conteúdo somente pode ser armazenado em repositório segregado quando tecnicamente necessário para investigação ou avaliação, com redaction, criptografia e acesso restrito. Dashboards e alertas não podem exibir conteúdo integral sensível.

**Rationale**

Captura indiscriminada cria nova base de dados sensíveis, amplia exposição e pode violar finalidade e minimização.

**Impact**

A redução de conteúdo pode limitar troubleshooting e exigir mecanismo controlado de captura sob demanda.

**Audit**

1. Inspecionar configurações de logging, tracing e APM em todos os componentes.
2. Executar prompt e output contendo dado de teste classificado e verificar eventos, alertas e dashboards.
3. Confirmar que o conteúdo integral não está presente e que referências/hashes são suficientes para correlação.
4. Reprovar se captura integral estiver habilitada globalmente ou acessível a perfis amplos.

**Remediation**

Desabilitar captura integral por padrão, aplicar redaction e mover amostras necessárias para storage segregado com controles específicos.

**Evidence**

Configuração de logging, amostras de eventos minimizados e teste com dado classificado.

**Mappings**

CIS Controls v8 3 e 8; NIST SP 800-53 AU-9, SI-12; NIST Privacy Framework

---

### 3.3 Certifique-se de que eventos sejam criptografados em trânsito e em repouso

**Control ID:** BAS-006.3.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes de coleta, filas, brokers, APIs, data lakes, SIEM, APM, backups e exportações de logs.

**Description**

Todo transporte deve utilizar TLS 1.2 ou superior com validação de certificado; conexões internas não são exceção. Armazenamento deve utilizar criptografia com chaves gerenciadas e rotação configurada. Protocolos sem criptografia e certificados não validados não são permitidos.

**Rationale**

Logs contêm identidades, arquitetura, decisões e indicadores úteis a atacantes; interceptação ou acesso ao storage expõe dados e controles internos.

**Impact**

Pode exigir atualização de agentes, certificados e integrações legadas.

**Audit**

1. Enumerar todos os caminhos de transporte e armazenamentos de telemetria.
2. Confirmar TLS 1.2+ com validação completa em cada conexão e criptografia ativa em cada storage.
3. Tentar conexão sem TLS ou com certificado inválido; a conexão deve falhar.
4. Reprovar se existir exportação, fila, syslog ou bucket sem criptografia.

**Remediation**

Habilitar TLS validado, desabilitar protocolos inseguros e configurar criptografia e rotação de chaves em todos os destinos e backups.

**Evidence**

Configurações TLS e de storage, inventário de fluxos e testes negativos de conexão insegura.

**Mappings**

CIS Controls v8 3 e 8; NIST SP 800-53 SC-8, SC-13, AU-9

---

### 3.4 Certifique-se de que o acesso a logs de IA aplique menor privilégio e segregação por função

**Control ID:** BAS-006.3.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** SIEM, data lakes, APM, stores de traces, buckets, dashboards e ferramentas de suporte.

**Description**

Permissões devem separar consulta operacional, investigação de segurança, administração da plataforma e gestão de retenção. Acesso a conteúdo sensível deve ser distinto do acesso a metadados. Contas de aplicação não podem ler o repositório central de logs e operadores não podem alterar ou excluir eventos.

**Rationale**

Privilégios amplos permitem vazamento, alteração de evidência e abuso de informações operacionais.

**Impact**

A segregação aumenta quantidade de roles e pode limitar troubleshooting informal.

**Audit**

1. Exportar roles e bindings de todos os repositórios de logs.
2. Confirmar que cada função possui apenas operações necessárias e que exclusão/alteração está restrita a identidade administrativa separada.
3. Testar leitura de conteúdo sensível por perfil de dashboard comum e alteração de evento por operador; ambas devem ser negadas.
4. Reprovar se grupos genéricos, contas compartilhadas ou aplicação produtiva possuírem leitura ampla.

**Remediation**

Criar roles separadas, remover permissões amplas, restringir conteúdo sensível e negar alteração/exclusão para perfis operacionais.

**Evidence**

Matriz de permissões, exportação de bindings e resultados de testes negativos.

**Mappings**

CIS Controls v8 5, 6 e 8; NIST SP 800-53 AC-6, AU-9

---

### 3.5 Certifique-se de que eventos críticos sejam protegidos contra alteração e exclusão

**Control ID:** BAS-006.3.5
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Eventos de autenticação, autorização, policy decision, tool action, administração, mudança, kill switch e incidentes.

**Description**

Eventos críticos devem ser enviados para storage append-only, WORM, object lock ou mecanismo equivalente antes que a identidade geradora possa alterá-los. A retenção técnica deve impedir exclusão antecipada, inclusive por administradores comuns da plataforma de origem.

**Rationale**

Um atacante ou operador privilegiado pode apagar ou adulterar evidências para ocultar ações e impedir investigação.

**Impact**

Imutabilidade aumenta custo de armazenamento e exige planejamento de retenção e correção de eventos inválidos por registros compensatórios.

**Audit**

1. Selecionar eventos críticos e identificar o destino imutável correspondente.
2. Tentar alterar e excluir eventos com identidade da aplicação, operador e administrador comum; todas as operações devem falhar.
3. Confirmar que alteração legítima é representada por novo evento e não por edição do original.
4. Reprovar se a mesma identidade que gera eventos puder removê-los antes da expiração.

**Remediation**

Habilitar retenção imutável, separar conta/chave do repositório e enviar eventos críticos de forma imediata para destino protegido.

**Evidence**

Configuração WORM/object lock, políticas de acesso e resultados de tentativas de alteração e exclusão.

**Mappings**

CIS Controls v8 8; NIST SP 800-53 AU-9, AU-11; SEC 17a-4 principles

---

### 3.6 Certifique-se de que consultas, exportações e alterações de configuração de logging sejam auditadas

**Control ID:** BAS-006.3.6
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** SIEM, data lakes, APM, stores de traces, dashboards, APIs de exportação e configurações de coleta/retenção.

**Description**

O sistema deve registrar quem consultou dados sensíveis, quais filtros utilizou, volume acessado, exportações realizadas e qualquer mudança em fontes, parsers, retenção, redaction, destinos ou regras de auditoria. Esses eventos de auditoria devem ser armazenados fora do alcance do administrador da ferramenta auditada.

**Rationale**

Acesso indevido e desativação de logging podem permanecer invisíveis se a própria plataforma não auditar seus administradores e usuários.

**Impact**

A telemetria adicional aumenta volume e pode exigir integração entre ferramentas.

**Audit**

1. Executar consulta, exportação e mudança de configuração com identidades distintas.
2. Confirmar geração de evento com identidade, ação, objeto, timestamp e resultado.
3. Verificar que o administrador da ferramenta não consegue excluir os eventos de auditoria correspondentes.
4. Reprovar se exportações ou mudanças de retenção/redaction não forem auditadas.

**Remediation**

Habilitar audit logs administrativos e de acesso, encaminhá-los a repositório independente e criar alertas para mudanças críticas.

**Evidence**

Eventos de consulta, exportação e mudança, configuração de destino independente e teste de exclusão negada.

**Mappings**

CIS Controls v8 5, 6 e 8; NIST SP 800-53 AU-2, AU-9, AC-6

---

## 4. Coleta, transporte e integração com SIEM

Assegura entrega confiável, validação, quarentena, monitoramento do pipeline e disponibilidade tempestiva dos eventos.

### 4.1 Certifique-se de que emissores mantenham buffer persistente quando o coletor estiver indisponível

**Control ID:** BAS-006.4.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Agentes, gateways, runtimes e serviços que enviem eventos para collector, broker, data lake ou SIEM.

**Description**

O emissor ou sidecar deve manter fila persistente limitada quando o destino estiver indisponível. O buffer deve sobreviver a reinício, aplicar ordem ou sequence_number e reenviar sem perda silenciosa. Quando atingir o limite, deve gerar alerta e aplicar comportamento explicitamente definido.

**Rationale**

Falhas temporárias de rede ou do coletor podem criar lacunas exatamente durante incidentes ou degradações.

**Impact**

Buffers consomem disco e precisam de limites para evitar esgotamento de recurso.

**Audit**

1. Interromper o coletor durante geração controlada de eventos por período superior ao retry imediato.
2. Reiniciar o emissor e restabelecer o coletor.
3. Confirmar entrega de todos os eventos gerados, sem perda e com ordem ou sequence_number verificável.
4. Reprovar se eventos forem descartados silenciosamente ou se o buffer existir apenas em memória.

**Remediation**

Habilitar fila persistente com tamanho e política definidos, configurar reenvio e alertar ocupação e descarte.

**Evidence**

Configuração do buffer, contagem antes/depois da indisponibilidade e eventos de ocupação da fila.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 AU-5, CP-10

---

### 4.2 Certifique-se de que perda de telemetria crítica provoque estado seguro em operações de alto impacto

**Control ID:** BAS-006.4.2
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Agentes com ação material, decisões sensíveis, transações financeiras, acesso a dados críticos e canais externos de alto impacto.

**Description**

Quando eventos obrigatórios não puderem ser persistidos ou encaminhados por período acima do limite técnico definido, a operação de alto impacto deve ser bloqueada, reduzida para modo somente leitura ou encaminhada para fallback seguro. Continuar execução sem trilha não é permitido.

**Rationale**

A indisponibilidade de logging pode ser explorada para executar ações sem evidência e pode impedir detecção de abuso.

**Impact**

Falha do pipeline de telemetria poderá reduzir disponibilidade do serviço crítico.

**Audit**

1. Identificar operações classificadas como alto impacto e o limite de perda de telemetria configurado.
2. Interromper o destino de logs até ultrapassar o limite.
3. Confirmar que novas operações são bloqueadas ou degradadas para modo seguro e que o estado retorna apenas após restabelecimento validado.
4. Reprovar se a operação continuar normalmente com eventos perdidos.

**Remediation**

Implementar health signal confiável do pipeline, circuit breaker de observabilidade e comportamento fail-closed ou read-only para operações de alto impacto.

**Evidence**

Configuração do limite, teste de indisponibilidade e eventos de entrada e saída do modo seguro.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 AU-5, SI-4, SC-24

---

### 4.3 Certifique-se de que eventos inválidos sejam colocados em quarentena e não descartados silenciosamente

**Control ID:** BAS-006.4.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Collectors, brokers, parsers, pipelines ETL e integrações de SIEM/APM.

**Description**

Evento que falhar em validação, parsing, enriquecimento ou indexação deve ser enviado a fila ou índice de quarentena com motivo, fonte e timestamp. A quantidade e taxa de falhas devem gerar métrica e alerta. O pipeline não pode converter erro em descarte sem registro.

**Rationale**

Descarte silencioso cria lacunas de visibilidade e pode ocultar mudança de schema ou ataque contra o parser.

**Impact**

Quarentena requer armazenamento adicional e mecanismo de reprocessamento.

**Audit**

1. Enviar eventos com JSON malformado, schema desconhecido, campo obrigatório ausente e tamanho excedido.
2. Confirmar que todos são direcionados à quarentena com motivo específico.
3. Confirmar geração de métrica e alerta quando a taxa ultrapassar o limiar configurado.
4. Reprovar se o evento desaparecer sem rastreabilidade ou for aceito com campos críticos ausentes.

**Remediation**

Configurar dead-letter queue ou índice de quarentena, métricas por motivo e reprocessamento controlado após correção.

**Evidence**

Eventos de teste em quarentena, métricas de falha e configuração de dead-letter queue.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 AU-5, SI-10

---

### 4.4 Certifique-se de que entrega de eventos possua confirmação, controle de duplicidade e sequência

**Control ID:** BAS-006.4.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Pipelines com brokers, filas, retries, replicação, collectors ou envio em lote.

**Description**

O transporte deve utilizar acknowledgment e retry com backoff. Eventos duplicados devem ser identificados por event_id sem remover ocorrências legítimas. Para fontes ordenadas, sequence_number deve permitir detectar lacuna e reordenação. Métricas de duplicidade e gap devem ser expostas.

**Rationale**

Sem confirmação e sequência, o pipeline pode perder eventos ou contar duplicidades como incidentes distintos.

**Impact**

A implementação exige estado de deduplicação e pode introduzir latência.

**Audit**

1. Forçar falha após envio e antes do acknowledgment para provocar retry.
2. Confirmar que o evento aparece uma única vez na visão analítica, preservando a tentativa de transporte em metadado técnico.
3. Remover artificialmente um sequence_number e confirmar detecção da lacuna.
4. Reprovar se não houver mecanismo para distinguir duplicidade de evento distinto.

**Remediation**

Habilitar acknowledgment, retries idempotentes, deduplicação por event_id e monitoramento de sequência por fonte.

**Evidence**

Configuração de entrega, teste de retry, métrica de duplicidade e alerta de sequence gap.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 AU-5, AU-12

---

### 4.5 Certifique-se de que a saúde do pipeline de telemetria seja monitorada independentemente da aplicação

**Control ID:** BAS-006.4.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Coletores, brokers, filas, parsers, data lakes, SIEM, APM e rotas de exportação.

**Description**

Devem existir métricas independentes de disponibilidade, taxa de ingestão, backlog, latência, falhas de parsing, descarte, uso de capacidade e última mensagem por fonte. Heartbeat deve ser gerado por cada fonte crítica em intervalo máximo de 5 minutos.

**Rationale**

Uma aplicação pode permanecer disponível enquanto seus logs deixam de chegar, criando falsa percepção de monitoramento.

**Impact**

Heartbeats e métricas adicionais consomem capacidade mínima de telemetria.

**Audit**

1. Listar todas as fontes críticas e verificar heartbeat recente no monitor independente.
2. Interromper uma fonte e confirmar alerta em até duas vezes o intervalo de heartbeat.
3. Simular backlog e erro de parser e confirmar métricas e alertas específicos.
4. Reprovar se a saúde for inferida somente pela disponibilidade da aplicação.

**Remediation**

Instrumentar cada estágio, criar heartbeat por fonte e monitorar o pipeline em sistema separado do caminho principal de logs.

**Evidence**

Dashboard de saúde, configuração de heartbeat e alertas gerados em testes de interrupção e backlog.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 AU-5, SI-4

---

### 4.6 Certifique-se de que eventos críticos estejam disponíveis no SIEM dentro do limite de latência definido

**Control ID:** BAS-006.4.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Eventos de autenticação, autorização, bloqueio, vazamento, tool action, administração, mudança e falha de segurança.

**Description**

Eventos críticos devem estar pesquisáveis no SIEM em até 2 minutos após sua geração. Eventos não críticos podem utilizar limite maior explicitamente configurado. A latência deve ser calculada entre event_timestamp e ingestion_timestamp e monitorada por percentis.

**Rationale**

Alta latência atrasa detecção e resposta mesmo quando todos os eventos são finalmente entregues.

**Impact**

O limite pode exigir ingestão em streaming e maior capacidade de processamento.

**Audit**

1. Gerar pelo menos 100 eventos críticos distribuídos entre as fontes principais.
2. Calcular a latência de ingestão p95 e confirmar valor igual ou inferior a 2 minutos.
3. Executar teste durante pico de volume e confirmar manutenção do limite.
4. Reprovar se eventos críticos forem enviados apenas em batch ou se a latência não for mensurada.

**Remediation**

Priorizar eventos críticos, reduzir intervalos de batch, aumentar capacidade do pipeline e criar alerta para violação do p95.

**Evidence**

Relatório de latência por fonte, configuração de prioridade e resultado de teste em carga.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 AU-6, SI-4

---

## 5. Detecções técnicas de segurança para IA

Define capacidades técnicas mínimas para detectar abuso, vazamento, ataques contra prompts, RAG, agentes e MCP.

### 5.1 Certifique-se de que o uso de modelo, provider, rota ou capability não permitida seja detectado

**Control ID:** BAS-006.5.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Gateways, aplicações, agentes e workloads que selecionem providers, modelos, deployments, tools ou capabilities.

**Description**

A detecção deve comparar o destino efetivo com allowlist técnica aplicável à aplicação, ambiente e classificação de dados. Deve alertar tentativa e uso consumado de item desconhecido, suspenso, desativado ou fora do escopo. A regra não pode depender somente de nome textual fornecido pelo cliente.

**Rationale**

Shadow AI e bypass de catálogo expõem dados a componentes não avaliados e reduzem controle sobre versões e regiões.

**Impact**

A regra exige fonte confiável de allowlist e sincronização de identificadores técnicos.

**Audit**

1. Configurar item de teste não permitido e tentar utilizá-lo por rota direta e via gateway.
2. Confirmar geração de alerta contendo aplicação, identidade, item solicitado, item efetivo e decisão aplicada.
3. Alterar nome amigável mantendo identificador não permitido e confirmar detecção.
4. Reprovar se a regra detectar apenas itens conhecidos por lista estática desatualizada ou somente chamadas bloqueadas.

**Remediation**

Integrar o inventário técnico à regra, normalizar identificadores efetivos e alertar tentativas e execuções fora da allowlist.

**Evidence**

Regra de detecção, fonte de allowlist e alertas produzidos por testes de rota direta e gateway.

**Mappings**

CIS Controls v8 1, 2 e 13; NIST SP 800-53 CM-7, SI-4; MITRE ATLAS

---

### 5.2 Certifique-se de que exposição de dados sensíveis, segredos e credenciais em prompts ou outputs seja detectada

**Control ID:** BAS-006.5.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Inputs, outputs, anexos, contexto RAG, tool parameters e canais externos.

**Description**

Mecanismos DLP ou detectores equivalentes devem inspecionar dados antes do envio e antes da entrega do output. A detecção deve identificar tipos corporativos definidos, segredos e credenciais, registrar classificação e ação, e utilizar conteúdo redigido ou fingerprint no alerta.

**Rationale**

Vazamentos por IA podem ocorrer tanto na entrada quanto na saída e podem não ser visíveis em controles tradicionais de arquivo ou e-mail.

**Impact**

Inspeção pode adicionar latência e produzir falsos positivos que exigem calibração.

**Audit**

1. Enviar valores sintéticos representando cada classe sensível e segredo suportado na entrada e simular saída equivalente.
2. Confirmar alerta e ação conforme política em ambos os sentidos.
3. Verificar que o alerta não contém o valor integral sensível.
4. Reprovar se algum tipo crítico passar sem detecção ou se a regra inspecionar somente prompts de texto simples.

**Remediation**

Habilitar inspeção bidirecional, incluir anexos e parâmetros estruturados, calibrar classificadores e redigir evidências nos alertas.

**Evidence**

Matriz de tipos detectados, casos de teste e alertas com conteúdo minimizado.

**Mappings**

CIS Controls v8 3 e 13; NIST SP 800-53 SI-4, AC-4; OWASP LLM Top 10 LLM02

---

### 5.3 Certifique-se de que tentativas de prompt injection, jailbreak e prompt leakage sejam detectadas por múltiplos sinais

**Control ID:** BAS-006.5.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Aplicações conversacionais, RAG, agentes, APIs e serviços expostos a conteúdo não confiável.

**Description**

A detecção deve combinar pelo menos dois tipos de sinal entre regras, classificadores, violações de policy, padrões de encoding, mudança de papel, tentativa de revelar instruções e comportamento anômalo. Deve distinguir input direto, conteúdo recuperado e output. Um único regex genérico não atende ao controle.

**Rationale**

Ataques variam em linguagem e codificação; detecção baseada em um único padrão é facilmente contornada.

**Impact**

Múltiplos sinais aumentam custo e podem elevar falsos positivos.

**Audit**

1. Executar conjunto de testes com prompt injection direta, indireta, encoding, role override, jailbreak e tentativa de prompt leak.
2. Confirmar detecção por categoria e origem do conteúdo, com registro dos sinais que contribuíram.
3. Executar entradas benignas semelhantes e medir falsos positivos.
4. Reprovar se a cobertura depender de um único padrão ou se ataques indiretos não forem distinguidos.

**Remediation**

Combinar detectores complementares, registrar sinais e origem, manter casos de teste e ajustar thresholds com base em resultados.

**Evidence**

Conjunto de testes, configuração dos detectores, alertas por categoria e resultado de falsos positivos.

**Mappings**

CIS Controls v8 13 e 16; NIST SP 800-53 SI-4, SA-11; OWASP LLM Top 10 LLM01; MITRE ATLAS

---

### 5.4 Certifique-se de que ações agentic anômalas ou sem autorização sejam detectadas

**Control ID:** BAS-006.5.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes, tool calling, MCP, computer use e automações que produzam efeitos em sistemas.

**Description**

A detecção deve alertar ação negada, tool fora da allowlist, ausência de subject/on_behalf_of, autorização incompatível, excesso de frequência, mudança abrupta de recurso, tentativa de ultrapassar limite e ação crítica sem approval_id quando exigido.

**Rationale**

Agentes podem executar ações rapidamente e em escala; falhas de autorização ou excessive agency exigem detecção imediata.

**Impact**

Regras comportamentais podem exigir baseline por agente e tipo de tool.

**Audit**

1. Executar testes para cada condição: tool não permitida, ação negada, ausência de identidade, limite excedido e ação crítica sem aprovação.
2. Confirmar alerta contendo agente, tool, recurso, subject, decisão e trace_id.
3. Executar uso normal e confirmar que não é marcado como anômalo sem motivo.
4. Reprovar se a detecção depender somente do erro retornado pelo modelo ou não correlacionar com a autorização.

**Remediation**

Criar regras determinísticas para violações e modelos de baseline para frequência/recursos, integrando logs do agente, IAM e sistema-alvo.

**Evidence**

Regras, alertas dos cenários de teste e correlação com decisões de autorização.

**Mappings**

CIS Controls v8 6 e 13; NIST SP 800-53 AC-3, SI-4; OWASP LLM Top 10 LLM06

---

### 5.5 Certifique-se de que poisoning e recuperação indevida em RAG sejam detectados

**Control ID:** BAS-006.5.5
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** RAG, vector stores, bases de conhecimento, conectores e memórias recuperáveis.

**Description**

A detecção deve identificar alteração inesperada de fonte, hash divergente, inclusão em massa, instrução adversarial em conteúdo, queda de qualidade, retrieval negado, cross-tenant, over-retrieval e uso de documento removido ou expirado. Deve correlacionar ingestão, índice e consulta.

**Rationale**

Poisoning e falhas de autorização podem manipular outputs ou expor dados sem comprometer diretamente a aplicação.

**Impact**

A correlação exige telemetria detalhada de ingestão e recuperação e pode demandar evals periódicas.

**Audit**

1. Inserir documento de teste com instrução adversarial, alterar hash e tentar recuperação cross-tenant.
2. Confirmar alertas distintos para poisoning, integridade e autorização.
3. Remover ou expirar um documento e confirmar alerta caso ele ainda seja recuperado.
4. Reprovar se a detecção observar apenas a resposta final sem identificar a fonte ou o evento de ingestão relacionado.

**Remediation**

Correlacionar manifests, hashes, eventos de ingestão e retrieval; criar regras para alterações, violações de ACL e padrões adversariais.

**Evidence**

Casos de teste de poisoning/cross-tenant, alertas e consulta de correlação da fonte ao output.

**Mappings**

CIS Controls v8 3, 13 e 16; NIST SP 800-53 SI-4, SI-7; OWASP LLM Top 10 LLM08

---

### 5.6 Certifique-se de que servidores, tools, resources e prompts MCP desconhecidos ou alterados sejam detectados

**Control ID:** BAS-006.5.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Clientes, servidores, registries e gateways MCP.

**Description**

A detecção deve comparar server_id, certificate identity, tool_id, resource_id, prompt_id, versão e digest com registry confiável. Deve alertar entidade desconhecida, versão não permitida, mudança de schema, assinatura inválida, discovery inesperado e alteração de descrição capaz de influenciar seleção do modelo.

**Rationale**

Shadow MCP, tool poisoning e model misbinding podem introduzir capacidades maliciosas sem mudança no agente principal.

**Impact**

Exige registry atualizado e coleta de eventos de discovery e invocation.

**Audit**

1. Registrar servidor e tool de teste não autorizados e alterar schema/descrição de item autorizado.
2. Confirmar alerta na descoberta e antes ou no momento da invocação.
3. Confirmar que digest e identidade técnica são comparados, não apenas nome amigável.
4. Reprovar se o controle não detectar mudança de versão/schema ou entidade descoberta fora do registry.

**Remediation**

Integrar o registry MCP às regras, registrar discovery e comparar identidade, versão, schema e digest em cada conexão e chamada.

**Evidence**

Exportação do registry, eventos de discovery e alertas para servidor/tool desconhecido e alterado.

**Mappings**

CIS Controls v8 1, 2 e 13; NIST SP 800-53 CM-7, SI-4, SI-7; MITRE ATLAS

---

## 6. Anomalias de comportamento, custo e desempenho

Estabelece medições e detecções de desvios operacionais capazes de indicar abuso, degradação ou falha de controle.

### 6.1 Certifique-se de que picos de tokens, requisições e custo sejam detectados por aplicação e identidade

**Control ID:** BAS-006.6.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Gateways, providers, modelos e aplicações com medição de consumo.

**Description**

Devem existir limites e baseline por app_id, subject_id, model_id e janela de tempo para número de requisições, tokens de entrada/saída e custo estimado. A detecção deve considerar desvio percentual e limite absoluto para identificar abuso, loop e comprometimento.

**Rationale**

Consumo anômalo pode indicar credencial vazada, automação indevida, retry loop ou ataque de negação econômica.

**Impact**

Thresholds iniciais podem gerar falsos positivos até que o padrão normal seja conhecido.

**Audit**

1. Gerar volume controlado acima do limite absoluto e acima do desvio configurado para uma única identidade.
2. Confirmar alerta com dimensão de aplicação, identidade, modelo e custo/tokens.
3. Confirmar que aumento global legítimo não oculta anomalia localizada.
4. Reprovar se a regra usar somente valor mensal agregado ou não identificar a origem do consumo.

**Remediation**

Criar métricas por dimensão, configurar thresholds absolutos e relativos e integrar dados de billing e gateway.

**Evidence**

Dashboards, configuração de thresholds e alertas produzidos pelo teste de pico localizado.

**Mappings**

CIS Controls v8 13; NIST SP 800-53 SI-4, SC-5; FinOps principles

---

### 6.2 Certifique-se de que loops, retries excessivos e tempestades de chamadas sejam detectados

**Control ID:** BAS-006.6.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Aplicações, agentes, orquestradores, filas e gateways com retries ou chamadas encadeadas.

**Description**

A detecção deve considerar attempt_number, chamadas por trace_id, repetição de payload hash, profundidade de cadeia, alternância entre tools e intervalo entre tentativas. Deve alertar quando o limite configurado for ultrapassado, mesmo que cada chamada isolada seja válida.

**Rationale**

Loops podem gerar ações repetidas, custos elevados, saturação e efeitos duplicados em sistemas downstream.

**Impact**

A regra pode exigir rastreamento stateful por trace ou job.

**Audit**

1. Criar retry loop e cadeia agentic que ultrapassem os limites configurados.
2. Confirmar alerta antes do consumo máximo e com identificação do trace/job.
3. Executar retries legítimos dentro do limite e confirmar ausência de alerta indevido.
4. Reprovar se a regra observar somente erros ou volume global sem identificar repetição por fluxo.

**Remediation**

Registrar attempt_number e depth, criar limites por trace/job e alertar repetição de payload ou tool antes do esgotamento de recursos.

**Evidence**

Eventos do loop, regra de correlação e alerta contendo trace_id, tentativas e profundidade.

**Mappings**

CIS Controls v8 13; NIST SP 800-53 SI-4, SC-5; OWASP LLM Top 10 LLM10

---

### 6.3 Certifique-se de que mudanças não esperadas de modelo, prompt, policy e configuração sejam detectadas

**Control ID:** BAS-006.6.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Deployments, gateways, prompts sistêmicos, guardrails, parâmetros e rotas produtivas.

**Description**

O estado efetivo deve ser comparado continuamente com manifesto ou baseline imutável de release. Mudança de model digest, prompt version, policy version, parâmetros críticos, rota ou feature flag fora do mecanismo de deploy deve gerar alerta. A detecção deve utilizar valores efetivos, não somente eventos de mudança declarados.

**Rationale**

Alterações diretas podem desativar controles, mudar comportamento e invalidar testes sem produzir novo release.

**Impact**

A comparação periódica adiciona consultas e exige fonte confiável do estado esperado.

**Audit**

1. Alterar um parâmetro ou versão diretamente em ambiente de teste fora da pipeline.
2. Confirmar detecção da divergência e identificação do campo alterado.
3. Restaurar o manifesto e confirmar encerramento do drift.
4. Reprovar se a regra depender somente de audit log da mudança ou não comparar estado efetivo.

**Remediation**

Implementar drift detection entre configuração efetiva e manifesto assinado, consultar periodicamente e alertar qualquer divergência não reconhecida.

**Evidence**

Manifesto de release, snapshot do estado efetivo e alerta de drift produzido pelo teste.

**Mappings**

CIS Controls v8 4, 8 e 13; NIST SP 800-53 CM-3, CM-6, SI-4

---

### 6.4 Certifique-se de que taxa de falha dos guardrails e validadores seja monitorada

**Control ID:** BAS-006.6.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Filtros de input/output, DLP, content safety, schema validators, authorization engines e policies.

**Description**

Devem ser medidas taxa de allow, block, redact, error, timeout e bypass test result por regra e versão. Aumento de erros, queda abrupta de bloqueios esperados ou mudança estatisticamente relevante da distribuição deve gerar alerta.

**Rationale**

Guardrail pode permanecer habilitado, mas falhar aberto, sofrer regressão ou deixar de receber tráfego.

**Impact**

O monitoramento exige baseline e volume mínimo para evitar conclusões incorretas.

**Audit**

1. Interromper um guardrail, forçar timeout e alterar rota para contorná-lo em ambiente de teste.
2. Confirmar alertas para ausência de tráfego, aumento de erro e queda de eficácia.
3. Comparar métricas por rule_id e version antes e depois da mudança.
4. Reprovar se o dashboard mostrar apenas número total de bloqueios sem taxa, erros e cobertura.

**Remediation**

Instrumentar decisões e erros por regra/versão, definir baseline e alertar ausência de tráfego, falha aberta e desvio de eficácia.

**Evidence**

Métricas por regra, alertas dos testes e consulta de cobertura de tráfego.

**Mappings**

CIS Controls v8 13 e 16; NIST SP 800-53 SI-4, SA-11; NIST AI RMF MEASURE

---

### 6.5 Certifique-se de que latência, erro, saturação e disponibilidade sejam medidos por camada

**Control ID:** BAS-006.6.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Aplicação, gateway, retriever, modelo/provider, agente, tool, MCP, filas e sistemas downstream.

**Description**

Devem existir métricas de p50/p95/p99 de latência, taxa de erro por categoria, saturação de workers/filas/conexões e disponibilidade por camada. Métrica agregada ponta a ponta não substitui a medição de componentes. Timeouts e throttling devem ser contabilizados separadamente.

**Rationale**

Sem decomposição por camada, degradação pode ser atribuída ao componente errado e permanecer sem contenção.

**Impact**

A granularidade aumenta cardinalidade de métricas e custo de observabilidade.

**Audit**

1. Executar carga e induzir lentidão em uma camada específica.
2. Confirmar alteração nas métricas da camada afetada e no resultado ponta a ponta.
3. Verificar p95/p99, erros, timeout, throttling e saturação separados.
4. Reprovar se somente média global ou disponibilidade binária forem coletadas.

**Remediation**

Instrumentar métricas por componente e rota, controlar cardinalidade e criar alertas baseados em percentis e saturação.

**Evidence**

Dashboards por camada, métricas do teste de degradação e configuração de alertas.

**Mappings**

CIS Controls v8 13; NIST SP 800-53 SI-4, CP-2; SRE principles

---

### 6.6 Certifique-se de que drift de entrada, saída e desempenho do modelo seja detectado

**Control ID:** BAS-006.6.6
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Modelos e aplicações cujo comportamento dependa de distribuição de dados, qualidade ou métricas de segurança.

**Description**

Devem ser monitoradas distribuições de features ou embeddings de entrada, categorias e características de output e métricas de desempenho relevantes. Limites devem ser definidos por release e segmento. Drift deve ser distinguido de mudança intencional de versão e avaliado com dados minimizados.

**Rationale**

Mudanças de população ou comportamento podem degradar segurança, qualidade e eficácia sem erro técnico visível.

**Impact**

A detecção requer dados de referência, métricas adequadas e revisão de falsos positivos sazonais.

**Audit**

1. Obter baseline do release e métricas atuais por segmento.
2. Aplicar conjunto de teste com distribuição alterada e confirmar detecção do drift definido.
3. Confirmar que mudança de versão inicia novo baseline sem apagar histórico.
4. Reprovar se houver apenas métrica global sem segmentação ou se o drift não possuir limiar objetivo.

**Remediation**

Definir métricas e limites por release/segmento, armazenar baseline imutável e alertar desvios persistentes ou críticos.

**Evidence**

Baselines, métricas de drift, conjunto de teste alterado e alerta correspondente.

**Mappings**

CIS Controls v8 13 e 16; NIST AI RMF MEASURE/MANAGE; NIST SP 800-53 SI-4

---

## 7. Contenção técnica e comportamento seguro

Define mecanismos técnicos para interrupção, isolamento, rollback, circuit breaking, retries seguros e fallback controlado.

### 7.1 Certifique-se de que exista kill switch técnico para agentes e serviços de IA de alto impacto

**Control ID:** BAS-006.7.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Agentes com ação, canais externos críticos, decisões sensíveis e serviços com potencial de impacto material.

**Description**

Deve existir mecanismo técnico autenticado que interrompa novas execuções em até 60 segundos, sem depender de alteração de código ou acesso ao provider. O kill switch deve poder ser acionado por componente ou rota e preservar eventos já gerados. Sessões em andamento devem ser canceladas ou impedidas de executar novas ações.

**Rationale**

Sem interrupção rápida, comportamento incorreto ou comprometido pode continuar em escala durante investigação.

**Impact**

O acionamento poderá causar indisponibilidade e exigir fallback operacional.

**Audit**

1. Acionar o kill switch durante execução controlada.
2. Medir o tempo até bloqueio de novas requisições e confirmar valor igual ou inferior a 60 segundos.
3. Confirmar que sessões ativas não executam novas ações e que o evento de acionamento é registrado.
4. Reprovar se o mecanismo exigir deploy, alteração manual em múltiplos componentes ou acesso exclusivo do fornecedor.

**Remediation**

Implementar flag ou policy de bloqueio centralizada, autenticada e distribuída, com cancelamento de ações pendentes e logging independente.

**Evidence**

Configuração do kill switch, teste cronometrado e eventos de acionamento e bloqueio.

**Mappings**

CIS Controls v8 4 e 13; NIST SP 800-53 IR-4, SI-4; NIST AI RMF MANAGE

---

### 7.2 Certifique-se de que modelo, provider, tool, MCP server ou fonte RAG possam ser bloqueados individualmente

**Control ID:** BAS-006.7.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Plataformas com múltiplos componentes, rotas, tools, providers ou fontes de conhecimento.

**Description**

A camada de enforcement deve permitir deny por identificador e versão para model, provider, deployment, tool, capability, MCP server, RAG source e route sem necessidade de desligar toda a plataforma. A negação deve prevalecer sobre caches e configurações locais em até 5 minutos.

**Rationale**

Contenção granular reduz impacto e impede continuidade de uso de componente comprometido enquanto preserva serviços não afetados.

**Impact**

Exige identificadores consistentes e distribuição rápida de policies.

**Audit**

1. Bloquear um item de cada tipo disponível e manter outros itens ativos.
2. Tentar utilizar o item bloqueado por rota normal, cache e chamada direta; todas devem ser negadas.
3. Medir propagação e confirmar bloqueio em até 5 minutos.
4. Reprovar se o bloqueio depender de remoção manual em cada aplicação ou permitir uso por alias alternativo.

**Remediation**

Implementar denylist central com resolução de aliases, invalidação de cache e enforcement em gateway/orquestrador.

**Evidence**

Policies de bloqueio, resultados de testes por tipo e medição do tempo de propagação.

**Mappings**

CIS Controls v8 4, 13 e 15; NIST SP 800-53 CM-7, IR-4, SC-7

---

### 7.3 Certifique-se de que rollback para configuração conhecida e íntegra possa ser executado sem reconstrução manual

**Control ID:** BAS-006.7.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Deployments, modelos, prompts, policies, gateways, RAG indexes e agentes versionados.

**Description**

Deve existir mecanismo para restaurar versão anterior identificada de modelo, código, prompt, policy e configuração por comando ou pipeline repetível. O rollback deve verificar assinatura/hash, não reutilizar estado mutável comprometido e registrar a versão anterior e a restaurada.

**Rationale**

Rollback manual e incompleto prolonga exposição e pode restaurar artefato diferente do que foi testado.

**Impact**

Manter versões e índices anteriores consome armazenamento e exige compatibilidade de dados.

**Audit**

1. Implantar alteração de teste e acionar rollback para a última versão conhecida.
2. Confirmar restauração dos artefatos e configurações vinculados, não apenas do modelo.
3. Validar hashes/versões após a restauração e executar smoke test técnico.
4. Reprovar se o rollback exigir reconstruir artefatos, editar console ou depender de referência mutável.

**Remediation**

Manter releases imutáveis e mecanismo automatizado de rollback que restaure conjunto completo e valide integridade.

**Evidence**

Manifestos das versões, logs do rollback, hashes restaurados e resultado do smoke test.

**Mappings**

CIS Controls v8 4, 11 e 16; NIST SP 800-53 CM-3, CP-10, SI-7

---

### 7.4 Certifique-se de que circuit breakers interrompam chamadas quando falhas ultrapassarem limites

**Control ID:** BAS-006.7.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Chamadas a providers, modelos, retrievers, tools, MCP servers e sistemas downstream.

**Description**

Cada dependência externa ou de alto impacto deve possuir circuit breaker com limiar de erro/timeout, janela, período aberto e teste controlado de recuperação. Enquanto aberto, novas chamadas devem falhar rapidamente ou utilizar fallback definido, sem continuar consumindo a dependência degradada.

**Rationale**

Falhas em cascata ampliam indisponibilidade, custo e repetição de ações.

**Impact**

Configuração inadequada pode abrir o circuito durante picos legítimos ou retardar recuperação.

**Audit**

1. Induzir taxa de falha acima do limiar e confirmar abertura do circuito.
2. Verificar que novas chamadas não atingem a dependência durante o período aberto.
3. Restabelecer a dependência e confirmar half-open controlado antes do fechamento.
4. Reprovar se o sistema continuar enviando chamadas completas enquanto a dependência falha.

**Remediation**

Configurar circuit breaker por dependência, limites explícitos e fallback/fail-fast; monitorar mudanças de estado.

**Evidence**

Configuração, eventos de abertura/half-open/fechamento e captura de tráfego durante o teste.

**Mappings**

CIS Controls v8 13; NIST SP 800-53 CP-10, SC-5; SRE resilience patterns

---

### 7.5 Certifique-se de que retries sejam limitados, espaçados e idempotentes

**Control ID:** BAS-006.7.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Aplicações, agentes, filas e integrações que repetem inferências ou ações após falha.

**Description**

Retries devem possuir quantidade máxima, backoff exponencial com jitter e lista explícita de erros elegíveis. Ações com efeito devem utilizar idempotency_key reconhecida pelo sistema-alvo. Timeout ou resposta ambígua não pode provocar repetição irrestrita de transação.

**Rationale**

Retries incorretos causam tempestades, custos e ações duplicadas, inclusive transferências ou alterações repetidas.

**Impact**

Idempotência pode exigir alteração nos sistemas downstream.

**Audit**

1. Induzir erros elegíveis e não elegíveis e observar número e intervalo das tentativas.
2. Confirmar que o limite nunca é ultrapassado e erros não elegíveis não são repetidos.
3. Simular timeout após execução de ação e confirmar que a idempotency_key impede duplicação.
4. Reprovar se houver retry infinito, intervalo fixo sem jitter ou ação repetida com efeito duplicado.

**Remediation**

Definir políticas de retry por operação, implementar backoff/jitter e exigir idempotency_key para ações com efeito.

**Evidence**

Configuração de retries, logs de tentativas e teste de ação sem duplicidade após timeout.

**Mappings**

CIS Controls v8 13; NIST SP 800-53 SC-5, CP-10; OWASP API Security

---

### 7.6 Certifique-se de que fallback preserve restrições de segurança e não amplie privilégios

**Control ID:** BAS-006.7.6
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Rotas com fallback para outro modelo/provider, resposta estática, modo degradado, operador humano ou serviço alternativo.

**Description**

O fallback deve aplicar classificação de dados, autenticação, autorização, DLP, filtros, logging e limites equivalentes ou mais restritivos que a rota principal. Dados não podem ser enviados a provider, região ou modelo não autorizado apenas porque a rota principal falhou.

**Rationale**

Fallback inseguro transforma indisponibilidade em bypass de controles e pode expor dados a componente inadequado.

**Impact**

Algumas funcionalidades poderão permanecer indisponíveis se não houver alternativa com controles equivalentes.

**Audit**

1. Forçar ativação de cada fallback configurado.
2. Comparar policies, destino, região, modelo, logging e autorização com a rota principal.
3. Enviar dado classificado que não é permitido no destino alternativo e confirmar bloqueio.
4. Reprovar se o fallback omitir qualquer controle crítico ou selecionar destino não permitido.

**Remediation**

Configurar fallback como rota governada com policy própria, allowlists equivalentes e testes de segurança; remover alternativas não conformes.

**Evidence**

Configuração das rotas, matriz de controles e resultados de testes com falha da rota principal.

**Mappings**

CIS Controls v8 4 e 13; NIST SP 800-53 CP-2, CP-10, AC-4; NIST AI RMF MANAGE

---

## 8. Recuperação, continuidade e desativação técnica

Estabelece controles de backup, restauração, redundância, revogação e remoção segura de componentes.

### 8.1 Certifique-se de que configurações, policies, schemas e dashboards críticos possuam backup versionado

**Control ID:** BAS-006.8.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Gateways, SIEM, collectors, alertas, dashboards, registries, policies, schemas e mecanismos de contenção.

**Description**

Configurações críticas devem ser exportadas automaticamente para storage versionado e criptografado ao menos diariamente e após cada mudança. O backup deve incluir dependências necessárias para reconstrução e não pode conter segredos em texto claro.

**Rationale**

Perda ou corrupção de configuração pode eliminar visibilidade, detecções e capacidade de contenção.

**Impact**

Backups aumentam armazenamento e exigem proteção de credenciais e artefatos exportados.

**Audit**

1. Enumerar componentes críticos e localizar o backup mais recente de cada um.
2. Confirmar periodicidade diária e criação após mudança recente.
3. Inspecionar amostra e verificar versionamento, criptografia e ausência de segredo em texto claro.
4. Reprovar se dashboard, regra, parser ou policy existir apenas dentro da ferramenta sem exportação recuperável.

**Remediation**

Automatizar exportação para repositório versionado, criptografar backups e remover segredos substituindo-os por referências.

**Evidence**

Inventário de backups, histórico de versões, configuração de criptografia e varredura de segredos.

**Mappings**

CIS Controls v8 11; NIST SP 800-53 CP-9, CM-2

---

### 8.2 Certifique-se de que restauração de configurações e telemetria seja testada em ambiente isolado

**Control ID:** BAS-006.8.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Backups de configurações, policies, schemas, dashboards, índices, eventos e componentes de observabilidade.

**Description**

Deve ser possível restaurar amostra representativa em ambiente isolado e validar integridade, compatibilidade e funcionalidade. O teste deve confirmar que regras, parsers, dashboards, retenção e controles de acesso retornam ao estado esperado sem afetar produção.

**Rationale**

Backup não testado pode estar incompleto, corrompido ou incompatível com a versão atual.

**Impact**

Testes consomem infraestrutura temporária e tempo de engenharia.

**Audit**

1. Selecionar backup recente de cada categoria crítica.
2. Restaurar em ambiente isolado usando procedimento técnico reproduzível.
3. Executar eventos sintéticos e confirmar parsing, alertas, dashboards e acesso.
4. Reprovar se a restauração exigir arquivos não incluídos, falhar em integridade ou não reproduzir o comportamento esperado.

**Remediation**

Completar conteúdo do backup, automatizar restauração e manter ambiente ou pipeline de teste isolado.

**Evidence**

Logs de restauração, hashes, screenshots/consultas de validação e resultado de eventos sintéticos.

**Mappings**

CIS Controls v8 11; NIST SP 800-53 CP-4, CP-9, CP-10

---

### 8.3 Certifique-se de que componentes críticos de enforcement e observabilidade não possuam ponto único de falha

**Control ID:** BAS-006.8.3
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Gateways, policy engines, collectors, brokers, registries e mecanismos de kill switch para serviços críticos.

**Description**

Componentes devem utilizar múltiplas instâncias em domínios de falha distintos, balanceamento e estado replicado quando necessário. Falha de uma instância, zona ou nó não pode remover enforcement nem interromper toda a coleta. Modo de bypass automático não é permitido.

**Rationale**

Ponto único de falha pode causar indisponibilidade ou, pior, continuidade sem controles de segurança.

**Impact**

Redundância eleva custo e complexidade de consistência e operação.

**Audit**

1. Mapear dependências e domínios de falha de cada componente crítico.
2. Desativar uma instância e, quando aplicável, um domínio de falha completo.
3. Confirmar continuidade do enforcement e da coleta sem bypass e sem perda acima do limite definido.
4. Reprovar se uma única falha desativar controles ou exigir rota direta ao provider.

**Remediation**

Implantar redundância multi-instância e multi-zona, replicar estado necessário e remover qualquer bypass automático em falha.

**Evidence**

Diagrama de redundância, configuração de balanceamento/replicação e resultado do teste de falha.

**Mappings**

CIS Controls v8 11 e 13; NIST SP 800-53 CP-2, CP-6, SC-6

---

### 8.4 Certifique-se de que objetivos técnicos de recuperação sejam medidos por testes de falha

**Control ID:** BAS-006.8.4
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Serviços de IA e componentes de enforcement/observabilidade classificados como críticos.

**Description**

Devem existir valores técnicos configurados de RTO e RPO para serviço, configuração e telemetria. Testes de falha devem medir tempo real até restauração e quantidade máxima de dados/eventos perdidos. Os resultados devem ser comparados objetivamente aos valores definidos.

**Rationale**

Objetivos não medidos podem ser incompatíveis com a arquitetura e produzir interrupção ou perda de evidência maior que a prevista.

**Impact**

Testes podem causar indisponibilidade controlada e demandar ambiente representativo.

**Audit**

1. Obter RTO e RPO técnicos configurados para os componentes críticos.
2. Executar falha controlada e medir do início até serviço e telemetria íntegros.
3. Calcular perda de dados/eventos e comparar com RPO.
4. Reprovar se não houver medição objetiva ou se os valores excederem os limites configurados.

**Remediation**

Ajustar redundância, backups, automação e capacidade até que testes atendam aos objetivos técnicos definidos.

**Evidence**

Resultados cronometrados de testes, cálculo de perda e comparação com RTO/RPO.

**Mappings**

CIS Controls v8 11; NIST SP 800-53 CP-2, CP-4, CP-10

---

### 8.5 Certifique-se de que credenciais, tokens e sessões possam ser revogados centralmente

**Control ID:** BAS-006.8.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Usuários, aplicações, agentes, gateways, providers, tools, MCP servers e integrações de observabilidade.

**Description**

Deve existir mecanismo central para revogar token, chave, certificado, sessão e identidade técnica comprometida. A revogação deve impedir novas autenticações em até 5 minutos e invalidar sessões longas ou exigir revalidação. Dependências em credenciais estáticas locais não atendem ao controle.

**Rationale**

Sem revogação rápida, identidade comprometida continua acessando modelos, dados e tools mesmo após detecção.

**Impact**

Revogação pode interromper múltiplos componentes se credenciais forem compartilhadas, expondo dívida técnica existente.

**Audit**

1. Emitir credencial e sessão de teste para usuário, aplicação e agente.
2. Revogar cada uma centralmente e tentar novo uso e reutilização da sessão.
3. Confirmar negação em até 5 minutos e geração de eventos de revogação e tentativa posterior.
4. Reprovar se for necessário editar manualmente cada host ou aguardar expiração longa.

**Remediation**

Migrar para identidades centralizadas e tokens curtos, habilitar revogação/introspection e eliminar credenciais compartilhadas ou locais.

**Evidence**

Configuração de IAM, eventos de revogação e resultados de tentativas após revogação.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-2, IA-5, IR-4

---

### 8.6 Certifique-se de que a desativação técnica remova rotas, credenciais, dados operacionais e mecanismos de execução

**Control ID:** BAS-006.8.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Modelos, deployments, agentes, tools, MCP servers, índices RAG, endpoints e serviços descontinuados.

**Description**

A desativação deve bloquear novas chamadas, remover DNS/rotas/endpoints, revogar identidades e credenciais, desabilitar schedules e filas, invalidar caches, remover dados temporários conforme retenção e manter somente logs exigidos em storage protegido. Alias não pode continuar resolvendo para o componente desativado.

**Rationale**

Componentes órfãos continuam acessíveis, acumulam vulnerabilidades e podem ser reativados ou usados sem monitoramento.

**Impact**

A remoção pode impedir rollback tardio se não houver artefato arquivado corretamente.

**Audit**

1. Selecionar componente desativado e enumerar rotas, identidades, secrets, jobs, filas, caches e storages associados.
2. Tentar acesso por endpoint direto, alias, schedule e credencial antiga; todas as tentativas devem falhar.
3. Confirmar remoção de dados temporários e preservação somente dos logs sujeitos à retenção.
4. Reprovar se qualquer mecanismo de execução permanecer ativo ou se a credencial continuar válida.

**Remediation**

Executar desmontagem técnica completa, revogar credenciais, remover rotas e jobs, expurgar dados temporários e arquivar artefatos necessários de forma inerte.

**Evidence**

Inventário antes/depois, resultados de testes negativos e evidência de revogação e expurgo.

**Mappings**

CIS Controls v8 1, 2, 3, 5 e 6; NIST SP 800-53 CM-8, MP-6, AC-2

---
