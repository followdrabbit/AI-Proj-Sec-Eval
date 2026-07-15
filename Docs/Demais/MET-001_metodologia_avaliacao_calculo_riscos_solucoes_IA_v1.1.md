---
title: "MET-001 — Metodologia de Avaliação e Cálculo de Riscos de Soluções de Inteligência Artificial"
subtitle: "Uso Interno | Versão 1.1 | Minuta para revisão"
---

| Campo | Valor |
|---|---|
| **Código** | MET-001 |
| **Nome** | Metodologia de Avaliação e Cálculo de Riscos de Soluções de Inteligência Artificial |
| **Tipo documental** | Metodologia |
| **Domínio sugerido** | Segurança de IA > Metodologias |
| **Classificação da informação** | Uso Interno |
| **Prioridade** | P0 |
| **Status** | Minuta para revisão |
| **Versão** | 1.1 |
| **Data** | 13/07/2026 |
| **Vigência** | Após aprovação formal |
| **Periodicidade mínima de revisão** | Semestral, ou extraordinária em caso de mudança regulatória, alteração do apetite de risco, incidente relevante, nova classe de ameaça, mudança material nos baselines ou alteração do método de cálculo |
| **Owner institucional** | GRC / Riscos Operacionais / Segurança da Informação |
| **Custodiante técnico** | Segurança de IA / Arquitetura de Segurança da Informação |
| **Corresponsáveis** | Arquitetura Corporativa; Jurídico Regulatório; DPO/Privacidade; IAM/PAM; Cloud Security; AppSec; Dados; SOC/Blue Team; Red Team; Continuidade; Gestão de Terceiros; Compras; Owners de Plataforma de IA; Owners de Negócio e Tecnologia |
| **Público-alvo** | Áreas demandantes, product owners, squads, arquitetos, segurança, GRC, jurídico, privacidade, dados, cloud, IAM, AppSec, SOC, compras, fornecedores, auditoria e terceiros envolvidos na avaliação de soluções de IA |
| **Documento superior relacionado** | POL-001 — Política Corporativa de Segurança para Inteligência Artificial e Tecnologias Associadas |
| **Documentos correlatos** | PRC-001; PRC-002; PRC-003; PRC-004; PRC-005; PRC-007; PRC-008; FRM-001; CHK-001; MTR-001; BAS-001 a BAS-006 |
| **Fonte primária para** | Método simplificado de classificação do rigor de homologação, cálculo do risco inerente e residual, seleção de baselines, avaliação de controles e tratamento de soluções internas ou de terceiros |

**Sumário**

[[TOC]]

# 1. Finalidade

Esta metodologia estabelece um método corporativo simples, reproduzível e auditável para avaliar riscos associados ao uso de Inteligência Artificial, independentemente de a solução ter sido desenvolvida internamente, contratada, incorporada a um produto de terceiro ou utilizada pelo fornecedor na prestação de um serviço.

A avaliação deve considerar conjuntamente:

- o cenário de uso;
- a solução tecnológica;
- o modelo de fornecimento e hospedagem;
- os dados processados;
- as capacidades habilitadas;
- as integrações e ações executáveis;
- as responsabilidades da organização e do fornecedor;
- os controles implementados e suas evidências.

A unidade de avaliação é:

```text
Cenário de uso + solução tecnológica + modelo de fornecimento + dados + capacidades
```

O mesmo produto pode receber classificações diferentes quando utilizado em contextos diferentes. Um SaaS empregado para resumir conteúdo público não deve ser avaliado da mesma forma quando processa dados bancários, apoia decisões sobre clientes ou executa ações em sistemas corporativos.

# 2. Posicionamento documental

O MET-001 define **como o risco é calculado**. Ele não substitui processos de homologação, contratação, aceite, exceção, monitoramento ou resposta a incidentes.

| Documento | Responsabilidade principal |
|---|---|
| **FRM-001** | Intake e triagem inicial da iniciativa. |
| **PRC-001** | Fluxo de homologação e decisão sobre o caso de uso. |
| **PRC-004** | Identificação, tratamento, aceite, registro e monitoramento dos riscos. |
| **PRC-008 e CHK-001** | Avaliação e contratação de soluções de terceiros com IA embarcada. |
| **BAS-001 a BAS-006** | Controles técnicos aplicáveis às características da solução. |
| **MTR-001** | Rastreabilidade entre risco, controle, documento, evidência, owner e status. |
| **MET-001** | Regras para impacto, probabilidade, risco inerente, controles e risco residual. |

A classificação **H1–H4** determina o rigor da homologação. Ela não substitui o risco inerente ou residual, expresso como **Baixo, Moderado, Alto ou Crítico**.

# 3. Escopo e cenários abrangidos

A metodologia deve ser aplicável, entre outros, aos seguintes cenários:

| Cenário | Exemplos |
|---|---|
| Consumo interno de IA corporativa | Gateway corporativo, modelos homologados e serviços gerenciados internos. |
| Aplicação integrada a provider externo | Sistema interno consumindo API ou deployment de terceiro. |
| SaaS ou COTS com IA embarcada | CRM, ERP, RH, jurídico, segurança, produtividade ou atendimento. |
| Solução desenvolvida por terceiro | Aplicação encomendada, consultoria ou fábrica de software. |
| Serviço gerenciado de IA | Terceiro que hospeda modelos, RAG, agentes ou processamento para a organização. |
| Desenvolvimento interno | Modelos próprios, treinamento, fine-tuning e pipelines MLOps/LLMOps. |
| RAG e conhecimento | Bases corporativas, embeddings, vector stores, memória e busca semântica. |
| Agentes e automações | Tools, function calling, MCP, browser agents e ações em sistemas. |
| Ferramentas de produtividade | Copilots, assistentes de código, extensões, plugins e aplicações desktop. |
| Modelos locais | Ollama, modelos open source, execução em servidor ou endpoint interno. |
| IA em dispositivos ou appliances | Câmeras, antifraude, segurança física, equipamentos e produtos conectados. |
| IA utilizada pelo fornecedor | Terceiro que usa IA internamente para executar parte do serviço contratado. |

A metodologia deve ser utilizada tanto para novos projetos quanto para soluções existentes, renovações contratuais, mudanças materiais, revalidações, incidentes, achados ou solicitações de exceção.

# 4. Princípios

1. **Avaliação por cenário:** o risco deve refletir a forma concreta como a IA será utilizada.
2. **Independência do modelo de fornecimento:** ser uma solução de terceiro não elimina a aplicabilidade de controles.
3. **Maior condição plausível:** informação desconhecida não deve ser interpretada como ausência de risco.
4. **Risco inerente antes dos controles:** o cálculo inicial representa o cenário sem considerar controles existentes.
5. **Controles somente com evidência:** controles não comprovados não reduzem o risco residual.
6. **Aplicação cumulativa:** BAS-001 e todos os baselines especializados aplicáveis devem ser combinados.
7. **Sem média entre cenários:** o risco consolidado deve preservar o maior cenário material identificado.
8. **Condições bloqueantes prevalecem:** uma pontuação não pode compensar ausência de controle indispensável.
9. **Responsabilidade compartilhada:** controles podem ser da organização, do fornecedor ou de ambos.
10. **Reprodutibilidade:** respostas, regras, versões, evidências e resultado devem permanecer auditáveis.

# 5. Fluxo simplificado de avaliação

A avaliação deve seguir seis etapas:

1. Identificar o cenário de uso e o modelo de fornecimento.
2. Classificar o rigor de homologação H1–H4.
3. Determinar o impacto.
4. Determinar a probabilidade e calcular o risco inerente.
5. Selecionar e avaliar os controles aplicáveis.
6. Calcular o risco residual e definir a decisão recomendada.

```text
Cenário → H1–H4 → Impacto → Probabilidade → Risco inerente
        → Controles aplicáveis → Efetividade → Risco residual → Decisão
```

# 6. Identificação do cenário e das responsabilidades

## 6.1 Informações mínimas

A avaliação deve registrar, no mínimo:

- finalidade e público-alvo;
- owner de negócio e owner técnico;
- tipo de solução e modelo de fornecimento;
- desenvolvedor, operador e responsável pela hospedagem;
- provider, modelo, região e deployment quando conhecidos;
- dados de entrada, saída, treinamento, memória e logs;
- integrações, APIs, RAG, agentes, tools, MCP e ações executáveis;
- exposição interna, externa, a clientes ou a parceiros;
- possibilidade de desabilitar a funcionalidade de IA;
- alterações que o fornecedor pode realizar sem ação da organização;
- responsabilidades pelos controles e evidências disponíveis.

Respostas como **“Não sei”**, **“Não informado pelo fornecedor”** ou **“Não foi possível validar”** devem permanecer explícitas e não podem ser convertidas automaticamente em resposta negativa.

## 6.2 Modelo de responsabilidade

Cada controle aplicável deve ser atribuído a uma das categorias:

| Responsabilidade | Definição |
|---|---|
| **Organização** | Implementação e operação sob controle direto da organização. |
| **Fornecedor** | Implementação e operação sob responsabilidade do terceiro. |
| **Compartilhada** | Depende de configuração ou atuação de ambas as partes. |
| **Não determinada** | Não foi possível identificar quem implementa ou opera o controle. |
| **Não aplicável** | A condição técnica que originaria o controle não existe. |

A justificativa **“não aplicável por ser solução de terceiro”** não é válida. Quando o controle pertence ao fornecedor, ele deve permanecer aplicável e ser sustentado por evidência contratual ou técnica.

# 7. Classificação do rigor de homologação H1–H4

A classificação H indica a profundidade da avaliação. O nível do cenário é o maior nível acionado por suas características.

| Classe | Critérios orientativos |
|---|---|
| **H1** | Uso interno controlado, sem dados sensíveis, sem cliente, sem exposição externa e sem ação material. |
| **H2** | Dados corporativos internos, integração limitada, recomendação ou apoio operacional sem decisão crítica. |
| **H3** | Dados pessoais, bancários ou confidenciais; RAG; fornecedor externo; IA embarcada; MCP; tool calling; agente assistido ou integração relevante. |
| **H4** | Cliente, canal digital, exposição pública, decisão sensível, ação financeira, sistema core, acesso privilegiado, agente autônomo ou obrigação regulatória material. |

```text
H do cenário = maior nível acionado pelas respostas e características
```

Quando uma informação necessária para distinguir H2, H3 ou H4 não estiver disponível, deve ser adotado o maior nível plausível até o esclarecimento.

# 8. Cálculo do impacto

O impacto deve ser avaliado em quatro dimensões. Cada dimensão recebe um nível de I1 a I4.

| Dimensão | I1 — Baixo | I2 — Moderado | I3 — Alto | I4 — Crítico |
|---|---|---|---|---|
| **Dados e privacidade** | Sem dados sensíveis. | Dados internos de baixa criticidade. | Dados pessoais, confidenciais ou restritos. | Dados bancários, pagamento, credenciais, segredos críticos ou exposição material de cliente. |
| **Cliente, financeiro e regulatório** | Sem cliente ou obrigação material. | Retrabalho ou custo limitado. | Perda relevante, impacto limitado a clientes ou possível descumprimento. | Fraude, crédito, pagamento, direito de cliente, sanção ou perda material. |
| **Operação e continuidade** | Interrupção irrelevante. | Indisponibilidade limitada e reversível. | Impacto em serviço ou processo relevante. | Canal, sistema core, processo crítico ou dependência sem alternativa viável. |
| **Segurança e autonomia** | Sem privilégio ou ação. | Acesso restrito e reversível. | Integração relevante, escrita controlada ou privilégio material. | Execução crítica, acesso privilegiado, ação irreversível ou autonomia elevada. |

A classificação oficial é o maior impacto identificado:

```text
Impacto do cenário = máximo das quatro dimensões
```

A justificativa deve registrar qual dimensão determinou o resultado.

# 9. Cálculo da probabilidade

A probabilidade inerente utiliza cinco fatores objetivos. Cada resposta **Sim** vale um ponto.

| ID | Fator |
|---|---|
| **F1** | A solução recebe conteúdo, arquivos, comandos ou dados não confiáveis? |
| **F2** | Está exposta externamente, a clientes, parceiros ou a grande quantidade de usuários? |
| **F3** | Utiliza RAG, agentes, tools, MCP, integrações dinâmicas ou modelos alteráveis? |
| **F4** | Executa ações, decisões, escrita em sistemas ou acessa dados e privilégios relevantes? |
| **F5** | Existe dependência de terceiro com transparência limitada, evidência insuficiente ou mudanças fora do controle da organização? |

| Pontos | Probabilidade |
|---:|---|
| **0** | P1 — Baixa |
| **1** | P2 — Moderada |
| **2 ou 3** | P3 — Alta |
| **4 ou 5** | P4 — Muito alta |

## 9.1 Pisos obrigatórios

A probabilidade não pode ser inferior a P3 quando existir qualquer uma das condições abaixo:

- aplicação ou API pública;
- agente com escrita, transação ou ação material;
- conteúdo da Internet alimentando RAG ou memória;
- provider, modelo, região ou capacidade não homologada;
- fornecedor sem evidências mínimas de segurança;
- IA embarcada que não possa ser desabilitada ou controlada;
- alteração automática de modelo, provider ou capacidade pelo fornecedor;
- uso de dados corporativos para treinamento pelo fornecedor sem controle formal;
- retenção, localização ou subprocessadores desconhecidos para dados relevantes;
- componente crítico sem fallback, exportação ou plano de saída.

```text
Probabilidade inerente = maior valor entre a pontuação e os pisos aplicáveis
```

# 10. Risco inerente

O risco inerente é obtido pela combinação do impacto e da probabilidade.

| Impacto \ Probabilidade | P1 Baixa | P2 Moderada | P3 Alta | P4 Muito alta |
|---|---|---|---|---|
| **I1 Baixo** | Baixo | Baixo | Moderado | Moderado |
| **I2 Moderado** | Baixo | Moderado | Alto | Alto |
| **I3 Alto** | Moderado | Alto | Alto | Crítico |
| **I4 Crítico** | Alto | Alto | Crítico | Crítico |

```text
Risco inerente = matriz(Impacto, Probabilidade inerente)
```

Quando houver vários cenários:

```text
Risco consolidado = maior risco material identificado
```

Uma média entre cenários não deve ser utilizada para reduzir ou ocultar um cenário crítico.

# 11. Seleção dos baselines e controles

A seleção deve considerar as capacidades e a arquitetura, e não apenas o tipo de contratação.

| Condição identificada | Baseline aplicável |
|---|---|
| Qualquer solução ou uso corporativo de IA | **BAS-001** |
| Aplicações, APIs, gateways, roteamento ou exposição | **BAS-002** |
| Dados, RAG, contexto, memória, índices ou conhecimento | **BAS-003** |
| Agentes, tools, function calling, MCP ou computer use | **BAS-004** |
| Desenvolvimento, treinamento, modelos, registries ou MLOps | **BAS-005** |
| Produção, telemetria, detecção, contenção, continuidade ou recuperação | **BAS-006** |

Os baselines são cumulativos. A aplicabilidade deve ser determinada também no nível de cada controle. Por exemplo, o uso de RAG torna o BAS-003 aplicável, mas controles de multi-tenancy somente se aplicam quando houver compartilhamento entre tenants ou domínios equivalentes.

Para soluções terceirizadas, os controles devem ser selecionados normalmente e sua responsabilidade atribuída ao fornecedor, à organização ou a ambos.

# 12. Avaliação dos controles

Cada controle aplicável deve receber um dos seguintes resultados:

| Resultado | Definição |
|---|---|
| **Conforme** | Implementado, operacional e sustentado por evidência válida. |
| **Parcialmente conforme** | Implementação incompleta, cobertura limitada ou evidência parcial. |
| **Não conforme** | Não implementado ou implementação incompatível com o requisito. |
| **Não comprovado** | Não foi possível obter evidência suficiente, especialmente em solução de terceiro. |
| **Não aplicável** | A condição técnica não existe, com justificativa registrada. |

A evidência pode incluir configuração, teste, log, relatório independente, certificação, contrato, declaração técnica específica, arquitetura, API, captura ou outro artefato verificável. Evidência genérica ou declaração comercial não deve sustentar conformidade de controle crítico.

## 12.1 Efetividade geral

| Efetividade | Critério |
|---|---|
| **Efetiva** | Todos os controles críticos aplicáveis estão conformes e pelo menos 80% dos controles aplicáveis estão conformes. |
| **Parcial** | Não há controle crítico não conforme, mas a cobertura conforme é inferior a 80% ou existem lacunas relevantes. |
| **Ineficaz** | Existe controle crítico não conforme ou não comprovado. |
| **Indeterminada** | As informações disponíveis não permitem concluir a avaliação. |

Controles planejados, ainda não implementados, devem constar do plano de tratamento e não podem reduzir o risco atual.

# 13. Cálculo do risco residual

O impacto permanece igual ao impacto inerente. A consequência potencial não desaparece apenas porque existem controles.

A probabilidade residual é determinada assim:

| Efetividade | Probabilidade residual |
|---|---|
| **Efetiva** | Reduz a probabilidade inerente em um nível, nunca abaixo de P1. |
| **Parcial** | Mantém a probabilidade inerente. |
| **Ineficaz** | Mantém a probabilidade inerente e pode gerar condição bloqueante. |
| **Indeterminada** | Mantém a probabilidade inerente; o resultado deve ser marcado como inconclusivo. |

```text
Impacto residual = Impacto inerente
Probabilidade residual = regra de efetividade
Risco residual = matriz(Impacto residual, Probabilidade residual)
```

Pisos obrigatórios continuam válidos no risco residual enquanto a condição que os originou não tiver sido tecnicamente eliminada ou comprovadamente controlada.

# 14. Condições bloqueantes

A avaliação não deve recomendar aprovação quando houver condição bloqueante não tratada, ainda que a matriz produza risco inferior. Exemplos:

- controle crítico aplicável não conforme ou não comprovado em cenário de alto impacto;
- uso de provider, modelo ou capacidade proibida sem exceção válida;
- tratamento de dado proibido ou uso para treinamento sem autorização e controle;
- agente executando ação material sem autorização determinística;
- exposição pública sem ponto de enforcement aprovado;
- isolamento entre tenants não comprovado para dados sensíveis;
- ausência de trilha para ação material ou decisão sensível;
- impossibilidade de desativar, conter ou interromper capacidade crítica;
- ausência de informações mínimas do fornecedor para concluir a avaliação.

A condição bloqueante deve gerar plano de tratamento, devolução, suspensão, reprovação ou processo de exceção conforme o caso.

# 15. Decisão recomendada

A metodologia deve produzir uma das seguintes recomendações:

| Decisão | Uso esperado |
|---|---|
| **Aprovado** | Risco residual compatível, controles críticos conformes e nenhuma condição bloqueante. |
| **Aprovado com condições** | Existem ações não bloqueantes, prazos e monitoramento definidos. |
| **Aprovado mediante exceção** | Controle obrigatório não atendido, com exceção válida, prazo e risco aceito na alçada competente. |
| **Devolvido para complementação** | Informações, arquitetura ou evidências insuficientes, mas obteníveis. |
| **Não aprovado** | Risco incompatível, condição proibida ou controle indispensável sem tratamento viável. |
| **Avaliação inconclusiva** | Não há informação suficiente para determinar o risco ou a efetividade. |

O resultado calculado é uma recomendação técnica e deve seguir as alçadas e processos corporativos aplicáveis.

# 16. Saídas mínimas e trilha de auditoria

A avaliação deve registrar:

- identificação do projeto, produto, serviço ou fornecedor;
- cenário ou cenários avaliados;
- modelo de fornecimento e responsabilidades;
- classe H1–H4;
- quatro dimensões de impacto e justificativas;
- cinco fatores de probabilidade e pisos aplicados;
- risco inerente;
- baselines e controles aplicáveis;
- status, responsabilidade e evidência de cada controle;
- efetividade geral;
- risco residual;
- condições bloqueantes;
- decisão recomendada;
- plano de tratamento, owner e prazo;
- versões do formulário, metodologia, regras e baselines;
- data, avaliadores e histórico de alterações.

Qualquer alteração manual de impacto, probabilidade, aplicabilidade, efetividade ou resultado deve possuir justificativa, responsável, data e aprovação conforme alçada.

# 17. Gatilhos de reavaliação

A avaliação deve ser repetida quando ocorrer:

- mudança de finalidade, público-alvo ou dados tratados;
- novo provider, modelo, região, deployment ou capacidade;
- ativação de RAG, agente, tool, MCP, memória ou autonomia;
- alteração relevante do fornecedor, contrato, subprocessador ou termo de uso;
- mudança de retenção, treinamento com dados, localização ou compartilhamento;
- exposição externa, integração com sistema crítico ou aumento de privilégio;
- incidente, quase incidente, vulnerabilidade ou falha de controle;
- exceção vencida, condicionante não cumprida ou evidência expirada;
- descontinuação de modelo, provider ou serviço;
- mudança regulatória, normativa ou no apetite de risco.

# 18. Exemplos de aplicação

## 18.1 SaaS com IA para resumir documentos públicos

- Cenário: solução de terceiro, sem dados sensíveis e sem integração com sistemas.
- Impacto: I1.
- Fatores positivos: dependência de terceiro — 1 ponto.
- Probabilidade: P2.
- Risco inerente: Baixo.
- Baselines: BAS-001 e BAS-006, conforme operação e logging.
- Controles efetivos: probabilidade reduzida para P1.
- Risco residual: Baixo.

## 18.2 SaaS com IA processando dados bancários

- Cenário: solução de terceiro, dados bancários, subprocessadores e retenção não comprovada.
- Impacto: I4.
- Fatores positivos: conteúdo relevante, terceiro, integrações — 3 pontos.
- Piso: fornecedor sem evidências mínimas e localização desconhecida — P3.
- Probabilidade: P3.
- Risco inerente: Crítico.
- Controles não comprovados: efetividade ineficaz.
- Risco residual: Crítico e avaliação não recomendada para aprovação.

## 18.3 Agente interno com ação em sistema corporativo

- Cenário: agente homologado que consulta RAG e cria registros em sistema interno.
- Impacto: I3.
- Fatores positivos: conteúdo não confiável, RAG, ação em sistema — 3 pontos.
- Piso: agente com escrita — P3.
- Probabilidade: P3.
- Risco inerente: Alto.
- Baselines: BAS-001, BAS-002, BAS-003, BAS-004 e BAS-006.
- Todos os controles críticos conformes e cobertura de 88%: efetividade efetiva.
- Probabilidade residual: P2.
- Risco residual: Alto.
- Decisão possível: aprovado com condições e monitoramento reforçado.

# 19. Resumo do algoritmo

```text
1. Identificar o cenário, o fornecedor e as responsabilidades.
2. Definir H = maior classe acionada.
3. Definir I = maior impacto entre as quatro dimensões.
4. Somar F1 a F5 e converter para P1 a P4.
5. Aplicar pisos obrigatórios de probabilidade.
6. Consultar a matriz para obter o risco inerente.
7. Selecionar cumulativamente BAS-001 a BAS-006 e os controles aplicáveis.
8. Classificar cada controle e determinar a efetividade geral.
9. Reduzir P em um nível somente quando a efetividade for Efetiva.
10. Manter I e consultar novamente a matriz para obter o risco residual.
11. Aplicar bloqueios e emitir a decisão recomendada.
```

# 20. Histórico de versão

| Versão | Data | Descrição | Responsável |
|---|---:|---|---|
| **1.1** | 13/07/2026 | Simplificação do método; redução das dimensões e fatores; inclusão explícita de SaaS, IA embarcada, soluções de terceiros, serviços gerenciados e responsabilidade compartilhada; adoção de regra simples para risco residual. | Segurança de IA / Arquitetura de Segurança / GRC |
| **1.0** | 13/07/2026 | Criação da metodologia corporativa inicial para cálculo de riscos de soluções de IA. | Segurança de IA / Arquitetura de Segurança / GRC |
