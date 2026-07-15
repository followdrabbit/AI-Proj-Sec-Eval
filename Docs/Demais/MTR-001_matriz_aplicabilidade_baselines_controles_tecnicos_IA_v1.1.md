---
title: "MTR-001 — Matriz de Aplicabilidade de Baselines e Controles Técnicos de Inteligência Artificial"
subtitle: "Uso Interno | Versão 1.1 | Minuta para revisão"
---

| Campo | Valor |
|---|---|
| **Código** | MTR-001 |
| **Nome** | Matriz de Aplicabilidade de Baselines e Controles Técnicos de Inteligência Artificial |
| **Tipo documental** | Matriz de aplicabilidade |
| **Domínio sugerido** | Segurança de IA > Matrizes |
| **Classificação da informação** | Uso Interno |
| **Prioridade** | P0 |
| **Status** | Minuta para revisão |
| **Versão** | 1.1 |
| **Data** | 15/07/2026 |
| **Vigência** | Após aprovação formal |
| **Periodicidade mínima de revisão** | Semestral, ou extraordinária em caso de alteração do MET-001, FRM-001, BAS-001 a BAS-006, processo de homologação, arquitetura de referência, apetite de risco ou lógica do MVP. |
| **Owner institucional** | Segurança da Informação / Segurança de IA / GRC |
| **Custodiante técnico** | Arquitetura de Segurança da Informação / Segurança de IA |
| **Corresponsáveis** | Arquitetura Corporativa; AppSec; Cloud Security; IAM/PAM; Dados; MLOps/LLMOps; SOC/Blue Team; Red Team; Continuidade; Gestão de Terceiros; Compras; Jurídico; Privacidade; Owners de Plataforma e de Negócio |
| **Público-alvo** | Analistas de Segurança de IA, arquitetos, GRC, squads, owners, fornecedores, auditoria e equipes responsáveis por avaliar, implementar ou evidenciar controles de IA |
| **Documento superior relacionado** | MET-001 v1.2 — Metodologia de Avaliação e Cálculo de Riscos de Soluções de Inteligência Artificial |
| **Documentos correlatos** | FRM-001; MET-001; PRC-001; PRC-003; PRC-004; PRC-007; PRC-008; BAS-001; BAS-002; BAS-003; BAS-004; BAS-005; BAS-006 |
| **Fonte primária para** | Conversão das respostas do FRM-001 em baselines, perfis, controles técnicos aplicáveis, responsabilidades e insumos para o Parecer de Segurança. |

**Sumário**

[[TOC]]

# 1. Finalidade

Estabelecer regras determinísticas e auditáveis para converter as respostas do **FRM-001 — Formulário de Avaliação de Risco e Aplicabilidade de Controles de Inteligência Artificial** em baselines, perfis e controles técnicos aplicáveis ao cenário avaliado.

A MTR-001 complementa a **MET-001 — Metodologia de Avaliação e Cálculo de Riscos de Soluções de Inteligência Artificial**. A metodologia calcula a classificação e os riscos; a matriz seleciona cumulativamente os controles técnicos, atribui responsabilidades e fornece a base do anexo técnico do Parecer de Segurança.

O FRM-001 é autossuficiente e constitui a única fonte de perguntas da avaliação. Nenhum outro formulário é pré-requisito para executar esta matriz.

# 2. Escopo

Aplica-se a projetos internos, soluções existentes, SaaS, COTS, IA embarcada, providers, modelos locais, ferramentas de produtividade, RAG, agentes, MCP, MLOps, serviços gerenciados e serviços prestados por terceiros que utilizem IA.

A matriz possui duas representações complementares:

1. este documento, que define regras, precedências e exemplos;
2. a planilha operacional, que contém uma linha para cada controle dos BAS-001 a BAS-006.

# 3. Entradas e saídas

| Elemento | Uso |
|---|---|
| **FRM-001** | Fonte autossuficiente das respostas sobre cenário, arquitetura, dados, terceiros, capacidades e responsabilidades. |
| **MET-001 v1.2** | Fonte da classe H1–H4, impacto, probabilidade, pisos, risco inerente e risco residual projetado. |
| **BAS-001 a BAS-006** | Catálogo oficial de controles, perfil, criticidade, aplicabilidade, audit, remediação e evidência esperada. |
| **MTR-001** | Resultado de aplicabilidade, perfil, responsabilidade, critério de atribuição e justificativa de seleção de cada controle. |
| **Parecer de Segurança** | Saída consolidada com respostas, cálculos, baselines e anexo técnico dos controles selecionados. |

A matriz não declara conformidade nem comprova implementação. Para a projeção do risco residual, o motor considera que todos os controles selecionados serão aplicados integralmente. A impossibilidade de implementar um controle exige exceção formal e recálculo; a discordância sobre aplicabilidade exige revisão manual.

# 4. Princípios de aplicação

1. **Aplicação cumulativa:** BAS-001 e todos os baselines especializados compatíveis devem ser combinados.
2. **Seleção por capacidade:** o modelo de contratação não elimina controles tecnicamente aplicáveis.
3. **Duas etapas:** primeiro é selecionado o baseline; depois cada controle é avaliado segundo sua condição de aplicabilidade.
4. **Level 1:** controle obrigatório quando sua condição técnica existir.
5. **Level 2:** obrigatório quando o perfil de defesa em profundidade for acionado; caso contrário pode permanecer recomendado.
6. **Terceiros:** o controle permanece aplicável quando estiver sob domínio do fornecedor e deve receber responsabilidade correspondente.
7. **Incerteza não reduz escopo:** “Não sei”, “Não determinado” ou ausência de informação geram revisão técnica, não exclusão automática.
8. **Não aplicável exige justificativa:** a condição técnica inexistente deve ser registrada de forma específica.
9. **Condição bloqueante prevalece:** a ausência de controle indispensável não pode ser compensada por controles de outra natureza.
10. **Projeção condicionada:** a seleção de um controle não declara que ele já está implementado; o risco residual projetado pressupõe aplicação integral futura.
11. **Exceção e revisão:** controle não implementável exige exceção; controle questionado exige revisão manual antes de ser removido.
12. **Versionamento:** o resultado deve registrar as versões do FRM-001, MET-001, MTR-001 e baselines utilizados.

# 5. Resultados de aplicabilidade

| Resultado | Critério |
|---|---|
| Aplicável — Obrigatório | Controle Level 1 aplicável ou Level 2 com perfil acionado. |
| Aplicável — Recomendado | Controle Level 2 tecnicamente útil, mas sem gatilho obrigatório de defesa em profundidade. |
| Revisão técnica obrigatória | Informação insuficiente, resposta contraditória, texto livre relevante ou condição não decidível automaticamente. |
| Não aplicável | A capacidade, componente, fluxo ou condição descrita no campo Applicability do controle não existe. |

# 6. Fluxo de decisão

```text
FRM-001 → Regra do baseline → Regra da seção → Applicability do controle
        → Perfil Level 1/Level 2 → Resultado de aplicabilidade
        → Responsabilidade e critério de atribuição
        → Evidência esperada como orientação → Parecer de Segurança
```

A expressão conceitual é:

```text
Controle selecionado = baseline ativo
                    AND seção ativa
                    AND condição técnica do controle presente
```

Respostas desconhecidas relacionadas à condição devem produzir **Revisão técnica obrigatória**. A seleção não representa comprovação de implementação ou conformidade.

# 7. Regras de seleção dos baselines

| Regra | Baseline | Perguntas | Gatilho de seleção | Gatilho Level 2 |
|---|---|---|---|---|
| MTR1-B001 | BAS-001 | B01; B02 | Qualquer uso corporativo, projeto, produto, sistema, serviço ou funcionalidade que utilize IA. | H3 ou H4; risco Alto ou Crítico; dados sensíveis; exposição externa; multi-tenancy; privilégio; autonomia ou impacto material. |
| MTR1-B002 | BAS-002 | B01; E02; F01; F02 | Aplicação, API, gateway, proxy, broker, roteamento, integração com provider ou exposição de capacidade de IA. | Serviço externo, multi-tenant, crítico, com dados sensíveis, alta disponibilidade ou impacto material. |
| MTR1-B003 | BAS-003 | B01; G01; G02; G03 | RAG, embeddings, vector store, memória, cache semântico, base de conhecimento, ingestão ou recuperação de contexto. | Dados sensíveis; conteúdo externo; multi-tenancy; agentes; decisão ou operação de impacto material. |
| MTR1-B004 | BAS-004 | B01; H01; H02; H03 | Agente, planner, executor, tool/function calling, plugin, action, skill, MCP, computer use ou automação acionada por IA. | Agente autônomo; ação material; computer use; acesso privilegiado; ambiente crítico; múltiplos tenants ou operação irreversível. |
| MTR1-B005 | BAS-005 | B01; B09; B10; I01 | Desenvolvimento, treinamento, adaptação, empacotamento, registro, avaliação, implantação ou gestão de modelo e artefatos de IA. | Modelo crítico; dados sensíveis; componente externo; serviço exposto; pipeline de alto impacto; artefato executável ou supply chain relevante. |
| MTR1-B006 | BAS-006 | A08; A09; J01; J06; J07; J09; J10 | Solução em homologação material, produção, operação existente ou que exija telemetria, detecção, contenção, continuidade ou recuperação. | Solução crítica, sensível, externa, regulada, de alto impacto ou cuja falha possa produzir ação sem trilha ou indisponibilidade material. |

# 8. Regras de perfil Level 2

O perfil Level 2 deve ser acionado por baseline quando existir qualquer uma das condições específicas registradas na tabela anterior ou quando:

- a classe de homologação for H3 ou H4;
- o risco inerente for Alto ou Crítico;
- houver dado sensível, cliente, exposição externa, multi-tenancy, privilégio, autonomia ou processo crítico;
- a ausência do controle puder impedir contenção, segregação, detecção ou recuperação adequada.

O acionamento do Level 2 não elimina os controles Level 1. Os perfis são cumulativos.

# 9. Regras de aplicabilidade por seção

As regras abaixo ativam a revisão dos controles de cada seção. A aplicabilidade final continua condicionada ao campo **Applicability** de cada controle.

## 9.1 BAS-001 — Controles Técnicos Transversais para Soluções de IA

| Regra | Seção | Perguntas do FRM-001 | Condição de revisão |
|---|---|---|---|
| MTR1-B001-S01 | 1. Arquitetura e configuração segura | A09; B05; F01; F02; F07; F10 | Sempre que houver componente, deployment, endpoint, runtime, gateway ou ambiente de IA. |
| MTR1-B001-S02 | 2. Identidade, acesso e segredos | C05; F03; F04; F05; F06; F12; J12 | Quando houver usuário, workload, conta administrativa, credencial, segredo ou acesso a recurso de IA. |
| MTR1-B001-S03 | 3. Proteção de dados, prompts e outputs | D01–D12; E03; F08; F09; J04; J05 | Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs. |
| MTR1-B001-S04 | 4. Modelos, runtime e cadeia de fornecimento | B05; B07; B09; B10; I01–I07; I12 | Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica. |
| MTR1-B001-S05 | 5. Segurança de aplicação e integrações | E02; F01–F13; H01; G01 | Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente. |
| MTR1-B001-S06 | 6. Logging, auditoria e monitoramento | C06; J01–J08 | Quando a solução estiver em teste material, homologação, produção ou processar dados relevantes. |
| MTR1-B001-S07 | 7. Resiliência e recuperação | C10; C11; E10; E11; I11; J09–J13 | Quando houver dependência operacional, serviço produtivo, ação material ou necessidade de recuperação e desativação. |

## 9.2 BAS-002 — Integração e Exposição de Serviços de IA

| Regra | Seção | Perguntas do FRM-001 | Condição de revisão |
|---|---|---|---|
| MTR1-B002-S01 | 1. Arquitetura de integração e fronteiras | E02; F01; F02; F07; F10 | Quando houver consumo, intermediação, roteamento ou exposição de serviço de IA. |
| MTR1-B002-S02 | 2. Autenticação e identidade | C05; F03; F04; F05 | Quando usuários, workloads ou clientes acessarem aplicação, API, gateway ou provider. |
| MTR1-B002-S03 | 3. Autorização e segregação | C04; F11; F12; F13 | Quando houver múltiplos usuários, tenants, ambientes, privilégios, recursos ou políticas de autorização. |
| MTR1-B002-S04 | 4. Roteamento, modelos e policies | B05; B07; F01; F02; I12 | Quando houver escolha de provider/modelo, aliases, rotas, fallback ou policies de gateway. |
| MTR1-B002-S05 | 5. Entrada, prompt e payload | D12; E02; F08; G03; H07 | Quando entradas, prompts, anexos, parâmetros ou conteúdo não confiável forem aceitos. |
| MTR1-B002-S06 | 6. Saída e uso downstream | E03; E04; E05; F09; H05 | Quando outputs forem exibidos, persistidos, usados em decisões ou encaminhados a sistemas downstream. |
| MTR1-B002-S07 | 7. Exposição, sessão e abuso | E01–E07; F11; J08 | Quando houver Internet, clientes, público, muitos usuários, sessão, streaming, custo ou risco de abuso. |
| MTR1-B002-S08 | 8. Resiliência e comportamento de falha | C10; E10; E11; F13; J09 | Quando a integração exigir timeout, retry, fallback, circuit breaker, fail-closed ou continuidade. |

## 9.3 BAS-003 — Dados, Contexto e Conhecimento em IA

| Regra | Seção | Perguntas do FRM-001 | Condição de revisão |
|---|---|---|---|
| MTR1-B003-S01 | 1. Fontes, ingestão e elegibilidade | D01–D08; G02–G05 | Quando fontes, uploads, conectores, APIs, Internet ou terceiros alimentarem contexto ou conhecimento. |
| MTR1-B003-S02 | 2. Transformação, parsing e metadados | G04; G05; G10; I02 | Quando houver parsing, chunking, normalização, enriquecimento, OCR ou geração de derivados. |
| MTR1-B003-S03 | 3. Embeddings, índices e armazenamento | G01; G07; G08; G09 | Quando houver embeddings, índices, vector stores, caches, memória ou armazenamento de derivados. |
| MTR1-B003-S04 | 4. Autorização, segregação e recuperação permitida | C04; F11; G06; G07 | Quando dados ou documentos possuírem escopo por usuário, grupo, tenant, classificação ou autorização. |
| MTR1-B003-S05 | 5. Retrieval, ranking e montagem de contexto | G06; G10; G11 | Quando o sistema recuperar, ranquear, filtrar ou montar contexto para o modelo. |
| MTR1-B003-S06 | 6. Proteção contra poisoning e conteúdo adversarial | G03; G05; G11; J07 | Quando fontes externas, uploads ou conteúdo não confiável puderem influenciar ingestão ou recuperação. |
| MTR1-B003-S07 | 7. Memória, caches e dados derivados em execução | G07; G09; H14 | Quando houver memória persistente, cache semântico, estado conversacional ou compartilhamento de contexto. |
| MTR1-B003-S08 | 8. Retenção, exclusão, sincronização e recuperação | C11; D10; D11; G08; J10 | Quando dados, índices, embeddings, memória ou derivados forem persistidos e precisarem ser excluídos ou restaurados. |

## 9.4 BAS-004 — Agentes, Ferramentas e Protocolos Agentic

| Regra | Seção | Perguntas do FRM-001 | Condição de revisão |
|---|---|---|---|
| MTR1-B004-S01 | 1. Identidades agentic e contexto de execução | F04; F05; H01; H09 | Quando existir agente, worker, executor ou ação realizada em nome de usuário ou workload. |
| MTR1-B004-S02 | 2. Registro, integridade e schemas de tools | H01; H02; H06; H07 | Quando houver tools, functions, actions, skills, plugins, capabilities, resources ou prompts MCP. |
| MTR1-B004-S03 | 3. Autorização determinística e limites de ação | H05; H08; H10; H11 | Quando o agente puder acessar recurso, tomar decisão ou produzir efeito em sistema externo. |
| MTR1-B004-S04 | 4. Segurança de clientes, servidores e registries MCP | H02; H06; H12 | Quando houver cliente, servidor, registry, discovery, resource ou prompt MCP. |
| MTR1-B004-S05 | 5. Proteção contra instruções e capabilities adversariais | G03; H01; H06; H07; J07 | Quando conteúdo não confiável puder influenciar planejamento, seleção de tool, capability ou instrução do agente. |
| MTR1-B004-S06 | 6. Sandbox, host, navegador e computer use | B09; H03; H13 | Quando houver execução de código, terminal, navegador, desktop, IDE, endpoint ou computer use. |
| MTR1-B004-S07 | 7. Memória, delegação e comunicação entre agentes | G09; H04; H14 | Quando houver memória agentic, agentes secundários, delegação, comunicação multiagente ou contexto persistente. |
| MTR1-B004-S08 | 8. Observabilidade agentic e comportamento fail-safe | H05; H11; H12; J01–J09 | Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro. |

## 9.5 BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos de Modelos de IA

| Regra | Seção | Perguntas do FRM-001 | Condição de revisão |
|---|---|---|---|
| MTR1-B005-S01 | 1. Repositórios, código e versionamento | B10; I01; I02 | Quando código, notebook, prompt, policy, manifesto ou configuração for desenvolvido ou mantido para a solução. |
| MTR1-B005-S02 | 2. Datasets, prompts e configurações de treinamento e avaliação | B10; D06; I02; I03 | Quando houver treinamento, fine-tuning, avaliação, dataset, prompt sistêmico ou configuração de geração por release. |
| MTR1-B005-S03 | 3. Modelos, artefatos e registries | B05; B09; I04; I05; I06 | Quando modelos, weights, checkpoints, adapters, tokenizers ou bundles forem registrados, carregados ou distribuídos. |
| MTR1-B005-S04 | 4. Dependências, containers e proveniência | I05; I06; I07 | Quando builds utilizarem pacotes, containers, imagens, dependências ou artefatos externos. |
| MTR1-B005-S05 | 5. Pipelines MLOps, LLMOps e ambientes de build | I01; I08; I09 | Quando houver pipeline de dados, treinamento, build, teste, promoção ou deploy. |
| MTR1-B005-S06 | 6. Testes, evals e critérios técnicos de release | C07; I10; J07 | Quando releases, modelos, prompts ou soluções forem avaliados antes da promoção ou contratação. |
| MTR1-B005-S07 | 7. Deploy, serving e mudança técnica | A09; B07; I09; I12; J08 | Quando houver deployment, endpoint, serving, atualização, reconciliação ou mudança de versão/configuração. |
| MTR1-B005-S08 | 8. Rollback, descontinuação e descarte técnico | C11; I11; J10; J13 | Quando a solução precisar retornar versão, retirar modelo, revogar acesso, eliminar caches ou impedir reativação. |

## 9.6 BAS-006 — Telemetria, Detecção e Resiliência de IA

| Regra | Seção | Perguntas do FRM-001 | Condição de revisão |
|---|---|---|---|
| MTR1-B006-S01 | 1. Geração de eventos e integridade temporal | J01; J02 | Quando execuções, decisões, erros ou bloqueios precisarem produzir eventos auditáveis. |
| MTR1-B006-S02 | 2. Correlação e contexto ponta a ponta | F05; G10; H09; J03 | Quando o fluxo atravessar aplicação, gateway, provider, RAG, agente, tool, fila ou sistema downstream. |
| MTR1-B006-S03 | 3. Proteção, minimização e integridade dos registros | C06; D01–D05; J04; J05; J06 | Quando logs, traces, prompts, outputs ou eventos contiverem informação sensível ou evidência crítica. |
| MTR1-B006-S04 | 4. Coleta, transporte e integração com SIEM | C06; J06 | Quando eventos forem enviados a collector, broker, data lake, APM, SIEM ou SOC. |
| MTR1-B006-S05 | 5. Detecções técnicas de segurança para IA | D12; G11; H12; J07 | Quando forem necessárias detecções de vazamento, prompt injection, abuso agentic, poisoning, shadow AI ou MCP desconhecido. |
| MTR1-B006-S06 | 6. Anomalias de comportamento, custo e desempenho | E07; H11; J08 | Quando volume, custo, tokens, loops, drift, falha, latência ou saturação precisarem ser monitorados. |
| MTR1-B006-S07 | 7. Contenção técnica e comportamento seguro | F13; H12; J09; J12 | Quando a solução exigir kill switch, bloqueio individual, circuit breaker, retries limitados, revogação ou fallback seguro. |
| MTR1-B006-S08 | 8. Recuperação, continuidade e desativação técnica | C10; C11; E10; I11; J10; J11; J13 | Quando houver requisito de backup, restauração, redundância, recuperação, plano de saída ou desativação segura. |

# 10. Regra individual de controle

Após a ativação da seção, cada controle deve ser decidido individualmente:

1. verificar o campo **Applicability** do baseline;
2. confirmar se o componente, capacidade ou fluxo existe;
3. aplicar o perfil Level 1 ou Level 2;
4. atribuir responsabilidade;
5. registrar o critério específico que justificou a responsabilidade;
6. associar a evidência esperada apenas como orientação para implementação e futura verificação;
7. gerar o resultado de aplicabilidade.

| Situação | Resultado |
|---|---|
| Level 1 e condição técnica presente | Aplicável — Obrigatório |
| Level 2, condição técnica presente e perfil Level 2 acionado | Aplicável — Obrigatório |
| Level 2, condição técnica presente e perfil Level 2 não acionado | Aplicável — Recomendado |
| Condição técnica comprovadamente inexistente | Não aplicável, com justificativa específica |
| Resposta desconhecida ou informação contraditória | Revisão técnica obrigatória |

O resultado **Não aplicável** não pode ser usado apenas porque a solução é de terceiro, porque a organização não tem acesso à configuração ou porque o controle ainda não foi implementado.

# 11. Responsabilidade e soluções terceiras

| Responsabilidade | Tratamento |
|---|---|
| **Organização** | A implementação e a operação dependem de componentes, configurações ou processos técnicos sob controle direto da organização. |
| **Fornecedor** | O controle permanece selecionado, mas sua implementação depende predominantemente da plataforma ou do serviço operado pelo terceiro. |
| **Compartilhada** | A eficácia depende de implementação, configuração ou integração de ambas as partes. |
| **Não determinada** | Não foi possível identificar o domínio de implementação; o controle permanece em revisão técnica. |

O critério de atribuição deve citar o requisito técnico do controle, o cenário selecionado no FRM-001 e as respostas sobre quem desenvolve/configura e quem hospeda/opera a solução.

A falta de acesso à configuração do fornecedor não torna o controle não aplicável. A evidência esperada exibida no Parecer é orientação para futura implementação, homologação ou verificação e não altera automaticamente o cálculo prospectivo.

# 12. Precedência e tratamento de conflitos

1. A condição técnica específica do controle prevalece sobre a regra genérica da seção.
2. O gatilho Level 2 prevalece sobre a classificação recomendada.
3. A criticidade Crítica não altera a aplicabilidade, mas exige tratamento prioritário quando o controle for selecionado.
4. A resposta “Não” pode indicar ausência da capacidade ou ausência do controle; o significado deve ser distinguido pelo texto da pergunta.
5. Respostas textuais podem ativar revisão manual mesmo sem resposta booleana.
6. Divergência entre arquitetura, FRM-001, contrato e fornecedor deve resultar em revisão técnica.
7. Uma exceção aprovada não transforma o controle em não aplicável; ela registra o desvio e exige recálculo do risco.
8. Um controle não pode ser removido automaticamente do Parecer somente porque a área o considera difícil, custoso ou ainda não implementado.

# 13. Estrutura da planilha operacional

| Aba | Conteúdo |
|---|---|
| **Matriz_Controles** | 282 controles dos BAS-001 a BAS-006 com regra, perfil, criticidade, aplicabilidade, responsabilidade, critério de atribuição e evidência esperada orientativa. |
| **Regras_Baselines** | Gatilhos para ativar cada baseline e seu perfil Level 2. |
| **Regras_Secoes** | Regras de revisão para cada seção dos baselines. |
| **Perguntas_FRM001** | Catálogo das 119 perguntas do FRM-001 e vínculo com as regras. |
| **Valores** | Resultados, responsabilidades, operadores e valores permitidos. |
| **Historico** | Versões, alterações, data e responsável pela matriz. |

A planilha operacional deve preservar os identificadores técnicos dos controles e regras para permitir rastreabilidade entre o FRM-001, a MTR-001, os baselines e o Parecer.

# 14. Exemplos de aplicação

## 14.1 SaaS com IA embarcada e dados confidenciais

- BAS-001: ativo por ser solução de IA.
- BAS-002: ativo por existir aplicação integrada e serviço externo.
- BAS-006: ativo por uso produtivo e necessidade de logs, detecção e continuidade.
- BAS-003, BAS-004 e BAS-005: ativados somente se houver RAG, agente/MCP ou desenvolvimento/modelo gerenciado no escopo.
- Controles do fornecedor permanecem aplicáveis e recebem responsabilidade “Fornecedor” ou “Compartilhada”.

## 14.2 Assistente RAG interno

- BAS-001, BAS-002, BAS-003 e BAS-006 ativos.
- BAS-004 é adicionado se o assistente executar tools ou ações.
- Controles de multi-tenancy somente se tornam aplicáveis quando houver compartilhamento entre usuários, grupos ou tenants.

## 14.3 Agente local com computer use

- BAS-001, BAS-004 e BAS-006 ativos.
- BAS-005 é adicionado quando modelo, artefato, container ou pipeline forem mantidos pela organização.
- Controles de sandbox, identidade, autorização, limites, kill switch e rastreabilidade tornam-se obrigatórios.

# 15. Saída mínima da avaliação

A execução da matriz deve produzir:

- baselines ativos;
- perfil aplicável por baseline;
- controles obrigatórios e recomendados;
- controles em revisão técnica;
- controles não aplicáveis e justificativas específicas;
- responsabilidade de cada controle;
- critério detalhado de atribuição da responsabilidade;
- regra e respostas que provocaram a seleção;
- requisito, descrição, audit, remediação, impacto e evidência esperada de cada controle;
- versões das regras e documentos utilizados;
- premissa de implementação integral utilizada na projeção do risco residual;
- encaminhamento para exceção ou revisão manual quando necessário.

# 16. Manutenção e versionamento

Alterações em perguntas, gatilhos, perfis, nomes de seções, controles, critérios de responsabilidade ou condições de aplicabilidade devem gerar nova versão da MTR-001.

A matriz deve ser revisada sempre que houver nova versão do FRM-001, da MET-001 ou dos BAS-001 a BAS-006. Avaliações anteriores devem manter a versão histórica utilizada e não podem ser recalculadas silenciosamente.

O MVP e as exportações do Parecer devem declarar as versões do FRM-001, MET-001, MTR-001 e baselines efetivamente incorporadas.

# 17. Histórico de versão

| Versão | Data | Descrição | Responsável |
|---|---|---|---|
| **1.1** | 15/07/2026 | Renumeração definitiva para MTR-001; alinhamento ao FRM-001 autossuficiente e à MET-001 v1.2; remoção de outros formulários; inclusão do critério detalhado de responsabilidade e da premissa prospectiva de implementação integral dos controles. | Segurança de IA / Arquitetura de Segurança / GRC |
| **1.0** | 13/07/2026 | Criação da matriz para seleção cumulativa de baselines, perfis e controles técnicos. | Segurança de IA / Arquitetura de Segurança / GRC |

