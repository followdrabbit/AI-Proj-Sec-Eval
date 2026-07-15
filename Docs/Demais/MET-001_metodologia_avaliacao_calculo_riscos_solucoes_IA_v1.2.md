---
title: "MET-001 — Metodologia de Avaliação e Cálculo de Riscos de Soluções de Inteligência Artificial"
subtitle: "Uso Interno | Versão 1.2 | Minuta para revisão"
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
| **Versão** | 1.2 |
| **Data** | 15/07/2026 |
| **Vigência** | Após aprovação formal |
| **Periodicidade mínima de revisão** | Semestral, ou extraordinária em caso de mudança regulatória, alteração do apetite de risco, incidente relevante, nova classe de ameaça, mudança material nos baselines ou alteração do método de cálculo |
| **Owner institucional** | GRC / Riscos Operacionais / Segurança da Informação |
| **Custodiante técnico** | Segurança de IA / Arquitetura de Segurança da Informação |
| **Corresponsáveis** | Arquitetura Corporativa; Jurídico Regulatório; DPO/Privacidade; IAM/PAM; Cloud Security; AppSec; Dados; SOC/Blue Team; Red Team; Continuidade; Gestão de Terceiros; Compras; Owners de Plataforma de IA; Owners de Negócio e Tecnologia |
| **Público-alvo** | Áreas demandantes, product owners, squads, arquitetos, segurança, GRC, jurídico, privacidade, dados, cloud, IAM, AppSec, SOC, compras, fornecedores, auditoria e terceiros envolvidos na avaliação de soluções de IA |
| **Documento superior relacionado** | POL-001 — Política Corporativa de Segurança para Inteligência Artificial e Tecnologias Associadas |
| **Documentos correlatos** | FRM-001; MTR-001; BAS-001 a BAS-006; PRC-001; PRC-003; PRC-004; PRC-005; PRC-008 |
| **Fonte primária para** | Classificação do rigor de homologação, cálculo do risco inerente, seleção de controles, projeção do risco residual e geração do Parecer de Segurança para soluções internas ou de terceiros |

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
- os controles técnicos selecionados para o cenário.

A unidade de avaliação é:

```text
Cenário de uso + solução tecnológica + modelo de fornecimento + dados + capacidades
```

O mesmo produto pode receber classificações diferentes quando utilizado em contextos diferentes. Um SaaS empregado para resumir conteúdo público não deve ser avaliado da mesma forma quando processa dados bancários, apoia decisões sobre clientes ou executa ações em sistemas corporativos.

O resultado desta metodologia é prospectivo: o risco residual representa a exposição esperada caso todos os controles aplicáveis selecionados sejam implementados integralmente antes da homologação ou entrada em produção.
# 2. Posicionamento documental

A Metodologia de Avaliação e Cálculo de Riscos de Soluções de Inteligência Artificial define **como a classificação e os riscos são calculados**. Ela não substitui processos corporativos de homologação, contratação, aceite, exceção, monitoramento ou resposta a incidentes.

| Documento | Responsabilidade principal |
|---|---|
| **FRM-001 — Formulário de Avaliação de Risco e Aplicabilidade de Controles de Inteligência Artificial** | Documento autossuficiente para coleta das informações, caracterização do cenário, classificação, cálculo e geração do Parecer de Segurança. |
| **MTR-001 — Matriz de Aplicabilidade de Baselines e Controles Técnicos de Inteligência Artificial** | Converte as respostas do FRM-001 em baselines, perfis e controles técnicos aplicáveis. |
| **BAS-001 a BAS-006** | Definem o conteúdo completo, a criticidade, a aplicabilidade e os critérios técnicos dos controles. |
| **MET-001** | Define H1-H4, impacto, probabilidade, pisos, risco inerente e risco residual projetado. |
| **Processo de Gestão de Exceções de Segurança de Inteligência Artificial** | Trata controles aplicáveis que não possam ser implementados. |

O FRM-001 é o único formulário necessário para a avaliação prevista nesta metodologia. Não há dependência de formulários auxiliares para intake, cálculo, seleção ou registro dos controles.

A classificação **H1-H4** determina o rigor da homologação. Ela não substitui o risco inerente ou residual, expresso como **Baixo, Moderado, Alto ou Crítico**.
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
2. **Formulário autossuficiente:** o FRM-001 concentra as informações necessárias para classificação, cálculo e seleção de controles.
3. **Independência do modelo de fornecimento:** ser uma solução de terceiro não elimina a aplicabilidade de controles.
4. **Maior condição plausível:** informação desconhecida não deve ser interpretada como ausência de risco.
5. **Risco inerente antes dos controles:** o cálculo inicial representa o cenário sem considerar a aplicação dos controles selecionados.
6. **Aplicação cumulativa:** BAS-001 e todos os baselines especializados aplicáveis devem ser combinados.
7. **Aplicação integral presumida:** o risco residual é uma projeção que considera todos os controles selecionados como integralmente implementados.
8. **Sem exigência de evidência nesta etapa:** a avaliação prospectiva não exige status, comprovação ou evidência individual dos controles.
9. **Exceção obrigatória para impossibilidade:** controle aplicável que não possa ser implementado deve seguir o processo formal de exceção e gerar novo cálculo.
10. **Revisão manual para divergência de aplicabilidade:** controle considerado tecnicamente não pertinente somente pode ser retirado após revisão manual e novo processamento da MTR-001.
11. **Sem média entre cenários:** o risco consolidado deve preservar o maior cenário material identificado.
12. **Responsabilidade compartilhada:** controles podem ser da organização, do fornecedor ou de ambos.
13. **Reprodutibilidade:** respostas, regras, versões, fórmulas e resultados devem permanecer auditáveis.
# 5. Fluxo simplificado de avaliação

A avaliação deve seguir seis etapas:

1. Preencher o FRM-001 e identificar o cenário de uso, o modelo de fornecimento e as responsabilidades.
2. Classificar o rigor de homologação H1-H4.
3. Determinar o impacto.
4. Determinar a probabilidade, aplicar os pisos e calcular o risco inerente.
5. Aplicar a MTR-001 para selecionar cumulativamente os baselines e controles técnicos.
6. Projetar o risco residual sob a premissa de implementação integral dos controles e emitir o Parecer de Segurança.

```text
FRM-001 → H1-H4 → Impacto → Probabilidade e pisos → Risco inerente
        → MTR-001 → Controles aplicáveis → Aplicação integral presumida
        → Risco residual projetado → Parecer de Segurança
```

A implementação real, a comprovação e o monitoramento dos controles ocorrem nos processos corporativos posteriores. Caso um controle não possa ser implementado, o resultado projetado deixa de ser válido até que a exceção seja decidida e o risco seja recalculado.
# 6. Identificação do cenário e das responsabilidades

## 6.1 Informações mínimas

O FRM-001 deve registrar, no mínimo:

- finalidade e público-alvo;
- owner de negócio e owner técnico;
- tipo de solução e modelo de fornecimento;
- desenvolvedor, configurador, operador e responsável pela hospedagem;
- provider, modelo, região e deployment quando conhecidos;
- dados de entrada, saída, treinamento, memória e logs;
- integrações, APIs, RAG, agentes, tools, MCP e ações executáveis;
- exposição interna, externa, a clientes ou a parceiros;
- possibilidade de desabilitar a funcionalidade de IA;
- alterações que o fornecedor pode realizar sem ação da organização;
- condições de continuidade, fallback e plano de saída;
- informações necessárias para atribuir responsabilidade aos controles.

Respostas como **“Não sei”**, **“Não informado pelo fornecedor”** ou **“Não foi possível validar”** devem permanecer explícitas e não podem ser convertidas automaticamente em resposta negativa.

## 6.2 Modelo de responsabilidade

Cada controle aplicável deve ser atribuído a uma das categorias:

| Responsabilidade | Definição |
|---|---|
| **Organização** | Implementação e operação sob controle direto da organização. |
| **Fornecedor** | Implementação e operação sob responsabilidade do terceiro. |
| **Compartilhada** | Depende de configuração, integração, operação ou monitoramento de ambas as partes. |
| **Não determinada** | As respostas do FRM-001 não permitem identificar quem implementa ou opera o controle. |

A atribuição deve considerar principalmente:

- quem cria, adapta ou configura a parte de IA;
- quem hospeda, atualiza e mantém a solução;
- qual componente técnico é afetado pelo controle;
- qual parte possui capacidade real de implementar o requisito.

A justificativa **“não aplicável por ser solução de terceiro”** não é válida. Quando o requisito depender do fornecedor, o controle permanece aplicável e recebe responsabilidade **Fornecedor** ou **Compartilhada**.

A classificação **Não aplicável** somente pode ser usada após revisão manual que confirme a inexistência da condição técnica que originaria o controle.
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

A seleção deve considerar as capacidades e a arquitetura, e não apenas o tipo de contratação. A MTR-001 converte as respostas do FRM-001 em baselines, perfis e controles técnicos aplicáveis.

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

Cada controle selecionado deve preservar, no mínimo:

- identificador e baseline;
- seção e perfil de aplicabilidade;
- criticidade e obrigatoriedade;
- conteúdo completo do controle;
- condição e justificativa de aplicabilidade;
- responsabilidade e critério específico de atribuição;
- orientações técnicas de auditoria e remediação;
- mapeamentos e referências existentes no baseline.
# 12. Premissa de aplicação dos controles

Esta metodologia não realiza, nesta etapa, avaliação individual de conformidade ou coleta obrigatória de evidências. Todos os controles selecionados pela MTR-001 são considerados parte do plano técnico obrigatório do projeto.

Para o cálculo prospectivo do risco residual, considera-se que:

- todos os controles aplicáveis serão implementados integralmente antes da homologação ou entrada em produção;
- os controles estarão operacionais e cobrirão todo o escopo técnico previsto;
- a responsabilidade atribuída será aceita e executada pela organização, pelo fornecedor ou por ambos;
- não haverá exclusão unilateral de controles selecionados;
- a implementação parcial não satisfaz a premissa de aplicação integral.

```text
Controles considerados no cálculo residual = todos os controles selecionados pela MTR-001
Aplicação considerada = integral
Cobertura considerada = 100% dos controles aplicáveis
```

A evidência descrita nos baselines permanece útil para implementação, auditoria e monitoramento, mas não é requisito de preenchimento do FRM-001 nem entrada para o cálculo prospectivo.

## 12.1 Controle que não possa ser implementado

Quando um controle aplicável não puder ser implementado:

1. o responsável deve solicitar exceção formal;
2. a solicitação deve identificar o controle, a justificativa, o risco, os controles compensatórios, o owner e o prazo;
3. o risco residual deve ser recalculado após a decisão da exceção;
4. até a aprovação, o Parecer não deve ser interpretado como autorização do desvio.

## 12.2 Controle cuja aplicabilidade seja questionada

Quando um controle selecionado não fizer sentido para a arquitetura ou cenário:

1. o controle não deve ser removido automaticamente;
2. deve ser solicitada revisão manual à Segurança de IA ou à Arquitetura de Segurança;
3. a decisão deve registrar a condição técnica inexistente e a justificativa;
4. a MTR-001 deve ser processada novamente após a revisão.
# 13. Cálculo do risco residual projetado

O impacto residual permanece igual ao impacto inerente. A consequência potencial não desaparece apenas porque controles serão implementados.

A probabilidade residual é reduzida em um nível, nunca abaixo de P1, porque a projeção presume a implementação integral de todos os controles aplicáveis.

```text
Impacto residual = Impacto inerente
Probabilidade residual = máximo(P1, Probabilidade inerente - 1 nível)
Risco residual projetado = matriz(Impacto residual, Probabilidade residual)
```

| Probabilidade inerente | Probabilidade residual projetada |
|---|---|
| **P1 — Baixa** | P1 — Baixa |
| **P2 — Moderada** | P1 — Baixa |
| **P3 — Alta** | P2 — Moderada |
| **P4 — Muito alta** | P3 — Alta |

O risco residual é uma **projeção condicionada**. Ele somente permanece válido enquanto todos os controles selecionados forem implementados integralmente.

Se um controle não puder ser implementado ou tiver sua aplicabilidade alterada, o cenário deve ser revisto e o risco recalculado.
# 14. Condicionantes, exceções e revisão manual

A avaliação prospectiva não produz bloqueio por ausência de evidência individual dos controles. Entretanto, o Parecer deve registrar condicionantes que preservem a validade do cálculo.

São condições materiais para encaminhamento:

- pergunta aplicável sem resposta ou informação crítica desconhecida;
- uso de provider, modelo, região ou capacidade proibida ou não autorizada;
- tratamento de dado proibido ou incompatível com a finalidade;
- controle aplicável que não possa ser implementado;
- responsabilidade por controle não determinada;
- divergência sobre a aplicabilidade de controle selecionado;
- mudança material posterior ao cálculo;
- exceção vencida ou condicionante não cumprida.

## 14.1 Exceção

A impossibilidade de aplicar um controle deve gerar solicitação formal de exceção. A aprovação da exceção não é automática e depende das alçadas corporativas aplicáveis.

## 14.2 Revisão manual

A alegação de que um controle não faz sentido deve gerar revisão manual. Somente após a decisão registrada o controle pode ser removido e a aplicabilidade recalculada.

## 14.3 Validade do Parecer

O Parecer permanece condicionado:

- à implementação integral dos controles selecionados;
- ao atendimento das aprovações corporativas pertinentes;
- à inexistência de mudança material após a avaliação;
- ao tratamento das pendências e exceções identificadas.
# 15. Decisão recomendada

O cálculo automatizado deve produzir uma das seguintes recomendações técnicas:

| Decisão | Uso esperado |
|---|---|
| **Aprovado** | Risco residual projetado Baixo ou Moderado, condicionado à implementação integral dos controles e às demais aprovações corporativas. |
| **Aprovado com condições** | Risco residual projetado Alto, exigindo implementação integral dos controles, acompanhamento reforçado e atendimento das condicionantes registradas. |
| **Não aprovado** | Risco residual projetado Crítico ou existência de condição incompatível com o uso pretendido. |

Encaminhamentos complementares podem ser necessários:

- **Solicitação de exceção**, quando um controle aplicável não puder ser implementado;
- **Revisão manual**, quando a aplicabilidade de um controle for questionada;
- **Complementação de informações**, quando respostas necessárias não estiverem disponíveis.

O resultado calculado é uma recomendação técnica e não substitui alçadas de homologação, aceite de risco, contratação, privacidade, jurídico, continuidade ou GRC.
# 16. Saídas mínimas e trilha de auditoria

A avaliação deve registrar:

- identificação do projeto, produto, serviço ou fornecedor;
- respostas aplicáveis do FRM-001;
- cenário ou cenários avaliados;
- modelo de fornecimento e responsabilidades;
- classe H1-H4 e justificativa;
- quatro dimensões de impacto, valores e justificativas;
- cinco fatores de probabilidade, pontuação e justificativas;
- pisos aplicados e condições que os acionaram;
- risco inerente;
- baselines e controles aplicáveis selecionados pela MTR-001;
- conteúdo completo dos controles;
- responsabilidade e critério de atribuição de cada controle;
- premissa de aplicação integral;
- risco residual projetado;
- condicionantes, pendências, exceções e revisões manuais necessárias;
- decisão recomendada;
- versões do FRM-001, MET-001, MTR-001 e BAS-001 a BAS-006;
- data e hora de geração;
- identificador único e impressão digital do snapshot exportado.

Não são exigidos nesta etapa:

- status individual de conformidade;
- percentual de controles conformes;
- evidência individual anexada ao formulário;
- classificação de efetividade baseada em evidência.

Qualquer alteração manual de impacto, probabilidade, aplicabilidade, responsabilidade ou resultado deve possuir justificativa, responsável, data e aprovação conforme alçada.
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
- Probabilidade inerente: P2.
- Risco inerente: Baixo.
- Baselines: BAS-001 e BAS-006, conforme operação e logging.
- Premissa: todos os controles selecionados serão implementados integralmente.
- Probabilidade residual projetada: P1.
- Risco residual projetado: Baixo.
- Decisão técnica: Aprovado, condicionado à implementação dos controles.

## 18.2 SaaS com IA processando dados bancários

- Cenário: solução de terceiro, dados bancários, subprocessadores e retenção desconhecida.
- Impacto: I4.
- Fatores positivos: conteúdo relevante, terceiro e integrações — 3 pontos.
- Piso: localização ou subprocessadores desconhecidos — P3.
- Probabilidade inerente: P3.
- Risco inerente: Crítico.
- Premissa: aplicação integral dos controles selecionados.
- Probabilidade residual projetada: P2.
- Risco residual projetado: Alto.
- Decisão técnica: Aprovado com condições, desde que todos os controles sejam implementados e as informações pendentes sejam resolvidas.
- Caso o fornecedor não possa atender um controle: solicitar exceção e recalcular.

## 18.3 Agente interno com ação em sistema corporativo

- Cenário: agente que consulta RAG e cria registros em sistema interno.
- Impacto: I3.
- Fatores positivos: conteúdo não confiável, RAG e ação em sistema — 3 pontos.
- Piso: agente com escrita — P3.
- Probabilidade inerente: P3.
- Risco inerente: Alto.
- Baselines: BAS-001, BAS-002, BAS-003, BAS-004 e BAS-006.
- Premissa: aplicação integral dos controles selecionados, incluindo autorização determinística, limites de ação, logging e contenção.
- Probabilidade residual projetada: P2.
- Risco residual projetado: Alto.
- Decisão técnica: Aprovado com condições e monitoramento reforçado.
# 19. Resumo do algoritmo

```text
1. Coletar no FRM-001 as informações do cenário, dados, capacidades e responsabilidades.
2. Definir H = maior classe acionada.
3. Definir I = maior impacto entre as quatro dimensões.
4. Somar F1 a F5 e converter para P1 a P4.
5. Aplicar pisos obrigatórios de probabilidade.
6. Consultar a matriz para obter o risco inerente.
7. Aplicar a MTR-001 para selecionar cumulativamente BAS-001 a BAS-006 e os controles específicos.
8. Atribuir responsabilidade a cada controle com base no FRM-001 e na natureza técnica do requisito.
9. Presumir a aplicação integral de todos os controles selecionados.
10. Reduzir P em um nível, nunca abaixo de P1, e manter I.
11. Consultar novamente a matriz para obter o risco residual projetado.
12. Emitir o Parecer de Segurança e registrar condicionantes, exceções ou revisões manuais necessárias.
```
# 20. Histórico de versão

| Versão | Data | Descrição | Responsável |
|---|---:|---|---|
| **1.2** | 15/07/2026 | Alinhamento ao FRM-001 autossuficiente e à MTR-001; remoção de dependências de outros formulários; adoção do cálculo prospectivo com aplicação integral presumida dos controles; inclusão de orientação para exceção e revisão manual; atualização das saídas mínimas e decisões recomendadas. | Segurança de IA / Arquitetura de Segurança / GRC |
| **1.1** | 13/07/2026 | Simplificação do método; redução das dimensões e fatores; inclusão explícita de SaaS, IA embarcada, soluções de terceiros, serviços gerenciados e responsabilidade compartilhada; adoção de regra simples para risco residual. | Segurança de IA / Arquitetura de Segurança / GRC |
| **1.0** | 13/07/2026 | Criação da metodologia corporativa inicial para cálculo de riscos de soluções de IA. | Segurança de IA / Arquitetura de Segurança / GRC |
