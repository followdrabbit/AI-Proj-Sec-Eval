# BAS-005 — Baseline de Controles Técnicos para Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos de Modelos de IA

| Campo | Valor |
|---|---|
| **Código** | BAS-005 |
| **Nome** | Baseline de Controles Técnicos para Desenvolvimento, Versionamento, MLOps e Cadeia de Suprimentos de Modelos de IA |
| **Tipo documental** | Baseline técnico |
| **Classificação da informação** | Uso Interno |
| **Status** | Minuta para revisão |
| **Versão** | 1.2 |
| **Data** | 13/07/2026 |
| **Owner institucional** | Segurança da Informação / Segurança de IA |
| **Custodiante técnico** | Arquitetura de Segurança / MLOps / LLMOps / DevSecOps |
| **Quantidade de controles** | 48 |

## 1. Objetivo

Estabelecer recomendações técnicas mínimas, verificáveis e auditáveis para desenvolvimento e versionamento de código, datasets, prompts, modelos e configurações, bem como para treinamento, avaliação, empacotamento, registro, promoção, implantação, rollback e descontinuação por pipelines MLOps, LLMOps e ModelOps. O documento também estabelece controles para dependências, containers, registries, integridade, assinatura, proveniência, SBOM, AI BOM e demais elementos da cadeia de suprimentos de modelos de IA. O documento segue a estrutura de recomendações dos CIS Benchmarks e contém somente controles técnicos. Fluxos de aprovação, governança, contratação, exceção, RACI e resposta processual estão fora do escopo.

## 2. Escopo

Aplica-se a repositórios de código, notebooks produtivos, datasets de treinamento e avaliação, prompts, policies, modelos, weights, checkpoints, adapters, tokenizers, containers, bibliotecas, imagens base, dependências, model registries, artifact registries, pipelines MLOps, LLMOps e ModelOps, serviços de serving, mecanismos de assinatura e proveniência, SBOMs, AI BOMs e demais componentes utilizados para construir, testar e implantar modelos de IA. Este baseline não deve ser aplicado isoladamente: BAS-001 a BAS-004 permanecem aplicáveis, e os demais baselines especializados devem ser combinados cumulativamente conforme a arquitetura e as capacidades avaliadas.

## 3. Modelo de classificação

### 3.1 Profile Applicability

- **Level 1:** configuração técnica fundamental para processos de desenvolvimento, versionamento, treinamento, avaliação, empacotamento, registro, promoção e implantação de modelos de IA.
- **Level 2:** defesa em profundidade para modelos críticos, dados sensíveis, ambientes regulados, componentes externos, serviços expostos ou pipelines com alto impacto. Pressupõe conformidade com os controles Level 1 aplicáveis.

### 3.2 Criticidade

| Criticidade | Critério |
|---|---|
| **Crítica** | A ausência permite adulteração do release, execução de artefato malicioso, bypass de testes, perda de integridade, implantação não rastreada ou impossibilidade de rollback seguro. |
| **Alta** | A ausência enfraquece significativamente reprodutibilidade, rastreabilidade, isolamento, detecção de vulnerabilidades ou controle de mudanças técnicas. |
| **Média** | Controle de hardening cuja ausência normalmente exige outra falha para produzir impacto material. Esta versão não contém recomendações de criticidade Média. |
| **Baixa** | Otimização técnica com impacto limitado. Esta versão não contém recomendações de criticidade Baixa. |

## 4. Regras de interpretação

1. BAS-001 a BAS-004 são pré-requisitos quando aplicáveis aos componentes cobertos por este documento.
2. Cada recomendação deve ser avaliada de forma independente.
3. Um controle é **Conforme** somente quando todos os critérios descritos em **Audit** forem atendidos.
4. Implementação parcial deve ser registrada como **Não Conforme**; não existe conformidade parcial neste baseline.
5. Quando uma recomendação não se aplicar tecnicamente, a justificativa deve indicar o componente, capacidade ou etapa inexistente.
6. Relatórios, aprovações ou declarações não substituem enforcement técnico de integridade, versionamento, teste e promoção.

## Sumário

- [1. Repositórios, código e versionamento](#1-repositorios-codigo-e-versionamento)
  - [1.1 Certifique-se de que todo código e artefato textual utilizado no desenvolvimento, treinamento, avaliação e implantação de IA esteja em repositório corporativo versionado](#11-certifique-se-de-que-todo-codigo-e-artefato-textual-utilizado-no-desenvolvimento-treinamento-avaliacao-e-implantacao-de-ia-esteja-em-repositorio-corporativo-versionado)
  - [1.2 Certifique-se de que branches utilizadas para releases estejam protegidas contra alteração direta e force push](#12-certifique-se-de-que-branches-utilizadas-para-releases-estejam-protegidas-contra-alteracao-direta-e-force-push)
  - [1.3 Certifique-se de que commits e tags de release possuam identidade verificável](#13-certifique-se-de-que-commits-e-tags-de-release-possuam-identidade-verificavel)
  - [1.4 Certifique-se de que tags e releases sejam imutáveis após a publicação](#14-certifique-se-de-que-tags-e-releases-sejam-imutaveis-apos-a-publicacao)
  - [1.5 Certifique-se de que segredos sejam detectados e bloqueados antes de entrarem no repositório ou artefato de build](#15-certifique-se-de-que-segredos-sejam-detectados-e-bloqueados-antes-de-entrarem-no-repositorio-ou-artefato-de-build)
  - [1.6 Certifique-se de que ambientes de desenvolvimento e build utilizem dependências bloqueadas por versão e hash](#16-certifique-se-de-que-ambientes-de-desenvolvimento-e-build-utilizem-dependencias-bloqueadas-por-versao-e-hash)
- [2. Datasets, prompts e configurações de treinamento e avaliação](#2-datasets-prompts-e-configuracoes-de-treinamento-e-avaliacao)
  - [2.1 Certifique-se de que datasets de treinamento, fine-tuning e avaliação possuam versão imutável e hash verificável](#21-certifique-se-de-que-datasets-de-treinamento-fine-tuning-e-avaliacao-possuam-versao-imutavel-e-hash-verificavel)
  - [2.2 Certifique-se de que transformações de dados sejam rastreáveis da origem ao dataset resultante](#22-certifique-se-de-que-transformacoes-de-dados-sejam-rastreaveis-da-origem-ao-dataset-resultante)
  - [2.3 Certifique-se de que conjuntos de treinamento, validação e teste sejam segregados e protegidos contra contaminação](#23-certifique-se-de-que-conjuntos-de-treinamento-validacao-e-teste-sejam-segregados-e-protegidos-contra-contaminacao)
  - [2.4 Certifique-se de que prompts sistêmicos, policies e parâmetros de geração sejam versionados e fixados por release](#24-certifique-se-de-que-prompts-sistemicos-policies-e-parametros-de-geracao-sejam-versionados-e-fixados-por-release)
  - [2.5 Certifique-se de que tokenizer, adapters e pré-processamento sejam versionados como dependências do modelo](#25-certifique-se-de-que-tokenizer-adapters-e-pre-processamento-sejam-versionados-como-dependencias-do-modelo)
  - [2.6 Certifique-se de que manifests técnicos e cards sejam validados por schema antes da criação do release](#26-certifique-se-de-que-manifests-tecnicos-e-cards-sejam-validados-por-schema-antes-da-criacao-do-release)
- [3. Modelos, artefatos e registries](#3-modelos-artefatos-e-registries)
  - [3.1 Certifique-se de que modelos produtivos sejam carregados somente de registry corporativo permitido](#31-certifique-se-de-que-modelos-produtivos-sejam-carregados-somente-de-registry-corporativo-permitido)
  - [3.2 Certifique-se de que a integridade do artefato seja verificada antes do registro e de cada carregamento](#32-certifique-se-de-que-a-integridade-do-artefato-seja-verificada-antes-do-registro-e-de-cada-carregamento)
  - [3.3 Certifique-se de que cada release de modelo seja um bundle atômico e imutável](#33-certifique-se-de-que-cada-release-de-modelo-seja-um-bundle-atomico-e-imutavel)
  - [3.4 Certifique-se de que formatos de serialização capazes de executar código sejam bloqueados ou carregados em sandbox](#34-certifique-se-de-que-formatos-de-serializacao-capazes-de-executar-codigo-sejam-bloqueados-ou-carregados-em-sandbox)
  - [3.5 Certifique-se de que artefatos de modelo sejam inspecionados quanto a arquivos executáveis e conteúdo malicioso](#35-certifique-se-de-que-artefatos-de-modelo-sejam-inspecionados-quanto-a-arquivos-executaveis-e-conteudo-malicioso)
  - [3.6 Certifique-se de que versões publicadas no registry sejam imutáveis e protegidas contra exclusão ou sobrescrita não autorizada](#36-certifique-se-de-que-versoes-publicadas-no-registry-sejam-imutaveis-e-protegidas-contra-exclusao-ou-sobrescrita-nao-autorizada)
- [4. Dependências, containers e proveniência](#4-dependencias-containers-e-proveniencia)
  - [4.1 Certifique-se de que pacotes e imagens sejam obtidos somente de repositórios permitidos](#41-certifique-se-de-que-pacotes-e-imagens-sejam-obtidos-somente-de-repositorios-permitidos)
  - [4.2 Certifique-se de que cada release possua SBOM e AI BOM gerados automaticamente](#42-certifique-se-de-que-cada-release-possua-sbom-e-ai-bom-gerados-automaticamente)
  - [4.3 Certifique-se de que vulnerabilidades de dependências e imagens bloqueiem releases acima do limite definido](#43-certifique-se-de-que-vulnerabilidades-de-dependencias-e-imagens-bloqueiem-releases-acima-do-limite-definido)
  - [4.4 Certifique-se de que imagens base e ferramentas de build sejam fixadas por digest imutável](#44-certifique-se-de-que-imagens-base-e-ferramentas-de-build-sejam-fixadas-por-digest-imutavel)
  - [4.5 Certifique-se de que artefatos de build sejam assinados e possuam atestação de proveniência](#45-certifique-se-de-que-artefatos-de-build-sejam-assinados-e-possuam-atestacao-de-proveniencia)
  - [4.6 Certifique-se de que builds de release não possuam acesso irrestrito à Internet](#46-certifique-se-de-que-builds-de-release-nao-possuam-acesso-irrestrito-a-internet)
- [5. Pipelines MLOps, LLMOps e ambientes de build](#5-pipelines-mlops-llmops-e-ambientes-de-build)
  - [5.1 Certifique-se de que cada pipeline utilize identidade técnica exclusiva e de curta duração](#51-certifique-se-de-que-cada-pipeline-utilize-identidade-tecnica-exclusiva-e-de-curta-duracao)
  - [5.2 Certifique-se de que runners e ambientes de build sejam efêmeros e isolados entre execuções](#52-certifique-se-de-que-runners-e-ambientes-de-build-sejam-efemeros-e-isolados-entre-execucoes)
  - [5.3 Certifique-se de que definições de pipeline sejam versionadas e não editáveis diretamente em produção](#53-certifique-se-de-que-definicoes-de-pipeline-sejam-versionadas-e-nao-editaveis-diretamente-em-producao)
  - [5.4 Certifique-se de que somente a pipeline de release possa implantar ou alterar artefatos em produção](#54-certifique-se-de-que-somente-a-pipeline-de-release-possa-implantar-ou-alterar-artefatos-em-producao)
  - [5.5 Certifique-se de que build, teste e deploy utilizem identidades e permissões segregadas](#55-certifique-se-de-que-build-teste-e-deploy-utilizem-identidades-e-permissoes-segregadas)
  - [5.6 Certifique-se de que o mesmo digest testado seja promovido entre ambientes sem reconstrução](#56-certifique-se-de-que-o-mesmo-digest-testado-seja-promovido-entre-ambientes-sem-reconstrucao)
- [6. Testes, evals e critérios técnicos de release](#6-testes-evals-e-criterios-tecnicos-de-release)
  - [6.1 Certifique-se de que os testes sejam executados sobre o artefato exato destinado ao deploy](#61-certifique-se-de-que-os-testes-sejam-executados-sobre-o-artefato-exato-destinado-ao-deploy)
  - [6.2 Certifique-se de que métricas e limiares de aprovação sejam expressos em configuração executável](#62-certifique-se-de-que-metricas-e-limiares-de-aprovacao-sejam-expressos-em-configuracao-executavel)
  - [6.3 Certifique-se de que o release execute suíte de segurança compatível com suas capacidades habilitadas](#63-certifique-se-de-que-o-release-execute-suite-de-seguranca-compativel-com-suas-capacidades-habilitadas)
  - [6.4 Certifique-se de que modelos sejam avaliados quanto a memorização, vazamento e extração de dados](#64-certifique-se-de-que-modelos-sejam-avaliados-quanto-a-memorizacao-vazamento-e-extracao-de-dados)
  - [6.5 Certifique-se de que robustez e consumo de recursos sejam testados nos limites técnicos suportados](#65-certifique-se-de-que-robustez-e-consumo-de-recursos-sejam-testados-nos-limites-tecnicos-suportados)
  - [6.6 Certifique-se de que falhas em testes obrigatórios bloqueiem tecnicamente a promoção do release](#66-certifique-se-de-que-falhas-em-testes-obrigatorios-bloqueiem-tecnicamente-a-promocao-do-release)
- [7. Deploy, serving e mudança técnica](#7-deploy-serving-e-mudanca-tecnica)
  - [7.1 Certifique-se de que deployments fixem versões exatas de modelo, runtime, container e configuração](#71-certifique-se-de-que-deployments-fixem-versoes-exatas-de-modelo-runtime-container-e-configuracao)
  - [7.2 Certifique-se de que o runtime valide o digest esperado durante a inicialização](#72-certifique-se-de-que-o-runtime-valide-o-digest-esperado-durante-a-inicializacao)
  - [7.3 Certifique-se de que configurações de serving sejam declarativas e reconciliadas continuamente](#73-certifique-se-de-que-configuracoes-de-serving-sejam-declarativas-e-reconciliadas-continuamente)
  - [7.4 Certifique-se de que releases de maior risco utilizem canary ou shadow com limite técnico de exposição](#74-certifique-se-de-que-releases-de-maior-risco-utilizem-canary-ou-shadow-com-limite-tecnico-de-exposicao)
  - [7.5 Certifique-se de que alterações fora da pipeline sejam detectadas e bloqueadas ou revertidas](#75-certifique-se-de-que-alteracoes-fora-da-pipeline-sejam-detectadas-e-bloqueadas-ou-revertidas)
  - [7.6 Certifique-se de que atualização automática de modelo por provider esteja desabilitada ou detectada antes do uso](#76-certifique-se-de-que-atualizacao-automatica-de-modelo-por-provider-esteja-desabilitada-ou-detectada-antes-do-uso)
- [8. Rollback, descontinuação e descarte técnico](#8-rollback-descontinuacao-e-descarte-tecnico)
  - [8.1 Certifique-se de que exista release anterior conhecido e tecnicamente apto para rollback](#81-certifique-se-de-que-exista-release-anterior-conhecido-e-tecnicamente-apto-para-rollback)
  - [8.2 Certifique-se de que o rollback seja testado de ponta a ponta e atenda ao tempo técnico definido](#82-certifique-se-de-que-o-rollback-seja-testado-de-ponta-a-ponta-e-atenda-ao-tempo-tecnico-definido)
  - [8.3 Certifique-se de que modelos descontinuados não possam receber novas requisições](#83-certifique-se-de-que-modelos-descontinuados-nao-possam-receber-novas-requisicoes)
  - [8.4 Certifique-se de que credenciais e permissões associadas a pipelines e deployments descontinuados sejam revogadas](#84-certifique-se-de-que-credenciais-e-permissoes-associadas-a-pipelines-e-deployments-descontinuados-sejam-revogadas)
  - [8.5 Certifique-se de que artefatos temporários, caches e cópias de modelos retirados sejam eliminados dos ambientes de execução](#85-certifique-se-de-que-artefatos-temporarios-caches-e-copias-de-modelos-retirados-sejam-eliminados-dos-ambientes-de-execucao)
  - [8.6 Certifique-se de que não existam referências ativas a versões retiradas e que sua reativação automática seja impedida](#86-certifique-se-de-que-nao-existam-referencias-ativas-a-versoes-retiradas-e-que-sua-reativacao-automatica-seja-impedida)
## 1. Repositórios, código e versionamento

Controles para garantir que código, notebooks, prompts, pipelines e configurações possuam origem rastreável, histórico íntegro e dependências reproduzíveis.

### 1.1 Certifique-se de que todo código e artefato textual utilizado no desenvolvimento, treinamento, avaliação e implantação de IA esteja em repositório corporativo versionado

**Control ID:** BAS-005.1.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Código de treinamento, inferência, avaliação, transformação de dados, notebooks produtivos, prompts, policies, manifests, pipelines e configurações de serving.

**Description**

Todo artefato textual utilizado para construir, testar ou implantar uma solução de IA deve estar armazenado em repositório corporativo com controle de versão. Arquivos locais, compartilhamentos sem histórico, conteúdo copiado diretamente para consoles e notebooks não versionados não podem ser fonte de build ou deploy produtivo.

**Rationale**

Artefatos fora de controle de versão não possuem histórico confiável, dificultam reprodução, permitem alterações invisíveis e impedem determinar exatamente o conteúdo implantado.

**Impact**

A migração pode exigir adaptação de notebooks, prompts e configurações mantidos atualmente em interfaces proprietárias.

**Audit**

1. Enumerar os arquivos e artefatos consumidos pelos pipelines de build, treinamento, avaliação e deploy.
2. Confirmar que 100% possuem caminho e commit identificável em repositório corporativo.
3. Comparar o conteúdo implantado com o conteúdo do commit registrado e confirmar igualdade.
4. Reprovar se qualquer etapa produtiva consumir arquivo local, upload manual, notebook sem commit ou configuração sem histórico versionado.

**Remediation**

Mover os artefatos para repositório corporativo, ajustar pipelines para consumirem commits identificados e eliminar uploads ou edições manuais como fonte de produção.

**Evidence**

Inventário de artefatos, URLs de repositórios, commits e comparação entre conteúdo versionado e implantado.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 CM-2, CM-3, SA-10

---

### 1.2 Certifique-se de que branches utilizadas para releases estejam protegidas contra alteração direta e force push

**Control ID:** BAS-005.1.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Repositórios que originem modelos, containers, prompts, pipelines ou configurações implantadas em homologação ou produção.

**Description**

Branches de release e a branch padrão devem bloquear push direto, force push, exclusão e alteração do histórico. Mudanças devem ocorrer por merge de referência rastreável e os controles não podem ser desabilitados por identidades comuns de desenvolvimento.

**Rationale**

Alteração direta ou reescrita do histórico permite inserir código ou configuração sem trilha íntegra e substituir a origem de um artefato já avaliado.

**Impact**

Pode reduzir a velocidade de correções emergenciais e exigir um caminho técnico específico de break-glass.

**Audit**

1. Exportar regras de proteção da branch padrão e das branches usadas para release.
2. Confirmar bloqueio de push direto, force push e exclusão para usuários e contas de automação não administrativas.
3. Tentar executar push direto e force push com identidade de desenvolvedor; ambas as operações devem ser negadas.
4. Reprovar se uma branch produtiva não possuir proteção ou se a própria pipeline puder remover a proteção.

**Remediation**

Habilitar branch protection, impedir reescrita de histórico e limitar alterações das regras a identidade administrativa separada do desenvolvimento e da pipeline.

**Evidence**

Exportação das regras de proteção e logs de tentativas negadas de push direto e force push.

**Mappings**

CIS Controls v8 4, 5, 6 e 16; NIST SP 800-53 CM-3, CM-5, AC-6

---

### 1.3 Certifique-se de que commits e tags de release possuam identidade verificável

**Control ID:** BAS-005.1.3
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Repositórios que originem artefatos de IA para ambientes críticos, regulados ou expostos externamente.

**Description**

Commits incorporados a releases e tags de versão devem possuir assinatura criptográfica válida ou atestação equivalente vinculada à identidade autenticada do autor ou da pipeline. Assinaturas inválidas, expiradas, desconhecidas ou ausentes devem impedir a criação da release.

**Rationale**

Uma identidade de commit não verificada pode ser falsificada e não demonstra quem produziu o conteúdo efetivamente utilizado.

**Impact**

A exigência requer gerenciamento de chaves, certificados ou identidade de workload para desenvolvedores e automações.

**Audit**

1. Selecionar todas as tags e commits de uma amostra de releases produtivas.
2. Validar assinatura ou atestação de cada commit e tag contra identidades confiáveis.
3. Criar commit ou tag sem assinatura em repositório de teste e tentar gerar release; a operação deve falhar.
4. Reprovar se a pipeline aceitar assinatura desconhecida ou considerar somente o nome e e-mail declarados no commit.

**Remediation**

Configurar verificação obrigatória de assinatura ou identidade attestada para commits/tags de release e bloquear a pipeline quando a validação falhar.

**Evidence**

Relatório de verificação de assinaturas, políticas da pipeline e teste negativo com commit ou tag não verificada.

**Mappings**

CIS Controls v8 5, 6 e 16; NIST SP 800-53 IA-5, SI-7, CM-5; SLSA provenance

---

### 1.4 Certifique-se de que tags e releases sejam imutáveis após a publicação

**Control ID:** BAS-005.1.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Tags, releases e referências utilizadas por builds, treinamentos, evals e deployments.

**Description**

Uma tag ou identificador de release publicado não pode ser movido, sobrescrito ou reutilizado para apontar a conteúdo diferente. Qualquer alteração deve produzir novo identificador de versão. Builds não podem depender de branches mutáveis como main, master ou develop sem resolução para commit imutável.

**Rationale**

Se uma versão puder mudar após a avaliação, o mesmo identificador pode representar conteúdo diferente e invalidar testes, evidências e rollback.

**Impact**

Correções exigirão nova versão em vez de substituir a versão existente.

**Audit**

1. Selecionar tags e releases utilizadas em produção e registrar os respectivos commits.
2. Tentar mover ou recriar uma tag existente; a operação deve ser negada.
3. Confirmar que pipelines resolvem referências mutáveis para commit imutável antes do build.
4. Reprovar se um identificador publicado puder referenciar conteúdo diferente sem alteração da versão.

**Remediation**

Habilitar proteção e imutabilidade de tags/releases, impedir sobrescrita e exigir nova versão para qualquer modificação.

**Evidence**

Configuração de imutabilidade, mapa de releases para commits e teste de sobrescrita bloqueado.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 CM-2, CM-3, SI-7

---

### 1.5 Certifique-se de que segredos sejam detectados e bloqueados antes de entrarem no repositório ou artefato de build

**Control ID:** BAS-005.1.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Código, notebooks, prompts, datasets de exemplo, manifests, logs de build e arquivos de configuração.

**Description**

O fluxo de commit e de build deve executar secret scanning capaz de detectar chaves, tokens, certificados, senhas e padrões internos. A presença de segredo deve bloquear merge e build. A ferramenta deve inspecionar o histórico e conteúdo gerado, não apenas o diff mais recente.

**Rationale**

Segredos em repositórios e artefatos podem ser copiados, persistidos em caches e reutilizados para comprometer serviços internos ou providers.

**Impact**

Pode produzir falsos positivos que exigirão ajuste de regras ou uso de valores fictícios em exemplos.

**Audit**

1. Revisar a configuração do secret scanner nos repositórios e pipelines.
2. Inserir segredo de teste reconhecido em código, notebook e arquivo de configuração; merge e build devem ser bloqueados.
3. Confirmar que o scanner analisa histórico e artefatos gerados.
4. Reprovar se o bloqueio depender apenas de alerta ou se houver exclusão ampla de notebooks, prompts ou arquivos de dados.

**Remediation**

Habilitar secret scanning pré-commit e na pipeline, incluir todos os formatos relevantes, bloquear resultados confirmados e substituir segredos reais por referências ao cofre.

**Evidence**

Configuração do scanner, logs de bloqueio e casos de teste com segredos detectados.

**Mappings**

CIS Controls v8 3, 4 e 16; NIST SP 800-53 IA-5, SA-11; OWASP Secrets Management

---

### 1.6 Certifique-se de que ambientes de desenvolvimento e build utilizem dependências bloqueadas por versão e hash

**Control ID:** BAS-005.1.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Projetos Python, JavaScript, Java, Go, Rust, containers, notebooks e ambientes equivalentes utilizados para IA.

**Description**

Dependências diretas e transitivas devem ser resolvidas por lockfile ou manifesto equivalente contendo versões exatas. Quando suportado, cada pacote deve possuir hash ou digest esperado. Intervalos abertos, wildcards, latest e resolução não determinística não são permitidos em builds de release.

**Rationale**

Resolução mutável pode introduzir código diferente sem mudança no repositório e impedir reprodução ou investigação do build.

**Impact**

Atualizações de dependência precisarão ser explícitas e gerar nova revisão do lockfile.

**Audit**

1. Inspecionar manifests e lockfiles utilizados pela pipeline.
2. Confirmar versões exatas para dependências diretas e transitivas e hashes quando suportados.
3. Executar duas instalações limpas usando o mesmo commit e comparar o conjunto de pacotes; os resultados devem ser idênticos.
4. Reprovar se o build aceitar latest, branch remota, intervalo não bloqueado ou pacote sem origem definida.

**Remediation**

Gerar e versionar lockfiles, fixar versões e hashes, e configurar o gerenciador para falhar quando o lockfile estiver ausente ou divergente do manifesto.

**Evidence**

Manifests, lockfiles, relatório de dependências e comparação de instalações reproduzíveis.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 CM-2, SA-10, SI-7

---

## 2. Datasets, prompts e configurações de treinamento e avaliação

Controles de versionamento, linhagem, segregação e validação estrutural dos artefatos que determinam treinamento, avaliação e comportamento do modelo.

### 2.1 Certifique-se de que datasets de treinamento, fine-tuning e avaliação possuam versão imutável e hash verificável

**Control ID:** BAS-005.2.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Datasets usados para treinamento, fine-tuning, alinhamento, benchmark, validação, teste ou segurança.

**Description**

Cada dataset deve ser referenciado por identificador de versão imutável e possuir hash do manifesto ou do conjunto de objetos. O conteúdo de uma versão publicada não pode ser alterado; inclusão, remoção ou transformação deve gerar nova versão.

**Rationale**

Alteração silenciosa do dataset invalida resultados, impede reprodução e pode introduzir dados maliciosos ou não autorizados.

**Impact**

Novas correções exigirão nova versão e poderão aumentar consumo de armazenamento.

**Audit**

1. Selecionar datasets referenciados por releases de modelo e obter identificador e hash registrados.
2. Recalcular o hash a partir dos objetos e confirmar correspondência.
3. Tentar substituir um objeto dentro de versão publicada; a alteração deve ser negada ou gerar nova versão.
4. Reprovar se o dataset for referenciado somente por nome, diretório mutável ou consulta sem snapshot.

**Remediation**

Armazenar datasets em sistema versionado ou snapshot imutável, gerar manifesto com hashes e referenciar a versão exata nos pipelines.

**Evidence**

Manifesto do dataset, hashes recalculados, snapshot e teste de imutabilidade.

**Mappings**

CIS Controls v8 3, 4 e 16; NIST SP 800-53 CM-2, SI-7; NIST AI RMF MAP

---

### 2.2 Certifique-se de que transformações de dados sejam rastreáveis da origem ao dataset resultante

**Control ID:** BAS-005.2.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Pipelines de limpeza, normalização, rotulagem, enriquecimento, deduplicação, filtragem e geração sintética.

**Description**

Cada versão de dataset deve registrar as versões das fontes, do código de transformação, dos parâmetros, do ambiente e do output produzido. Deve ser possível identificar quais entradas e transformações originaram cada artefato final.

**Rationale**

Sem linhagem técnica, não é possível reproduzir o dataset, localizar a origem de erro ou remover conteúdo derivado de uma fonte comprometida.

**Impact**

A captura de linhagem adiciona metadados e pode exigir integração entre armazenamento, orquestração e repositório.

**Audit**

1. Selecionar uma versão de dataset e obter o registro de linhagem.
2. Confirmar que o registro aponta para snapshots de origem, commit do código, parâmetros e ambiente de execução.
3. Reexecutar uma amostra da transformação e comparar hashes ou métricas definidas do resultado.
4. Reprovar se qualquer etapa depender de comando manual, arquivo local ou parâmetro não registrado.

**Remediation**

Instrumentar o pipeline para registrar entradas, código, parâmetros, ambiente e outputs; eliminar transformações manuais fora do fluxo rastreável.

**Evidence**

Grafo ou registro de linhagem, commits, parâmetros de execução e resultado de reexecução.

**Mappings**

CIS Controls v8 3, 4 e 16; NIST SP 800-53 AU-12, CM-3, SA-10; NIST AI RMF MEASURE

---

### 2.3 Certifique-se de que conjuntos de treinamento, validação e teste sejam segregados e protegidos contra contaminação

**Control ID:** BAS-005.2.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Treinamento, fine-tuning, seleção de hiperparâmetros, benchmarks e evals de segurança ou qualidade.

**Description**

Registros usados em teste ou avaliação não podem ser utilizados no treinamento ou ajuste do mesmo release. O particionamento deve ocorrer por identificador estável e, quando houver dados correlacionados, por entidade, período ou grupo capaz de evitar vazamento entre conjuntos.

**Rationale**

Contaminação produz métricas artificialmente elevadas e oculta falhas reais de generalização, segurança e privacidade.

**Impact**

Particionamento mais rigoroso pode reduzir o volume disponível para treinamento e alterar métricas existentes.

**Audit**

1. Obter manifests dos conjuntos de treinamento, validação e teste.
2. Comparar identificadores e hashes e confirmar ausência de interseção não autorizada.
3. Para dados correlacionados, verificar que a chave de agrupamento impede presença da mesma entidade ou evento em conjuntos incompatíveis.
4. Reprovar se a separação ocorrer apenas por sorteio de linhas sem controlar duplicatas, versões ou entidades relacionadas.

**Remediation**

Refazer o particionamento com identificadores estáveis, deduplicar conjuntos, isolar evals sensíveis e regenerar métricas do release.

**Evidence**

Manifests dos conjuntos, relatório de interseção e código de particionamento.

**Mappings**

CIS Controls v8 3 e 16; NIST AI RMF MEASURE; NIST SP 800-53 SA-11

---

### 2.4 Certifique-se de que prompts sistêmicos, policies e parâmetros de geração sejam versionados e fixados por release

**Control ID:** BAS-005.2.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** System prompts, developer prompts, policy prompts, templates, guardrail policies, temperatura, top-p, limites de tokens e parâmetros equivalentes.

**Description**

Cada release deve referenciar versões imutáveis de prompts, policies e parâmetros. Edição direta em console, banco ou interface sem gerar nova versão não é permitida em produção. O identificador efetivo deve ser incluído nos metadados do deployment ou evento de execução.

**Rationale**

Mudanças nesses artefatos alteram comportamento e segurança mesmo sem mudança do modelo, podendo invalidar evals e controles.

**Impact**

Pequenos ajustes exigirão nova versão e execução de testes correspondentes.

**Audit**

1. Exportar prompts, policies e parâmetros efetivos de deployments produtivos.
2. Confirmar que cada item possui versão imutável vinculada ao release.
3. Tentar editar o conteúdo diretamente sem alterar versão; a plataforma deve bloquear ou registrar nova versão.
4. Reprovar se a execução utilizar valor current, latest, default ou conteúdo não recuperável pelo identificador registrado.

**Remediation**

Mover prompts e policies para armazenamento versionado, fixar versões no manifesto de release e desabilitar edição direta em produção.

**Evidence**

Manifestos de release, histórico de prompts/policies e exportação de configuração efetiva.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 CM-2, CM-3; OWASP GenAI Security Project

---

### 2.5 Certifique-se de que tokenizer, adapters e pré-processamento sejam versionados como dependências do modelo

**Control ID:** BAS-005.2.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Modelos que utilizem tokenizer, vocabulary, adapters, LoRA, feature extractors, normalizadores, encoders ou pós-processamento específico.

**Description**

O release do modelo deve referenciar versões exatas e compatíveis de tokenizer, vocabulary, adapters, código de pré-processamento e pós-processamento. A plataforma não pode resolver automaticamente a versão mais recente desses componentes.

**Rationale**

A troca de um componente auxiliar pode alterar tokens, features e resultados mesmo mantendo os mesmos pesos do modelo.

**Impact**

O empacotamento atômico aumenta o tamanho dos releases e exige gestão de compatibilidade.

**Audit**

1. Inspecionar o manifesto de uma amostra de releases.
2. Confirmar versões ou hashes explícitos para tokenizer, adapters e transformações auxiliares.
3. Substituir um componente por versão incompatível em ambiente de teste; startup ou validação deve falhar.
4. Reprovar se qualquer componente for baixado dinamicamente por alias mutável durante a inicialização.

**Remediation**

Adicionar componentes auxiliares ao manifesto atômico do modelo, fixar versões/hashes e validar compatibilidade antes do serving.

**Evidence**

Manifesto do modelo, hashes dos componentes e teste de incompatibilidade bloqueado.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 CM-2, SI-7; ML supply chain security

---

### 2.6 Certifique-se de que manifests técnicos e cards sejam validados por schema antes da criação do release

**Control ID:** BAS-005.2.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Model cards, dataset cards, prompt cards, eval cards, AI BOMs e manifests de release mantidos em formato estruturado.

**Description**

Os metadados técnicos obrigatórios devem ser armazenados em formato estruturado e validados contra schema versionado. A criação do release deve falhar quando campos obrigatórios estiverem ausentes, vazios, fora do tipo esperado ou referenciando versão inexistente.

**Rationale**

Metadados incompletos impedem associar artefatos, testes, limitações e dependências ao release efetivamente implantado.

**Impact**

A validação exige schemas e atualização coordenada quando novos campos forem introduzidos.

**Audit**

1. Obter o schema vigente e os manifests de releases recentes.
2. Executar o validador e confirmar ausência de erros.
3. Remover campo obrigatório e inserir referência inexistente em release de teste; a criação deve ser bloqueada.
4. Reprovar se cards existirem somente como texto livre sem validação ou vínculo técnico com o artefato.

**Remediation**

Definir schemas versionados, integrar validação à pipeline e bloquear release com campos ausentes, inválidos ou referências quebradas.

**Evidence**

Schemas, manifests validados e logs de testes negativos.

**Mappings**

CIS Controls v8 1, 2, 4 e 16; NIST SP 800-53 CM-8, SA-10; NIST AI RMF GOVERN

---

## 3. Modelos, artefatos e registries

Controles para origem permitida, integridade, empacotamento atômico, formatos seguros e imutabilidade dos artefatos de modelo.

### 3.1 Certifique-se de que modelos produtivos sejam carregados somente de registry corporativo permitido

**Control ID:** BAS-005.3.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pesos, checkpoints, adapters, tokenizers e bundles de modelo usados em homologação ou produção.

**Description**

Runtimes e pipelines produtivos devem obter artefatos exclusivamente de registries corporativos ou repositórios explicitamente permitidos. Download direto de marketplace público, URL arbitrária, notebook, estação de trabalho ou bucket pessoal deve ser negado por configuração e rede.

**Rationale**

Artefatos externos podem ser substituídos, removidos ou conter código malicioso e não possuem cadeia de custódia corporativa.

**Impact**

Modelos externos precisarão ser espelhados e registrados internamente antes do uso.

**Audit**

1. Enumerar as origens configuradas nos runtimes e pipelines produtivos.
2. Confirmar que todas correspondem a registries permitidos.
3. Tentar carregar modelo por URL pública ou repositório não permitido; a operação deve falhar antes do download ou load.
4. Reprovar se o runtime possuir egress irrestrito capaz de buscar artefato não registrado.

**Remediation**

Espelhar artefatos externos em registry corporativo, restringir origens por configuração e rede e remover suporte a URLs arbitrárias em produção.

**Evidence**

Configuração de registries, políticas de rede e teste negativo de carregamento externo.

**Mappings**

CIS Controls v8 2, 4, 12 e 16; NIST SP 800-53 CM-7, SA-12, SC-7

---

### 3.2 Certifique-se de que a integridade do artefato seja verificada antes do registro e de cada carregamento

**Control ID:** BAS-005.3.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pesos, checkpoints, adapters, tokenizer bundles, containers de modelo e artefatos equivalentes.

**Description**

O pipeline deve calcular e validar hash criptográfico ou assinatura do artefato antes de registrá-lo. O runtime deve verificar o digest esperado antes de carregar a versão. Divergência deve impedir registro, inicialização ou inferência.

**Rationale**

Sem verificação no registro e no consumo, um artefato pode ser adulterado no transporte, armazenamento ou cache.

**Impact**

A validação aumenta tempo de transferência e inicialização de modelos grandes.

**Audit**

1. Obter o digest registrado para uma amostra de modelos e recalculá-lo a partir do artefato armazenado.
2. Confirmar correspondência e verificar assinatura quando aplicável.
3. Alterar um byte de cópia de teste e tentar registrar e carregar; ambas as ações devem falhar.
4. Reprovar se a plataforma validar somente nome, tamanho ou timestamp.

**Remediation**

Gerar digest ou assinatura na origem confiável, armazená-lo no registry e configurar registro e runtime para rejeitar divergências.

**Evidence**

Digests, assinaturas, logs de verificação e teste de artefato adulterado bloqueado.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 SI-7, SC-13; SLSA provenance

---

### 3.3 Certifique-se de que cada release de modelo seja um bundle atômico e imutável

**Control ID:** BAS-005.3.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Releases compostos por pesos, tokenizer, adapters, configuração, código auxiliar, prompts ou outros arquivos interdependentes.

**Description**

Todos os componentes necessários ao serving devem ser agrupados em um manifesto de release único com versões e digests. O release não pode combinar componentes selecionados dinamicamente de versões diferentes nem permitir substituição parcial após a publicação.

**Rationale**

Mistura de componentes incompatíveis altera o comportamento, cria resultados não reproduzíveis e permite substituir apenas uma parte do modelo avaliado.

**Impact**

O bundle pode aumentar armazenamento e exigir atualização completa para mudanças pequenas.

**Audit**

1. Inspecionar o manifesto de releases produtivos e listar todos os componentes referenciados.
2. Confirmar que cada componente possui digest e que o conjunto é imutável.
3. Tentar substituir somente adapter, tokenizer ou config mantendo o mesmo ID de release; a operação deve ser negada.
4. Reprovar se o runtime resolver componentes separadamente por aliases mutáveis.

**Remediation**

Criar manifesto atômico, fixar digests de todos os componentes e bloquear atualização parcial de release publicado.

**Evidence**

Manifesto do bundle, digests e teste de substituição parcial bloqueado.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 CM-2, CM-3, SI-7

---

### 3.4 Certifique-se de que formatos de serialização capazes de executar código sejam bloqueados ou carregados em sandbox

**Control ID:** BAS-005.3.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Modelos e objetos serializados em pickle, joblib, torch load, custom op, plugin ou formato capaz de materializar código.

**Description**

A plataforma deve permitir somente formatos de dados seguros ou loaders configurados para modo restrito. Quando formato com execução de código for inevitável, a inspeção e conversão devem ocorrer em sandbox isolada, sem credenciais, sem acesso a produção e com egress bloqueado.

**Rationale**

Artefatos serializados podem executar código arbitrário durante o load e comprometer o host antes que o modelo seja avaliado.

**Impact**

Pode exigir conversão de formatos e impedir uso de modelos com operadores customizados não suportados.

**Audit**

1. Listar formatos e loaders permitidos nos pipelines e runtimes.
2. Confirmar bloqueio de formatos executáveis em ambientes não isolados.
3. Tentar carregar artefato de teste com payload de execução; o payload não deve executar e o artefato deve ser rejeitado.
4. Reprovar se o loader utilizar desserialização genérica com privilégios ou credenciais do ambiente produtivo.

**Remediation**

Adotar formatos seguros, habilitar modo weights-only quando disponível e converter formatos arriscados em sandbox sem credenciais e sem rede.

**Evidence**

Allowlist de formatos/loaders, configuração da sandbox e resultado de teste com payload bloqueado.

**Mappings**

CIS Controls v8 4, 10 e 16; NIST SP 800-53 CM-7, SI-3, SI-7; MITRE ATLAS supply chain

---

### 3.5 Certifique-se de que artefatos de modelo sejam inspecionados quanto a arquivos executáveis e conteúdo malicioso

**Control ID:** BAS-005.3.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Bundles de modelos externos ou internos contendo arquivos, bibliotecas, custom ops, scripts, archives ou recursos auxiliares.

**Description**

Antes do registro, o conteúdo deve ser enumerado, descompactado com limites seguros e analisado por malware scanning e regras de tipo. Executáveis, scripts, links simbólicos, caminhos absolutos, path traversal e arquivos não previstos pelo manifesto devem bloquear o registro.

**Rationale**

Bundles podem esconder malware, persistência, scripts de instalação ou arquivos capazes de escapar do diretório de extração.

**Impact**

Modelos legítimos com extensões customizadas podem exigir conversão ou tratamento específico.

**Audit**

1. Revisar regras de inspeção e allowlist de tipos de arquivo.
2. Submeter bundle de teste com executável, link simbólico e entrada ../; todos devem ser bloqueados.
3. Confirmar que a extração impõe limites de tamanho, quantidade e profundidade.
4. Reprovar se o scanner analisar apenas o arquivo compactado sem inspecionar o conteúdo interno.

**Remediation**

Implementar extração segura, enumeração de conteúdo, allowlist de tipos, antimalware e bloqueio de path traversal, links e arquivos não declarados.

**Evidence**

Relatórios de inspeção, configuração de limites e bundles adversariais rejeitados.

**Mappings**

CIS Controls v8 2, 4, 10 e 16; NIST SP 800-53 SI-3, SI-7, SI-10

---

### 3.6 Certifique-se de que versões publicadas no registry sejam imutáveis e protegidas contra exclusão ou sobrescrita não autorizada

**Control ID:** BAS-005.3.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Model registries, artifact registries e storage de pesos ou bundles utilizados por releases.

**Description**

Versões publicadas devem ser write-once ou possuir object lock equivalente. Identidades de build podem criar novas versões, mas não sobrescrever ou excluir versões existentes. Exclusão deve exigir identidade técnica separada e não pode ocorrer enquanto houver referência ativa.

**Rationale**

Sobrescrita ou exclusão permite alterar um release aprovado, quebrar rollback e apagar evidências após comprometimento.

**Impact**

A imutabilidade aumenta consumo de armazenamento e exige política de retenção técnica.

**Audit**

1. Exportar permissões e configuração de imutabilidade do registry.
2. Tentar sobrescrever e excluir versão existente com identidade de build; ambas as ações devem ser negadas.
3. Confirmar que versões referenciadas por deployments possuem proteção contra exclusão.
4. Reprovar se uma mesma identidade puder publicar, sobrescrever e excluir artefatos produtivos.

**Remediation**

Habilitar imutabilidade/object lock, separar permissões de publicação e exclusão e impedir remoção de versões com referência ativa.

**Evidence**

Políticas do registry, configuração de retenção e testes de sobrescrita/exclusão negados.

**Mappings**

CIS Controls v8 3, 4, 5, 6 e 16; NIST SP 800-53 AC-5, CM-5, SI-7

---

## 4. Dependências, containers e proveniência

Controles de software supply chain para pacotes, imagens, BOMs, vulnerabilidades, assinatura, proveniência e isolamento de rede do build.

### 4.1 Certifique-se de que pacotes e imagens sejam obtidos somente de repositórios permitidos

**Control ID:** BAS-005.4.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Builds de treinamento, avaliação, serving, notebooks controlados e containers de IA.

**Description**

Gerenciadores de pacotes e builders devem consultar somente proxies ou registries permitidos. Dependências por URL arbitrária, repositório pessoal, branch Git ou registry público direto devem ser negadas em builds de release.

**Rationale**

Origem não controlada permite dependency confusion, substituição de pacote e inclusão de componente malicioso.

**Impact**

Novas dependências precisarão ser espelhadas ou disponibilizadas no repositório permitido.

**Audit**

1. Inspecionar configurações de package managers, Dockerfiles e builders.
2. Confirmar que todas as origens correspondem à allowlist corporativa.
3. Adicionar dependência de registry público ou URL não permitida em build de teste; o download deve falhar.
4. Reprovar se o builder possuir fallback automático para Internet.

**Remediation**

Configurar proxies internos, remover origens públicas diretas, bloquear egress não permitido e espelhar dependências necessárias.

**Evidence**

Configurações de repositórios, políticas de rede e log de download externo bloqueado.

**Mappings**

CIS Controls v8 2, 4, 12 e 16; NIST SP 800-53 SA-12, CM-7, SC-7

---

### 4.2 Certifique-se de que cada release possua SBOM e AI BOM gerados automaticamente

**Control ID:** BAS-005.4.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Releases de modelos, aplicações de serving, pipelines e soluções de IA empacotadas.

**Description**

A pipeline deve produzir SBOM contendo bibliotecas, pacotes, imagens e sistemas operacionais, e AI BOM contendo modelos, versões, providers, datasets, prompts, adapters e componentes de IA aplicáveis. Os BOMs devem ser vinculados ao digest do release.

**Rationale**

Sem inventário por release, vulnerabilidades ou componentes comprometidos não podem ser localizados de forma rápida e precisa.

**Impact**

A geração e armazenamento dos BOMs adiciona tempo e metadados à pipeline.

**Audit**

1. Selecionar releases produtivos e obter SBOM e AI BOM correspondentes.
2. Confirmar que ambos referenciam o digest exato do release e incluem dependências diretas e transitivas.
3. Adicionar dependência e modelo de teste e confirmar presença automática nos BOMs.
4. Reprovar se o BOM for manual, genérico para o projeto ou não estiver vinculado à versão do artefato.

**Remediation**

Integrar geração automática de SBOM e AI BOM ao build, validar campos mínimos e armazenar os documentos junto ao release.

**Evidence**

SBOM, AI BOM, logs de geração e vínculo com digest do release.

**Mappings**

CIS Controls v8 1, 2 e 16; NIST SP 800-53 CM-8, SA-12; NIST AI RMF MAP

---

### 4.3 Certifique-se de que vulnerabilidades de dependências e imagens bloqueiem releases acima do limite definido

**Control ID:** BAS-005.4.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Bibliotecas, pacotes, containers, sistemas operacionais e componentes nativos incluídos em releases de IA.

**Description**

A pipeline deve analisar dependências e imagens contra bases de vulnerabilidade atualizadas. Vulnerabilidade crítica explorável, malware confirmado ou componente bloqueado deve falhar o build. O critério deve estar configurado como regra técnica e não apenas como relatório informativo.

**Rationale**

Componentes vulneráveis podem comprometer datasets, modelos, credenciais e ambientes de serving.

**Impact**

Releases podem ser atrasados até atualização, substituição ou mitigação técnica do componente.

**Audit**

1. Revisar as regras de severidade, exploitabilidade e componentes bloqueados.
2. Executar build com dependência de teste contendo vulnerabilidade que exceda o limite; o build deve falhar.
3. Confirmar atualização automática das bases do scanner antes da análise.
4. Reprovar se resultados críticos permitirem release sem mecanismo técnico de bloqueio.

**Remediation**

Configurar scanners no build e registry, definir critérios de falha, atualizar bases e remover ou atualizar componentes que excedam o limite.

**Evidence**

Configuração do scanner, relatórios por release e log de build bloqueado.

**Mappings**

CIS Controls v8 7, 10 e 16; NIST SP 800-53 RA-5, SI-2, SA-11

---

### 4.4 Certifique-se de que imagens base e ferramentas de build sejam fixadas por digest imutável

**Control ID:** BAS-005.4.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Dockerfiles, buildpacks, runners, imagens de notebook, ambientes de treinamento e serving.

**Description**

Imagens base, actions, buildpacks e ferramentas executadas pela pipeline devem ser referenciadas por digest ou versão imutável. Tags mutáveis como latest, stable ou major-only não são permitidas em releases.

**Rationale**

Uma tag mutável pode introduzir binário diferente sem alteração de código e comprometer a reprodutibilidade ou a cadeia de build.

**Impact**

Atualizações de base exigirão alteração explícita e novo build.

**Audit**

1. Inspecionar todos os manifests e definições de pipeline.
2. Confirmar uso de digests ou versões imutáveis para imagens e ferramentas externas.
3. Alterar a tag remota em ambiente de teste e confirmar que o build continua usando o digest fixado.
4. Reprovar se qualquer componente executável da pipeline for obtido por referência mutável.

**Remediation**

Substituir tags por digests, fixar versões de actions/buildpacks e automatizar propostas de atualização controlada.

**Evidence**

Dockerfiles/manifests, lista de digests e comparação de builds.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 CM-2, SA-10, SI-7

---

### 4.5 Certifique-se de que artefatos de build sejam assinados e possuam atestação de proveniência

**Control ID:** BAS-005.4.5
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Model bundles, containers, packages e manifests promovidos para ambientes críticos ou externos.

**Description**

A pipeline deve assinar o digest do artefato com identidade de workload e gerar atestação contendo repositório, commit, builder, parâmetros relevantes e dependências. O ambiente de deploy deve verificar assinatura e proveniência antes de aceitar o artefato.

**Rationale**

Assinatura sem proveniência não demonstra como o artefato foi produzido; proveniência sem verificação não impede substituição.

**Impact**

Exige infraestrutura de assinatura, identidade de workload e políticas de verificação no deploy.

**Audit**

1. Selecionar releases produtivos e verificar assinatura e atestação contra a identidade confiável do builder.
2. Confirmar que a atestação referencia o mesmo digest implantado.
3. Tentar implantar artefato sem assinatura, com assinatura inválida ou proveniência de builder não permitido; todas as tentativas devem falhar.
4. Reprovar se a verificação ocorrer apenas na geração e não no ambiente de deploy.

**Remediation**

Configurar assinatura keyless ou com chave protegida, gerar atestação de proveniência e aplicar policy de verificação no registry e no deployment.

**Evidence**

Assinaturas, attestations, políticas de verificação e testes negativos de deploy.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 SI-7, SA-12; SLSA provenance

---

### 4.6 Certifique-se de que builds de release não possuam acesso irrestrito à Internet

**Control ID:** BAS-005.4.6
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Runners, builders e ambientes que criem modelos, containers ou pacotes de produção.

**Description**

Durante o build, egress deve ser bloqueado por padrão e permitido apenas para repositórios, storage e serviços explicitamente necessários. A pipeline não pode baixar scripts ou executar conteúdo remoto arbitrário. Dependências devem ser obtidas por proxies controlados.

**Rationale**

Acesso irrestrito permite exfiltração de segredos, download de payloads e comportamento diferente entre builds.

**Impact**

Pode exigir proxy, mirror e manutenção de allowlist de destinos.

**Audit**

1. Revisar regras de egress do runner e lista de destinos permitidos.
2. Tentar acessar domínio público não permitido e executar curl|shell; a conexão deve ser bloqueada.
3. Confirmar que builds continuam funcionando somente com os repositórios permitidos.
4. Reprovar se o runner possuir rota genérica para Internet ou resolver destino fornecido pelo código do projeto.

**Remediation**

Executar builds em rede isolada, aplicar default deny de egress e disponibilizar dependências por proxies ou mirrors corporativos.

**Evidence**

Regras de rede, allowlist de destinos e logs de conexão bloqueada.

**Mappings**

CIS Controls v8 4, 12 e 16; NIST SP 800-53 SC-7, CM-7, SA-12

---

## 5. Pipelines MLOps, LLMOps e ambientes de build

Controles para identidades, runners, segregação de etapas, configuração declarativa e promoção do mesmo artefato entre ambientes.

### 5.1 Certifique-se de que cada pipeline utilize identidade técnica exclusiva e de curta duração

**Control ID:** BAS-005.5.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pipelines de dados, treinamento, avaliação, registro, promoção e deploy.

**Description**

Cada pipeline e ambiente deve usar identidade de workload distinta. Credenciais devem ser emitidas sob demanda, possuir tempo de vida limitado e não ser reutilizadas por usuários ou pipelines diferentes. Chaves estáticas armazenadas em variáveis de projeto não atendem ao controle.

**Rationale**

Credenciais compartilhadas ampliam o impacto do comprometimento e impedem revogar somente a automação afetada.

**Impact**

Pode exigir federação OIDC, workload identity ou broker de credenciais.

**Audit**

1. Enumerar pipelines e identidades utilizadas em cada ambiente.
2. Confirmar relação exclusiva entre pipeline/ambiente e principal técnico.
3. Inspecionar TTL e origem dos tokens emitidos e verificar ausência de chaves estáticas.
4. Reprovar se a mesma credencial for usada por pessoas, projetos ou ambientes distintos.

**Remediation**

Criar identidades de workload exclusivas, substituir chaves estáticas por tokens temporários e restringir audience e escopo.

**Evidence**

Inventário de pipelines/identidades, claims de tokens mascaradas e configuração de federação.

**Mappings**

CIS Controls v8 5, 6 e 16; NIST SP 800-53 AC-2, IA-5, AC-6

---

### 5.2 Certifique-se de que runners e ambientes de build sejam efêmeros e isolados entre execuções

**Control ID:** BAS-005.5.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Runners de CI/CD, clusters de treinamento, jobs de avaliação e builders que processem código ou artefatos mutáveis.

**Description**

Cada execução deve iniciar em ambiente limpo e ser destruída ou reimaginada ao final. Workspace, cache, credenciais, sockets, volumes e processos não podem ser compartilhados entre projetos ou execuções com níveis de confiança diferentes.

**Rationale**

Persistência entre jobs permite roubo de segredos, adulteração de artefatos e movimentação lateral entre builds.

**Impact**

Ambientes efêmeros podem aumentar tempo de inicialização e reduzir benefício de caches locais.

**Audit**

1. Executar job que grave marcador e secret fictício no workspace e cache.
2. Executar job subsequente em contexto diferente e confirmar que os dados não estão acessíveis.
3. Confirmar destruição ou recriação do runner após cada execução de release.
4. Reprovar se runners compartilhados mantiverem volumes, processos ou credenciais entre jobs.

**Remediation**

Adotar runners efêmeros, limpar caches por escopo, isolar namespaces/VMs e destruir credenciais e volumes ao final do job.

**Evidence**

Configuração de runners, logs de criação/destruição e teste de persistência negativo.

**Mappings**

CIS Controls v8 4, 5 e 16; NIST SP 800-53 SC-2, SC-4, CM-7

---

### 5.3 Certifique-se de que definições de pipeline sejam versionadas e não editáveis diretamente em produção

**Control ID:** BAS-005.5.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Pipelines de orquestração, CI/CD, treinamento, avaliação e deploy.

**Description**

A definição efetiva do pipeline deve ser derivada de arquivo versionado. Edição direta em console ou API produtiva deve ser bloqueada ou reconciliada automaticamente para a versão declarada. O ID do commit deve acompanhar cada execução.

**Rationale**

Alteração fora do repositório pode inserir etapas, remover testes ou trocar destinos sem deixar trilha correspondente no código.

**Impact**

Plataformas que dependem de configuração visual podem exigir exportação declarativa ou reconciliação GitOps.

**Audit**

1. Comparar a definição efetiva da pipeline com o arquivo versionado e confirmar equivalência.
2. Tentar alterar uma etapa diretamente no ambiente produtivo; a operação deve ser negada ou revertida automaticamente.
3. Confirmar que cada execução registra o commit da definição.
4. Reprovar se houver configuração produtiva que não possa ser reconstruída a partir do repositório.

**Remediation**

Migrar a pipeline para definição declarativa, restringir edição direta e habilitar reconciliação ou implantação somente a partir do repositório.

**Evidence**

Arquivo de pipeline, exportação da configuração efetiva e teste de alteração direta bloqueada/revertida.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 CM-2, CM-3, SA-10

---

### 5.4 Certifique-se de que somente a pipeline de release possa implantar ou alterar artefatos em produção

**Control ID:** BAS-005.5.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Model endpoints, registries produtivos, serving clusters, prompts e configurações associadas.

**Description**

Permissões de criação, atualização e remoção de deployments produtivos devem estar limitadas à identidade da pipeline de release. Identidades pessoais, notebooks, ferramentas locais e pipelines de desenvolvimento não podem alterar diretamente esses recursos.

**Rationale**

Acesso direto permite bypass de testes, substituição de artefatos e mudança sem vínculo com um release reproduzível.

**Impact**

Correções emergenciais precisarão utilizar pipeline controlada ou identidade break-glass separada e registrada.

**Audit**

1. Exportar políticas de acesso aos recursos produtivos.
2. Confirmar que a identidade de release possui as operações necessárias e identidades comuns não possuem write/delete.
3. Tentar alterar deployment com identidade de desenvolvedor e notebook; a operação deve ser negada.
4. Reprovar se usuários comuns puderem modificar versão, prompt, config ou endpoint produtivo.

**Remediation**

Remover permissões diretas, criar identidade exclusiva de release e aplicar políticas de negação explícita a usuários e pipelines não produtivos.

**Evidence**

Matriz de permissões e testes negativos de alteração direta.

**Mappings**

CIS Controls v8 5, 6 e 16; NIST SP 800-53 AC-5, AC-6, CM-5

---

### 5.5 Certifique-se de que build, teste e deploy utilizem identidades e permissões segregadas

**Control ID:** BAS-005.5.5
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Pipelines de release para ambientes críticos, regulados ou expostos externamente.

**Description**

A etapa de build pode produzir artefatos, a etapa de teste pode lê-los e publicar resultados, e a etapa de deploy pode promover apenas digests aprovados tecnicamente. Nenhuma identidade deve acumular capacidade de alterar fonte, produzir artefato e implantá-lo sem um ponto de verificação independente.

**Rationale**

Concentração de privilégios permite que comprometimento de uma única etapa altere código, resultado de teste e produção.

**Impact**

A segregação adiciona identidades, storage intermediário e políticas de acesso.

**Audit**

1. Mapear identidades e permissões das etapas de build, teste e deploy.
2. Confirmar que build não pode implantar, teste não pode substituir artefato e deploy não pode reconstruir ou alterar o conteúdo.
3. Executar tentativas cruzadas de escrita e deploy; todas devem ser negadas.
4. Reprovar se uma mesma credencial possuir todas as capacidades em uma única execução.

**Remediation**

Criar identidades separadas por etapa, armazenar artefatos imutáveis entre etapas e limitar cada principal às operações estritamente necessárias.

**Evidence**

Diagrama da pipeline, políticas de acesso e resultados de testes cruzados.

**Mappings**

CIS Controls v8 5, 6 e 16; NIST SP 800-53 AC-5, AC-6, SC-2

---

### 5.6 Certifique-se de que o mesmo digest testado seja promovido entre ambientes sem reconstrução

**Control ID:** BAS-005.5.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Model bundles, containers, packages e manifests promovidos de build para homologação e produção.

**Description**

A pipeline deve construir o artefato uma única vez e promover o mesmo digest entre os ambientes. Rebuild durante a promoção não é permitido. Configurações específicas de ambiente devem ser separadas do artefato e referenciadas de forma versionada.

**Rationale**

Reconstrução pode resolver dependências diferentes ou incorporar conteúdo não testado, mesmo usando o mesmo commit.

**Impact**

Exige registry compartilhado ou mecanismo confiável de cópia por digest.

**Audit**

1. Registrar o digest produzido no build e os digests implantados em homologação e produção.
2. Confirmar igualdade exata entre eles.
3. Inspecionar a pipeline e verificar ausência de etapa de rebuild durante promoção.
4. Reprovar se a promoção gerar novo digest ou baixar novamente dependências mutáveis.

**Remediation**

Separar build e promoção, armazenar artefato imutável em registry e implantar por digest previamente testado.

**Evidence**

Logs de pipeline e mapa de digest entre build, homologação e produção.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 CM-2, SA-10, SI-7; SLSA build principles

---

## 6. Testes, evals e critérios técnicos de release

Controles que vinculam os testes ao artefato exato, estabelecem critérios executáveis e bloqueiam tecnicamente releases que não atendam aos resultados obrigatórios.

### 6.1 Certifique-se de que os testes sejam executados sobre o artefato exato destinado ao deploy

**Control ID:** BAS-005.6.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Model bundles, containers, prompts, policies e configurações que componham um release.

**Description**

A suíte de testes e evals deve receber o mesmo digest e manifesto que serão promovidos. Não é permitido testar um checkpoint, prompt ou container e implantar outro, ainda que possuam o mesmo nome ou versão lógica.

**Rationale**

Diferença entre alvo testado e implantado invalida os resultados e pode introduzir componente não avaliado.

**Impact**

A pipeline precisará empacotar o release antes dos testes e manter o artefato imutável.

**Audit**

1. Obter o digest registrado na execução dos testes e o digest do deployment.
2. Confirmar igualdade exata e vínculo ao mesmo manifesto de release.
3. Tentar substituir artefato após o teste; a promoção deve ser bloqueada por divergência de digest.
4. Reprovar se o relatório indicar apenas nome de modelo, branch ou tag mutável.

**Remediation**

Gerar o artefato antes dos testes, registrar digest nos resultados e bloquear promoção quando o digest divergir.

**Evidence**

Relatórios de testes com digest e comparação com deployment.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 SA-11, CM-3; NIST AI RMF MEASURE

---

### 6.2 Certifique-se de que métricas e limiares de aprovação sejam expressos em configuração executável

**Control ID:** BAS-005.6.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Evals de segurança, qualidade, robustez, privacidade e desempenho executados na pipeline.

**Description**

Cada suíte obrigatória deve possuir métricas, direção, limiar, população e regra de agregação em arquivo versionado e legível por máquina. A pipeline deve calcular o resultado e produzir pass/fail sem depender de interpretação livre do operador.

**Rationale**

Critérios vagos permitem aceitar degradação ou comparar resultados com bases diferentes entre releases.

**Impact**

Nem toda avaliação qualitativa pode ser reduzida a uma única métrica; nesses casos o componente manual deve ser um controle separado.

**Audit**

1. Inspecionar a configuração das suítes e confirmar presença de métrica, limiar e regra de agregação.
2. Alterar resultado de teste para abaixo do limiar e confirmar falha automática.
3. Confirmar que limiares estão versionados junto ao release ou à suíte.
4. Reprovar se o resultado final depender somente de comentário, planilha manual ou decisão sem regra executável.

**Remediation**

Definir critérios em YAML/JSON ou formato equivalente, versionar as regras e integrar cálculo pass/fail à pipeline.

**Evidence**

Arquivos de critérios, resultados calculados e teste de falha abaixo do limiar.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 SA-11; NIST AI RMF MEASURE

---

### 6.3 Certifique-se de que o release execute suíte de segurança compatível com suas capacidades habilitadas

**Control ID:** BAS-005.6.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Releases de modelos, prompts ou soluções com geração, classificação, visão, áudio, RAG, tools ou capacidades equivalentes.

**Description**

A suíte deve testar, conforme as capacidades presentes, prompt injection, jailbreak, bypass de policy, instruções conflitantes, output inseguro, extração de instruções, abuso de contexto e falhas de validação. Capacidades inexistentes podem ser excluídas, mas as capacidades habilitadas devem possuir casos positivos e negativos.

**Rationale**

Sem testes aderentes às capacidades, vulnerabilidades conhecidas podem permanecer ocultas até a produção.

**Impact**

A suíte precisa evoluir quando novas capacidades ou ataques forem adicionados.

**Audit**

1. Mapear capacidades habilitadas no manifesto do release para casos de teste correspondentes.
2. Executar a suíte e verificar que cada capability possui casos adversariais e critérios de aprovação.
3. Injetar uma falha controlada em policy ou prompt e confirmar que ao menos um teste detecta a regressão.
4. Reprovar se capability ativa não possuir cobertura ou se a suíte testar versão diferente do release.

**Remediation**

Adicionar casos adversariais por capability, incluir testes de regressão e vincular a suíte ao manifesto e digest do release.

**Evidence**

Matriz capability-teste, resultados de evals e evidência de detecção de regressão.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SA-11, CA-8; OWASP GenAI Security Project; MITRE ATLAS

---

### 6.4 Certifique-se de que modelos sejam avaliados quanto a memorização, vazamento e extração de dados

**Control ID:** BAS-005.6.4
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Modelos treinados, fine-tuned ou adaptados com dados corporativos, pessoais, sigilosos ou proprietários.

**Description**

Os evals devem tentar recuperar registros, segredos, identificadores, trechos raros e dados de treinamento por prompting direto, indireto e técnicas de extração. O conjunto de canários e casos sensíveis deve ser controlado e o release deve falhar quando exceder o limiar definido.

**Rationale**

Modelos podem memorizar e revelar conteúdo sensível mesmo quando a aplicação não fornece o dado no prompt.

**Impact**

Os testes podem ser custosos e requerem conjunto de canários cuidadosamente protegido.

**Audit**

1. Selecionar canários e amostras sensíveis conhecidos somente pela equipe de teste.
2. Executar ataques de recuperação e extração sobre o release exato.
3. Calcular a taxa conforme critério versionado e confirmar resultado abaixo do limite.
4. Reprovar se o modelo recuperar canário ou dado protegido além do limiar, ou se o teste não cobrir dados usados no treinamento/fine-tuning.

**Remediation**

Remover ou transformar dados de treinamento, aplicar técnicas de redução de memorização, refazer o treinamento e repetir a suíte até atender ao limiar.

**Evidence**

Eval card, conjunto de canários controlado, resultados e reteste.

**Mappings**

CIS Controls v8 3 e 16; NIST AI RMF MEASURE; NIST SP 800-53 PT-2, SA-11

---

### 6.5 Certifique-se de que robustez e consumo de recursos sejam testados nos limites técnicos suportados

**Control ID:** BAS-005.6.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Modelos e serviços sujeitos a variação de tamanho de entrada, concorrência, sequência, mídia ou parâmetros de geração.

**Description**

A suíte deve testar entradas nos limites e acima deles, concorrência máxima prevista, timeouts, cancelamento e consumo de CPU, GPU e memória. O sistema deve rejeitar entradas fora do limite e permanecer dentro dos thresholds de erro, latência e recursos definidos.

**Rationale**

Entradas extremas ou concorrência podem causar exaustão, travamento, indisponibilidade ou custo descontrolado.

**Impact**

Testes de carga consomem recursos e podem exigir ambiente semelhante à produção.

**Audit**

1. Executar casos no limite máximo e acima do limite para cada dimensão suportada.
2. Confirmar rejeição antes do processamento para valores fora do limite.
3. Executar carga concorrente e medir erro, latência, memória e acelerador conforme thresholds versionados.
4. Reprovar se ocorrer crash, OOM, crescimento não limitado ou aceitação de input acima do limite.

**Remediation**

Definir limites técnicos, aplicar validação antes do processamento, ajustar quotas e otimizar ou dimensionar o runtime para atender aos thresholds.

**Evidence**

Resultados de carga, métricas de recursos, thresholds e logs de rejeição.

**Mappings**

CIS Controls v8 4, 13 e 16; NIST SP 800-53 SC-5, SI-13, SA-11

---

### 6.6 Certifique-se de que falhas em testes obrigatórios bloqueiem tecnicamente a promoção do release

**Control ID:** BAS-005.6.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pipelines de release para homologação e produção.

**Description**

A etapa de promoção deve depender de resultados assinados ou protegidos por integridade para todas as suítes obrigatórias. Resultado ausente, expirado, referente a outro digest ou com status fail deve impedir a promoção. A pipeline não pode converter falha em aviso para ambientes produtivos.

**Rationale**

Testes sem enforcement não impedem que artefato inseguro ou não avaliado seja implantado.

**Impact**

Releases serão interrompidos quando infraestrutura de teste estiver indisponível ou resultado não puder ser validado.

**Audit**

1. Inspecionar dependências e condições da etapa de promoção.
2. Forçar falha, ausência, expiração e digest divergente em resultados de teste; cada condição deve bloquear a promoção.
3. Confirmar que identidades de projeto não podem alterar o status final do gate.
4. Reprovar se existir opção de continuar, ignore failure ou caminho alternativo que alcance produção sem todos os resultados válidos.

**Remediation**

Configurar gates obrigatórios por digest, proteger resultados contra alteração e remover caminhos de promoção que não dependam das suítes exigidas.

**Evidence**

Definição da pipeline e logs de promoções bloqueadas por cada condição negativa.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 SA-11, CM-3, CM-5

---

## 7. Deploy, serving e mudança técnica

Controles para fixação de versões, validação no startup, reconciliação, rollout limitado e prevenção de mudanças não rastreadas ou realizadas pelo provider.

### 7.1 Certifique-se de que deployments fixem versões exatas de modelo, runtime, container e configuração

**Control ID:** BAS-005.7.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Endpoints, jobs, batch inference e serviços de serving em homologação ou produção.

**Description**

O manifesto de deployment deve referenciar digests ou versões imutáveis de modelo, container/runtime, prompt, policy e configuração. Aliases mutáveis, auto-resolve e latest não são permitidos. O estado efetivo deve ser consultável após o deploy.

**Rationale**

Referências mutáveis podem alterar o comportamento sem novo release, invalidar evals e impedir rollback determinístico.

**Impact**

Atualizações exigirão alteração explícita do manifesto.

**Audit**

1. Exportar manifests e estado efetivo dos deployments.
2. Confirmar versões/digests explícitos para todos os componentes.
3. Alterar alias remoto e verificar que o deployment não muda automaticamente.
4. Reprovar se qualquer componente for selecionado por latest, default, current ou família sem versão.

**Remediation**

Fixar digests no manifesto, desabilitar resolução automática e implantar por release imutável.

**Evidence**

Manifestos de deployment e exportação do estado efetivo.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 CM-2, CM-3, SI-7

---

### 7.2 Certifique-se de que o runtime valide o digest esperado durante a inicialização

**Control ID:** BAS-005.7.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Runtimes self-hosted, containers e plataformas capazes de expor ou verificar hash do artefato carregado.

**Description**

Antes de ficar ready, o runtime deve calcular ou verificar o digest do modelo e dos componentes críticos contra o manifesto do deployment. Divergência deve impedir readiness e tráfego. O digest efetivo deve ser publicado em health metadata ou logs protegidos.

**Rationale**

Um arquivo pode ser alterado após o deploy ou um cache pode fornecer versão diferente da declarada.

**Impact**

A verificação aumenta o tempo de startup, especialmente para modelos grandes.

**Audit**

1. Iniciar o runtime com artefato válido e confirmar que o digest efetivo corresponde ao manifesto.
2. Substituir o artefato por cópia alterada e reiniciar; readiness deve falhar.
3. Confirmar que tráfego não é roteado antes da validação.
4. Reprovar se a plataforma declarar somente nome ou versão lógica sem verificar o conteúdo.

**Remediation**

Adicionar verificação de digest ao init/readiness, bloquear tráfego em divergência e registrar o digest efetivo.

**Evidence**

Configuração de startup, health metadata e teste com artefato adulterado.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 SI-7, CM-3

---

### 7.3 Certifique-se de que configurações de serving sejam declarativas e reconciliadas continuamente

**Control ID:** BAS-005.7.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Configurações de endpoint, autoscaling, recursos, safety settings, prompts, policies e roteamento do deployment.

**Description**

O estado desejado deve estar em manifesto versionado e um reconciliador deve detectar e reverter alterações fora da fonte declarativa. Parâmetros alteráveis em runtime devem estar limitados a uma lista explícita e não podem modificar controles de segurança.

**Rationale**

Configuração manual gera drift e pode desabilitar limites ou guardrails sem alterar o release.

**Impact**

Pode exigir GitOps, policy as code ou integração adicional com a plataforma.

**Audit**

1. Comparar o estado efetivo com o manifesto versionado.
2. Alterar manualmente parâmetro protegido em ambiente de teste e confirmar bloqueio ou reversão automática.
3. Confirmar geração de alerta de drift com identificação do campo alterado.
4. Reprovar se alterações manuais persistirem sem atualização do manifesto.

**Remediation**

Adotar configuração declarativa, habilitar reconciliação e marcar parâmetros de segurança como não alteráveis em runtime.

**Evidence**

Manifesto, relatório de drift e teste de alteração revertida.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 CM-2, CM-3, CM-6

---

### 7.4 Certifique-se de que releases de maior risco utilizem canary ou shadow com limite técnico de exposição

**Control ID:** BAS-005.7.4
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Mudanças de modelo, provider, prompt, adapter ou pipeline em serviços críticos, externos ou de alto volume.

**Description**

O deployment deve permitir exposição inicial a porcentagem ou conjunto explicitamente limitado de tráfego, sem ampliar automaticamente além do limite antes dos checks configurados. O tráfego canary/shadow deve ser identificável e reversível sem alterar o release estável.

**Rationale**

Falhas de comportamento podem afetar grande população quando a mudança é aplicada integralmente de uma vez.

**Impact**

A estratégia aumenta complexidade, custo e necessidade de comparação de métricas entre versões.

**Audit**

1. Revisar a configuração de rollout e confirmar limite explícito de tráfego ou população.
2. Iniciar release de teste e verificar que o limite não é excedido.
3. Forçar métrica de falha e confirmar interrupção ou rollback sem expansão do tráfego.
4. Reprovar se a plataforma promover automaticamente para 100% sem condições técnicas verificadas.

**Remediation**

Configurar canary/shadow com limite de exposição, métricas de parada e mecanismo automático de reversão.

**Evidence**

Configuração de rollout, métricas por versão e teste de interrupção.

**Mappings**

CIS Controls v8 4, 13 e 16; NIST SP 800-53 CM-3, SI-13; NIST AI RMF MANAGE

---

### 7.5 Certifique-se de que alterações fora da pipeline sejam detectadas e bloqueadas ou revertidas

**Control ID:** BAS-005.7.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Registries, endpoints, deployments, prompts, policies e configurações produtivas.

**Description**

O ambiente deve monitorar alterações por API, console ou credencial não pertencente à pipeline de release. Mudanças não correspondentes a release válido devem ser negadas preventivamente ou revertidas e o recurso deve retornar ao digest/configuração declarada.

**Rationale**

Alteração fora da pipeline pode substituir componentes testados e criar configuração sem evidência associada.

**Impact**

Bloqueio rígido pode afetar troubleshooting e exige um caminho técnico separado para emergência.

**Audit**

1. Executar alteração fora da pipeline com identidade não autorizada; a operação deve ser negada.
2. Quando a plataforma não suportar prevenção, realizar alteração controlada e confirmar detecção e reversão automática.
3. Confirmar correlação do evento com identidade, campo e valor anterior/novo.
4. Reprovar se mudança persistir ou não puder ser associada a um release válido.

**Remediation**

Aplicar políticas de negação a identidades não autorizadas, habilitar drift detection e reconciliação para o release declarado.

**Evidence**

Políticas de acesso, logs de alteração e evidência de bloqueio ou reversão.

**Mappings**

CIS Controls v8 4, 5, 6 e 16; NIST SP 800-53 CM-3, CM-5, AU-12

---

### 7.6 Certifique-se de que atualização automática de modelo por provider esteja desabilitada ou detectada antes do uso

**Control ID:** BAS-005.7.6
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Serviços gerenciados em que o provider possa alterar pesos, versão, endpoint, safety settings ou comportamento sem novo deployment do cliente.

**Description**

Quando houver versionamento imutável, o deployment deve fixar a versão. Quando isso não for possível, a solução deve detectar alteração do identificador ou comportamento e impedir uso produtivo até executar a suíte técnica mínima sobre a nova versão. Alias flutuante sem detecção não atende ao controle.

**Rationale**

Mudança unilateral do provider pode introduzir regressão, incompatibilidade ou alteração de segurança sem modificação local.

**Impact**

Pode exigir endpoint versionado, monitor sintético e fallback para versão ou provider alternativo.

**Audit**

1. Revisar as opções de versionamento e atualização do provider.
2. Confirmar pin de versão ou mecanismo de detecção por metadata e testes sintéticos.
3. Simular mudança de versão/identificador e verificar bloqueio do tráfego ou execução automática da suíte antes da liberação.
4. Reprovar se o serviço consumir alias mutável sem registrar e reagir à mudança.

**Remediation**

Fixar versão quando suportado; caso contrário, implementar detecção, bloqueio e reavaliação técnica antes de usar a versão alterada.

**Evidence**

Configuração do deployment, eventos de mudança e teste de bloqueio/reavaliação.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 CM-3, SA-9; NIST AI RMF MANAGE

---

## 8. Rollback, descontinuação e descarte técnico

Controles para reversão determinística, retirada completa de versões, revogação de acessos e eliminação de referências ou cópias residuais.

### 8.1 Certifique-se de que exista release anterior conhecido e tecnicamente apto para rollback

**Control ID:** BAS-005.8.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Deployments de IA em homologação ou produção que possam receber atualização de modelo, prompt, policy, container ou configuração.

**Description**

O ambiente deve manter pelo menos um release anterior íntegro, com artefatos, manifests, configurações e dependências acessíveis. O release de rollback deve ter digest conhecido e não pode depender de origem externa mutável ou rebuild.

**Rationale**

Sem release preservado, uma falha pode exigir reconstrução demorada ou retorno a versão não testada.

**Impact**

A retenção consome armazenamento e pode manter componentes antigos que exigem proteção contra vulnerabilidades.

**Audit**

1. Identificar o release atual e o release configurado para rollback.
2. Confirmar que todos os artefatos e manifests do release anterior estão disponíveis e passam na verificação de integridade.
3. Confirmar que o rollback utiliza digest existente e não executa rebuild.
4. Reprovar se a versão anterior depender de tag mutável, download externo ou artefato removido.

**Remediation**

Preservar release conhecido em registry imutável, manter manifesto completo e configurar o deployment para revertê-lo por digest.

**Evidence**

Manifesto de rollback, digests e verificação de disponibilidade dos artefatos.

**Mappings**

CIS Controls v8 3, 4 e 16; NIST SP 800-53 CP-10, CM-2, SI-7

---

### 8.2 Certifique-se de que o rollback seja testado de ponta a ponta e atenda ao tempo técnico definido

**Control ID:** BAS-005.8.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Serviços produtivos ou críticos com atualização de modelos e configurações.

**Description**

O teste deve reverter modelo, container, prompts, policies, schemas e rotas para o release anterior, confirmar readiness e executar casos funcionais mínimos. O tempo entre acionamento e restauração deve ser medido contra o limite técnico documentado.

**Rationale**

Um rollback não testado pode falhar por incompatibilidade de schema, artefato ausente ou dependência externa alterada.

**Impact**

O teste requer janela ou ambiente representativo e pode consumir capacidade adicional.

**Audit**

1. Executar rollback em ambiente representativo usando o mecanismo produtivo.
2. Confirmar retorno de todos os componentes ao digest anterior e ausência de referências ao release falho.
3. Executar health checks e casos mínimos e medir o tempo total.
4. Reprovar se qualquer componente permanecer na versão nova, se o serviço não ficar ready ou se o tempo exceder o limite definido.

**Remediation**

Corrigir manifests e compatibilidades, preservar dependências necessárias e automatizar o mecanismo até o teste completo atender ao limite.

**Evidence**

Logs do teste, digests antes/depois, resultados funcionais e medição de tempo.

**Mappings**

CIS Controls v8 11, 13 e 16; NIST SP 800-53 CP-4, CP-10, SI-13

---

### 8.3 Certifique-se de que modelos descontinuados não possam receber novas requisições

**Control ID:** BAS-005.8.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Modelos, endpoints, aliases, rotas e deployments marcados como descontinuados ou substituídos.

**Description**

A descontinuação deve remover o modelo de rotas, aliases, service discovery e allowlists de consumo. Chamadas diretas ao endpoint antigo devem retornar bloqueio e não executar inferência. O artefato pode permanecer retido, mas não deve estar servível.

**Rationale**

Rotas esquecidas permitem uso de versão vulnerável, não monitorada ou fora do suporte.

**Impact**

Clientes que ainda dependam da versão antiga deixarão de funcionar até migração.

**Audit**

1. Enumerar rotas e endpoints associados à versão descontinuada.
2. Confirmar ausência em aliases, discovery e allowlists.
3. Tentar chamada direta e indireta ao modelo; ambas devem ser negadas sem inferência.
4. Reprovar se qualquer rota produtiva ainda alcançar o artefato descontinuado.

**Remediation**

Remover bindings, rotas, aliases e discovery; desabilitar o deployment e aplicar deny explícito ao identificador descontinuado.

**Evidence**

Exportação de rotas/allowlists e logs de tentativas bloqueadas.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 CM-7, CM-8, SI-2

---

### 8.4 Certifique-se de que credenciais e permissões associadas a pipelines e deployments descontinuados sejam revogadas

**Control ID:** BAS-005.8.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Identidades de workload, chaves, tokens, certificados, roles e service accounts de componentes retirados de operação.

**Description**

Ao desativar pipeline, endpoint ou modelo, suas identidades e credenciais devem ser revogadas ou desabilitadas. Policies, trust relationships e bindings exclusivos devem ser removidos. Credenciais não podem permanecer válidas apenas porque o artefato foi desligado.

**Rationale**

Uma identidade órfã pode ser reutilizada para acessar dados, registries ou sistemas sem componente legítimo em operação.

**Impact**

Dependências ocultas que utilizem a mesma identidade podem ser interrompidas, evidenciando compartilhamento indevido.

**Audit**

1. Listar identidades e credenciais vinculadas ao componente descontinuado.
2. Confirmar status revogado/desabilitado e remoção de bindings exclusivos.
3. Tentar autenticação e acesso com credencial anterior; a operação deve falhar.
4. Reprovar se qualquer token, chave ou trust relationship permanecer funcional após a descontinuação.

**Remediation**

Revogar chaves e tokens, desabilitar identidades, remover roles/bindings e corrigir componentes que compartilhem credenciais.

**Evidence**

Inventário de identidades, logs de revogação e teste de autenticação negado.

**Mappings**

CIS Controls v8 5, 6 e 16; NIST SP 800-53 AC-2, IA-5, PS-4

---

### 8.5 Certifique-se de que artefatos temporários, caches e cópias de modelos retirados sejam eliminados dos ambientes de execução

**Control ID:** BAS-005.8.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Workers, nodes, volumes, caches, notebooks, buckets temporários e áreas de staging usadas para build, treinamento ou serving.

**Description**

Após a retirada, cópias não necessárias de pesos, datasets intermediários, prompts, tokens e bundles devem ser removidas de caches e volumes temporários. A retenção necessária deve permanecer somente em repositório controlado e protegido.

**Rationale**

Cópias residuais ampliam a superfície de exposição, podem conter propriedade intelectual e permitem reativação não controlada.

**Impact**

A limpeza pode aumentar tempo de novos deployments por eliminar caches reutilizáveis.

**Audit**

1. Identificar caminhos de cache, staging e volumes utilizados pelo release descontinuado.
2. Executar busca por digest, nome e identificador do artefato após a limpeza.
3. Confirmar ausência de cópias fora do registry de retenção permitido.
4. Reprovar se workers, volumes ou notebooks mantiverem cópias acessíveis do artefato retirado.

**Remediation**

Limpar caches e volumes, recriar workers quando necessário e restringir retenção ao registry corporativo definido.

**Evidence**

Relatório de busca pós-limpeza, logs de exclusão e inventário do local de retenção autorizado.

**Mappings**

CIS Controls v8 3, 4 e 16; NIST SP 800-53 MP-6, SI-12, CM-8

---

### 8.6 Certifique-se de que não existam referências ativas a versões retiradas e que sua reativação automática seja impedida

**Control ID:** BAS-005.8.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Pipelines, schedules, jobs, endpoints, aliases, manifests, configs, notebooks e automações que possam referenciar modelos ou releases.

**Description**

Antes de concluir a retirada, uma busca técnica deve confirmar ausência de referências ativas ao identificador ou digest. Schedules, auto-healing e reconciliação não podem recriar o deployment. O identificador retirado deve estar em denylist ou estado não promovível no registry.

**Rationale**

Referência esquecida pode recriar ou voltar a chamar a versão descontinuada após restart, rollback automático ou execução agendada.

**Impact**

Pode exigir atualização de pipelines legadas e manifests históricos usados por automações.

**Audit**

1. Pesquisar o identificador e digest em repositórios, manifests, schedules, deployment configs e registries.
2. Confirmar ausência de referência ativa e estado não promovível no registry.
3. Executar reconciliadores e jobs agendados em ambiente de teste; a versão não deve ser recriada.
4. Reprovar se qualquer automação puder promover ou reconstruir a versão retirada.

**Remediation**

Remover referências ativas, atualizar schedules/manifests, marcar o release como bloqueado e adicionar denylist de promoção quando suportado.

**Evidence**

Relatório de referências, status do registry e teste de não recriação.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 CM-3, CM-8, SI-2

---
