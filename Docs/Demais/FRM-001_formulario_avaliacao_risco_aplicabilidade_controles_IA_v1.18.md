# FRM-001 — Formulário de Avaliação de Risco e Aplicabilidade de Controles de Inteligência Artificial

| Campo | Valor |
|---|---|
| **Código** | FRM-001 |
| **Nome** | Formulário de Avaliação de Risco e Aplicabilidade de Controles de Inteligência Artificial |
| **Tipo documental** | Formulário |
| **Classificação da informação** | Uso Interno |
| **Status** | Minuta para revisão |
| **Versão** | 1.18 |
| **Data** | 15/07/2026 |
| **Owner institucional** | Segurança da Informação / Segurança de IA / Arquitetura / GRC |
| **Custodiante técnico** | Segurança de IA / Arquitetura de Segurança da Informação |
| **Quantidade de perguntas** | 119 |
| **Fonte** | Documento autossuficiente FRM-001 — Formulário de Avaliação de Risco e Aplicabilidade de Controles de Inteligência Artificial v1.18 |

## 1. Finalidade

Este documento constitui o FRM-001, formulário corporativo autossuficiente para avaliação de risco e aplicabilidade de controles de Inteligência Artificial. Ele reúne, em um único instrumento, a identificação e a triagem do cenário, as informações necessárias à classificação H1–H4, o cálculo de impacto e probabilidade, a seleção cumulativa dos baselines técnicos e a geração do Parecer de Segurança. Não depende do preenchimento de outro formulário.

## 2. Instruções de preenchimento

- Responda somente às perguntas aplicáveis ao cenário.
- A condição de exibição de cada pergunta indica quando ela deve ser preenchida.
- Perguntas condicionais não aplicáveis devem permanecer em branco.
- Em perguntas de escolha única, selecione somente uma alternativa.
- Em perguntas de múltipla escolha, selecione todas as alternativas aplicáveis.
- Utilize “Não sei” ou “Não determinado” quando a informação ainda não estiver confirmada.
- As definições, os exemplos e o efeito das alternativas devem ser consultados antes da resposta.

## 3. Documentos relacionados

> **Autossuficiência:** o FRM-001 concentra o intake, a caracterização do cenário, as perguntas de risco e as entradas para seleção dos controles. Nenhum outro formulário é pré-requisito para seu preenchimento.

- MET-001 v1.1 — Metodologia de Avaliação e Cálculo de Riscos de Soluções de IA.
- MTR-001 v1.0 — Matriz de Aplicabilidade de Baselines e Controles Técnicos de IA.
- BAS-001 a BAS-006 — Baselines técnicos aplicáveis cumulativamente.
- PRC-003 — Processo de Gestão de Exceções de Segurança de IA.

## 4. Formulário

## 1. Identificação da avaliação

### A01 — Como o projeto, produto, sistema ou serviço se chama?

**Orientação:** Use o nome pelo qual a iniciativa é conhecida na organização.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Sempre exibida na identificação da avaliação.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Informe o nome oficial usado no portfólio, contrato, arquitetura ou sistema de demandas. Evite nomes genéricos como “Projeto de IA”.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Assistente de Normativos Corporativos”
- “Copilot de Atendimento para Canal Digital”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É utilizado para identificação, rastreabilidade, agenda da avaliação e composição do Parecer de Segurança. Não altera diretamente o nível de risco, salvo quando indicado especificamente.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### A02 — Existe um número de solicitação, contrato, processo ou chamado relacionado?

**Orientação:** Informe o identificador usado para localizar esta avaliação futuramente.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Sempre exibida na identificação da avaliação.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Informe o identificador que permita localizar a iniciativa em outro sistema. Pode ser número de demanda, contrato, projeto, chamado, processo ou registro interno.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “JIRA AI-1842”
- “Contrato 2026-045”
- “Demanda ARQ-00981”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É utilizado para identificação, rastreabilidade, agenda da avaliação e composição do Parecer de Segurança. Não altera diretamente o nível de risco, salvo quando indicado especificamente.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### A03 — Qual área está solicitando ou utilizando a solução?

**Orientação:** Ex.: Recursos Humanos, Crédito, Jurídico, Tecnologia ou Atendimento.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Sempre exibida na identificação da avaliação.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Informe a área que solicitou a solução e, quando existir, a unidade de negócio beneficiada.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Recursos Humanos — Recrutamento e Seleção”
- “Operações — Prevenção a Fraudes”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É utilizado para identificação, rastreabilidade, agenda da avaliação e composição do Parecer de Segurança. Não altera diretamente o nível de risco, salvo quando indicado especificamente.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### A04 — Quem é o responsável de negócio?

**Orientação:** Informe nome e contato de quem responde pela finalidade e pelo resultado do uso.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Sempre exibida na identificação da avaliação.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Informe a pessoa responsável pela finalidade, pelo resultado de negócio e pela aceitação do risco. Inclua contato corporativo.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Marina Souza — Diretora de RH — marina.souza@empresa.com”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É utilizado para identificação, rastreabilidade, agenda da avaliação e composição do Parecer de Segurança. Não altera diretamente o nível de risco, salvo quando indicado especificamente.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### A05 — Quem é o responsável técnico?

**Orientação:** Informe nome e contato de quem conhece a arquitetura ou operação da solução.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Sempre exibida na identificação da avaliação.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Informe a pessoa ou equipe responsável pela implementação, integração ou operação técnica. Inclua contato corporativo.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Equipe Plataforma de IA — owner: João Lima — joao.lima@empresa.com”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É utilizado para identificação, rastreabilidade, agenda da avaliação e composição do Parecer de Segurança. Não altera diretamente o nível de risco, salvo quando indicado especificamente.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### A06 — Qual é o fornecedor principal?

**Orientação:** Preencha somente quando houver empresa externa, SaaS, software contratado ou serviço gerenciado.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Exibida somente quando existe cenário de terceiro, SaaS, serviço gerenciado ou componente externo.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Preencha somente quando houver empresa, consultoria, SaaS, fabricante ou prestador responsável por parte da solução.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Fornecedor TalentAI Ltda.”
- “Não aplicável — solução interna”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É utilizado para identificação, rastreabilidade, agenda da avaliação e composição do Parecer de Segurança. Não altera diretamente o nível de risco, salvo quando indicado especificamente.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### A07 — O que a solução fará e qual problema pretende resolver?

**Orientação:** Explique em linguagem simples. Ex.: resumir documentos, apoiar análise, atender clientes ou executar tarefas.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Sempre exibida na identificação da avaliação.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Descreva em linguagem simples o problema atual, como a IA será usada e o resultado que se espera obter. Não descreva somente a tecnologia.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Reduzir o tempo de consulta a normativos. O usuário fará uma pergunta, a solução buscará documentos internos e responderá com as fontes utilizadas.”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É utilizado para identificação, rastreabilidade, agenda da avaliação e composição do Parecer de Segurança. Não altera diretamente o nível de risco, salvo quando indicado especificamente.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### A08 — Em qual fase a solução está agora?

**Orientação:** Selecione somente a fase atual. Os ambientes planejados são informados na pergunta seguinte.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Sempre exibida na identificação da avaliação.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione a única fase que melhor representa o estado atual da iniciativa. Use a fase efetiva, não a fase desejada.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Ideação | A iniciativa ainda está sendo concebida. Escopo, arquitetura, fornecedor e dados podem não estar definidos. | Selecione quando existe apenas uma proposta, estudo de viabilidade ou desenho preliminar, sem protótipo implementado. | Mantém a avaliação em fase inicial. Perguntas desconhecidas devem ser registradas como pendências; controles operacionais de produção não são presumidos somente por esta opção. |
| Prova de conceito (PoC) | Existe um protótipo ou experimento para validar viabilidade, funcionalidade ou tecnologia, normalmente com escopo e usuários limitados. | Selecione para um chatbot experimental com dados fictícios e acesso restrito à equipe do projeto. | Ativa controles compatíveis com experimentação e ambientes não produtivos. Não deve ser usada para encobrir uso real em produção. |
| Desenvolvimento | A solução está sendo construída, integrada ou configurada e ainda não concluiu a validação para uso operacional. | Selecione quando a equipe está implementando APIs, prompts, RAG, agentes ou pipelines. | Ativa controles de desenvolvimento, versionamento, ambientes e cadeia de suprimentos quando aplicáveis. |
| Homologação / validação antes do uso | A solução está pronta para testes formais e validação antes da liberação para uso produtivo. | Selecione quando a versão candidata está em ambiente de homologação e será submetida a testes de segurança. | Ativa controles de teste, evals, telemetria e critérios de liberação. O parecer deve apoiar a decisão de entrada em produção. |
| Produção | A solução já está disponível para usuários, clientes, processos ou sistemas reais. | Selecione quando usuários reais já utilizam a solução ou ela processa transações e dados reais. | Ativa requisitos operacionais de telemetria, detecção, continuidade, contenção e revalidação. |
| Solução existente | A solução já existe ou já é utilizada, mas está sendo avaliada ou formalizada agora. | Selecione para um SaaS já contratado ou uma automação de IA que começou a operar antes do processo atual. | Exige avaliar o estado atual, riscos acumulados, lacunas e controles operacionais existentes. |
| Renovação ou reavaliação | Uma solução já aprovada ou contratada está sendo revista por vencimento, mudança de ciclo ou necessidade periódica. | Selecione quando o contrato será renovado ou quando a homologação anual está vencendo. | Direciona a comparação entre a avaliação anterior e o cenário atual, incluindo mudanças de fornecedor, modelo, dados e controles. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “PoC”, quando existe um experimento limitado ainda sem uso produtivo.
- “Produção”, quando usuários reais já dependem da solução.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

A fase atual pode ativar requisitos operacionais. Homologação, produção, solução existente e revalidação tornam o BAS-006 aplicável e elevam a dimensão Operação e continuidade para, no mínimo, I2.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B006 — BAS-006: Solução em homologação material, produção, operação existente ou que exija telemetria, detecção, contenção, continuidade ou recuperação.

</details>

---

### A09 — Em quais ambientes a solução será utilizada?

**Orientação:** Marque todos os ambientes previstos, como desenvolvimento, testes e produção.

**Tipo de resposta:** Múltipla escolha

**Condição de exibição:** Sempre exibida na identificação da avaliação.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Marque todos os ambientes em que a solução será executada ou testada. Não marque Produção se ainda não existe previsão de uso produtivo.

1. Leia todas as opções antes de responder.
2. Marque cada alternativa que possa ocorrer no cenário real ou planejado.
3. Revise se existem opções complementares; escolhas múltiplas são cumulativas.
4. Não marque opções apenas por possibilidade remota sem previsão de uso.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Desenvolvimento | Ambiente usado para construir e alterar a solução. | Marque quando desenvolvedores executam código, notebooks, prompts ou modelos em ambiente próprio de desenvolvimento. | Seleciona controles de segregação, versionamento, acesso de desenvolvimento e proteção de dados não produtivos. |
| Teste | Ambiente usado para testes técnicos ou funcionais antes da homologação. | Marque quando existem testes automatizados ou manuais em ambiente separado do desenvolvimento. | Seleciona controles de isolamento e uso seguro de dados de teste. |
| Homologação | Ambiente controlado que reproduz condições próximas da produção para validação final. | Marque quando a versão candidata é validada por negócio e segurança antes do go-live. | Seleciona controles de evals, segurança, telemetria e promoção de artefatos. |
| Produção | Ambiente que atende usuários ou processos reais. | Marque quando a solução processará dados reais ou produzirá efeitos reais. | Ativa BAS-006 e controles de operação, logs, detecção, continuidade e contenção. |
| Computador, dispositivo ou endpoint local | Algum componente é executado em notebook, estação, navegador, IDE, dispositivo ou servidor local. | Marque para Ollama em servidor interno, extensão de navegador ou copiloto instalado na IDE. | Ativa controles de endpoint, sandbox, modelos locais, plugins e cadeia de suprimentos quando aplicáveis. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Desenvolvimento + Homologação”, quando ainda não há produção.
- “Homologação + Produção”, quando a solução será validada antes do go-live.

**Evite:**

- Marcar todas as opções por precaução ou escolher apenas uma quando várias são verdadeiras.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Os ambientes selecionados definem controles de segregação, promoção e implantação. Homologação ou produção ativam o BAS-006; mais de um ambiente ativa controles específicos de isolamento.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.5 — BAS-005: desenvolvimento e MLOps; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S01 — BAS-001, 1. Arquitetura e configuração segura: Sempre que houver componente, deployment, endpoint, runtime, gateway ou ambiente de IA.
- MTR1-B005-S07 — BAS-005, 7. Deploy, serving e mudança técnica: Quando houver deployment, endpoint, serving, atualização, reconciliação ou mudança de versão/configuração.
- MTR1-B006 — BAS-006: Solução em homologação material, produção, operação existente ou que exija telemetria, detecção, contenção, continuidade ou recuperação.

</details>

---

### A10 — Qual é a data prevista para piloto, contratação, entrada em produção ou renovação?

**Orientação:** Use a data mais relevante para o andamento da avaliação.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Sempre exibida na identificação da avaliação.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Informe a próxima data material para a avaliação, como piloto, assinatura, renovação, homologação ou entrada em produção.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “30/09/2026 — entrada em produção”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É utilizado para identificação, rastreabilidade, agenda da avaliação e composição do Parecer de Segurança. Não altera diretamente o nível de risco, salvo quando indicado especificamente.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### A11 — Onde estão o desenho da solução e os documentos técnicos?

**Orientação:** Cole links para diagramas, fluxos de dados, especificações, contratos ou páginas internas.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Sempre exibida na identificação da avaliação.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Cole o link do documento mais atual. Pode ser diagrama, wiki, repositório, fluxo de dados ou página da arquitetura.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “https://wiki.empresa.local/arquitetura/assistente-rag-v3”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É utilizado para identificação, rastreabilidade, agenda da avaliação e composição do Parecer de Segurança. Não altera diretamente o nível de risco, salvo quando indicado especificamente.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### A12 — Por que esta avaliação está sendo realizada?

**Orientação:** Selecione o principal motivo: projeto novo, mudança, renovação, incidente, exceção ou revisão periódica.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Sempre exibida na identificação da avaliação.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione o evento que motivou esta avaliação. Escolha apenas o motivo principal; eventos adicionais podem ser descritos nas observações.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Novo projeto | A iniciativa está sendo criada agora e ainda não possui homologação ou parecer anterior válido. | Um novo assistente para colaboradores que ainda está em desenho ou desenvolvimento. | Executa a avaliação inicial completa antes de contratar, implantar ou liberar a solução. |
| Mudança material | Uma solução existente terá mudança capaz de alterar o risco, a arquitetura ou os controles aplicáveis. Exemplos: novo modelo, provider, dados, público, região, RAG, agente, MCP ou exposição externa. | Um chatbot interno passa a atender clientes ou recebe capacidade de executar transações. | Invalida a reutilização automática do parecer anterior e exige novo cálculo do risco e nova seleção de controles. |
| Renovação | O contrato, a licença, a assinatura ou a prestação de serviço será prorrogada ou renovada. | Renovação anual de uma plataforma SaaS de RH com recursos de IA. | Direciona a revisão de fornecedor, contrato, retenção, subprocessadores, SLA, mudanças ocorridas e plano de saída antes da renovação. |
| Incidente/achado | A avaliação foi iniciada em resposta a incidente, vulnerabilidade, finding de auditoria, teste de segurança, reclamação ou comportamento indevido. | Após um teste identificar prompt injection capaz de expor informações internas. | Exige verificar o cenário afetado, revisar o risco e identificar controles adicionais ou revalidação prioritária. |
| Exceção | Existe um controle ou requisito aplicável que não poderá ser atendido e a área deseja submetê-lo ao processo formal de exceção. | O SaaS não fornece um log obrigatório e será solicitada exceção temporária enquanto o fornecedor implementa a função. | Não aprova o desvio. Mantém a necessidade de registrar risco, justificativa, compensações, owner, prazo e decisão conforme o PRC-003. |
| Revalidação periódica | A solução está sendo revista por periodicidade obrigatória, mesmo sem renovação contratual ou mudança material conhecida. | Revisão semestral de um agente anteriormente homologado. | Confirma se dados, arquitetura, fornecedor, capacidades, riscos e controles continuam compatíveis com o parecer anterior. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Novo projeto” para uma iniciativa inédita.
- “Mudança material” para troca de modelo, provider, RAG, agente ou dados.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É utilizado para identificação, rastreabilidade, agenda da avaliação e composição do Parecer de Segurança. Não altera diretamente o nível de risco, salvo quando indicado especificamente.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registro do projeto, solicitação, contrato, cronograma, arquitetura ou contato do responsável.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

## 2. Cenário de uso e modelo de fornecimento

### B01 — Selecione as opções que descrevem como a IA será usada e fornecida.

**Orientação:** Marque todas as opções verdadeiras. Normalmente haverá uma opção sobre quem fornece a IA e outras sobre o que ela faz, como RAG, agente ou modelo local.

**Tipo de resposta:** Múltipla escolha

**Condição de exibição:** Sempre exibida; controla a abertura dos demais blocos.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Marque todos os modelos de uso e fornecimento que realmente fazem parte da solução. As escolhas controlam quais blocos técnicos serão exibidos.

1. Pense primeiro em quem fornece a IA: organização, software contratado, integração com plataforma externa ou fornecedor que usa IA no serviço.
2. Depois marque o que a solução faz: consulta documentos (RAG), executa tarefas (agente), roda modelo local ou funciona em dispositivo.
3. Marque todas as condições verdadeiras. As opções são cumulativas e não representam alternativas exclusivas.
4. Revise as opções quando a arquitetura ou o modelo de contratação mudar.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Uso interno pela organização — ex.: assistente para colaboradores; combine com as opções abaixo quando houver SaaS, RAG, agente ou modelo local | A IA será usada dentro da organização por colaboradores ou sistemas internos. | Assistente interno usado por analistas para resumir procedimentos. | Mantém o BAS-001 e abre perguntas gerais. Não exclui outras opções, como SaaS, RAG ou agente. |
| Sistema da organização conectado a uma IA externa por API — ex.: aplicação que chama Azure OpenAI, OpenAI, Gemini ou serviço equivalente | Uma aplicação própria ou contratada chama um serviço externo de modelo por API. | Sistema interno chamando Azure OpenAI, OpenAI ou Gemini por API. | Ativa BAS-002, integração, gateway, identidade, rede e fatores de exposição técnica. |
| Software contratado que já possui IA — ex.: plataforma de RH, CRM, ERP, ferramenta jurídica ou solução de segurança | Um software contratado já inclui recursos de IA como parte do produto. | Plataforma de RH, CRM ou ferramenta jurídica com copiloto integrado. | Ativa bloco de terceiros, responsabilidades compartilhadas, contrato, logs, dados e continuidade. |
| Aplicação construída sob encomenda por fornecedor, consultoria ou fábrica de software | Uma consultoria, fábrica ou fornecedor constrói a solução para a organização. | Fornecedor desenvolvendo chatbot ou modelo sob encomenda. | Ativa avaliação de terceiro e, quando houver desenvolvimento de componentes, controles do BAS-005. |
| Fornecedor hospeda e opera a solução de IA para a organização | O fornecedor opera modelo, RAG, agente ou plataforma em nome da organização. | Fornecedor gerencia um assistente com base de conhecimento corporativa. | Ativa terceiros, BAS-002 e requisitos de continuidade, operação e saída. |
| A organização desenvolve, configura ou publica a própria solução de IA | A organização constrói ou mantém código, prompts, modelos, datasets ou pipelines de IA. | Equipe interna desenvolvendo um classificador ou agente. | Ativa BAS-005 e perguntas de desenvolvimento, versionamento e MLOps. |
| A IA consulta documentos ou bases para responder — ex.: SharePoint, normativos, manuais, vector store ou memória | A IA consulta documentos, índices, memória ou bases para montar a resposta. | Assistente que consulta SharePoint, normativos e manuais. | Ativa BAS-003 e perguntas de fontes, autorização, ingestão, memória e exclusão. |
| A IA executa tarefas ou chama sistemas — ex.: criar chamado, consultar saldo, enviar mensagem ou alterar registro | A IA chama ferramentas ou executa tarefas em outros sistemas. | Agente que abre chamados, consulta CRM ou envia mensagens. | Ativa BAS-004 e perguntas sobre autorização, limites, ações, identidade e kill switch. |
| Ferramenta instalada ou usada por pessoas — ex.: copiloto, extensão de navegador, IDE, editor ou plugin | A IA é usada em editor, IDE, navegador, extensão, plugin ou ferramenta individual. | Copiloto de código na IDE ou extensão de IA no navegador. | Ativa avaliação de endpoint/terceiro e controles de integração, dados e cadeia de suprimentos. |
| Modelo executado em computador, servidor ou nuvem controlada pela organização — ex.: Ollama, Llama ou outro open source | O modelo ou componente é executado em infraestrutura controlada pela organização ou obtido como artefato open source. | Llama em Ollama, vLLM ou container interno. | Ativa BAS-005, integridade de artefatos, dependências, registries e operação local. |
| IA embutida em equipamento — ex.: câmera, appliance de segurança, terminal, sensor ou dispositivo | A IA está embutida em equipamento, appliance, câmera, endpoint ou produto físico. | Câmera com reconhecimento, appliance de segurança ou dispositivo com inferência local. | Ativa avaliação do fornecedor, do endpoint, das atualizações e dos fluxos de dados. |
| O fornecedor usa IA nos bastidores para entregar o serviço, mesmo que a organização não acesse a IA diretamente | O fornecedor usa IA nos bastidores para entregar o serviço, mesmo que a organização não acesse a IA diretamente. | Consultoria que usa IA para analisar documentos ou prestar atendimento. | Ativa diligência de terceiro, uso de dados, transparência e responsabilidade do fornecedor. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- Assistente interno que consulta normativos: marque “Uso interno pela organização” e “A IA consulta documentos ou bases para responder”.
- Plataforma de RH contratada com triagem automática: marque “Software contratado que já possui IA” e, se hospedada pelo fabricante, “Fornecedor hospeda e opera”.
- Aplicação interna que chama Azure OpenAI: marque “Uso interno pela organização” e “Sistema conectado a uma IA externa por API”.
- Agente interno que abre chamados: marque “Uso interno pela organização” e “A IA executa tarefas ou chama sistemas”.
- Modelo Llama em Ollama no servidor interno: marque “Uso interno pela organização”, “IA desenvolvida pela organização” quando aplicável e “Modelo executado em ambiente controlado”.

**Evite:**

- Marcar somente “Uso interno” quando a solução também é um SaaS, usa RAG ou executa ações.
- Escolher uma única opção por acreditar que as alternativas são exclusivas.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É a pergunta principal de roteamento. As opções escolhidas exibem ou ocultam os blocos condicionais e selecionam cumulativamente BAS-002, BAS-003, BAS-004 e BAS-005. BAS-001 permanece sempre aplicável.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Arquitetura, inventário de componentes, proposta técnica, catálogo de modelos ou descrição do serviço.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades; § 7 — Classificação H1–H4; § 11 — Seleção dos baselines e controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001 — BAS-001: Qualquer uso corporativo, projeto, produto, sistema, serviço ou funcionalidade que utilize IA.
- MTR1-B002 — BAS-002: Aplicação, API, gateway, proxy, broker, roteamento, integração com provider ou exposição de capacidade de IA.
- MTR1-B003 — BAS-003: RAG, embeddings, vector store, memória, cache semântico, base de conhecimento, ingestão ou recuperação de contexto.
- MTR1-B004 — BAS-004: Agente, planner, executor, tool/function calling, plugin, action, skill, MCP, computer use ou automação acionada por IA.
- MTR1-B005 — BAS-005: Desenvolvimento, treinamento, adaptação, empacotamento, registro, avaliação, implantação ou gestão de modelo e artefatos de IA.

</details>

---

### B02 — A solução depende da IA para cumprir sua finalidade principal?

**Orientação:** Escolha Essencial quando o processo não funciona sem IA. Escolha Opcional quando existe fluxo manual ou convencional equivalente.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após selecionar pelo menos um cenário de uso.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Considere se o produto continuaria cumprindo sua finalidade principal sem a IA. Se não cumprir, a IA é central.

1. Imagine a solução com a função de IA desligada.
2. Se o produto deixar de cumprir sua finalidade principal, selecione Essencial.
3. Se apenas perder sugestões, resumos ou automações opcionais, selecione Opcional.
4. Quando ainda não houver fluxo definido, selecione Ainda não sabemos.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Essencial — sem a IA a solução perde sua função principal | A IA é indispensável para a finalidade principal; sem ela o produto ou processo deixa de entregar o resultado esperado. | Um serviço de classificação cujo resultado é produzido exclusivamente pelo modelo. | Aumenta a relevância da dependência tecnológica e reforça requisitos de continuidade, fallback e plano de saída. |
| Opcional — a solução continua funcionando sem a IA | A IA melhora, acelera ou complementa uma função, mas o produto ou processo continua operando sem ela. | Um copiloto opcional para redigir textos em um sistema que funciona normalmente sem o recurso. | Registra dependência menor, embora os riscos dos dados e das capacidades continuem aplicáveis. |
| Ainda não sabemos; será necessária confirmação | Ainda não foi definido se a IA é essencial ou complementar. | A área ainda está desenhando o processo e não decidiu se haverá fluxo alternativo. | Mantém incerteza sobre continuidade e dependência, podendo exigir esclarecimento manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- Essencial: uma solução de triagem automática não realiza o processo sem o modelo.
- Opcional: um editor continua funcionando, mas perde a sugestão de texto por IA.
- Ainda não sabemos: o desenho ainda não definiu fallback ou fluxo manual.

**Evite:**

- Selecionar Opcional apenas porque existe um procedimento de contingência ainda não testado.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Registra se a IA é central ou acessória. Atualmente não altera diretamente a pontuação, mas compõe o contexto, o Parecer de Segurança e a decisão de dependência tecnológica.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Arquitetura, inventário de componentes, proposta técnica, catálogo de modelos ou descrição do serviço.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades; § 7 — Classificação H1–H4; § 11 — Seleção dos baselines e controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001 — BAS-001: Qualquer uso corporativo, projeto, produto, sistema, serviço ou funcionalidade que utilize IA.

</details>

---

### B03 — Quem cria, adapta ou configura a parte de IA?

**Orientação:** Considere modelo, prompts principais, RAG, agente, regras e parâmetros. Se cada parte tiver um responsável diferente, selecione Compartilhado.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após selecionar pelo menos um cenário de uso.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione quem cria, adapta ou configura o componente de IA, incluindo prompts sistêmicos, agentes, RAG e parâmetros relevantes.

1. Identifique quem controla modelo, prompts principais, base de conhecimento, agente e regras de comportamento.
2. Selecione Organização quando tudo isso estiver sob controle interno.
3. Selecione Fornecedor quando a empresa externa controlar a configuração.
4. Selecione Compartilhado quando as responsabilidades estiverem divididas.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Organização — equipe interna cria ou configura a IA | Equipes internas criam ou configuram modelo, prompts, RAG, agentes, regras ou parâmetros relevantes. | Equipe interna mantém prompts sistêmicos, pipeline e configuração do modelo. | Atribui à organização a responsabilidade primária pelos controles técnicos de desenvolvimento e configuração. |
| Fornecedor — empresa externa controla o desenvolvimento ou configuração | Uma empresa externa cria ou configura a parte de IA. | SaaS em que o fabricante define modelo, prompts e políticas internas. | Ativa diligência de terceiro e atribui ao fornecedor os controles que dependem da implementação sob seu domínio. |
| Compartilhado — organização e fornecedor atuam juntos | Organização e fornecedor controlam partes diferentes da configuração. | Fornecedor opera o modelo, enquanto a organização configura RAG, políticas e prompts. | Distribui responsabilidades e exige clareza sobre qual parte implementa cada controle. |
| Ainda não sabemos quem é responsável | Ainda não se sabe quem controla a configuração da IA. | Contrato e arquitetura ainda não esclarecem quem altera o modelo e os prompts. | Mantém responsabilidade não definida e pode exigir revisão antes da homologação. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- Organização: equipe interna define prompts, configura RAG e publica o agente.
- Fornecedor: SaaS controla modelo, prompts e regras sem acesso administrativo do cliente.
- Compartilhado: fornecedor mantém o modelo e a organização configura fontes, políticas e prompts.

**Evite:**

- Selecionar Organização apenas porque o contrato é da organização, mesmo quando o fornecedor controla modelo e prompts.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Define quem deverá implementar e comprovar os controles. Afeta a atribuição Organização, Fornecedor ou Compartilhada, sem reduzir risco por si só.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Arquitetura, inventário de componentes, proposta técnica, catálogo de modelos ou descrição do serviço.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades; § 7 — Classificação H1–H4; § 11 — Seleção dos baselines e controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### B04 — Quem hospeda, atualiza e mantém a IA funcionando?

**Orientação:** Considere infraestrutura, endpoint, disponibilidade, atualizações e suporte operacional.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após selecionar pelo menos um cenário de uso.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione quem mantém a infraestrutura, o endpoint, o modelo e a disponibilidade operacional.

1. Verifique onde o endpoint ou modelo é executado.
2. Identifique quem aplica atualizações, monitora disponibilidade e presta suporte.
3. Selecione Compartilhado quando a organização controla parte da infraestrutura, mas o fornecedor opera outra parte.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Organização — infraestrutura e operação ficam sob controle interno | A infraestrutura, o endpoint, a disponibilidade e a operação da IA são mantidos internamente. | Modelo hospedado em cluster corporativo e operado pela equipe interna. | Atribui à organização os controles operacionais, de telemetria, continuidade e atualização. |
| Fornecedor — serviço é hospedado e operado externamente | O terceiro hospeda e mantém o serviço de IA. | SaaS ou API de IA totalmente operada pelo fabricante. | Ativa controles contratuais, SLA, logs, continuidade, incidentes e plano de saída sob responsabilidade do fornecedor. |
| Compartilhado — parte interna e parte externa | A operação depende de componentes internos e externos. | Gateway interno consumindo modelo hospedado por provider externo. | Gera responsabilidade compartilhada para integração, monitoramento, continuidade e resposta. |
| Ainda não sabemos quem hospeda ou opera | A arquitetura operacional ainda não está definida. | A equipe ainda decide entre hospedagem interna ou serviço gerenciado. | Mantém incerteza de responsabilidade e pode impedir conclusão adequada da avaliação. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- Organização: modelo e endpoint executados no cluster corporativo.
- Fornecedor: SaaS totalmente hospedado e operado pelo fabricante.
- Compartilhado: aplicação e gateway internos, mas modelo hospedado pelo provider.

**Evite:**

- Confundir quem usa a solução com quem hospeda e opera a infraestrutura.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Define quem opera e hospeda a solução. Afeta responsabilidade, evidências esperadas e tratamento de terceiros.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Arquitetura, inventário de componentes, proposta técnica, catálogo de modelos ou descrição do serviço.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades; § 7 — Classificação H1–H4; § 11 — Seleção dos baselines e controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### B05 — Você sabe qual plataforma, modelo ou serviço executará a IA? Informe o que souber.

**Orientação:** Ex.: Azure OpenAI, Gemini, OpenAI, modelo local, versão, região e ambiente. Caso ainda não saiba, escreva “Não definido”.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Exibida após selecionar pelo menos um cenário de uso.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Informe apenas o que for conhecido. Prefira identificadores técnicos e versões concretas em vez de nomes comerciais genéricos.

1. Consulte arquitetura, contrato, console ou documentação técnica.
2. Informe plataforma/provider, nome do modelo, versão ou deployment, região e tipo de hospedagem.
3. Registre somente informações confirmadas; use “Não definido” para itens ainda desconhecidos.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Azure OpenAI; GPT-5; deployment atendimento-prod; Brazil South; API gerenciada.”
- “Ollama; Llama 3.x; servidor interno; ambiente de homologação.”
- “Provider e região ainda não definidos — confirmar antes da homologação.”

**Evite:**

- Informar somente “ChatGPT” ou “IA generativa”, sem plataforma, versão, região ou contexto disponível.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Identifica provider, modelo, versão, região e deployment. Em cenário externo, deixar esta informação em branco gera piso mínimo P3 por falta de identificação/homologação demonstrada.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Arquitetura, inventário de componentes, proposta técnica, catálogo de modelos ou descrição do serviço.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades; § 7 — Classificação H1–H4; § 11 — Seleção dos baselines e controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S01 — BAS-001, 1. Arquitetura e configuração segura: Sempre que houver componente, deployment, endpoint, runtime, gateway ou ambiente de IA.
- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B002-S04 — BAS-002, 4. Roteamento, modelos e policies: Quando houver escolha de provider/modelo, aliases, rotas, fallback ou policies de gateway.
- MTR1-B005-S03 — BAS-005, 3. Modelos, artefatos e registries: Quando modelos, weights, checkpoints, adapters, tokenizers ou bundles forem registrados, carregados ou distribuídos.

</details>

---

### B06 — A função de IA pode ser desligada sem interromper todo o produto ou processo?

**Orientação:** Ex.: desativar o copiloto e continuar usando o sistema, ou retornar temporariamente para um fluxo manual.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente para solução de terceiro, SaaS, serviço gerenciado ou IA embarcada.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Responda “Sim” somente se houver um mecanismo real e testável para desligar a IA sem impedir a função principal do produto.

1. Confirme se existe botão, feature flag, configuração ou procedimento para desligar apenas a IA.
2. Verifique se o processo continua por fluxo manual, regra convencional ou funcionalidade não baseada em IA.
3. Responda Sim somente quando esse comportamento puder ser demonstrado.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Ex.: desativar o copiloto e continuar usando o sistema, ou retornar temporariamente para um fluxo manual. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A função de IA pode ser desligada sem interromper todo o produto ou processo. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: desativar o copiloto e continuar usando o sistema, ou retornar temporariamente para um fluxo manual. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- Sim: feature flag desliga o copiloto e o processo continua manualmente.
- Não: a solução deixa de funcionar quando o serviço de IA fica indisponível.

**Evite:**

- Responder Sim com base em intenção futura, sem mecanismo de desligamento definido.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Em solução de terceiro, resposta diferente de “Sim” gera piso mínimo P3, pois a funcionalidade de IA não está comprovadamente sob controle ou não pode ser desativada.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Arquitetura, inventário de componentes, proposta técnica, catálogo de modelos ou descrição do serviço.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades; § 7 — Classificação H1–H4; § 11 — Seleção dos baselines e controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### B07 — Uma empresa externa pode alterar a IA sem aprovação prévia da organização?

**Orientação:** Considere troca de modelo, região, recursos, retenção, subfornecedor ou comportamento.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente para solução de terceiro, SaaS, serviço gerenciado ou IA embarcada.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Considere mudanças automáticas, atualizações de modelo, troca de região ou provider e habilitação de novas funcionalidades.

1. Consulte contrato, política de mudanças e documentação do fornecedor.
2. Considere troca automática de modelo, região, retenção, termos, recursos ou subprocessadores.
3. Responda Não somente quando houver controle ou comunicação prévia comprovável.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Considere troca de modelo, região, recursos, retenção, subfornecedor ou comportamento. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Uma empresa externa pode alterar a IA sem aprovação prévia da organização. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Considere troca de modelo, região, recursos, retenção, subfornecedor ou comportamento. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- Sim: o SaaS troca o modelo automaticamente e apenas publica nota de versão depois.
- Não: contrato exige aviso e aprovação antes de mudança de modelo ou região.

**Evite:**

- Responder Não sem consultar contrato ou política de atualização do fornecedor.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” ou “Não sei” ativa fator de probabilidade por modelo alterável, lacuna de terceiro e piso mínimo P3.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Arquitetura, inventário de componentes, proposta técnica, catálogo de modelos ou descrição do serviço.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades; § 7 — Classificação H1–H4; § 11 — Seleção dos baselines e controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B002-S04 — BAS-002, 4. Roteamento, modelos e policies: Quando houver escolha de provider/modelo, aliases, rotas, fallback ou policies de gateway.
- MTR1-B005-S07 — BAS-005, 7. Deploy, serving e mudança técnica: Quando houver deployment, endpoint, serving, atualização, reconciliação ou mudança de versão/configuração.

</details>

---

### B08 — Outras empresas, plataformas ou plugins participam do processamento?

**Orientação:** Ex.: nuvem, outro provedor de IA, serviço de moderação, marketplace, plugin ou subprocessador.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente para solução de terceiro, SaaS, serviço gerenciado ou IA embarcada.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Inclua empresas e componentes que recebem dados ou participam do processamento, mesmo quando contratados pelo fornecedor principal.

1. Liste todos os componentes externos que recebem dados ou participam da resposta.
2. Inclua nuvem, provider de IA, moderação, OCR, plugins, marketplace e subcontratados.
3. Quando a informação depender do fornecedor e não estiver disponível, selecione Não sei.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Ex.: nuvem, outro provedor de IA, serviço de moderação, marketplace, plugin ou subprocessador. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Outras empresas, plataformas ou plugins participam do processamento. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: nuvem, outro provedor de IA, serviço de moderação, marketplace, plugin ou subprocessador. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- Sim: fornecedor principal usa Azure, serviço externo de OCR e moderação de conteúdo.
- Não sei: o fornecedor ainda não apresentou a lista de subprocessadores.

**Evite:**

- Considerar apenas o fornecedor principal e ignorar nuvem, plugins e subprocessadores.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Ajuda a caracterizar o cenário, definir responsabilidades e selecionar perguntas, baselines e controles aplicáveis.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Arquitetura, inventário de componentes, proposta técnica, catálogo de modelos ou descrição do serviço.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades; § 7 — Classificação H1–H4; § 11 — Seleção dos baselines e controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### B09 — Alguma parte da IA será instalada ou executada em computador, servidor ou dispositivo controlado pela organização?

**Orientação:** Ex.: Ollama, modelo open source, extensão, plugin, IDE, container ou execução no endpoint.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida para modelo local, ferramenta instalada, plugin, endpoint ou desenvolvimento interno.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Considere modelos executados em notebook, estação, servidor local, container, Ollama, extensão de navegador ou IDE.

1. Verifique se há instalação em notebook, estação, servidor interno, container, appliance ou dispositivo.
2. Inclua extensões de navegador, plugins de IDE e modelos baixados de repositórios públicos.
3. Responda Sim mesmo que apenas uma parte da solução seja executada localmente.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Ex.: Ollama, modelo open source, extensão, plugin, IDE, container ou execução no endpoint. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Alguma parte da IA será instalada ou executada em computador, servidor ou dispositivo controlado pela organização. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: Ollama, modelo open source, extensão, plugin, IDE, container ou execução no endpoint. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- Sim: extensão de IA instalada na IDE dos desenvolvedores.
- Sim: modelo open source executado em container no datacenter interno.
- Não: toda a inferência ocorre em SaaS externo, sem componente instalado.

**Evite:**

- Ignorar extensões, plugins ou modelos executados em notebooks por não estarem em servidor de produção.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” pode ativar BAS-005, controles de modelo local, artefatos, sandbox e cadeia de suprimentos.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Arquitetura, inventário de componentes, proposta técnica, catálogo de modelos ou descrição do serviço.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades; § 7 — Classificação H1–H4; § 11 — Seleção dos baselines e controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B004-S06 — BAS-004, 6. Sandbox, host, navegador e computer use: Quando houver execução de código, terminal, navegador, desktop, IDE, endpoint ou computer use.
- MTR1-B005 — BAS-005: Desenvolvimento, treinamento, adaptação, empacotamento, registro, avaliação, implantação ou gestão de modelo e artefatos de IA.
- MTR1-B005-L2
- MTR1-B005-S03 — BAS-005, 3. Modelos, artefatos e registries: Quando modelos, weights, checkpoints, adapters, tokenizers ou bundles forem registrados, carregados ou distribuídos.

</details>

---

### B10 — Dados da organização serão usados para treinar, ajustar, testar ou melhorar a IA?

**Orientação:** Inclui fine-tuning, adaptação, avaliação, personalização e criação de exemplos com dados internos.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando existe desenvolvimento, modelo local ou solução construída por terceiro.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Considere qualquer uso de dados corporativos para treinar, ajustar, avaliar, melhorar ou personalizar o comportamento do modelo.

1. Considere treinamento, fine-tuning, adaptação, avaliação, criação de exemplos e melhoria contínua.
2. Inclua atividades realizadas pela organização e pelo fornecedor.
3. Responda Sim quando dados internos forem usados para modificar ou avaliar o comportamento da IA.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Inclui fine-tuning, adaptação, avaliação, personalização e criação de exemplos com dados internos. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Dados da organização serão usados para treinar, ajustar, testar ou melhorar a IA. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclui fine-tuning, adaptação, avaliação, personalização e criação de exemplos com dados internos. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- Sim: fine-tuning com chamados históricos da organização.
- Sim: testes e evals usam amostras de documentos internos.
- Não: serviço usa apenas modelo pronto e dados internos não são usados para treino ou melhoria.

**Evite:**

- Considerar treinamento apenas como criação de modelo do zero e ignorar fine-tuning, evals e personalização.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” ativa controles de datasets, treinamento, fine-tuning, avaliação e MLOps do BAS-005.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Arquitetura, inventário de componentes, proposta técnica, catálogo de modelos ou descrição do serviço.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6 — Identificação do cenário e das responsabilidades; § 7 — Classificação H1–H4; § 11 — Seleção dos baselines e controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B005 — BAS-005: Desenvolvimento, treinamento, adaptação, empacotamento, registro, avaliação, implantação ou gestão de modelo e artefatos de IA.
- MTR1-B005-S01 — BAS-005, 1. Repositórios, código e versionamento: Quando código, notebook, prompt, policy, manifesto ou configuração for desenvolvido ou mantido para a solução.
- MTR1-B005-S02 — BAS-005, 2. Datasets, prompts e configurações de treinamento e avaliação: Quando houver treinamento, fine-tuning, avaliação, dataset, prompt sistêmico ou configuração de geração por release.

</details>

---

## 3. Terceiros, SaaS, COTS e serviços gerenciados

### C01 — O fornecedor pode usar nossos dados para treinar ou melhorar seus modelos?

**Orientação:** Considere prompts, respostas, anexos e registros de uso.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Verifique contrato, configuração e política do serviço. “Não” deve estar sustentado por configuração ou cláusula aplicável ao tenant.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Considere prompts, respostas, anexos e registros de uso. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: O fornecedor pode usar nossos dados para treinar ou melhorar seus modelos. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Considere prompts, respostas, anexos e registros de uso. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Não — opt-out de treinamento habilitado e cláusula contratual proíbe uso secundário.”

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Quando houver dados protegidos, “Sim” ou “Não sei” pode gerar piso P3 pelo possível uso dos dados para treinamento do fornecedor.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### C02 — O fornecedor guarda algum conteúdo após o uso?

**Orientação:** Informe o que é guardado, por que motivo e por quanto tempo. Ex.: prompts por 30 dias e logs por 12 meses.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Informe separadamente o que é retido, por qual motivo e por quanto tempo. Inclua prompts, arquivos, outputs, logs e backups.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Prompts e outputs: 30 dias para suporte; logs administrativos: 12 meses; backups: 35 dias.”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

A ausência de informação sobre retenção, combinada com localização não comprovada, gera piso P3.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### C03 — Sabemos em quais países ou regiões os dados serão processados e armazenados?

**Orientação:** Responda Sim somente quando a localização estiver confirmada e for aceitável.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Responda Sim somente quando a localização estiver confirmada e for aceitável. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Sabemos em quais países ou regiões os dados serão processados e armazenados. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Responda Sim somente quando a localização estiver confirmada e for aceitável. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Resposta diferente de “Sim” contribui para lacuna de terceiro e piso P3 por localização/processamento não comprovados.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### C04 — O fornecedor comprova que os dados de um cliente não se misturam com os de outro?

**Orientação:** Também chamado de segregação entre clientes ou tenants.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Também chamado de segregação entre clientes ou tenants. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: O fornecedor comprova que os dados de um cliente não se misturam com os de outro. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Também chamado de segregação entre clientes ou tenants. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Resposta diferente de “Sim” contribui para lacuna de fornecedor e pode gerar condição bloqueante quando há dados sensíveis e ambiente compartilhado.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 9.2 — BAS-002: integração e exposição; § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B002-S03 — BAS-002, 3. Autorização e segregação: Quando houver múltiplos usuários, tenants, ambientes, privilégios, recursos ou políticas de autorização.
- MTR1-B003-S04 — BAS-003, 4. Autorização, segregação e recuperação permitida: Quando dados ou documentos possuírem escopo por usuário, grupo, tenant, classificação ou autorização.

</details>

---

### C05 — A solução permite usar login corporativo e controlar permissões?

**Orientação:** Ex.: SSO, autenticação multifator e perfis separados para usuário e administrador.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: SSO, autenticação multifator e perfis separados para usuário e administrador. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A solução permite usar login corporativo e controlar permissões. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: SSO, autenticação multifator e perfis separados para usuário e administrador. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Avalia transparência e responsabilidade do fornecedor. Respostas negativas, desconhecidas ou sem evidência não reduzem risco e podem aumentar a probabilidade ou exigir revisão técnica.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S02 — BAS-001, 2. Identidade, acesso e segredos: Quando houver usuário, workload, conta administrativa, credencial, segredo ou acesso a recurso de IA.
- MTR1-B002-S02 — BAS-002, 2. Autenticação e identidade: Quando usuários, workloads ou clientes acessarem aplicação, API, gateway ou provider.

</details>

---

### C06 — A organização consegue receber os registros de acesso, uso e administração?

**Orientação:** Ex.: exportar logs para auditoria, SIEM ou equipe de segurança.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: exportar logs para auditoria, SIEM ou equipe de segurança. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A organização consegue receber os registros de acesso, uso e administração. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: exportar logs para auditoria, SIEM ou equipe de segurança. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Avalia transparência e responsabilidade do fornecedor. Respostas negativas, desconhecidas ou sem evidência não reduzem risco e podem aumentar a probabilidade ou exigir revisão técnica.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S06 — BAS-001, 6. Logging, auditoria e monitoramento: Quando a solução estiver em teste material, homologação, produção ou processar dados relevantes.
- MTR1-B006-S03 — BAS-006, 3. Proteção, minimização e integridade dos registros: Quando logs, traces, prompts, outputs ou eventos contiverem informação sensível ou evidência crítica.
- MTR1-B006-S04 — BAS-006, 4. Coleta, transporte e integração com SIEM: Quando eventos forem enviados a collector, broker, data lake, APM, SIEM ou SOC.

</details>

---

### C07 — O fornecedor apresentou provas de segurança?

**Orientação:** Ex.: relatórios de teste, certificações, auditorias independentes ou resultados de avaliação de IA.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: relatórios de teste, certificações, auditorias independentes ou resultados de avaliação de IA. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: O fornecedor apresentou provas de segurança. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: relatórios de teste, certificações, auditorias independentes ou resultados de avaliação de IA. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Resposta diferente de “Sim” gera piso P3 por ausência de evidência mínima de segurança do fornecedor.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B005-S06 — BAS-005, 6. Testes, evals e critérios técnicos de release: Quando releases, modelos, prompts ou soluções forem avaliados antes da promoção ou contratação.

</details>

---

### C08 — O contrato define prazo para avisar incidentes e vulnerabilidades?

**Orientação:** Considere incidentes de segurança, privacidade, indisponibilidade ou falhas relevantes de IA.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Considere incidentes de segurança, privacidade, indisponibilidade ou falhas relevantes de IA. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: O contrato define prazo para avisar incidentes e vulnerabilidades. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Considere incidentes de segurança, privacidade, indisponibilidade ou falhas relevantes de IA. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Avalia transparência e responsabilidade do fornecedor. Respostas negativas, desconhecidas ou sem evidência não reduzem risco e podem aumentar a probabilidade ou exigir revisão técnica.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### C09 — O fornecedor avisa antes de mudanças importantes?

**Orientação:** Ex.: troca de modelo, região, subprocessador, retenção ou termos de uso.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: troca de modelo, região, subprocessador, retenção ou termos de uso. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: O fornecedor avisa antes de mudanças importantes. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: troca de modelo, região, subprocessador, retenção ou termos de uso. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Avalia transparência e responsabilidade do fornecedor. Respostas negativas, desconhecidas ou sem evidência não reduzem risco e podem aumentar a probabilidade ou exigir revisão técnica.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### C10 — Existe garantia de disponibilidade e recuperação do serviço?

**Orientação:** Ex.: SLA, continuidade, alternativa temporária e procedimento de recuperação.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: SLA, continuidade, alternativa temporária e procedimento de recuperação. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Existe garantia de disponibilidade e recuperação do serviço. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: SLA, continuidade, alternativa temporária e procedimento de recuperação. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Não” ou “Não sei” aumenta a lacuna de terceiro. Para componente crítico, ausência de continuidade/fallback pode gerar piso P3.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S07 — BAS-001, 7. Resiliência e recuperação: Quando houver dependência operacional, serviço produtivo, ação material ou necessidade de recuperação e desativação.
- MTR1-B002-S08 — BAS-002, 8. Resiliência e comportamento de falha: Quando a integração exigir timeout, retry, fallback, circuit breaker, fail-closed ou continuidade.
- MTR1-B006-S08 — BAS-006, 8. Recuperação, continuidade e desativação técnica: Quando houver requisito de backup, restauração, redundância, recuperação, plano de saída ou desativação segura.

</details>

---

### C11 — É possível sair do serviço sem perder dados ou ficar dependente do fornecedor?

**Orientação:** Verifique exportação e exclusão de dados, configurações, prompts, índices e outros artefatos.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Verifique exportação e exclusão de dados, configurações, prompts, índices e outros artefatos. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: É possível sair do serviço sem perder dados ou ficar dependente do fornecedor. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Verifique exportação e exclusão de dados, configurações, prompts, índices e outros artefatos. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Não” ou “Não sei” aumenta dependência de fornecedor e pode gerar piso P3 para componente crítico sem plano de saída.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.5 — BAS-005: desenvolvimento e MLOps; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S07 — BAS-001, 7. Resiliência e recuperação: Quando houver dependência operacional, serviço produtivo, ação material ou necessidade de recuperação e desativação.
- MTR1-B003-S08 — BAS-003, 8. Retenção, exclusão, sincronização e recuperação: Quando dados, índices, embeddings, memória ou derivados forem persistidos e precisarem ser excluídos ou restaurados.
- MTR1-B005-S08 — BAS-005, 8. Rollback, descontinuação e descarte técnico: Quando a solução precisar retornar versão, retirar modelo, revogar acesso, eliminar caches ou impedir reativação.
- MTR1-B006-S08 — BAS-006, 8. Recuperação, continuidade e desativação técnica: Quando houver requisito de backup, restauração, redundância, recuperação, plano de saída ou desativação segura.

</details>

---

### C12 — Está documentado quem é responsável por cada controle de segurança?

**Orientação:** Diferencie responsabilidades da organização e do fornecedor.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Diferencie responsabilidades da organização e do fornecedor. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Está documentado quem é responsável por cada controle de segurança. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Diferencie responsabilidades da organização e do fornecedor. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Resposta diferente de “Sim” aumenta a incerteza de responsabilidade e, junto com ausência de evidências, pode tornar a avaliação inconclusiva ou bloqueante.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### C13 — O contrato limita treinamento, compartilhamento, retenção e outros usos dos dados?

**Orientação:** Responda Sim somente se as restrições estiverem formalmente registradas.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Responda Sim somente se as restrições estiverem formalmente registradas. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: O contrato limita treinamento, compartilhamento, retenção e outros usos dos dados. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Responda Sim somente se as restrições estiverem formalmente registradas. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Avalia transparência e responsabilidade do fornecedor. Respostas negativas, desconhecidas ou sem evidência não reduzem risco e podem aumentar a probabilidade ou exigir revisão técnica.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### C14 — Quais informações ou provas o fornecedor não apresentou?

**Orientação:** Liste respostas recusadas, dúvidas, limitações de acesso ou evidências incompletas.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Exibida somente quando o cenário possui fornecedor, SaaS, COTS ou serviço gerenciado.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Liste somente lacunas objetivas: perguntas sem resposta, evidências não fornecidas, restrições de auditoria ou informações contraditórias.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Fornecedor não apresentou evidência de segregação entre tenants.”
- “Região de backup não informada.”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Qualquer limitação registrada é considerada lacuna de transparência do fornecedor e participa do fator F5 de probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Contrato, DPA, questionário do fornecedor, relatório de auditoria, SLA, certificação ou documentação oficial.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 6.2 — Modelo de responsabilidade; § 9 — Probabilidade; § 9.1 — Pisos obrigatórios; § 12 — Avaliação dos controles
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

## 4. Dados, privacidade e sigilo

### D00 — Selecione os tipos de dados que a solução poderá receber, consultar, armazenar ou gerar.

**Orientação:** Marque todas as opções aplicáveis. Os exemplos ajudam a identificar a categoria; não é necessário conhecer a classificação formal.

**Tipo de resposta:** Múltipla escolha

**Condição de exibição:** Exibida após definir o cenário; perguntas adicionais aparecem quando há dados protegidos ou compartilhamento externo.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Marque todos os tipos de dados que podem aparecer em entradas, arquivos, contexto, memória, treinamento, logs ou respostas. Considere o pior caso razoavelmente previsível.

1. Leia todas as opções antes de responder.
2. Marque cada alternativa que possa ocorrer no cenário real ou planejado.
3. Revise se existem opções complementares; escolhas múltiplas são cumulativas.
4. Não marque opções apenas por possibilidade remota sem previsão de uso.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Somente dados públicos ou nenhum dado — ex.: páginas públicas, materiais já publicados ou conteúdo sem restrição | A solução utilizará apenas conteúdo já público ou não processará dados. | FAQ público, notícias ou dados sintéticos. | Define Dados e privacidade como I1, salvo outro fator independente. |
| Dados pessoais básicos — ex.: nome, idade, e-mail, telefone, endereço, cargo ou matrícula | A solução utilizará informações que identificam ou permitem identificar uma pessoa. | Nome, e-mail, telefone, endereço ou matrícula. | Define impacto de dados de pelo menos I3 no motor atual. |
| Dados pessoais sensíveis — ex.: saúde, biometria, origem racial ou étnica, religião, opinião política, vida sexual ou filiação sindical | A solução utilizará dados sobre saúde, biometria, religião, origem racial ou outras categorias sensíveis. | Laudo médico, biometria ou informação religiosa. | Define impacto de dados de pelo menos I3 e ativa controles reforçados. |
| Dados bancários e financeiros — ex.: conta, agência, saldo, limite, cartão, transação, renda, crédito ou investimento | A solução utilizará informações sobre conta, saldo, limite, cartão, transação, renda, crédito ou investimento. | Extrato, limite de crédito ou dados de transação. | Define impacto de dados como I4. |
| Credenciais, segredos e informações de segurança — ex.: senha, token, chave de API, cookie, certificado, código-fonte ou configuração de segurança | A solução poderá receber senhas, tokens, chaves, certificados, código ou configuração de segurança. | Chave de API, token OAuth ou connection string. | Define impacto de dados como I4 e ativa controles críticos de segredo e inspeção. |
| Dados corporativos internos — ex.: contratos, procedimentos, relatórios, documentos internos, estratégia ou informações operacionais | A solução utilizará documentos e informações internas que não são públicos. | Procedimentos, relatórios internos e contratos. | Define impacto de dados de pelo menos I2 e ativa controles de acesso e proteção. |
| Dados regulados ou protegidos por sigilo — ex.: segredo bancário, fiscal, judicial, investigação ou informação classificada como restrita | A solução utilizará informação submetida a sigilo, regulação ou classificação de acesso muito restrita. | Segredo bancário, fiscal, judicial ou investigação. | Define impacto de dados como I4. |
| Não sei informar — selecione esta opção quando precisar de apoio para identificar os dados | O respondente ainda não consegue identificar os tipos de dados utilizados. | Arquitetura ou inventário de dados ainda não disponível. | Aplica tratamento conservador I4 e exige revisão antes da conclusão. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- Dados pessoais básicos: nome, e-mail e telefone de candidatos.
- Dados bancários: conta, saldo, limite e histórico de transações.
- Credenciais e segredos: token de API presente em logs ou arquivos.

**Evite:**

- Marcar todas as opções por precaução ou escolher apenas uma quando várias são verdadeiras.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Define a dimensão Dados e privacidade: dados públicos → I1; dados corporativos internos → I2; dados pessoais, sensíveis ou regulados → pelo menos I3; dados bancários, credenciais, segredos ou “Não sei” → I4. Também seleciona controles específicos de proteção de dados.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Inventário de dados, fluxo de dados, classificação, amostras mascaradas, política de retenção ou configuração de DLP.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001 — BAS-001: Qualquer uso corporativo, projeto, produto, sistema, serviço ou funcionalidade que utilize IA.
- MTR1-B002 — BAS-002: Aplicação, API, gateway, proxy, broker, roteamento, integração com provider ou exposição de capacidade de IA.
- MTR1-B003 — BAS-003: RAG, embeddings, vector store, memória, cache semântico, base de conhecimento, ingestão ou recuperação de contexto.
- MTR1-B006 — BAS-006: Solução em homologação material, produção, operação existente ou que exija telemetria, detecção, contenção, continuidade ou recuperação.

</details>

---

### D06 — Dê exemplos dos dados que entram e saem da solução.

**Orientação:** Inclua textos, arquivos, anexos, dados usados como contexto, memória, treinamento e respostas geradas.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Exibida após definir o cenário; perguntas adicionais aparecem quando há dados protegidos ou compartilhamento externo.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Descreva o percurso dos dados: o que entra, de onde vem, o que a IA consulta, o que fica armazenado e o que é gerado.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Entrada: currículos em PDF. Contexto: descrição da vaga. Armazenamento: arquivo por 30 dias. Output: resumo e classificação para o recrutador.”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

É usado para contextualizar a avaliação, selecionar evidências e produzir o Parecer de Segurança. Não altera a pontuação diretamente.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Inventário de dados, fluxo de dados, classificação, amostras mascaradas, política de retenção ou configuração de DLP.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.
- MTR1-B003-S01 — BAS-003, 1. Fontes, ingestão e elegibilidade: Quando fontes, uploads, conectores, APIs, Internet ou terceiros alimentarem contexto ou conhecimento.
- MTR1-B005-S02 — BAS-005, 2. Datasets, prompts e configurações de treinamento e avaliação: Quando houver treinamento, fine-tuning, avaliação, dataset, prompt sistêmico ou configuração de geração por release.

</details>

---

### D07 — Algum dado será enviado ou disponibilizado para outra empresa?

**Orientação:** Inclua fornecedores, provedores de IA, consultorias, subprocessadores e parceiros.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário; perguntas adicionais aparecem quando há dados protegidos ou compartilhamento externo.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Inclua fornecedores, provedores de IA, consultorias, subprocessadores e parceiros. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Algum dado será enviado ou disponibilizado para outra empresa. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclua fornecedores, provedores de IA, consultorias, subprocessadores e parceiros. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Caracteriza dados e privacidade. Pode alterar impacto, selecionar controles de proteção, retenção, inspeção e exclusão.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Inventário de dados, fluxo de dados, classificação, amostras mascaradas, política de retenção ou configuração de DLP.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.
- MTR1-B003-S01 — BAS-003, 1. Fontes, ingestão e elegibilidade: Quando fontes, uploads, conectores, APIs, Internet ou terceiros alimentarem contexto ou conhecimento.

</details>

---

### D08 — Os dados poderão ser processados ou armazenados fora do Brasil?

**Orientação:** Responda Sim quando houver transferência ou processamento internacional.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário; perguntas adicionais aparecem quando há dados protegidos ou compartilhamento externo.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Responda Sim quando houver transferência ou processamento internacional. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Os dados poderão ser processados ou armazenados fora do Brasil. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Responda Sim quando houver transferência ou processamento internacional. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Caracteriza dados e privacidade. Pode alterar impacto, selecionar controles de proteção, retenção, inspeção e exclusão.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Inventário de dados, fluxo de dados, classificação, amostras mascaradas, política de retenção ou configuração de DLP.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.
- MTR1-B003-S01 — BAS-003, 1. Fontes, ingestão e elegibilidade: Quando fontes, uploads, conectores, APIs, Internet ou terceiros alimentarem contexto ou conhecimento.

</details>

---

### D09 — Os dados serão reduzidos ou protegidos antes de entrar na IA?

**Orientação:** Ex.: remover campos desnecessários, ocultar nomes, mascarar números, tokenizar ou anonimizar.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário; perguntas adicionais aparecem quando há dados protegidos ou compartilhamento externo.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: remover campos desnecessários, ocultar nomes, mascarar números, tokenizar ou anonimizar. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Os dados serão reduzidos ou protegidos antes de entrar na IA. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: remover campos desnecessários, ocultar nomes, mascarar números, tokenizar ou anonimizar. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Caracteriza dados e privacidade. Pode alterar impacto, selecionar controles de proteção, retenção, inspeção e exclusão.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Inventário de dados, fluxo de dados, classificação, amostras mascaradas, política de retenção ou configuração de DLP.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.

</details>

---

### D10 — Existe prazo para apagar prompts, respostas, anexos, memória e registros?

**Orientação:** Informe se há regras de retenção e exclusão automática.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário; perguntas adicionais aparecem quando há dados protegidos ou compartilhamento externo.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Informe se há regras de retenção e exclusão automática. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Existe prazo para apagar prompts, respostas, anexos, memória e registros. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Informe se há regras de retenção e exclusão automática. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Caracteriza dados e privacidade. Pode alterar impacto, selecionar controles de proteção, retenção, inspeção e exclusão.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Inventário de dados, fluxo de dados, classificação, amostras mascaradas, política de retenção ou configuração de DLP.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.
- MTR1-B003-S08 — BAS-003, 8. Retenção, exclusão, sincronização e recuperação: Quando dados, índices, embeddings, memória ou derivados forem persistidos e precisarem ser excluídos ou restaurados.

</details>

---

### D11 — Quando o dado original for apagado, suas cópias e derivados também serão removidos?

**Orientação:** Inclui índices, embeddings, memória, cache e dados derivados.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário; perguntas adicionais aparecem quando há dados protegidos ou compartilhamento externo.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Inclui índices, embeddings, memória, cache e dados derivados. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Quando o dado original for apagado, suas cópias e derivados também serão removidos. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclui índices, embeddings, memória, cache e dados derivados. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Caracteriza dados e privacidade. Pode alterar impacto, selecionar controles de proteção, retenção, inspeção e exclusão.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Inventário de dados, fluxo de dados, classificação, amostras mascaradas, política de retenção ou configuração de DLP.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.
- MTR1-B003-S08 — BAS-003, 8. Retenção, exclusão, sincronização e recuperação: Quando dados, índices, embeddings, memória ou derivados forem persistidos e precisarem ser excluídos ou restaurados.

</details>

---

### D12 — Existe verificação automática para impedir envio ou saída indevida de dados?

**Orientação:** Ex.: DLP ou ferramenta que identifica dados pessoais, bancários, segredos e informações restritas.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário; perguntas adicionais aparecem quando há dados protegidos ou compartilhamento externo.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: DLP ou ferramenta que identifica dados pessoais, bancários, segredos e informações restritas. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Existe verificação automática para impedir envio ou saída indevida de dados. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: DLP ou ferramenta que identifica dados pessoais, bancários, segredos e informações restritas. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Caracteriza dados e privacidade. Pode alterar impacto, selecionar controles de proteção, retenção, inspeção e exclusão.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Inventário de dados, fluxo de dados, classificação, amostras mascaradas, política de retenção ou configuração de DLP.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.
- MTR1-B002-S05 — BAS-002, 5. Entrada, prompt e payload: Quando entradas, prompts, anexos, parâmetros ou conteúdo não confiável forem aceitos.
- MTR1-B006-S05 — BAS-006, 5. Detecções técnicas de segurança para IA: Quando forem necessárias detecções de vazamento, prompt injection, abuso agentic, poisoning, shadow AI ou MCP desconhecido.

</details>

---

## 5. Usuários, exposição e impacto de negócio

### E01 — Quem usará a solução ou poderá ser afetado por ela?

**Orientação:** Marque usuários diretos e pessoas que podem sofrer efeito de decisões ou respostas.

**Tipo de resposta:** Múltipla escolha

**Condição de exibição:** Exibida após definir o cenário de uso.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Marque quem usa diretamente e quem pode sofrer efeitos da solução, mesmo sem interagir com ela.

1. Leia todas as opções antes de responder.
2. Marque cada alternativa que possa ocorrer no cenário real ou planejado.
3. Revise se existem opções complementares; escolhas múltiplas são cumulativas.
4. Não marque opções apenas por possibilidade remota sem previsão de uso.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Colaboradores | Empregados ou usuários internos utilizarão diretamente a solução. | Analistas utilizando um assistente interno. | Mantém o cenário interno, sem excluir impactos de dados, privilégios ou escala. |
| Terceiros | Prestadores, consultores ou usuários externos contratados utilizarão ou serão afetados. | Consultoria com acesso ao copiloto corporativo. | Pode elevar impacto de cliente/regulatório para pelo menos I2 e exigir segregação e controle de acesso. |
| Parceiros | Empresas parceiras ou integrantes do ecossistema utilizarão ou receberão resultados. | Parceiro comercial consumindo uma API de recomendação. | Ativa o fator de exposição F2 e controles para acesso e comunicação externa. |
| Clientes | Clientes da organização usarão a solução ou serão afetados por suas respostas ou decisões. | Chatbot no aplicativo bancário ou análise que influencia limite de cliente. | Eleva a classe para H4, pode elevar impacto para I3 e ativa o fator F2. |
| Público geral | A solução estará disponível ou produzirá efeitos para pessoas sem vínculo prévio com a organização. | Assistente disponível em site público. | Eleva a classe para H4 e ativa exposição externa e o fator F2. |
| Outros sistemas ou processos automáticos | Outros sistemas consumirão respostas ou ações sem interação humana direta. | Um serviço backend utiliza a classificação da IA para encaminhar transações. | Ativa controles de identidade de workload, integração, validação e contenção. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Colaboradores + Terceiros”, quando recrutadores usam a solução e candidatos são afetados.

**Evite:**

- Marcar todas as opções por precaução ou escolher apenas uma quando várias são verdadeiras.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Clientes ou público geral elevam o rigor para H4; clientes podem elevar impacto de negócio para I3; parceiros, clientes ou público ativam o fator F2 de probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B002-S07 — BAS-002, 7. Exposição, sessão e abuso: Quando houver Internet, clientes, público, muitos usuários, sessão, streaming, custo ou risco de abuso.

</details>

---

### E02 — A solução ficará acessível pela Internet ou por canal externo?

**Orientação:** Ex.: site, aplicativo, API externa, chatbot de cliente ou dispositivo público.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário de uso.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Ex.: site, aplicativo, API externa, chatbot de cliente ou dispositivo público. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A solução ficará acessível pela Internet ou por canal externo. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: site, aplicativo, API externa, chatbot de cliente ou dispositivo público. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” eleva o rigor para H4, ativa F1 e F2, estabelece piso P3 e seleciona controles de exposição externa e gateway.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-L2
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002 — BAS-002: Aplicação, API, gateway, proxy, broker, roteamento, integração com provider ou exposição de capacidade de IA.
- MTR1-B002-L2
- MTR1-B002-S01 — BAS-002, 1. Arquitetura de integração e fronteiras: Quando houver consumo, intermediação, roteamento ou exposição de serviço de IA.
- MTR1-B002-S05 — BAS-002, 5. Entrada, prompt e payload: Quando entradas, prompts, anexos, parâmetros ou conteúdo não confiável forem aceitos.
- MTR1-B002-S07 — BAS-002, 7. Exposição, sessão e abuso: Quando houver Internet, clientes, público, muitos usuários, sessão, streaming, custo ou risco de abuso.
- MTR1-B006-L2

</details>

---

### E03 — A IA produzirá conteúdo que será enviado para fora da organização?

**Orientação:** Ex.: resposta a cliente, publicação, e-mail, parecer ou conteúdo público.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário de uso.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Ex.: resposta a cliente, publicação, e-mail, parecer ou conteúdo público. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A IA produzirá conteúdo que será enviado para fora da organização. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: resposta a cliente, publicação, e-mail, parecer ou conteúdo público. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” eleva o impacto de cliente/regulatório e seleciona controles de validação e proteção de saída.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.
- MTR1-B002-S06 — BAS-002, 6. Saída e uso downstream: Quando outputs forem exibidos, persistidos, usados em decisões ou encaminhados a sistemas downstream.
- MTR1-B002-S07 — BAS-002, 7. Exposição, sessão e abuso: Quando houver Internet, clientes, público, muitos usuários, sessão, streaming, custo ou risco de abuso.

</details>

---

### E04 — A IA ajudará a decidir algo importante sobre uma pessoa ou empresa?

**Orientação:** Ex.: contratação, promoção, bloqueio, atendimento, elegibilidade, limite ou aprovação.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário de uso.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Ex.: contratação, promoção, bloqueio, atendimento, elegibilidade, limite ou aprovação. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A IA ajudará a decidir algo importante sobre uma pessoa ou empresa. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: contratação, promoção, bloqueio, atendimento, elegibilidade, limite ou aprovação. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” eleva o rigor para H4, impacto de cliente e segurança para pelo menos I3, ativa F4 e perguntas de revisão/contestação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-L2
- MTR1-B002-S06 — BAS-002, 6. Saída e uso downstream: Quando outputs forem exibidos, persistidos, usados em decisões ou encaminhados a sistemas downstream.
- MTR1-B002-S07 — BAS-002, 7. Exposição, sessão e abuso: Quando houver Internet, clientes, público, muitos usuários, sessão, streaming, custo ou risco de abuso.
- MTR1-B003-L2

</details>

---

### E05 — A IA poderá afetar dinheiro, crédito, fraude, pagamento, investimento ou autenticação?

**Orientação:** Marque Sim mesmo quando a IA apenas recomenda e outra pessoa confirma.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário de uso.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Marque Sim mesmo quando a IA apenas recomenda e outra pessoa confirma. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A IA poderá afetar dinheiro, crédito, fraude, pagamento, investimento ou autenticação. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Marque Sim mesmo quando a IA apenas recomenda e outra pessoa confirma. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” eleva o rigor para H4, impacto de cliente/financeiro para I4 e ativa F4. Sem fallback adequado pode gerar piso P3.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-L2
- MTR1-B002-L2
- MTR1-B002-S06 — BAS-002, 6. Saída e uso downstream: Quando outputs forem exibidos, persistidos, usados em decisões ou encaminhados a sistemas downstream.
- MTR1-B002-S07 — BAS-002, 7. Exposição, sessão e abuso: Quando houver Internet, clientes, público, muitos usuários, sessão, streaming, custo ou risco de abuso.
- MTR1-B004-L2
- MTR1-B006-L2

</details>

---

### E06 — A solução participa de processo crítico ou obrigatório?

**Orientação:** Ex.: sistema core, canal essencial, fechamento, operação regulatória ou serviço que não pode parar.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário de uso.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Ex.: sistema core, canal essencial, fechamento, operação regulatória ou serviço que não pode parar. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A solução participa de processo crítico ou obrigatório. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: sistema core, canal essencial, fechamento, operação regulatória ou serviço que não pode parar. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” eleva o rigor para H4, impacto de cliente e operação para I4 e amplia requisitos de continuidade, telemetria e contenção.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-L2
- MTR1-B002-L2
- MTR1-B002-S07 — BAS-002, 7. Exposição, sessão e abuso: Quando houver Internet, clientes, público, muitos usuários, sessão, streaming, custo ou risco de abuso.
- MTR1-B003-L2
- MTR1-B004-L2
- MTR1-B005-L2
- MTR1-B006-L2

</details>

---

### E07 — Um erro poderia afetar muitas pessoas, transações ou processos de uma vez?

**Orientação:** Considere escala, automação e possibilidade de propagação.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário de uso.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Considere escala, automação e possibilidade de propagação. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Um erro poderia afetar muitas pessoas, transações ou processos de uma vez. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Considere escala, automação e possibilidade de propagação. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” pode elevar impacto de cliente e operação para I3 e ativa F2 por escala.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 9.2 — BAS-002: integração e exposição; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B002-L2
- MTR1-B002-S07 — BAS-002, 7. Exposição, sessão e abuso: Quando houver Internet, clientes, público, muitos usuários, sessão, streaming, custo ou risco de abuso.
- MTR1-B006-L2
- MTR1-B006-S06 — BAS-006, 6. Anomalias de comportamento, custo e desempenho: Quando volume, custo, tokens, loops, drift, falha, latência ou saturação precisarem ser monitorados.

</details>

---

### E08 — Uma pessoa revisa decisões ou ações de alto impacto antes de serem executadas?

**Orientação:** A revisão deve acontecer antes do efeito e permitir impedir a ação.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando a IA participa de decisão ou ação material.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. A revisão deve acontecer antes do efeito e permitir impedir a ação. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Uma pessoa revisa decisões ou ações de alto impacto antes de serem executadas. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. A revisão deve acontecer antes do efeito e permitir impedir a ação. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Caracteriza usuários, exposição e consequências. Pode alterar H1–H4, impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### E09 — A pessoa afetada consegue contestar e corrigir a decisão?

**Orientação:** Considere recurso, revisão, correção e reversão.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando a IA participa de decisão ou ação material.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Considere recurso, revisão, correção e reversão. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A pessoa afetada consegue contestar e corrigir a decisão. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Considere recurso, revisão, correção e reversão. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Caracteriza usuários, exposição e consequências. Pode alterar H1–H4, impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

### E10 — Existe uma alternativa humana ou manual quando a IA falhar?

**Orientação:** Ex.: atendimento humano, processo manual ou outro sistema seguro.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida após definir o cenário de uso.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: atendimento humano, processo manual ou outro sistema seguro. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Existe uma alternativa humana ou manual quando a IA falhar. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: atendimento humano, processo manual ou outro sistema seguro. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Caracteriza usuários, exposição e consequências. Pode alterar H1–H4, impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S07 — BAS-001, 7. Resiliência e recuperação: Quando houver dependência operacional, serviço produtivo, ação material ou necessidade de recuperação e desativação.
- MTR1-B002-S08 — BAS-002, 8. Resiliência e comportamento de falha: Quando a integração exigir timeout, retry, fallback, circuit breaker, fail-closed ou continuidade.
- MTR1-B006-S08 — BAS-006, 8. Recuperação, continuidade e desativação técnica: Quando houver requisito de backup, restauração, redundância, recuperação, plano de saída ou desativação segura.

</details>

---

### E11 — Uma ação errada pode ser desfeita no tempo necessário?

**Orientação:** Considere estorno, cancelamento, restauração ou correção.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando a IA participa de decisão ou ação material.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Considere estorno, cancelamento, restauração ou correção. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Uma ação errada pode ser desfeita no tempo necessário. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Considere estorno, cancelamento, restauração ou correção. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Caracteriza usuários, exposição e consequências. Pode alterar H1–H4, impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle

**Regras vinculadas:**

- MTR1-B001-S07 — BAS-001, 7. Resiliência e recuperação: Quando houver dependência operacional, serviço produtivo, ação material ou necessidade de recuperação e desativação.
- MTR1-B002-S08 — BAS-002, 8. Resiliência e comportamento de falha: Quando a integração exigir timeout, retry, fallback, circuit breaker, fail-closed ou continuidade.

</details>

---

### E12 — O que pode acontecer se a solução errar, for abusada, parar ou vazar dados?

**Orientação:** Descreva consequências reais para pessoas, dinheiro, operação, segurança e reputação.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Exibida após definir o cenário de uso.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Descreva consequências concretas e plausíveis. Considere erro, abuso, indisponibilidade, vazamento, viés e execução indevida.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Classificação incorreta pode excluir candidato; vazamento pode expor currículo; indisponibilidade pode atrasar contratação.”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Caracteriza usuários, exposição e consequências. Pode alterar H1–H4, impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Descrição do processo, jornada do usuário, análise de impacto, regras de decisão, fallback e procedimento de contestação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Cálculo do impacto; § 9 — Cálculo da probabilidade
- MTR-001 v1.0 — § 6 Fluxo de decisão; § 10 Regra individual de controle

**Regras vinculadas:**

- Sem regra individual; utilizada para contexto, rastreabilidade, parecer ou cálculo metodológico.

</details>

---

## 6. Arquitetura, integração, identidade e acesso

### F01 — As chamadas de IA passam por um ponto corporativo de controle?

**Orientação:** Ex.: gateway, proxy ou broker que aplica autenticação, regras, filtros e registros.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há provider, terceiro, integração ou exposição externa.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: gateway, proxy ou broker que aplica autenticação, regras, filtros e registros. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: As chamadas de IA passam por um ponto corporativo de controle. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: gateway, proxy ou broker que aplica autenticação, regras, filtros e registros. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Em exposição externa, resposta diferente de “Sim” pode gerar condição bloqueante por ausência de gateway ou ponto de enforcement.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-S01 — BAS-001, 1. Arquitetura e configuração segura: Sempre que houver componente, deployment, endpoint, runtime, gateway ou ambiente de IA.
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002 — BAS-002: Aplicação, API, gateway, proxy, broker, roteamento, integração com provider ou exposição de capacidade de IA.
- MTR1-B002-S01 — BAS-002, 1. Arquitetura de integração e fronteiras: Quando houver consumo, intermediação, roteamento ou exposição de serviço de IA.
- MTR1-B002-S04 — BAS-002, 4. Roteamento, modelos e policies: Quando houver escolha de provider/modelo, aliases, rotas, fallback ou policies de gateway.

</details>

---

### F02 — Algum usuário ou sistema se conecta diretamente ao provedor de IA?

**Orientação:** Conexão direta pode contornar controles centralizados.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há provider, terceiro, integração ou exposição externa.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Conexão direta pode contornar controles centralizados. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Algum usuário ou sistema se conecta diretamente ao provedor de IA. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Conexão direta pode contornar controles centralizados. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina aplicabilidade e evidência de controles de arquitetura, identidade, integração e acesso. Lacunas críticas podem bloquear a aprovação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-S01 — BAS-001, 1. Arquitetura e configuração segura: Sempre que houver componente, deployment, endpoint, runtime, gateway ou ambiente de IA.
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002 — BAS-002: Aplicação, API, gateway, proxy, broker, roteamento, integração com provider ou exposição de capacidade de IA.
- MTR1-B002-S01 — BAS-002, 1. Arquitetura de integração e fronteiras: Quando houver consumo, intermediação, roteamento ou exposição de serviço de IA.
- MTR1-B002-S04 — BAS-002, 4. Roteamento, modelos e policies: Quando houver escolha de provider/modelo, aliases, rotas, fallback ou policies de gateway.

</details>

---

### F03 — Usuários, sistemas e administradores precisam se identificar e ter permissão?

**Orientação:** Responda Sim quando autenticação e autorização forem aplicadas.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando existe cenário técnico a avaliar; algumas perguntas dependem de exposição, privilégio ou integração.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Responda Sim quando autenticação e autorização forem aplicadas. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Usuários, sistemas e administradores precisam se identificar e ter permissão. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Responda Sim quando autenticação e autorização forem aplicadas. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina aplicabilidade e evidência de controles de arquitetura, identidade, integração e acesso. Lacunas críticas podem bloquear a aprovação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-S02 — BAS-001, 2. Identidade, acesso e segredos: Quando houver usuário, workload, conta administrativa, credencial, segredo ou acesso a recurso de IA.
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002-S02 — BAS-002, 2. Autenticação e identidade: Quando usuários, workloads ou clientes acessarem aplicação, API, gateway ou provider.

</details>

---

### F04 — Cada sistema usa uma identidade técnica própria?

**Orientação:** Evite contas ou chaves compartilhadas entre aplicações.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando existe cenário técnico a avaliar; algumas perguntas dependem de exposição, privilégio ou integração.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Evite contas ou chaves compartilhadas entre aplicações. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Cada sistema usa uma identidade técnica própria. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Evite contas ou chaves compartilhadas entre aplicações. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina aplicabilidade e evidência de controles de arquitetura, identidade, integração e acesso. Lacunas críticas podem bloquear a aprovação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-S02 — BAS-001, 2. Identidade, acesso e segredos: Quando houver usuário, workload, conta administrativa, credencial, segredo ou acesso a recurso de IA.
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002-S02 — BAS-002, 2. Autenticação e identidade: Quando usuários, workloads ou clientes acessarem aplicação, API, gateway ou provider.
- MTR1-B004-S01 — BAS-004, 1. Identidades agentic e contexto de execução: Quando existir agente, worker, executor ou ação realizada em nome de usuário ou workload.

</details>

---

### F05 — É possível saber qual pessoa originou uma ação realizada pela IA?

**Orientação:** A identidade deve acompanhar a execução até o sistema final.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida para agente, automação ou decisão/ação material.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. A identidade deve acompanhar a execução até o sistema final. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: É possível saber qual pessoa originou uma ação realizada pela IA. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. A identidade deve acompanhar a execução até o sistema final. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina aplicabilidade e evidência de controles de arquitetura, identidade, integração e acesso. Lacunas críticas podem bloquear a aprovação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-S02 — BAS-001, 2. Identidade, acesso e segredos: Quando houver usuário, workload, conta administrativa, credencial, segredo ou acesso a recurso de IA.
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002-S02 — BAS-002, 2. Autenticação e identidade: Quando usuários, workloads ou clientes acessarem aplicação, API, gateway ou provider.
- MTR1-B004-S01 — BAS-004, 1. Identidades agentic e contexto de execução: Quando existir agente, worker, executor ou ação realizada em nome de usuário ou workload.
- MTR1-B006-S02 — BAS-006, 2. Correlação e contexto ponta a ponta: Quando o fluxo atravessar aplicação, gateway, provider, RAG, agente, tool, fila ou sistema downstream.

</details>

---

### F06 — Senhas, tokens e chaves ficam em cofre seguro e com acesso mínimo?

**Orientação:** Ex.: secret manager ou vault, com credenciais temporárias quando possível.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando existe cenário técnico a avaliar; algumas perguntas dependem de exposição, privilégio ou integração.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: secret manager ou vault, com credenciais temporárias quando possível. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Senhas, tokens e chaves ficam em cofre seguro e com acesso mínimo. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: secret manager ou vault, com credenciais temporárias quando possível. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina aplicabilidade e evidência de controles de arquitetura, identidade, integração e acesso. Lacunas críticas podem bloquear a aprovação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-S02 — BAS-001, 2. Identidade, acesso e segredos: Quando houver usuário, workload, conta administrativa, credencial, segredo ou acesso a recurso de IA.
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.

</details>

---

### F07 — Desenvolvimento, teste, homologação e produção estão separados?

**Orientação:** Considere rede, dados, credenciais, contas e permissões.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando mais de um ambiente foi selecionado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Marque “Sim” apenas quando os ambientes têm contas, redes, credenciais, dados e permissões segregados de forma verificável.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Considere rede, dados, credenciais, contas e permissões. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Desenvolvimento, teste, homologação e produção estão separados. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Considere rede, dados, credenciais, contas e permissões. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Assinaturas e redes separadas para dev, homologação e produção; credenciais não são reutilizadas.”

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina aplicabilidade e evidência de controles de arquitetura, identidade, integração e acesso. Lacunas críticas podem bloquear a aprovação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-S01 — BAS-001, 1. Arquitetura e configuração segura: Sempre que houver componente, deployment, endpoint, runtime, gateway ou ambiente de IA.
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002-S01 — BAS-002, 1. Arquitetura de integração e fronteiras: Quando houver consumo, intermediação, roteamento ou exposição de serviço de IA.

</details>

---

### F08 — Textos, parâmetros e arquivos são verificados antes do processamento?

**Orientação:** Ex.: formato, tamanho, conteúdo malicioso e valores inválidos.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando existe cenário técnico a avaliar; algumas perguntas dependem de exposição, privilégio ou integração.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: formato, tamanho, conteúdo malicioso e valores inválidos. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Textos, parâmetros e arquivos são verificados antes do processamento. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: formato, tamanho, conteúdo malicioso e valores inválidos. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina aplicabilidade e evidência de controles de arquitetura, identidade, integração e acesso. Lacunas críticas podem bloquear a aprovação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002-S05 — BAS-002, 5. Entrada, prompt e payload: Quando entradas, prompts, anexos, parâmetros ou conteúdo não confiável forem aceitos.

</details>

---

### F09 — As respostas da IA são verificadas antes de serem exibidas ou usadas por outro sistema?

**Orientação:** Inclua validação de conteúdo, formato, código, links e resultados de ferramentas.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando existe cenário técnico a avaliar; algumas perguntas dependem de exposição, privilégio ou integração.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Inclua validação de conteúdo, formato, código, links e resultados de ferramentas. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: As respostas da IA são verificadas antes de serem exibidas ou usadas por outro sistema. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclua validação de conteúdo, formato, código, links e resultados de ferramentas. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina aplicabilidade e evidência de controles de arquitetura, identidade, integração e acesso. Lacunas críticas podem bloquear a aprovação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002-S06 — BAS-002, 6. Saída e uso downstream: Quando outputs forem exibidos, persistidos, usados em decisões ou encaminhados a sistemas downstream.

</details>

---

### F10 — A solução só consegue se comunicar com destinos realmente necessários?

**Orientação:** Ex.: lista permitida de endereços e bloqueio de conexões desnecessárias.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há provider, terceiro, integração ou exposição externa.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: lista permitida de endereços e bloqueio de conexões desnecessárias. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A solução só consegue se comunicar com destinos realmente necessários. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: lista permitida de endereços e bloqueio de conexões desnecessárias. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina aplicabilidade e evidência de controles de arquitetura, identidade, integração e acesso. Lacunas críticas podem bloquear a aprovação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-S01 — BAS-001, 1. Arquitetura e configuração segura: Sempre que houver componente, deployment, endpoint, runtime, gateway ou ambiente de IA.
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002-S01 — BAS-002, 1. Arquitetura de integração e fronteiras: Quando houver consumo, intermediação, roteamento ou exposição de serviço de IA.

</details>

---

### F11 — Vários clientes ou usuários compartilham infraestrutura, memória ou dados?

**Orientação:** Marque Sim para solução multi-tenant ou recursos compartilhados.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando existe cenário técnico a avaliar; algumas perguntas dependem de exposição, privilégio ou integração.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Marque Sim para solução multi-tenant ou recursos compartilhados. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Vários clientes ou usuários compartilham infraestrutura, memória ou dados. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Marque Sim para solução multi-tenant ou recursos compartilhados. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina aplicabilidade e evidência de controles de arquitetura, identidade, integração e acesso. Lacunas críticas podem bloquear a aprovação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-L2
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002-L2
- MTR1-B002-S03 — BAS-002, 3. Autorização e segregação: Quando houver múltiplos usuários, tenants, ambientes, privilégios, recursos ou políticas de autorização.
- MTR1-B002-S07 — BAS-002, 7. Exposição, sessão e abuso: Quando houver Internet, clientes, público, muitos usuários, sessão, streaming, custo ou risco de abuso.
- MTR1-B003-S04 — BAS-003, 4. Autorização, segregação e recuperação permitida: Quando dados ou documentos possuírem escopo por usuário, grupo, tenant, classificação ou autorização.

</details>

---

### F12 — Existem telas administrativas ou acessos com alto privilégio?

**Orientação:** Ex.: administração, alteração de regras, acesso a dados críticos ou execução privilegiada.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando existe cenário técnico a avaliar; algumas perguntas dependem de exposição, privilégio ou integração.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: administração, alteração de regras, acesso a dados críticos ou execução privilegiada. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Existem telas administrativas ou acessos com alto privilégio. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: administração, alteração de regras, acesso a dados críticos ou execução privilegiada. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” ou “Não sei” eleva o rigor para H4, impacto Segurança e autonomia para I4 e ativa F4 por privilégio relevante.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-L2
- MTR1-B001-S02 — BAS-001, 2. Identidade, acesso e segredos: Quando houver usuário, workload, conta administrativa, credencial, segredo ou acesso a recurso de IA.
- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002-L2
- MTR1-B002-S03 — BAS-002, 3. Autorização e segregação: Quando houver múltiplos usuários, tenants, ambientes, privilégios, recursos ou políticas de autorização.
- MTR1-B004-L2

</details>

---

### F13 — Quando uma verificação de segurança falha, a operação é bloqueada?

**Orientação:** Falha fechada significa negar a ação em vez de continuar sem proteção.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando existe cenário técnico a avaliar; algumas perguntas dependem de exposição, privilégio ou integração.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Falha fechada significa negar a ação em vez de continuar sem proteção. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Quando uma verificação de segurança falha, a operação é bloqueada. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Falha fechada significa negar a ação em vez de continuar sem proteção. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina aplicabilidade e evidência de controles de arquitetura, identidade, integração e acesso. Lacunas críticas podem bloquear a aprovação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Diagrama, configuração de gateway, IAM, rede, secrets, policy, teste negativo ou exportação de configuração.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos baselines e controles; § 12 — Avaliação dos controles; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-001 — Controles Técnicos Transversais
- BAS-002 — Integração e Exposição

**Regras vinculadas:**

- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B002-S03 — BAS-002, 3. Autorização e segregação: Quando houver múltiplos usuários, tenants, ambientes, privilégios, recursos ou políticas de autorização.
- MTR1-B002-S08 — BAS-002, 8. Resiliência e comportamento de falha: Quando a integração exigir timeout, retry, fallback, circuit breaker, fail-closed ou continuidade.
- MTR1-B006-S07 — BAS-006, 7. Contenção técnica e comportamento seguro: Quando a solução exigir kill switch, bloqueio individual, circuit breaker, retries limitados, revogação ou fallback seguro.

</details>

---

## 7. RAG, memória e bases de conhecimento — preencher quando aplicável

### G01 — A solução consulta documentos ou uma base de conhecimento para responder?

**Orientação:** Isso inclui RAG, busca semântica, embeddings, vector store ou memória recuperável.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando o cenário RAG/base de conhecimento foi selecionado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Isso inclui RAG, busca semântica, embeddings, vector store ou memória recuperável. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A solução consulta documentos ou uma base de conhecimento para responder. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Isso inclui RAG, busca semântica, embeddings, vector store ou memória recuperável. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” ou “Não sei” ativa o bloco RAG, BAS-003 e controles de fontes, ingestão, autorização, memória e recuperação.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Manifesto de fontes, ACLs, configuração de ingestão, índices, testes de retrieval, lineage ou logs de recuperação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle
- BAS-003 — Dados, Contexto e Conhecimento

**Regras vinculadas:**

- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B003 — BAS-003: RAG, embeddings, vector store, memória, cache semântico, base de conhecimento, ingestão ou recuperação de contexto.
- MTR1-B003-S03 — BAS-003, 3. Embeddings, índices e armazenamento: Quando houver embeddings, índices, vector stores, caches, memória ou armazenamento de derivados.

</details>

---

### G02 — De onde vêm os documentos e informações consultados?

**Orientação:** Marque todas as fontes que podem alimentar a base.

**Tipo de resposta:** Múltipla escolha

**Condição de exibição:** Exibida somente quando o projeto possui RAG ou base de conhecimento e G01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Marque todas as origens que podem alimentar o RAG ou a memória, incluindo uploads, Internet, e-mail, SharePoint, bancos e APIs.

1. Leia todas as opções antes de responder.
2. Marque cada alternativa que possa ocorrer no cenário real ou planejado.
3. Revise se existem opções complementares; escolhas múltiplas são cumulativas.
4. Não marque opções apenas por possibilidade remota sem previsão de uso.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Repositórios internos | Documentos ou dados vêm de fontes corporativas controladas. | SharePoint, GED, wiki ou banco interno. | Ativa controles de autorização, linhagem, exclusão e atualização das fontes. |
| Upload de usuário | Usuários podem enviar arquivos ou conteúdo para ingestão ou consulta. | Usuário envia PDF para o assistente resumir. | Ativa F1 e controles de validação de tipo, malware, conteúdo ativo e instruções adversariais. |
| E-mail/chat | Mensagens e anexos de e-mail ou colaboração alimentam a solução. | Assistente consulta caixa de e-mail ou conversas do Teams. | Ativa controles de dados, identidade, autorização e conteúdo não confiável conforme a origem. |
| APIs | Dados são obtidos dinamicamente de sistemas por interfaces programáticas. | Consulta a CRM, cadastro ou sistema financeiro por API. | Ativa controles de integração, autenticação, autorização, validação e rastreabilidade. |
| Internet | Conteúdo público externo é coletado ou recuperado da Internet. | Crawler consulta sites públicos para compor respostas. | Ativa F1 e piso mínimo P3 por fonte não confiável, além de controles contra poisoning e instruções adversariais. |
| Terceiros | A fonte é mantida por fornecedor, parceiro ou organização externa. | Base documental fornecida por parceiro. | Ativa F1 e controles de integridade, autorização, contrato e proveniência. |
| Outras | A solução usa fonte diferente das categorias anteriores. | Sensor, fila de eventos ou base legada não classificada acima. | Mantém a fonte no escopo e exige descrição e revisão de seus riscos específicos. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “SharePoint corporativo + upload do usuário”
- “Internet + base interna de procedimentos”

**Evite:**

- Marcar todas as opções por precaução ou escolher apenas uma quando várias são verdadeiras.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Internet, upload de usuário ou terceiros ativam F1. Internet também estabelece piso mínimo P3.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Manifesto de fontes, ACLs, configuração de ingestão, índices, testes de retrieval, lineage ou logs de recuperação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle
- BAS-003 — Dados, Contexto e Conhecimento

**Regras vinculadas:**

- MTR1-B003 — BAS-003: RAG, embeddings, vector store, memória, cache semântico, base de conhecimento, ingestão ou recuperação de contexto.
- MTR1-B003-S01 — BAS-003, 1. Fontes, ingestão e elegibilidade: Quando fontes, uploads, conectores, APIs, Internet ou terceiros alimentarem contexto ou conhecimento.

</details>

---

### G03 — A base recebe conteúdo da Internet, de usuários ou de fonte não confiável?

**Orientação:** Essas fontes podem conter instruções maliciosas ou informações falsas.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o projeto possui RAG ou base de conhecimento e G01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Essas fontes podem conter instruções maliciosas ou informações falsas. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A base recebe conteúdo da Internet, de usuários ou de fonte não confiável. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Essas fontes podem conter instruções maliciosas ou informações falsas. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” ativa F1 e piso P3 por conteúdo não confiável capaz de influenciar o RAG.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Manifesto de fontes, ACLs, configuração de ingestão, índices, testes de retrieval, lineage ou logs de recuperação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.2 — BAS-002: integração e exposição; § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-003 — Dados, Contexto e Conhecimento

**Regras vinculadas:**

- MTR1-B002-S05 — BAS-002, 5. Entrada, prompt e payload: Quando entradas, prompts, anexos, parâmetros ou conteúdo não confiável forem aceitos.
- MTR1-B003 — BAS-003: RAG, embeddings, vector store, memória, cache semântico, base de conhecimento, ingestão ou recuperação de contexto.
- MTR1-B003-L2
- MTR1-B003-S01 — BAS-003, 1. Fontes, ingestão e elegibilidade: Quando fontes, uploads, conectores, APIs, Internet ou terceiros alimentarem contexto ou conhecimento.
- MTR1-B003-S06 — BAS-003, 6. Proteção contra poisoning e conteúdo adversarial: Quando fontes externas, uploads ou conteúdo não confiável puderem influenciar ingestão ou recuperação.
- MTR1-B004-S05 — BAS-004, 5. Proteção contra instruções e capabilities adversariais: Quando conteúdo não confiável puder influenciar planejamento, seleção de tool, capability ou instrução do agente.

</details>

---

### G04 — É possível identificar a origem e a versão de cada documento?

**Orientação:** A solução deve registrar fonte, versão, integridade e classificação.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o projeto possui RAG ou base de conhecimento e G01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. A solução deve registrar fonte, versão, integridade e classificação. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: É possível identificar a origem e a versão de cada documento. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. A solução deve registrar fonte, versão, integridade e classificação. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de RAG, fontes, autorização, memória, integridade e recuperação. Algumas respostas também influenciam a probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Manifesto de fontes, ACLs, configuração de ingestão, índices, testes de retrieval, lineage ou logs de recuperação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle
- BAS-003 — Dados, Contexto e Conhecimento

**Regras vinculadas:**

- MTR1-B003-S01 — BAS-003, 1. Fontes, ingestão e elegibilidade: Quando fontes, uploads, conectores, APIs, Internet ou terceiros alimentarem contexto ou conhecimento.
- MTR1-B003-S02 — BAS-003, 2. Transformação, parsing e metadados: Quando houver parsing, chunking, normalização, enriquecimento, OCR ou geração de derivados.

</details>

---

### G05 — Arquivos e documentos são verificados antes de entrar na base?

**Orientação:** Ex.: tipo real, malware, conteúdo ativo e instruções maliciosas.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o projeto possui RAG ou base de conhecimento e G01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: tipo real, malware, conteúdo ativo e instruções maliciosas. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Arquivos e documentos são verificados antes de entrar na base. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: tipo real, malware, conteúdo ativo e instruções maliciosas. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de RAG, fontes, autorização, memória, integridade e recuperação. Algumas respostas também influenciam a probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Manifesto de fontes, ACLs, configuração de ingestão, índices, testes de retrieval, lineage ou logs de recuperação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle
- BAS-003 — Dados, Contexto e Conhecimento

**Regras vinculadas:**

- MTR1-B003-S01 — BAS-003, 1. Fontes, ingestão e elegibilidade: Quando fontes, uploads, conectores, APIs, Internet ou terceiros alimentarem contexto ou conhecimento.
- MTR1-B003-S02 — BAS-003, 2. Transformação, parsing e metadados: Quando houver parsing, chunking, normalização, enriquecimento, OCR ou geração de derivados.
- MTR1-B003-S06 — BAS-003, 6. Proteção contra poisoning e conteúdo adversarial: Quando fontes externas, uploads ou conteúdo não confiável puderem influenciar ingestão ou recuperação.

</details>

---

### G06 — A solução verifica a permissão do usuário antes de recuperar cada documento?

**Orientação:** O acesso deve valer também para trechos, índices e resultados da busca.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o projeto possui RAG ou base de conhecimento e G01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. O acesso deve valer também para trechos, índices e resultados da busca. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A solução verifica a permissão do usuário antes de recuperar cada documento. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. O acesso deve valer também para trechos, índices e resultados da busca. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de RAG, fontes, autorização, memória, integridade e recuperação. Algumas respostas também influenciam a probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Manifesto de fontes, ACLs, configuração de ingestão, índices, testes de retrieval, lineage ou logs de recuperação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle
- BAS-003 — Dados, Contexto e Conhecimento

**Regras vinculadas:**

- MTR1-B003-L2
- MTR1-B003-S04 — BAS-003, 4. Autorização, segregação e recuperação permitida: Quando dados ou documentos possuírem escopo por usuário, grupo, tenant, classificação ou autorização.
- MTR1-B003-S05 — BAS-003, 5. Retrieval, ranking e montagem de contexto: Quando o sistema recuperar, ranquear, filtrar ou montar contexto para o modelo.

</details>

---

### G07 — Dados, memória e índices ficam separados entre usuários e clientes?

**Orientação:** Evita que um usuário recupere conteúdo de outro.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o projeto possui RAG ou base de conhecimento e G01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Evita que um usuário recupere conteúdo de outro. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Dados, memória e índices ficam separados entre usuários e clientes. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Evita que um usuário recupere conteúdo de outro. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de RAG, fontes, autorização, memória, integridade e recuperação. Algumas respostas também influenciam a probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Manifesto de fontes, ACLs, configuração de ingestão, índices, testes de retrieval, lineage ou logs de recuperação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle
- BAS-003 — Dados, Contexto e Conhecimento

**Regras vinculadas:**

- MTR1-B003-L2
- MTR1-B003-S03 — BAS-003, 3. Embeddings, índices e armazenamento: Quando houver embeddings, índices, vector stores, caches, memória ou armazenamento de derivados.
- MTR1-B003-S04 — BAS-003, 4. Autorização, segregação e recuperação permitida: Quando dados ou documentos possuírem escopo por usuário, grupo, tenant, classificação ou autorização.
- MTR1-B003-S07 — BAS-003, 7. Memória, caches e dados derivados em execução: Quando houver memória persistente, cache semântico, estado conversacional ou compartilhamento de contexto.

</details>

---

### G08 — Quando um documento perde acesso ou é apagado, ele deixa de aparecer na IA?

**Orientação:** A alteração deve chegar aos índices, embeddings e cópias derivadas.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o projeto possui RAG ou base de conhecimento e G01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. A alteração deve chegar aos índices, embeddings e cópias derivadas. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Quando um documento perde acesso ou é apagado, ele deixa de aparecer na IA. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. A alteração deve chegar aos índices, embeddings e cópias derivadas. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de RAG, fontes, autorização, memória, integridade e recuperação. Algumas respostas também influenciam a probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Manifesto de fontes, ACLs, configuração de ingestão, índices, testes de retrieval, lineage ou logs de recuperação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.3 — BAS-003: dados, contexto e conhecimento; § 10 — Regra individual de controle
- BAS-003 — Dados, Contexto e Conhecimento

**Regras vinculadas:**

- MTR1-B003-S03 — BAS-003, 3. Embeddings, índices e armazenamento: Quando houver embeddings, índices, vector stores, caches, memória ou armazenamento de derivados.
- MTR1-B003-S08 — BAS-003, 8. Retenção, exclusão, sincronização e recuperação: Quando dados, índices, embeddings, memória ou derivados forem persistidos e precisarem ser excluídos ou restaurados.

</details>

---

### G09 — A memória da solução tem prazo, limite e separação por usuário?

**Orientação:** TTL é o tempo máximo de permanência da memória.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o projeto possui RAG ou base de conhecimento e G01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. TTL é o tempo máximo de permanência da memória. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A memória da solução tem prazo, limite e separação por usuário. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. TTL é o tempo máximo de permanência da memória. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de RAG, fontes, autorização, memória, integridade e recuperação. Algumas respostas também influenciam a probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Manifesto de fontes, ACLs, configuração de ingestão, índices, testes de retrieval, lineage ou logs de recuperação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-003 — Dados, Contexto e Conhecimento

**Regras vinculadas:**

- MTR1-B003-S03 — BAS-003, 3. Embeddings, índices e armazenamento: Quando houver embeddings, índices, vector stores, caches, memória ou armazenamento de derivados.
- MTR1-B003-S07 — BAS-003, 7. Memória, caches e dados derivados em execução: Quando houver memória persistente, cache semântico, estado conversacional ou compartilhamento de contexto.
- MTR1-B004-S07 — BAS-004, 7. Memória, delegação e comunicação entre agentes: Quando houver memória agentic, agentes secundários, delegação, comunicação multiagente ou contexto persistente.

</details>

---

### G10 — A resposta registra quais fontes foram realmente utilizadas?

**Orientação:** Isso permite auditoria, citação e investigação.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o projeto possui RAG ou base de conhecimento e G01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Isso permite auditoria, citação e investigação. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A resposta registra quais fontes foram realmente utilizadas. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Isso permite auditoria, citação e investigação. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de RAG, fontes, autorização, memória, integridade e recuperação. Algumas respostas também influenciam a probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Manifesto de fontes, ACLs, configuração de ingestão, índices, testes de retrieval, lineage ou logs de recuperação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-003 — Dados, Contexto e Conhecimento

**Regras vinculadas:**

- MTR1-B003-S02 — BAS-003, 2. Transformação, parsing e metadados: Quando houver parsing, chunking, normalização, enriquecimento, OCR ou geração de derivados.
- MTR1-B003-S05 — BAS-003, 5. Retrieval, ranking e montagem de contexto: Quando o sistema recuperar, ranquear, filtrar ou montar contexto para o modelo.
- MTR1-B006-S02 — BAS-006, 2. Correlação e contexto ponta a ponta: Quando o fluxo atravessar aplicação, gateway, provider, RAG, agente, tool, fila ou sistema downstream.

</details>

---

### G11 — Foram testados vazamento entre usuários, conteúdo malicioso e recuperação indevida?

**Orientação:** Inclui over-retrieval, cross-tenant, poisoning e relevância.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando o projeto possui RAG ou base de conhecimento e G01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Inclui over-retrieval, cross-tenant, poisoning e relevância. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Foram testados vazamento entre usuários, conteúdo malicioso e recuperação indevida. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclui over-retrieval, cross-tenant, poisoning e relevância. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de RAG, fontes, autorização, memória, integridade e recuperação. Algumas respostas também influenciam a probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Manifesto de fontes, ACLs, configuração de ingestão, índices, testes de retrieval, lineage ou logs de recuperação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-003 — Dados, Contexto e Conhecimento

**Regras vinculadas:**

- MTR1-B003-S05 — BAS-003, 5. Retrieval, ranking e montagem de contexto: Quando o sistema recuperar, ranquear, filtrar ou montar contexto para o modelo.
- MTR1-B003-S06 — BAS-003, 6. Proteção contra poisoning e conteúdo adversarial: Quando fontes externas, uploads ou conteúdo não confiável puderem influenciar ingestão ou recuperação.
- MTR1-B006-S05 — BAS-006, 5. Detecções técnicas de segurança para IA: Quando forem necessárias detecções de vazamento, prompt injection, abuso agentic, poisoning, shadow AI ou MCP desconhecido.

</details>

---

## 8. Agentes, tools, MCP e automações — preencher quando aplicável

### H01 — A IA executa tarefas ou chama ferramentas automaticamente?

**Orientação:** Ex.: agente, automação, function calling, plugin, action ou skill.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando o cenário Agente ou automação foi selecionado.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Ex.: agente, automação, function calling, plugin, action ou skill. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A IA executa tarefas ou chama ferramentas automaticamente. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: agente, automação, function calling, plugin, action ou skill. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” ou “Não sei” ativa o bloco agentic e o BAS-004.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B001-S05 — BAS-001, 5. Segurança de aplicação e integrações: Quando houver aplicação consumidora, API, integração, sessão, payload, gateway, RAG ou agente.
- MTR1-B003-L2
- MTR1-B004 — BAS-004: Agente, planner, executor, tool/function calling, plugin, action, skill, MCP, computer use ou automação acionada por IA.
- MTR1-B004-S01 — BAS-004, 1. Identidades agentic e contexto de execução: Quando existir agente, worker, executor ou ação realizada em nome de usuário ou workload.
- MTR1-B004-S02 — BAS-004, 2. Registro, integridade e schemas de tools: Quando houver tools, functions, actions, skills, plugins, capabilities, resources ou prompts MCP.
- MTR1-B004-S05 — BAS-004, 5. Proteção contra instruções e capabilities adversariais: Quando conteúdo não confiável puder influenciar planejamento, seleção de tool, capability ou instrução do agente.

</details>

---

### H02 — A solução usa MCP para conectar ferramentas ou fontes?

**Orientação:** MCP é um protocolo usado para conectar modelos a servidores, ferramentas, recursos e prompts.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. MCP é um protocolo usado para conectar modelos a servidores, ferramentas, recursos e prompts. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A solução usa MCP para conectar ferramentas ou fontes. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. MCP é um protocolo usado para conectar modelos a servidores, ferramentas, recursos e prompts. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” ou “Não sei” ativa somente os controles de clientes, servidores, registries, tools, resources e prompts MCP.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B004 — BAS-004: Agente, planner, executor, tool/function calling, plugin, action, skill, MCP, computer use ou automação acionada por IA.
- MTR1-B004-S02 — BAS-004, 2. Registro, integridade e schemas de tools: Quando houver tools, functions, actions, skills, plugins, capabilities, resources ou prompts MCP.
- MTR1-B004-S04 — BAS-004, 4. Segurança de clientes, servidores e registries MCP: Quando houver cliente, servidor, registry, discovery, resource ou prompt MCP.

</details>

---

### H03 — A IA controla navegador, computador, terminal ou executa código?

**Orientação:** Também chamado de computer use.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Também chamado de computer use. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A IA controla navegador, computador, terminal ou executa código. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Também chamado de computer use. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” ou “Não sei” eleva H4, Segurança e autonomia para I4, ativa F4, piso P3 e controles de sandbox/computer use.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B001-L2
- MTR1-B004 — BAS-004: Agente, planner, executor, tool/function calling, plugin, action, skill, MCP, computer use ou automação acionada por IA.
- MTR1-B004-L2
- MTR1-B004-S06 — BAS-004, 6. Sandbox, host, navegador e computer use: Quando houver execução de código, terminal, navegador, desktop, IDE, endpoint ou computer use.

</details>

---

### H04 — A quais sistemas, dados e operações o agente tem acesso?

**Orientação:** Liste sistemas consultados e ações permitidas.

**Tipo de resposta:** Texto livre

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:**

> 
> 
> 

<details>
<summary><strong>Como preencher</strong></summary>

Liste os sistemas e operações efetivas do agente. Diferencie consulta, criação, alteração, exclusão, aprovação e envio.

1. Identifique a fonte mais confiável da informação: responsável de negócio, equipe técnica, contrato, console ou arquitetura.
2. Registre a condição atual ou o desenho aprovado, usando termos objetivos e verificáveis.
3. Inclua nomes, limites, datas, responsáveis ou referências quando forem relevantes.
4. Quando a informação não estiver disponível, registre claramente que ela precisa ser confirmada.

**Quando usar “Não sei”:** Quando não houver opção “Não sei”, registre a dúvida no campo textual relacionado ou solicite apoio ao responsável antes de concluir a avaliação.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

Campo de texto livre. Registre informação objetiva, atual e verificável.

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Consulta saldo; cria proposta; envia e-mail; bloqueia cartão somente após confirmação humana.”

**Evite:**

- Respostas genéricas como “conforme”, “padrão da empresa”, “a definir” ou “dados do negócio” sem contexto.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de agentes, tools, MCP, autonomia, autorização e contenção. Capacidades de ação podem elevar impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B004-S07 — BAS-004, 7. Memória, delegação e comunicação entre agentes: Quando houver memória agentic, agentes secundários, delegação, comunicação multiagente ou contexto persistente.

</details>

---

### H05 — O agente pode criar, alterar, excluir, aprovar, enviar, pagar ou conceder acesso?

**Orientação:** Marque Sim para qualquer ação que produza efeito real.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Marque Sim para qualquer ação que produza efeito real. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: O agente pode criar, alterar, excluir, aprovar, enviar, pagar ou conceder acesso. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Marque Sim para qualquer ação que produza efeito real. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” ou “Não sei” eleva H4, Segurança e autonomia para I4, ativa F4, piso P3 e controles de autorização, confirmação, limites e contenção.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.2 — BAS-002: integração e exposição; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B001-L2
- MTR1-B002-S06 — BAS-002, 6. Saída e uso downstream: Quando outputs forem exibidos, persistidos, usados em decisões ou encaminhados a sistemas downstream.
- MTR1-B004-L2
- MTR1-B004-S03 — BAS-004, 3. Autorização determinística e limites de ação: Quando o agente puder acessar recurso, tomar decisão ou produzir efeito em sistema externo.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B006-L2

</details>

---

### H06 — Existe uma lista explícita das ferramentas e operações permitidas?

**Orientação:** A IA não deve descobrir ou usar qualquer ferramenta livremente.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. A IA não deve descobrir ou usar qualquer ferramenta livremente. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Existe uma lista explícita das ferramentas e operações permitidas. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. A IA não deve descobrir ou usar qualquer ferramenta livremente. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de agentes, tools, MCP, autonomia, autorização e contenção. Capacidades de ação podem elevar impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B004-S02 — BAS-004, 2. Registro, integridade e schemas de tools: Quando houver tools, functions, actions, skills, plugins, capabilities, resources ou prompts MCP.
- MTR1-B004-S04 — BAS-004, 4. Segurança de clientes, servidores e registries MCP: Quando houver cliente, servidor, registry, discovery, resource ou prompt MCP.
- MTR1-B004-S05 — BAS-004, 5. Proteção contra instruções e capabilities adversariais: Quando conteúdo não confiável puder influenciar planejamento, seleção de tool, capability ou instrução do agente.

</details>

---

### H07 — As ferramentas aceitam somente campos e formatos definidos?

**Orientação:** Schemas estritos reduzem parâmetros inesperados ou manipulados.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Schemas estritos reduzem parâmetros inesperados ou manipulados. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: As ferramentas aceitam somente campos e formatos definidos. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Schemas estritos reduzem parâmetros inesperados ou manipulados. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de agentes, tools, MCP, autonomia, autorização e contenção. Capacidades de ação podem elevar impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.2 — BAS-002: integração e exposição; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B002-S05 — BAS-002, 5. Entrada, prompt e payload: Quando entradas, prompts, anexos, parâmetros ou conteúdo não confiável forem aceitos.
- MTR1-B004-S02 — BAS-004, 2. Registro, integridade e schemas de tools: Quando houver tools, functions, actions, skills, plugins, capabilities, resources ou prompts MCP.
- MTR1-B004-S05 — BAS-004, 5. Proteção contra instruções e capabilities adversariais: Quando conteúdo não confiável puder influenciar planejamento, seleção de tool, capability ou instrução do agente.

</details>

---

### H08 — Um controle independente da IA autoriza cada ação?

**Orientação:** A própria resposta do modelo não deve ser a única autorização.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. A própria resposta do modelo não deve ser a única autorização. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Um controle independente da IA autoriza cada ação. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. A própria resposta do modelo não deve ser a única autorização. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Para agente com ação material, resposta diferente de “Sim” gera condição bloqueante por ausência de autorização determinística.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B004-S03 — BAS-004, 3. Autorização determinística e limites de ação: Quando o agente puder acessar recurso, tomar decisão ou produzir efeito em sistema externo.

</details>

---

### H09 — O sistema final sabe qual pessoa pediu a ação?

**Orientação:** A identidade do solicitante deve acompanhar todo o fluxo.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. A identidade do solicitante deve acompanhar todo o fluxo. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: O sistema final sabe qual pessoa pediu a ação. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. A identidade do solicitante deve acompanhar todo o fluxo. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de agentes, tools, MCP, autonomia, autorização e contenção. Capacidades de ação podem elevar impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B004-S01 — BAS-004, 1. Identidades agentic e contexto de execução: Quando existir agente, worker, executor ou ação realizada em nome de usuário ou workload.
- MTR1-B006-S02 — BAS-006, 2. Correlação e contexto ponta a ponta: Quando o fluxo atravessar aplicação, gateway, provider, RAG, agente, tool, fila ou sistema downstream.

</details>

---

### H10 — Ações irreversíveis ou importantes exigem confirmação humana?

**Orientação:** A confirmação deve mostrar contexto, destino, valor e efeito da ação.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. A confirmação deve mostrar contexto, destino, valor e efeito da ação. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Ações irreversíveis ou importantes exigem confirmação humana. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. A confirmação deve mostrar contexto, destino, valor e efeito da ação. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de agentes, tools, MCP, autonomia, autorização e contenção. Capacidades de ação podem elevar impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B004-L2
- MTR1-B004-S03 — BAS-004, 3. Autorização determinística e limites de ação: Quando o agente puder acessar recurso, tomar decisão ou produzir efeito em sistema externo.

</details>

---

### H11 — Existem limites para tempo, custo, quantidade de chamadas e ações?

**Orientação:** Inclua iterações, tokens, volume, valor e frequência.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Inclua iterações, tokens, volume, valor e frequência. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Existem limites para tempo, custo, quantidade de chamadas e ações. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclua iterações, tokens, volume, valor e frequência. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de agentes, tools, MCP, autonomia, autorização e contenção. Capacidades de ação podem elevar impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B004-S03 — BAS-004, 3. Autorização determinística e limites de ação: Quando o agente puder acessar recurso, tomar decisão ou produzir efeito em sistema externo.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B006-S06 — BAS-006, 6. Anomalias de comportamento, custo e desempenho: Quando volume, custo, tokens, loops, drift, falha, latência ou saturação precisarem ser monitorados.

</details>

---

### H12 — É possível desligar rapidamente o agente ou uma ferramenta específica?

**Orientação:** Inclui kill switch e bloqueio individual de agente, tool ou servidor MCP.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Inclui kill switch e bloqueio individual de agente, tool ou servidor MCP. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: É possível desligar rapidamente o agente ou uma ferramenta específica. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclui kill switch e bloqueio individual de agente, tool ou servidor MCP. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Para ação material ou processo crítico, a ausência de kill switch/contenção pode gerar condição bloqueante.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B004-S04 — BAS-004, 4. Segurança de clientes, servidores e registries MCP: Quando houver cliente, servidor, registry, discovery, resource ou prompt MCP.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B006-S05 — BAS-006, 5. Detecções técnicas de segurança para IA: Quando forem necessárias detecções de vazamento, prompt injection, abuso agentic, poisoning, shadow AI ou MCP desconhecido.
- MTR1-B006-S07 — BAS-006, 7. Contenção técnica e comportamento seguro: Quando a solução exigir kill switch, bloqueio individual, circuit breaker, retries limitados, revogação ou fallback seguro.

</details>

---

### H13 — Código e controle do computador são executados em ambiente isolado?

**Orientação:** Sandbox deve impedir acesso indevido ao computador e às credenciais do host.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há computer use, navegador, terminal ou execução de código.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Sandbox deve impedir acesso indevido ao computador e às credenciais do host. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Código e controle do computador são executados em ambiente isolado. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Sandbox deve impedir acesso indevido ao computador e às credenciais do host. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de agentes, tools, MCP, autonomia, autorização e contenção. Capacidades de ação podem elevar impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B004-L2
- MTR1-B004-S06 — BAS-004, 6. Sandbox, host, navegador e computer use: Quando houver execução de código, terminal, navegador, desktop, IDE, endpoint ou computer use.

</details>

---

### H14 — Agentes secundários recebem somente as permissões necessárias?

**Orientação:** Delegações não podem ampliar a autoridade original.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando existe agente ou automação e H01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Delegações não podem ampliar a autoridade original. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Agentes secundários recebem somente as permissões necessárias. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Delegações não podem ampliar a autoridade original. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de agentes, tools, MCP, autonomia, autorização e contenção. Capacidades de ação podem elevar impacto e probabilidade.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Registry de tools/MCP, schemas, políticas de autorização, limites, logs de ação, sandbox e teste de kill switch.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 8 — Impacto; § 9 — Probabilidade; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 10 — Regra individual de controle
- BAS-004 — Agentes, Ferramentas e Protocolos Agentic

**Regras vinculadas:**

- MTR1-B003-S07 — BAS-003, 7. Memória, caches e dados derivados em execução: Quando houver memória persistente, cache semântico, estado conversacional ou compartilhamento de contexto.
- MTR1-B004-L2
- MTR1-B004-S07 — BAS-004, 7. Memória, delegação e comunicação entre agentes: Quando houver memória agentic, agentes secundários, delegação, comunicação multiagente ou contexto persistente.

</details>

---

## 9. Desenvolvimento, modelos e MLOps — preencher quando aplicável

### I01 — A organização ou o fornecedor desenvolve ou implanta algum componente de IA?

**Orientação:** Inclui treinar, adaptar, empacotar, publicar ou operar modelos.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando existe desenvolvimento interno, modelo local, fine-tuning ou MLOps.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Inclua desenvolvimento realizado pela organização ou por fornecedor. Considere treino, fine-tuning, adapters, prompts, empacotamento e implantação.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Inclui treinar, adaptar, empacotar, publicar ou operar modelos. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A organização ou o fornecedor desenvolve ou implanta algum componente de IA. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclui treinar, adaptar, empacotar, publicar ou operar modelos. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Fornecedor realiza fine-tuning e publica o modelo em registry próprio.”

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” ou “Não sei” ativa o BAS-005 e as perguntas de desenvolvimento, artefatos, pipeline e release.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B005 — BAS-005: Desenvolvimento, treinamento, adaptação, empacotamento, registro, avaliação, implantação ou gestão de modelo e artefatos de IA.
- MTR1-B005-S01 — BAS-005, 1. Repositórios, código e versionamento: Quando código, notebook, prompt, policy, manifesto ou configuração for desenvolvido ou mantido para a solução.
- MTR1-B005-S05 — BAS-005, 5. Pipelines MLOps, LLMOps e ambientes de build: Quando houver pipeline de dados, treinamento, build, teste, promoção ou deploy.

</details>

---

### I02 — Código, notebooks, prompts e configurações possuem controle de versão?

**Orientação:** Deve ser possível saber quem alterou, quando e qual versão foi usada.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há desenvolvimento/modelo e I01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Deve ser possível saber quem alterou, quando e qual versão foi usada. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Código, notebooks, prompts e configurações possuem controle de versão. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Deve ser possível saber quem alterou, quando e qual versão foi usada. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de desenvolvimento, artefatos, cadeia de suprimentos, MLOps, testes, deploy e rollback.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B003-S02 — BAS-003, 2. Transformação, parsing e metadados: Quando houver parsing, chunking, normalização, enriquecimento, OCR ou geração de derivados.
- MTR1-B005-S01 — BAS-005, 1. Repositórios, código e versionamento: Quando código, notebook, prompt, policy, manifesto ou configuração for desenvolvido ou mantido para a solução.
- MTR1-B005-S02 — BAS-005, 2. Datasets, prompts e configurações de treinamento e avaliação: Quando houver treinamento, fine-tuning, avaliação, dataset, prompt sistêmico ou configuração de geração por release.

</details>

---

### I03 — Os conjuntos de dados de treino e teste possuem versão e origem registradas?

**Orientação:** Inclua hash, linhagem e separação entre treino, validação e teste.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há desenvolvimento/modelo e I01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Inclua hash, linhagem e separação entre treino, validação e teste. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Os conjuntos de dados de treino e teste possuem versão e origem registradas. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclua hash, linhagem e separação entre treino, validação e teste. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de desenvolvimento, artefatos, cadeia de suprimentos, MLOps, testes, deploy e rollback.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B005-S02 — BAS-005, 2. Datasets, prompts e configurações de treinamento e avaliação: Quando houver treinamento, fine-tuning, avaliação, dataset, prompt sistêmico ou configuração de geração por release.

</details>

---

### I04 — Modelos e arquivos de IA vêm de fonte aprovada?

**Orientação:** Ex.: registry permitido para weights, adapters, tokenizers e checkpoints.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há desenvolvimento/modelo e I01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: registry permitido para weights, adapters, tokenizers e checkpoints. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Modelos e arquivos de IA vêm de fonte aprovada. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: registry permitido para weights, adapters, tokenizers e checkpoints. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de desenvolvimento, artefatos, cadeia de suprimentos, MLOps, testes, deploy e rollback.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B005-S03 — BAS-005, 3. Modelos, artefatos e registries: Quando modelos, weights, checkpoints, adapters, tokenizers ou bundles forem registrados, carregados ou distribuídos.

</details>

---

### I05 — A integridade dos modelos e arquivos é verificada antes do uso?

**Orientação:** Ex.: assinatura, hash ou digest.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há desenvolvimento/modelo e I01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: assinatura, hash ou digest. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A integridade dos modelos e arquivos é verificada antes do uso. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: assinatura, hash ou digest. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de desenvolvimento, artefatos, cadeia de suprimentos, MLOps, testes, deploy e rollback.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B005-L2
- MTR1-B005-S03 — BAS-005, 3. Modelos, artefatos e registries: Quando modelos, weights, checkpoints, adapters, tokenizers ou bundles forem registrados, carregados ou distribuídos.
- MTR1-B005-S04 — BAS-005, 4. Dependências, containers e proveniência: Quando builds utilizarem pacotes, containers, imagens, dependências ou artefatos externos.

</details>

---

### I06 — Arquivos capazes de executar código são bloqueados ou abertos em ambiente isolado?

**Orientação:** Alguns formatos de modelo podem executar código durante o carregamento.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há desenvolvimento/modelo e I01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Alguns formatos de modelo podem executar código durante o carregamento. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Arquivos capazes de executar código são bloqueados ou abertos em ambiente isolado. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Alguns formatos de modelo podem executar código durante o carregamento. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de desenvolvimento, artefatos, cadeia de suprimentos, MLOps, testes, deploy e rollback.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B005-L2
- MTR1-B005-S03 — BAS-005, 3. Modelos, artefatos e registries: Quando modelos, weights, checkpoints, adapters, tokenizers ou bundles forem registrados, carregados ou distribuídos.
- MTR1-B005-S04 — BAS-005, 4. Dependências, containers e proveniência: Quando builds utilizarem pacotes, containers, imagens, dependências ou artefatos externos.

</details>

---

### I07 — Cada versão possui inventário e verificação de componentes?

**Orientação:** Inclui SBOM, AI BOM, vulnerabilidades, malware e dependências.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há desenvolvimento/modelo e I01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Inclui SBOM, AI BOM, vulnerabilidades, malware e dependências. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Cada versão possui inventário e verificação de componentes. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclui SBOM, AI BOM, vulnerabilidades, malware e dependências. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de desenvolvimento, artefatos, cadeia de suprimentos, MLOps, testes, deploy e rollback.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B005-L2
- MTR1-B005-S04 — BAS-005, 4. Dependências, containers e proveniência: Quando builds utilizarem pacotes, containers, imagens, dependências ou artefatos externos.

</details>

---

### I08 — Build, teste e publicação usam acessos separados e ambientes temporários?

**Orientação:** Reduz reutilização de credenciais e contaminação entre etapas.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há desenvolvimento/modelo e I01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Reduz reutilização de credenciais e contaminação entre etapas. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Build, teste e publicação usam acessos separados e ambientes temporários. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Reduz reutilização de credenciais e contaminação entre etapas. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de desenvolvimento, artefatos, cadeia de suprimentos, MLOps, testes, deploy e rollback.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B005-L2
- MTR1-B005-S05 — BAS-005, 5. Pipelines MLOps, LLMOps e ambientes de build: Quando houver pipeline de dados, treinamento, build, teste, promoção ou deploy.

</details>

---

### I09 — A mesma versão testada é promovida sem ser reconstruída?

**Orientação:** O digest do artefato deve permanecer igual entre ambientes.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há desenvolvimento/modelo e I01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. O digest do artefato deve permanecer igual entre ambientes. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A mesma versão testada é promovida sem ser reconstruída. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. O digest do artefato deve permanecer igual entre ambientes. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de desenvolvimento, artefatos, cadeia de suprimentos, MLOps, testes, deploy e rollback.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B005-S05 — BAS-005, 5. Pipelines MLOps, LLMOps e ambientes de build: Quando houver pipeline de dados, treinamento, build, teste, promoção ou deploy.
- MTR1-B005-S07 — BAS-005, 7. Deploy, serving e mudança técnica: Quando houver deployment, endpoint, serving, atualização, reconciliação ou mudança de versão/configuração.

</details>

---

### I10 — Os testes são executados exatamente sobre a versão que irá para produção?

**Orientação:** Inclui evals funcionais, segurança e critérios de aceitação.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há desenvolvimento/modelo e I01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Inclui evals funcionais, segurança e critérios de aceitação. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Os testes são executados exatamente sobre a versão que irá para produção. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclui evals funcionais, segurança e critérios de aceitação. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de desenvolvimento, artefatos, cadeia de suprimentos, MLOps, testes, deploy e rollback.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B005-L2
- MTR1-B005-S06 — BAS-005, 6. Testes, evals e critérios técnicos de release: Quando releases, modelos, prompts ou soluções forem avaliados antes da promoção ou contratação.

</details>

---

### I11 — É possível voltar rapidamente para uma versão segura anterior?

**Orientação:** Rollback deve usar versão conhecida e íntegra.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há desenvolvimento/modelo e I01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Rollback deve usar versão conhecida e íntegra. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: É possível voltar rapidamente para uma versão segura anterior. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Rollback deve usar versão conhecida e íntegra. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de desenvolvimento, artefatos, cadeia de suprimentos, MLOps, testes, deploy e rollback.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.5 — BAS-005: desenvolvimento e MLOps; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B001-S07 — BAS-001, 7. Resiliência e recuperação: Quando houver dependência operacional, serviço produtivo, ação material ou necessidade de recuperação e desativação.
- MTR1-B005-S08 — BAS-005, 8. Rollback, descontinuação e descarte técnico: Quando a solução precisar retornar versão, retirar modelo, revogar acesso, eliminar caches ou impedir reativação.
- MTR1-B006-S08 — BAS-006, 8. Recuperação, continuidade e desativação técnica: Quando houver requisito de backup, restauração, redundância, recuperação, plano de saída ou desativação segura.

</details>

---

### I12 — Atualizações automáticas são bloqueadas ou detectadas antes do uso?

**Orientação:** Considere modelo, fornecedor, dependências e artefatos.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida somente quando há desenvolvimento/modelo e I01 não foi respondida como “Não”.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a condição, exposição ou capacidade descrita faz parte do cenário. Considere modelo, fornecedor, dependências e artefatos. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Atualizações automáticas são bloqueadas ou detectadas antes do uso. | Ativa a condição de risco ou capacidade e pode elevar H, impacto, probabilidade ou selecionar perguntas, baselines e controles. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Considere modelo, fornecedor, dependências e artefatos. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Não ativa essa condição; perguntas e controles exclusivamente dependentes dela podem ser ocultados ou removidos. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

“Sim” ativa F3 por mudança dinâmica e controles de detecção de drift e atualização técnica.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Repositório, commits, hashes, SBOM/AI BOM, registry, pipeline, evals, assinatura e teste de rollback.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 7 — Classificação H1–H4; § 9 — Probabilidade; § 11 — Seleção dos controles
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.5 — BAS-005: desenvolvimento e MLOps; § 10 — Regra individual de controle
- BAS-005 — Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos

**Regras vinculadas:**

- MTR1-B001-S04 — BAS-001, 4. Modelos, runtime e cadeia de fornecimento: Quando houver modelo, runtime, container, dependência, provider, artefato ou atualização técnica.
- MTR1-B002-S04 — BAS-002, 4. Roteamento, modelos e policies: Quando houver escolha de provider/modelo, aliases, rotas, fallback ou policies de gateway.
- MTR1-B005-S07 — BAS-005, 7. Deploy, serving e mudança técnica: Quando houver deployment, endpoint, serving, atualização, reconciliação ou mudança de versão/configuração.

</details>

---

## 10. Telemetria, detecção, continuidade e resposta

### J01 — Cada uso importante da IA gera registro de início, fim, decisão e resultado?

**Orientação:** Permite identificar sucesso, bloqueio, erro, cancelamento e timeout.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Permite identificar sucesso, bloqueio, erro, cancelamento e timeout. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Cada uso importante da IA gera registro de início, fim, decisão e resultado. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Permite identificar sucesso, bloqueio, erro, cancelamento e timeout. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Em decisão sensível ou ação material, resposta diferente de “Sim” gera condição bloqueante por ausência de trilha auditável.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S06 — BAS-001, 6. Logging, auditoria e monitoramento: Quando a solução estiver em teste material, homologação, produção ou processar dados relevantes.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B006 — BAS-006: Solução em homologação material, produção, operação existente ou que exija telemetria, detecção, contenção, continuidade ou recuperação.
- MTR1-B006-S01 — BAS-006, 1. Geração de eventos e integridade temporal: Quando execuções, decisões, erros ou bloqueios precisarem produzir eventos auditáveis.

</details>

---

### J02 — Os registros informam qual modelo, versão, usuário e ambiente foram usados?

**Orientação:** Inclua fornecedor, deployment, tenant e identidade efetiva.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Inclua fornecedor, deployment, tenant e identidade efetiva. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Os registros informam qual modelo, versão, usuário e ambiente foram usados. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclua fornecedor, deployment, tenant e identidade efetiva. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de telemetria, detecção, contenção, continuidade e recuperação. Lacunas críticas podem impedir a redução do risco residual.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S06 — BAS-001, 6. Logging, auditoria e monitoramento: Quando a solução estiver em teste material, homologação, produção ou processar dados relevantes.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B006-S01 — BAS-006, 1. Geração de eventos e integridade temporal: Quando execuções, decisões, erros ou bloqueios precisarem produzir eventos auditáveis.

</details>

---

### J03 — É possível acompanhar uma solicitação do início ao fim?

**Orientação:** Use um identificador de correlação entre aplicação, base de conhecimento, modelo, agente e sistema final.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Use um identificador de correlação entre aplicação, base de conhecimento, modelo, agente e sistema final. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: É possível acompanhar uma solicitação do início ao fim. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Use um identificador de correlação entre aplicação, base de conhecimento, modelo, agente e sistema final. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de telemetria, detecção, contenção, continuidade e recuperação. Lacunas críticas podem impedir a redução do risco residual.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S06 — BAS-001, 6. Logging, auditoria e monitoramento: Quando a solução estiver em teste material, homologação, produção ou processar dados relevantes.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B006-S02 — BAS-006, 2. Correlação e contexto ponta a ponta: Quando o fluxo atravessar aplicação, gateway, provider, RAG, agente, tool, fila ou sistema downstream.

</details>

---

### J04 — Prompts, respostas e documentos deixam de ser gravados por inteiro por padrão?

**Orientação:** Prefira metadados, hashes e referências; grave conteúdo somente quando necessário e protegido.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Prefira metadados, hashes e referências; grave conteúdo somente quando necessário e protegido. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Prompts, respostas e documentos deixam de ser gravados por inteiro por padrão. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Prefira metadados, hashes e referências; grave conteúdo somente quando necessário e protegido. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de telemetria, detecção, contenção, continuidade e recuperação. Lacunas críticas podem impedir a redução do risco residual.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.
- MTR1-B001-S06 — BAS-001, 6. Logging, auditoria e monitoramento: Quando a solução estiver em teste material, homologação, produção ou processar dados relevantes.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B006-S03 — BAS-006, 3. Proteção, minimização e integridade dos registros: Quando logs, traces, prompts, outputs ou eventos contiverem informação sensível ou evidência crítica.

</details>

---

### J05 — Senhas, tokens e dados sensíveis são ocultados antes de entrar nos registros?

**Orientação:** A remoção deve ocorrer antes do envio para ferramentas de log.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. A remoção deve ocorrer antes do envio para ferramentas de log. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Senhas, tokens e dados sensíveis são ocultados antes de entrar nos registros. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. A remoção deve ocorrer antes do envio para ferramentas de log. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de telemetria, detecção, contenção, continuidade e recuperação. Lacunas críticas podem impedir a redução do risco residual.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S03 — BAS-001, 3. Proteção de dados, prompts e outputs: Quando a solução processar, armazenar, transmitir ou produzir dados, prompts, anexos, contexto ou outputs.
- MTR1-B001-S06 — BAS-001, 6. Logging, auditoria e monitoramento: Quando a solução estiver em teste material, homologação, produção ou processar dados relevantes.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B006-S03 — BAS-006, 3. Proteção, minimização e integridade dos registros: Quando logs, traces, prompts, outputs ou eventos contiverem informação sensível ou evidência crítica.

</details>

---

### J06 — Eventos importantes chegam à equipe de segurança e não podem ser apagados facilmente?

**Orientação:** Ex.: SIEM/SOC e armazenamento protegido contra alteração.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: SIEM/SOC e armazenamento protegido contra alteração. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Eventos importantes chegam à equipe de segurança e não podem ser apagados facilmente. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: SIEM/SOC e armazenamento protegido contra alteração. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de telemetria, detecção, contenção, continuidade e recuperação. Lacunas críticas podem impedir a redução do risco residual.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S06 — BAS-001, 6. Logging, auditoria e monitoramento: Quando a solução estiver em teste material, homologação, produção ou processar dados relevantes.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B006 — BAS-006: Solução em homologação material, produção, operação existente ou que exija telemetria, detecção, contenção, continuidade ou recuperação.
- MTR1-B006-L2
- MTR1-B006-S03 — BAS-006, 3. Proteção, minimização e integridade dos registros: Quando logs, traces, prompts, outputs ou eventos contiverem informação sensível ou evidência crítica.
- MTR1-B006-S04 — BAS-006, 4. Coleta, transporte e integração com SIEM: Quando eventos forem enviados a collector, broker, data lake, APM, SIEM ou SOC.

</details>

---

### J07 — Existem alertas específicos para ataques e vazamentos envolvendo IA?

**Orientação:** Ex.: prompt injection, jailbreak, abuso de agente, poisoning e MCP desconhecido.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: prompt injection, jailbreak, abuso de agente, poisoning e MCP desconhecido. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Existem alertas específicos para ataques e vazamentos envolvendo IA. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: prompt injection, jailbreak, abuso de agente, poisoning e MCP desconhecido. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de telemetria, detecção, contenção, continuidade e recuperação. Lacunas críticas podem impedir a redução do risco residual.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.5 — BAS-005: desenvolvimento e MLOps; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S06 — BAS-001, 6. Logging, auditoria e monitoramento: Quando a solução estiver em teste material, homologação, produção ou processar dados relevantes.
- MTR1-B003-S06 — BAS-003, 6. Proteção contra poisoning e conteúdo adversarial: Quando fontes externas, uploads ou conteúdo não confiável puderem influenciar ingestão ou recuperação.
- MTR1-B004-S05 — BAS-004, 5. Proteção contra instruções e capabilities adversariais: Quando conteúdo não confiável puder influenciar planejamento, seleção de tool, capability ou instrução do agente.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B005-S06 — BAS-005, 6. Testes, evals e critérios técnicos de release: Quando releases, modelos, prompts ou soluções forem avaliados antes da promoção ou contratação.
- MTR1-B006 — BAS-006: Solução em homologação material, produção, operação existente ou que exija telemetria, detecção, contenção, continuidade ou recuperação.
- MTR1-B006-L2
- MTR1-B006-S05 — BAS-006, 5. Detecções técnicas de segurança para IA: Quando forem necessárias detecções de vazamento, prompt injection, abuso agentic, poisoning, shadow AI ou MCP desconhecido.

</details>

---

### J08 — A solução monitora aumento anormal de uso, custo, erros e mudanças?

**Orientação:** Inclua tokens, loops, retries, latência e alteração de configuração.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Inclua tokens, loops, retries, latência e alteração de configuração. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A solução monitora aumento anormal de uso, custo, erros e mudanças. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclua tokens, loops, retries, latência e alteração de configuração. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de telemetria, detecção, contenção, continuidade e recuperação. Lacunas críticas podem impedir a redução do risco residual.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.5 — BAS-005: desenvolvimento e MLOps; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S06 — BAS-001, 6. Logging, auditoria e monitoramento: Quando a solução estiver em teste material, homologação, produção ou processar dados relevantes.
- MTR1-B002-S07 — BAS-002, 7. Exposição, sessão e abuso: Quando houver Internet, clientes, público, muitos usuários, sessão, streaming, custo ou risco de abuso.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B005-S07 — BAS-005, 7. Deploy, serving e mudança técnica: Quando houver deployment, endpoint, serving, atualização, reconciliação ou mudança de versão/configuração.
- MTR1-B006-S06 — BAS-006, 6. Anomalias de comportamento, custo e desempenho: Quando volume, custo, tokens, loops, drift, falha, latência ou saturação precisarem ser monitorados.

</details>

---

### J09 — A solução interrompe chamadas repetidas ou falhas antes de causar dano?

**Orientação:** Ex.: circuit breaker, limite de tentativas e fallback seguro.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: circuit breaker, limite de tentativas e fallback seguro. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: A solução interrompe chamadas repetidas ou falhas antes de causar dano. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: circuit breaker, limite de tentativas e fallback seguro. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Em agente ou processo crítico, resposta diferente de “Sim”, sem kill switch, pode gerar condição bloqueante.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.2 — BAS-002: integração e exposição; § 9.4 — BAS-004: agentes, ferramentas e MCP; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S07 — BAS-001, 7. Resiliência e recuperação: Quando houver dependência operacional, serviço produtivo, ação material ou necessidade de recuperação e desativação.
- MTR1-B002-S08 — BAS-002, 8. Resiliência e comportamento de falha: Quando a integração exigir timeout, retry, fallback, circuit breaker, fail-closed ou continuidade.
- MTR1-B004-S08 — BAS-004, 8. Observabilidade agentic e comportamento fail-safe: Quando ações agentic exigirem logs, correlação, detecção, kill switch, limites e comportamento seguro.
- MTR1-B006 — BAS-006: Solução em homologação material, produção, operação existente ou que exija telemetria, detecção, contenção, continuidade ou recuperação.
- MTR1-B006-L2
- MTR1-B006-S07 — BAS-006, 7. Contenção técnica e comportamento seguro: Quando a solução exigir kill switch, bloqueio individual, circuit breaker, retries limitados, revogação ou fallback seguro.

</details>

---

### J10 — Configurações e componentes importantes possuem backup testado?

**Orientação:** Inclua policies, schemas, dashboards e artefatos.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Inclua policies, schemas, dashboards e artefatos. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Configurações e componentes importantes possuem backup testado. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Inclua policies, schemas, dashboards e artefatos. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de telemetria, detecção, contenção, continuidade e recuperação. Lacunas críticas podem impedir a redução do risco residual.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.3 — BAS-003: dados, contexto e conhecimento; § 9.5 — BAS-005: desenvolvimento e MLOps; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S07 — BAS-001, 7. Resiliência e recuperação: Quando houver dependência operacional, serviço produtivo, ação material ou necessidade de recuperação e desativação.
- MTR1-B003-S08 — BAS-003, 8. Retenção, exclusão, sincronização e recuperação: Quando dados, índices, embeddings, memória ou derivados forem persistidos e precisarem ser excluídos ou restaurados.
- MTR1-B005-S08 — BAS-005, 8. Rollback, descontinuação e descarte técnico: Quando a solução precisar retornar versão, retirar modelo, revogar acesso, eliminar caches ou impedir reativação.
- MTR1-B006 — BAS-006: Solução em homologação material, produção, operação existente ou que exija telemetria, detecção, contenção, continuidade ou recuperação.
- MTR1-B006-S08 — BAS-006, 8. Recuperação, continuidade e desativação técnica: Quando houver requisito de backup, restauração, redundância, recuperação, plano de saída ou desativação segura.

</details>

---

### J11 — Existe orientação prática para responder a incidente de IA?

**Orientação:** Ex.: runbook integrado ao processo corporativo de incidentes.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Responda “Sim” quando houver instruções operacionais acionáveis, responsáveis, contatos, contenção e critérios de escalonamento específicos para IA.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Ex.: runbook integrado ao processo corporativo de incidentes. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Existe orientação prática para responder a incidente de IA. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Ex.: runbook integrado ao processo corporativo de incidentes. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Runbook SOC-AI-03 com isolamento do agente, revogação de tokens e contato do owner.”

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de telemetria, detecção, contenção, continuidade e recuperação. Lacunas críticas podem impedir a redução do risco residual.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S07 — BAS-001, 7. Resiliência e recuperação: Quando houver dependência operacional, serviço produtivo, ação material ou necessidade de recuperação e desativação.
- MTR1-B006-S08 — BAS-006, 8. Recuperação, continuidade e desativação técnica: Quando houver requisito de backup, restauração, redundância, recuperação, plano de saída ou desativação segura.

</details>

---

### J12 — É possível revogar rapidamente credenciais, tokens e sessões?

**Orientação:** A revogação deve ser centralizada e efetiva.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. A revogação deve ser centralizada e efetiva. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: É possível revogar rapidamente credenciais, tokens e sessões. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. A revogação deve ser centralizada e efetiva. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Determina controles de telemetria, detecção, contenção, continuidade e recuperação. Lacunas críticas podem impedir a redução do risco residual.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S02 — BAS-001, 2. Identidade, acesso e segredos: Quando houver usuário, workload, conta administrativa, credencial, segredo ou acesso a recurso de IA.
- MTR1-B001-S07 — BAS-001, 7. Resiliência e recuperação: Quando houver dependência operacional, serviço produtivo, ação material ou necessidade de recuperação e desativação.
- MTR1-B006-S07 — BAS-006, 7. Contenção técnica e comportamento seguro: Quando a solução exigir kill switch, bloqueio individual, circuit breaker, retries limitados, revogação ou fallback seguro.

</details>

---

### J13 — Ao desativar a solução, rotas, acessos e dados operacionais são removidos?

**Orientação:** Evita reativação acidental ou acesso residual.

**Tipo de resposta:** Escolha única

**Condição de exibição:** Exibida quando há operação, homologação, RAG, agente, processo crítico ou necessidade de telemetria e continuidade.

**Resposta:** _______________________________________________

<details>
<summary><strong>Como preencher</strong></summary>

Selecione “Sim” somente quando a condição existir de forma efetiva. Se depender de validação ou evidência ainda não disponível, selecione “Não sei”.

1. Leia a pergunta considerando o cenário atual e o desenho que será implantado.
2. Selecione uma única alternativa.
3. Use Sim apenas quando a condição existir ou estiver formalmente definida.
4. Use Não sei quando depender de validação técnica, contratual ou do fornecedor.

**Quando usar “Não sei”:** Use “Não sei” ou “Não determinado” quando a informação ainda não foi confirmada. O motor tratará a incerteza de forma conservadora e poderá solicitar revisão.

</details>

<details>
<summary><strong>Definições das opções</strong></summary>

| Opção | Definição | Quando selecionar | Efeito na avaliação |
|---|---|---|---|
| Sim | A resposta confirma que a proteção ou capacidade descrita está implementada ou formalmente prevista. Evita reativação acidental ou acesso residual. | Selecione “Sim” quando a arquitetura, o contrato, a configuração ou o responsável confirmar a condição descrita: Ao desativar a solução, rotas, acessos e dados operacionais são removidos. | Registra a existência da proteção. Pode evitar piso, lacuna ou encaminhamento adicional e influencia a interpretação dos controles aplicáveis. |
| Não | A resposta confirma que a condição descrita não existe, não está implementada ou não fará parte do cenário atual. Evita reativação acidental ou acesso residual. | Selecione “Não” quando houver confirmação de que a condição não ocorre no desenho atual ou planejado. | Indica ausência da proteção e pode ativar controles, piso, condição bloqueante ou necessidade de tratamento. |
| Não sei | A informação ainda não foi confirmada, definida ou classificada pelas áreas responsáveis. | Selecione quando contrato, arquitetura, classificação ou responsável ainda não forneceram uma resposta confiável. | A incerteza é tratada de forma conservadora, pode manter perguntas abertas, aplicar piso ou exigir revisão manual. |

</details>

<details>
<summary><strong>Exemplos de preenchimento</strong></summary>

**Exemplos adequados:**

- “Sim” quando o mecanismo existe e pode ser demonstrado.
- “Não” quando a condição não existe.
- “Não sei” quando ainda é necessário confirmar com área técnica ou fornecedor.

**Evite:**

- Responder com base em expectativa, intenção futura ou suposição sem confirmação.

</details>

<details>
<summary><strong>Influência na avaliação e no cálculo</strong></summary>

Ativa controles de desativação técnica, remoção de rotas, credenciais e dados operacionais.

</details>

<details>
<summary><strong>Evidências e comprovações úteis</strong></summary>

Eventos, traces, dashboards, regras SIEM, alertas, teste de falha, backup, restore e evidência de desativação.

> Nesta versão, as evidências são orientativas. O cálculo prospectivo considera que os controles aplicáveis serão implementados.

</details>

<details>
<summary><strong>Referências e regras</strong></summary>

**Documentos e seções:**

- MET-001 v1.1 — § 11 — Seleção dos controles; § 12 — Avaliação dos controles; § 13 — Risco residual; § 14 — Condições bloqueantes
- MTR-001 v1.0 — § 9.1 — BAS-001: controles transversais; § 9.5 — BAS-005: desenvolvimento e MLOps; § 9.6 — BAS-006: telemetria, detecção e resiliência; § 10 — Regra individual de controle
- BAS-006 — Telemetria, Detecção e Resiliência

**Regras vinculadas:**

- MTR1-B001-S07 — BAS-001, 7. Resiliência e recuperação: Quando houver dependência operacional, serviço produtivo, ação material ou necessidade de recuperação e desativação.
- MTR1-B005-S08 — BAS-005, 8. Rollback, descontinuação e descarte técnico: Quando a solução precisar retornar versão, retirar modelo, revogar acesso, eliminar caches ou impedir reativação.
- MTR1-B006-S08 — BAS-006, 8. Recuperação, continuidade e desativação técnica: Quando houver requisito de backup, restauração, redundância, recuperação, plano de saída ou desativação segura.

</details>

---
