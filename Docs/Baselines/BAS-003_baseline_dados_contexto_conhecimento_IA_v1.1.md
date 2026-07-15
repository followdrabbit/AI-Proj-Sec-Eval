# BAS-003 — Baseline de Controles Técnicos para Dados, Contexto e Conhecimento em Inteligência Artificial

| Campo | Valor |
|---|---|
| **Código** | BAS-003 |
| **Nome** | Baseline de Controles Técnicos para Dados, Contexto e Conhecimento em IA |
| **Tipo documental** | Baseline técnico |
| **Classificação da informação** | Uso Interno |
| **Status** | Minuta para revisão |
| **Versão** | 1.1 |
| **Data** | 13/07/2026 |
| **Owner institucional** | Segurança da Informação / Segurança de IA |
| **Custodiante técnico** | Arquitetura de Segurança da Informação / Arquitetura de Dados |
| **Quantidade de controles** | 48 |

## 1. Objetivo

Estabelecer recomendações técnicas mínimas, verificáveis e auditáveis para proteger dados, fontes de conhecimento, pipelines de ingestão, mecanismos de recuperação de contexto, embeddings, índices, bases de conhecimento, memória e artefatos derivados utilizados por soluções de Inteligência Artificial. O documento segue a estrutura de recomendações dos CIS Benchmarks e contém somente controles técnicos. Fluxos de aprovação, homologação, classificação de risco, exceções, RACI, privacidade processual e resposta operacional estão fora do escopo.

## 2. Escopo

Aplica-se a pipelines de ingestão, crawlers, conectores, parsers, OCR, chunking, embeddings, busca lexical, semântica ou híbrida, vector stores, search indexes, knowledge graphs, rerankers, grounding, bases de conhecimento, memória persistente, caches semânticos e mecanismos equivalentes. Este baseline não deve ser aplicado isoladamente: o BAS-001 e o BAS-002 permanecem aplicáveis, e os demais baselines especializados devem ser combinados cumulativamente conforme a arquitetura avaliada.

## 3. Modelo de classificação

### 3.1 Profile Applicability

- **Level 1:** configuração técnica fundamental para qualquer implementação no escopo deste baseline.
- **Level 2:** defesa em profundidade para dados sensíveis, ambientes críticos, conteúdo externo, múltiplos tenants, agentes ou decisões de impacto material. Pressupõe conformidade com os controles Level 1 aplicáveis.

### 3.2 Criticidade

| Criticidade | Critério |
|---|---|
| **Crítica** | A ausência permite exposição direta de dados, recuperação entre tenants, bypass de autorização, poisoning com impacto material ou impossibilidade de revogação e exclusão. |
| **Alta** | A ausência enfraquece significativamente integridade, confidencialidade, lineage, retenção ou capacidade de contenção. |
| **Média** | Controle de hardening ou qualidade de segurança cuja ausência normalmente exige outra falha para produzir impacto material. |
| **Baixa** | Otimização técnica com impacto limitado. Esta versão não contém recomendações de criticidade Baixa. |

## 4. Regras de interpretação

1. O BAS-001 e o BAS-002 são pré-requisitos quando aplicáveis aos componentes cobertos por este documento.
2. Cada recomendação deve ser avaliada de forma independente.
3. Um controle é **Conforme** somente quando todos os critérios descritos em **Audit** forem atendidos.
4. Implementação parcial deve ser registrada como **Não Conforme**; não existe conformidade parcial neste baseline.
5. Quando uma recomendação não se aplicar tecnicamente, a justificativa deve indicar a característica arquitetural inexistente.
6. Aprovações, pareceres e controles processuais não substituem os requisitos técnicos deste documento.

## Sumário

- [1. Fontes, ingestão e elegibilidade](#1-fontes-ingestao-e-elegibilidade)
  - [1.1 Certifique-se de que somente fontes explicitamente permitidas possam alimentar a base de conhecimento](#11-certifique-se-de-que-somente-fontes-explicitamente-permitidas-possam-alimentar-a-base-de-conhecimento)
  - [1.2 Certifique-se de que a identidade e a integridade da fonte sejam verificadas antes da ingestão](#12-certifique-se-de-que-a-identidade-e-a-integridade-da-fonte-sejam-verificadas-antes-da-ingestao)
  - [1.3 Certifique-se de que arquivos ingeridos sejam validados por tipo real, tamanho e estrutura](#13-certifique-se-de-que-arquivos-ingeridos-sejam-validados-por-tipo-real-tamanho-e-estrutura)
  - [1.4 Certifique-se de que conteúdo ingerido seja inspecionado contra malware e conteúdo ativo](#14-certifique-se-de-que-conteudo-ingerido-seja-inspecionado-contra-malware-e-conteudo-ativo)
  - [1.5 Certifique-se de que dados proibidos sejam detectados e bloqueados antes da persistência](#15-certifique-se-de-que-dados-proibidos-sejam-detectados-e-bloqueados-antes-da-persistencia)
  - [1.6 Certifique-se de que a ingestão seja idempotente e impeça duplicação não controlada de conteúdo](#16-certifique-se-de-que-a-ingestao-seja-idempotente-e-impeca-duplicacao-nao-controlada-de-conteudo)
- [2. Transformação, parsing e metadados](#2-transformacao-parsing-e-metadados)
  - [2.1 Certifique-se de que regras de parsing, chunking e enriquecimento sejam versionadas e imutáveis por execução](#21-certifique-se-de-que-regras-de-parsing-chunking-e-enriquecimento-sejam-versionadas-e-imutaveis-por-execucao)
  - [2.2 Certifique-se de que cada derivado preserve metadados mínimos de origem e classificação](#22-certifique-se-de-que-cada-derivado-preserve-metadados-minimos-de-origem-e-classificacao)
  - [2.3 Certifique-se de que a classificação do derivado seja igual ou mais restritiva que a fonte](#23-certifique-se-de-que-a-classificacao-do-derivado-seja-igual-ou-mais-restritiva-que-a-fonte)
  - [2.4 Certifique-se de que texto oculto, metadados e comentários sejam tratados explicitamente](#24-certifique-se-de-que-texto-oculto-metadados-e-comentarios-sejam-tratados-explicitamente)
  - [2.5 Certifique-se de que chunks mantenham limites semânticos e não combinem domínios de autorização diferentes](#25-certifique-se-de-que-chunks-mantenham-limites-semanticos-e-nao-combinem-dominios-de-autorizacao-diferentes)
  - [2.6 Certifique-se de que dados estruturados sejam extraídos por schema e não por interpretação livre do modelo](#26-certifique-se-de-que-dados-estruturados-sejam-extraidos-por-schema-e-nao-por-interpretacao-livre-do-modelo)
- [3. Embeddings, índices e armazenamento](#3-embeddings-indices-e-armazenamento)
  - [3.1 Certifique-se de que embeddings e índices sejam tratados com a mesma proteção dos dados de origem](#31-certifique-se-de-que-embeddings-e-indices-sejam-tratados-com-a-mesma-protecao-dos-dados-de-origem)
  - [3.2 Certifique-se de que índices de ambientes diferentes sejam fisicamente ou logicamente isolados](#32-certifique-se-de-que-indices-de-ambientes-diferentes-sejam-fisicamente-ou-logicamente-isolados)
  - [3.3 Certifique-se de que o isolamento entre tenants seja imposto pelo store e pela identidade autenticada](#33-certifique-se-de-que-o-isolamento-entre-tenants-seja-imposto-pelo-store-e-pela-identidade-autenticada)
  - [3.4 Certifique-se de que o modelo de embedding e seus parâmetros estejam fixados por índice](#34-certifique-se-de-que-o-modelo-de-embedding-e-seus-parametros-estejam-fixados-por-indice)
  - [3.5 Certifique-se de que interfaces administrativas do store não sejam acessíveis por identidades de consulta](#35-certifique-se-de-que-interfaces-administrativas-do-store-nao-sejam-acessiveis-por-identidades-de-consulta)
  - [3.6 Certifique-se de que backups e réplicas preservem segregação, criptografia e exclusões](#36-certifique-se-de-que-backups-e-replicas-preservem-segregacao-criptografia-e-exclusoes)
- [4. Autorização, segregação e recuperação permitida](#4-autorizacao-segregacao-e-recuperacao-permitida)
  - [4.1 Certifique-se de que a autorização seja aplicada antes da busca e do cálculo de similaridade](#41-certifique-se-de-que-a-autorizacao-seja-aplicada-antes-da-busca-e-do-calculo-de-similaridade)
  - [4.2 Certifique-se de que permissões da fonte sejam propagadas para documentos, chunks e índices](#42-certifique-se-de-que-permissoes-da-fonte-sejam-propagadas-para-documentos-chunks-e-indices)
  - [4.3 Certifique-se de que a finalidade e o caso de uso restrinjam tecnicamente o escopo recuperável](#43-certifique-se-de-que-a-finalidade-e-o-caso-de-uso-restrinjam-tecnicamente-o-escopo-recuperavel)
  - [4.4 Certifique-se de que filtros de autorização não possam ser substituídos por filtros fornecidos pelo usuário](#44-certifique-se-de-que-filtros-de-autorizacao-nao-possam-ser-substituidos-por-filtros-fornecidos-pelo-usuario)
  - [4.5 Certifique-se de que consultas administrativas e de depuração não ignorem controles de acesso](#45-certifique-se-de-que-consultas-administrativas-e-de-depuracao-nao-ignorem-controles-de-acesso)
  - [4.6 Certifique-se de que a revogação de acesso interrompa novas recuperações dentro do prazo técnico definido](#46-certifique-se-de-que-a-revogacao-de-acesso-interrompa-novas-recuperacoes-dentro-do-prazo-tecnico-definido)
- [5. Retrieval, ranking e montagem de contexto](#5-retrieval-ranking-e-montagem-de-contexto)
  - [5.1 Certifique-se de que limites de top-k, tamanho e tokens de contexto sejam impostos pelo servidor](#51-certifique-se-de-que-limites-de-top-k-tamanho-e-tokens-de-contexto-sejam-impostos-pelo-servidor)
  - [5.2 Certifique-se de que a consulta seja normalizada e validada antes da busca](#52-certifique-se-de-que-a-consulta-seja-normalizada-e-validada-antes-da-busca)
  - [5.3 Certifique-se de que rerankers recebam somente candidatos já autorizados](#53-certifique-se-de-que-rerankers-recebam-somente-candidatos-ja-autorizados)
  - [5.4 Certifique-se de que contexto recuperado seja delimitado como dado não confiável](#54-certifique-se-de-que-contexto-recuperado-seja-delimitado-como-dado-nao-confiavel)
  - [5.5 Certifique-se de que o contexto preserve referências verificáveis à fonte e versão](#55-certifique-se-de-que-o-contexto-preserve-referencias-verificaveis-a-fonte-e-versao)
  - [5.6 Certifique-se de que resultados abaixo do limiar mínimo de relevância não sejam enviados ao modelo](#56-certifique-se-de-que-resultados-abaixo-do-limiar-minimo-de-relevancia-nao-sejam-enviados-ao-modelo)
- [6. Proteção contra poisoning e conteúdo adversarial](#6-protecao-contra-poisoning-e-conteudo-adversarial)
  - [6.1 Certifique-se de que fontes com níveis de confiança diferentes permaneçam separadas](#61-certifique-se-de-que-fontes-com-niveis-de-confianca-diferentes-permanecam-separadas)
  - [6.2 Certifique-se de que alterações anômalas na fonte ou no índice sejam detectadas antes da publicação](#62-certifique-se-de-que-alteracoes-anomalas-na-fonte-ou-no-indice-sejam-detectadas-antes-da-publicacao)
  - [6.3 Certifique-se de que conteúdo contenha detecção de instruções adversariais antes da indexação](#63-certifique-se-de-que-conteudo-contenha-deteccao-de-instrucoes-adversariais-antes-da-indexacao)
  - [6.4 Certifique-se de que conteúdo recuperado não possa alterar tools, modelos, rotas ou políticas](#64-certifique-se-de-que-conteudo-recuperado-nao-possa-alterar-tools-modelos-rotas-ou-politicas)
  - [6.5 Certifique-se de que o pipeline impeça SSRF e acesso a endereços internos durante captura de conteúdo](#65-certifique-se-de-que-o-pipeline-impeca-ssrf-e-acesso-a-enderecos-internos-durante-captura-de-conteudo)
  - [6.6 Certifique-se de que versões de índice possam ser comparadas e revertidas sem mesclar conteúdo suspeito](#66-certifique-se-de-que-versoes-de-indice-possam-ser-comparadas-e-revertidas-sem-mesclar-conteudo-suspeito)
- [7. Memória, caches e dados derivados em execução](#7-memoria-caches-e-dados-derivados-em-execucao)
  - [7.1 Certifique-se de que memória conversacional seja isolada por usuário, sessão, tenant e aplicação](#71-certifique-se-de-que-memoria-conversacional-seja-isolada-por-usuario-sessao-tenant-e-aplicacao)
  - [7.2 Certifique-se de que somente campos explicitamente permitidos sejam gravados em memória persistente](#72-certifique-se-de-que-somente-campos-explicitamente-permitidos-sejam-gravados-em-memoria-persistente)
  - [7.3 Certifique-se de que caches semânticos sejam particionados e autorizados antes do retorno](#73-certifique-se-de-que-caches-semanticos-sejam-particionados-e-autorizados-antes-do-retorno)
  - [7.4 Certifique-se de que TTL e invalidação de cache não excedam a validade da fonte ou da autorização](#74-certifique-se-de-que-ttl-e-invalidacao-de-cache-nao-excedam-a-validade-da-fonte-ou-da-autorizacao)
  - [7.5 Certifique-se de que dados temporários sejam removidos após a conclusão da execução](#75-certifique-se-de-que-dados-temporarios-sejam-removidos-apos-a-conclusao-da-execucao)
  - [7.6 Certifique-se de que respostas não exponham contexto bruto, scores ou metadados restritos](#76-certifique-se-de-que-respostas-nao-exponham-contexto-bruto-scores-ou-metadados-restritos)
- [8. Retenção, exclusão, sincronização e recuperação](#8-retencao-exclusao-sincronizacao-e-recuperacao)
  - [8.1 Certifique-se de que cada tipo de artefato possua retenção técnica configurada](#81-certifique-se-de-que-cada-tipo-de-artefato-possua-retencao-tecnica-configurada)
  - [8.2 Certifique-se de que exclusões na fonte removam todos os derivados relacionados](#82-certifique-se-de-que-exclusoes-na-fonte-removam-todos-os-derivados-relacionados)
  - [8.3 Certifique-se de que correções e novas versões não mantenham conteúdo obsoleto ativo](#83-certifique-se-de-que-correcoes-e-novas-versoes-nao-mantenham-conteudo-obsoleto-ativo)
  - [8.4 Certifique-se de que falhas de sincronização não publiquem estado parcial ou permissões desatualizadas](#84-certifique-se-de-que-falhas-de-sincronizacao-nao-publiquem-estado-parcial-ou-permissoes-desatualizadas)
  - [8.5 Certifique-se de que a perda da fonte de autorização resulte em bloqueio da recuperação](#85-certifique-se-de-que-a-perda-da-fonte-de-autorizacao-resulte-em-bloqueio-da-recuperacao)
  - [8.6 Certifique-se de que a restauração reconstrua índices a partir de fontes e configurações verificadas](#86-certifique-se-de-que-a-restauracao-reconstrua-indices-a-partir-de-fontes-e-configuracoes-verificadas)

## 1. Fontes, ingestão e elegibilidade

Controles para restringir origens, validar arquivos e impedir que conteúdo não autorizado, malicioso ou proibido entre na cadeia de conhecimento.

### 1.1 Certifique-se de que somente fontes explicitamente permitidas possam alimentar a base de conhecimento

**Control ID:** BAS-003.1.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pipelines de ingestão, conectores, crawlers, uploads, APIs e sincronizações que enviem conteúdo para RAG ou bases de conhecimento.

**Description**

O pipeline deve utilizar allowlist explícita de repositórios, buckets, sites, bancos, APIs, filas, diretórios e conectores. Qualquer origem não cadastrada deve ser negada antes da leitura ou persistência. Wildcards amplos, descoberta automática irrestrita e URLs fornecidas livremente pelo usuário não atendem ao controle.

**Rationale**

A ingestão de origem não autorizada permite incorporar dados sigilosos, conteúdo malicioso, documentos falsos ou material sem direito de uso, comprometendo confidencialidade e integridade do contexto.

**Impact**

Novas fontes exigirão inclusão na configuração técnica da allowlist e podem reduzir a flexibilidade de conectores genéricos.

**Audit**

1. Exportar a configuração de todos os conectores e origens habilitadas.
2. Confirmar que cada origem corresponde a entrada explícita e específica da allowlist.
3. Tentar ingerir conteúdo a partir de origem não cadastrada; a operação deve ser bloqueada antes do download ou leitura.
4. Reprovar se o pipeline aceitar URL, caminho, bucket, repositório ou datasource arbitrário fornecido pelo solicitante.

**Remediation**

Configurar allowlist por conector e bloquear descoberta ou resolução de origens não cadastradas. Remover wildcards amplos e negar origens desconhecidas por padrão.

**Evidence**

Configuração de conectores, allowlist de fontes e resultado de teste negativo com origem não permitida.

**Mappings**

CIS Controls v8 3, 4 e 13; NIST SP 800-53 AC-4, CM-7, SI-10; OWASP LLM Top 10 LLM08

---

### 1.2 Certifique-se de que a identidade e a integridade da fonte sejam verificadas antes da ingestão

**Control ID:** BAS-003.1.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Fontes internas ou externas consumidas por API, repositório, storage, feed, crawler ou transferência de arquivo.

**Description**

Antes da ingestão, o pipeline deve autenticar a fonte e verificar integridade por mecanismo adequado ao canal, como TLS validado, assinatura digital, checksum publicado, commit assinado, object version ID ou hash registrado. O identificador da versão verificada deve acompanhar o conteúdo ingerido.

**Rationale**

Sem autenticação e integridade, um atacante pode substituir documentos, inserir conteúdo adulterado ou redirecionar o pipeline para uma origem controlada.

**Impact**

A validação pode exigir suporte a assinatura, versionamento ou metadados adicionais na origem.

**Audit**

1. Selecionar amostra representativa de cada tipo de fonte habilitada.
2. Confirmar que a conexão autentica a origem e rejeita certificado, assinatura, hash ou versão inválida.
3. Alterar um arquivo ou resposta após o cálculo do hash e executar nova ingestão; o conteúdo adulterado deve ser rejeitado.
4. Confirmar que a versão, hash ou identificador de objeto verificado é persistido junto aos metadados do item.

**Remediation**

Habilitar validação TLS completa, assinatura ou checksum e persistir o identificador de integridade com cada item. Bloquear ingestão quando a verificação falhar ou estiver ausente.

**Evidence**

Configuração de autenticação da fonte, hashes/assinaturas, metadados de versão e teste de adulteração rejeitado.

**Mappings**

CIS Controls v8 3, 4 e 16; NIST SP 800-53 SC-8, SC-13, SI-7; SLSA provenance principles

---

### 1.3 Certifique-se de que arquivos ingeridos sejam validados por tipo real, tamanho e estrutura

**Control ID:** BAS-003.1.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Pipelines que processem arquivos, anexos, documentos, imagens, planilhas, apresentações, PDFs, arquivos compactados ou formatos equivalentes.

**Description**

O pipeline deve validar o tipo real por assinatura de arquivo ou parser, não apenas por extensão ou Content-Type. Deve impor allowlist de formatos, tamanho máximo descompactado, quantidade máxima de objetos internos, profundidade de arquivo compactado e limites de páginas, planilhas ou elementos conforme o parser.

**Rationale**

Arquivos malformados, poliglotas ou bombas de descompressão podem explorar parsers, consumir recursos ou ocultar conteúdo não autorizado.

**Impact**

Alguns documentos legítimos acima dos limites definidos serão rejeitados ou exigirão tratamento separado.

**Audit**

1. Revisar a configuração de formatos e limites do pipeline.
2. Enviar arquivo com extensão permitida e assinatura incompatível; a ingestão deve ser negada.
3. Enviar arquivo compactado que exceda tamanho, quantidade de itens ou profundidade permitida após descompressão; a ingestão deve ser bloqueada.
4. Reprovar se o pipeline confiar exclusivamente em extensão, nome ou Content-Type informado pelo cliente.

**Remediation**

Implementar identificação de tipo por conteúdo, parsers seguros e limites de tamanho, páginas, objetos e descompressão. Rejeitar arquivos fora da allowlist antes de qualquer extração.

**Evidence**

Configuração de formatos e limites, logs de bloqueio e arquivos de teste rejeitados.

**Mappings**

CIS Controls v8 4, 10 e 16; NIST SP 800-53 SI-3, SI-10; OWASP File Upload Cheat Sheet

---

### 1.4 Certifique-se de que conteúdo ingerido seja inspecionado contra malware e conteúdo ativo

**Control ID:** BAS-003.1.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pipelines que aceitem arquivos, páginas, anexos ou objetos provenientes de usuários, terceiros ou fontes externas.

**Description**

Todo conteúdo deve ser submetido a antimalware atualizado e inspeção de conteúdo ativo antes do parsing completo ou indexação. Macros, scripts, objetos incorporados, formulários ativos, links executáveis e payloads equivalentes devem ser removidos ou bloqueados conforme o formato.

**Rationale**

Conteúdo malicioso pode explorar o parser, comprometer o worker de ingestão, persistir payloads ou contaminar sistemas que reutilizem o documento original.

**Impact**

A inspeção adiciona latência e pode bloquear documentos com recursos ativos legítimos.

**Audit**

1. Confirmar que a inspeção ocorre antes da indexação e que falha do mecanismo resulta em bloqueio.
2. Enviar arquivo de teste antimalware e documento com macro ou script ativo; ambos devem ser bloqueados ou saneados conforme policy.
3. Verificar que conteúdo bloqueado não gera chunk, embedding, cache ou registro consultável.
4. Reprovar se a ingestão continuar quando o scanner estiver indisponível.

**Remediation**

Integrar antimalware e content disarm/reconstruction quando aplicável. Configurar fail closed e impedir que itens bloqueados prossigam para parsing ou persistência.

**Evidence**

Arquitetura do pipeline, política do scanner, logs de detecção e comprovação de ausência de derivados do arquivo bloqueado.

**Mappings**

CIS Controls v8 10 e 13; NIST SP 800-53 SI-3, SI-4; OWASP LLM Top 10 LLM08

---

### 1.5 Certifique-se de que dados proibidos sejam detectados e bloqueados antes da persistência

**Control ID:** BAS-003.1.5
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Bases de conhecimento que possam receber credenciais, segredos, dados de pagamento, dados pessoais sensíveis, sigilo bancário ou outras categorias proibidas pela solução.

**Description**

A ingestão deve aplicar classificação e DLP antes de gravar conteúdo, chunks, embeddings ou metadados. Categorias proibidas devem resultar em bloqueio do item inteiro ou redaction irreversível de todos os campos afetados. A versão não saneada não pode permanecer em staging, fila de erro ou cache.

**Rationale**

A indexação de dados proibidos os replica em diversos derivados e amplia a exposição para consultas, logs, backups e administradores.

**Impact**

Falsos positivos podem exigir ajuste de regras e revisão de fontes legítimas.

**Audit**

1. Identificar as categorias de dados configuradas como proibidas.
2. Inserir amostras controladas de segredo, token, dado de pagamento e identificador sensível no pipeline.
3. Confirmar que nenhum conteúdo, chunk, embedding, metadata ou cópia temporária consultável seja criado para o item bloqueado.
4. Reprovar se o bloqueio ocorrer somente após a indexação ou se a versão original permanecer acessível em staging.

**Remediation**

Aplicar DLP e classificação antes da persistência, excluir cópias temporárias e configurar bloqueio ou redaction irreversível por categoria.

**Evidence**

Política DLP, resultados de testes com dados sintéticos e consulta comprovando ausência de derivados.

**Mappings**

CIS Controls v8 3; NIST SP 800-53 AC-4, SC-28, SI-10; PCI DSS 4.0 Req. 3; OWASP LLM Top 10 LLM02

---

### 1.6 Certifique-se de que a ingestão seja idempotente e impeça duplicação não controlada de conteúdo

**Control ID:** BAS-003.1.6
**Profile Applicability:** Level 1
**Criticality:** Média
**Applicability:** Pipelines periódicos, orientados a eventos ou reexecutáveis que indexem a mesma fonte mais de uma vez.

**Description**

Cada item deve possuir chave estável derivada da fonte e versão. Reprocessamentos da mesma versão devem atualizar ou reutilizar o item existente, sem criar cópias adicionais de chunks ou embeddings. A duplicação intencional deve ser explicitamente identificada por namespace distinto.

**Rationale**

Duplicações alteram ranking, aumentam custos, dificultam exclusão e podem fazer conteúdo antigo ou malicioso dominar os resultados.

**Impact**

A implementação requer controle de versão e deduplicação no pipeline.

**Audit**

1. Ingerir duas vezes o mesmo item e versão.
2. Confirmar que a contagem final de documentos, chunks e embeddings permaneça igual à primeira execução.
3. Atualizar a fonte para nova versão e confirmar substituição ou versionamento controlado sem manter cópias ativas ambíguas.
4. Reprovar se retries ou reprocessamentos criarem duplicatas consultáveis.

**Remediation**

Definir chave idempotente por fonte, item e versão; utilizar upsert transacional e remover duplicatas existentes.

**Evidence**

Configuração de chaves, registros de execução e contagens antes/depois de reprocessamento.

**Mappings**

CIS Controls v8 3 e 8; NIST SP 800-53 SI-10, AU-10; NIST AI RMF MEASURE

---

## 2. Transformação, parsing e metadados

Controles para preservar origem, classificação, autorização e reprodutibilidade durante parsing, chunking, extração e enriquecimento.

### 2.1 Certifique-se de que regras de parsing, chunking e enriquecimento sejam versionadas e imutáveis por execução

**Control ID:** BAS-003.2.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Pipelines que transformem documentos em texto, chunks, resumos, entidades, metadados ou outros derivados.

**Description**

Cada execução deve registrar versão imutável do parser, configuração de chunking, normalização, OCR, sumarização, extração e enriquecimento utilizados. Alterações devem gerar nova versão e não podem modificar retroativamente o significado de registros já indexados sem reprocessamento explícito.

**Rationale**

Mudanças silenciosas impedem reproduzir resultados, investigar poisoning e determinar por que um trecho foi recuperado.

**Impact**

O versionamento aumenta metadados e pode exigir reprocessamento após alterações relevantes.

**Audit**

1. Selecionar itens ingeridos em execuções diferentes e verificar os identificadores de versão de transformação.
2. Confirmar que uma alteração de configuração gera novo identificador e não sobrescreve a configuração anterior.
3. Reexecutar a mesma versão e verificar resultado determinístico dentro dos limites esperados.
4. Reprovar se não for possível associar cada chunk à configuração exata que o produziu.

**Remediation**

Versionar código e parâmetros de transformação, persistir os identificadores em cada item derivado e exigir reprocessamento explícito para mudanças.

**Evidence**

Repositório de configuração, metadados de chunks e comparação entre execuções.

**Mappings**

CIS Controls v8 4, 8 e 16; NIST SP 800-53 CM-2, CM-3, SI-7

---

### 2.2 Certifique-se de que cada derivado preserve metadados mínimos de origem e classificação

**Control ID:** BAS-003.2.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Documentos, chunks, embeddings, resumos, entidades, índices, referências e caches utilizados na recuperação.

**Description**

Cada derivado deve manter, no mínimo, identificador da fonte, identificador e versão do item original, classificação, tenant/domínio, restrições de acesso, timestamps de criação e validade, versão da transformação e hash ou referência de integridade. Derivados sem esses campos não podem ser publicados para recuperação.

**Rationale**

A perda de metadados rompe autorização, exclusão, lineage e investigação, permitindo que dados sensíveis se tornem indistinguíveis de conteúdo público.

**Impact**

O aumento de metadados pode elevar armazenamento e complexidade do schema.

**Audit**

1. Consultar amostra de cada tipo de derivado.
2. Confirmar presença e preenchimento dos campos mínimos em 100% da amostra.
3. Remover um campo obrigatório em item de teste e tentar publicá-lo; a operação deve ser bloqueada.
4. Reprovar se a classificação ou restrição de acesso puder ser perdida durante transformação ou indexação.

**Remediation**

Adicionar schema obrigatório de metadados, validação antes de publicação e reprocessar itens incompletos.

**Evidence**

Schema de metadados, consultas de amostra e resultado de teste de publicação bloqueada.

**Mappings**

CIS Controls v8 3 e 8; NIST SP 800-53 AC-4, MP-3, SI-10; NIST AI RMF MAP

---

### 2.3 Certifique-se de que a classificação do derivado seja igual ou mais restritiva que a fonte

**Control ID:** BAS-003.2.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pipelines que gerem chunks, embeddings, resumos, tags, entidades, índices ou outros artefatos a partir de dados classificados.

**Description**

A classificação efetiva de cada derivado deve ser calculada como a classificação mais restritiva entre todas as fontes e campos utilizados. Transformação, sumarização, embedding ou remoção de identificadores não pode reduzir automaticamente a classificação sem mecanismo técnico aprovado de anonimização irreversível.

**Rationale**

Derivados podem reter ou revelar informações da fonte mesmo quando não são legíveis diretamente, e classificação inferior permite acesso e retenção inadequados.

**Impact**

Pode aumentar o volume de artefatos tratados em níveis mais restritivos.

**Audit**

1. Criar item a partir de fontes com classificações diferentes.
2. Confirmar que o derivado recebe a classificação mais restritiva.
3. Executar transformação de resumo e embedding e verificar que a classificação não é reduzida automaticamente.
4. Reprovar se qualquer etapa permitir downgrade sem evidência técnica de anonimização irreversível.

**Remediation**

Implementar herança de classificação por regra de máximo, bloquear downgrades automáticos e reclassificar derivados existentes.

**Evidence**

Regras de herança, amostras de derivados e testes com fontes de diferentes classificações.

**Mappings**

CIS Controls v8 3; NIST SP 800-53 AC-4, MP-3, SC-16; ISO/IEC 27001 A.5.12

---

### 2.4 Certifique-se de que texto oculto, metadados e comentários sejam tratados explicitamente

**Control ID:** BAS-003.2.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Parsers de PDF, Office, HTML, imagens com OCR, e-mails e formatos que suportem camadas ocultas, comentários ou metadados.

**Description**

O pipeline deve definir quais camadas são extraídas. Texto oculto, comentários, revisões, notas, propriedades, EXIF, conteúdo fora da área visível e elementos equivalentes devem ser removidos por padrão ou marcados como não confiáveis e separados do conteúdo principal. Não podem entrar silenciosamente no contexto.

**Rationale**

Informações ocultas podem conter segredos, instruções maliciosas ou dados não destinados ao usuário final.

**Impact**

A remoção pode descartar informação útil em casos específicos e requer testes por formato.

**Audit**

1. Criar documentos de teste com texto oculto, comentários, notas, revisões e metadados sensíveis.
2. Executar ingestão e confirmar que esses elementos são removidos ou armazenados separadamente com marcação não confiável.
3. Consultar o índice e verificar que o conteúdo oculto não é recuperado como texto principal.
4. Reprovar se o comportamento variar sem configuração explícita por formato.

**Remediation**

Configurar parsers para remover ou separar camadas ocultas e documentar o comportamento por formato. Reprocessar itens existentes quando necessário.

**Evidence**

Casos de teste por formato, saída do parser e consulta ao índice.

**Mappings**

CIS Controls v8 3 e 16; NIST SP 800-53 SI-10; OWASP LLM Top 10 LLM01 e LLM08

---

### 2.5 Certifique-se de que chunks mantenham limites semânticos e não combinem domínios de autorização diferentes

**Control ID:** BAS-003.2.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pipelines de chunking de documentos com seções, páginas ou registros sujeitos a permissões distintas.

**Description**

Um chunk não pode combinar conteúdo que possua classificações, tenants, ACLs, owners ou finalidades incompatíveis. O algoritmo deve respeitar fronteiras de registro, seção protegida, documento, tenant e política de acesso. Quando houver conflito, o conteúdo deve ser dividido ou receber a restrição mais elevada.

**Rationale**

Chunks mistos impedem aplicar autorização granular e podem expor partes restritas junto de conteúdo permitido.

**Impact**

Chunks menores podem reduzir contexto e exigir ajuste de recuperação e reranking.

**Audit**

1. Selecionar documentos com seções ou registros de permissões diferentes.
2. Inspecionar os chunks produzidos e confirmar que nenhum combina domínios de autorização incompatíveis.
3. Executar consulta com usuário autorizado apenas a uma seção e confirmar ausência de conteúdo das demais.
4. Reprovar se a autorização depender de filtrar texto dentro de um chunk já recuperado.

**Remediation**

Modificar o chunking para respeitar fronteiras de autorização e reprocessar documentos afetados. Aplicar a classificação mais restritiva quando a divisão não for possível.

**Evidence**

Configuração de chunking, amostras de chunks e testes de recuperação por permissão.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-3, AC-4; OWASP LLM Top 10 LLM02

---

### 2.6 Certifique-se de que dados estruturados sejam extraídos por schema e não por interpretação livre do modelo

**Control ID:** BAS-003.2.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Pipelines que extraiam campos de tabelas, formulários, registros, contratos, tickets ou outros dados estruturados para indexação.

**Description**

Campos usados em filtros de autorização, tenant, classificação, data, validade ou referência devem ser extraídos por parser determinístico ou validados contra schema e fonte autoritativa. O output de um modelo não pode definir sozinho metadados de segurança.

**Rationale**

Alucinação ou manipulação da extração pode classificar incorretamente conteúdo e contornar filtros de acesso.

**Impact**

Pode exigir parsers adicionais ou validação posterior ao uso de IA na extração.

**Audit**

1. Identificar campos que influenciam acesso, classificação, retenção ou roteamento.
2. Confirmar que esses campos são obtidos deterministicamente ou validados contra schema e fonte confiável.
3. Alterar o conteúdo para induzir o modelo a produzir tenant ou classificação incorretos; a validação deve rejeitar o valor.
4. Reprovar se um output não validado de IA puder alterar metadados de segurança.

**Remediation**

Mover metadados de segurança para parsers determinísticos ou implementar validação contra schema e fonte autoritativa. Rejeitar divergências.

**Evidence**

Mapeamento de campos, regras de validação e teste adversarial de extração.

**Mappings**

CIS Controls v8 3 e 16; NIST SP 800-53 SI-10, AC-3; OWASP LLM Top 10 LLM01

---

## 3. Embeddings, índices e armazenamento

Controles para proteger vetores, índices, grafos, caches e demais derivados com isolamento, integridade e menor privilégio.

### 3.1 Certifique-se de que embeddings e índices sejam tratados com a mesma proteção dos dados de origem

**Control ID:** BAS-003.3.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Vector stores, índices de busca, knowledge graphs, caches semânticos e demais armazenamentos derivados.

**Description**

Embeddings, vetores, índices invertidos, grafos, resumos e caches devem herdar criptografia, controle de acesso, isolamento, retenção e backup compatíveis com a classificação mais restritiva das fontes representadas. Não devem ser tratados como dados não sensíveis apenas por não serem diretamente legíveis.

**Rationale**

Ataques de inversão, membership inference, consulta exploratória e acesso administrativo podem revelar informações da fonte.

**Impact**

A proteção reforçada pode limitar serviços compartilhados e aumentar custo de armazenamento.

**Audit**

1. Comparar a classificação e os controles das fontes com os stores derivados.
2. Confirmar que criptografia, IAM, rede, retenção e backup atendem ao mesmo nível ou superior.
3. Tentar acessar o store com identidade que não possui acesso às fontes; a operação deve ser negada.
4. Reprovar se qualquer derivado possuir proteção inferior sem anonimização irreversível comprovada.

**Remediation**

Reclassificar os derivados, alinhar criptografia, IAM, rede, retenção e backup e migrar dados para store compatível.

**Evidence**

Matriz de classificação, configuração do store, políticas de acesso e teste negativo.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-3, SC-28, MP-3; OWASP LLM Top 10 LLM02

---

### 3.2 Certifique-se de que índices de ambientes diferentes sejam fisicamente ou logicamente isolados

**Control ID:** BAS-003.3.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Soluções com desenvolvimento, teste, homologação e produção ou ambientes equivalentes.

**Description**

Cada ambiente deve utilizar coleção, índice, namespace, database ou instância separada e credenciais próprias. O runtime não pode selecionar ambiente por parâmetro fornecido pelo usuário. Identidades não produtivas devem ser impedidas de consultar ou alterar índices produtivos.

**Rationale**

Mistura de ambientes expõe dados reais, permite poisoning por ambientes inferiores e compromete testes e produção.

**Impact**

A separação aumenta a quantidade de recursos e configurações.

**Audit**

1. Enumerar índices, namespaces e credenciais por ambiente.
2. Confirmar que não existe índice compartilhado entre produção e ambientes inferiores.
3. Executar consulta e escrita em produção usando identidade de desenvolvimento; ambas devem ser negadas.
4. Reprovar se a seleção de ambiente depender de campo controlado pelo cliente.

**Remediation**

Criar stores ou namespaces separados, credenciais exclusivas e políticas de negação cruzada. Migrar conteúdo misturado.

**Evidence**

Inventário de índices, políticas IAM e resultados de testes cruzados.

**Mappings**

CIS Controls v8 3, 4, 5 e 6; NIST SP 800-53 AC-4, SC-7

---

### 3.3 Certifique-se de que o isolamento entre tenants seja imposto pelo store e pela identidade autenticada

**Control ID:** BAS-003.3.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Bases de conhecimento multi-tenant, multi-cliente ou compartilhadas entre áreas com separação obrigatória.

**Description**

O tenant deve ser derivado de claim ou identidade confiável e aplicado no store por namespace dedicado, row-level security, ABAC ou mecanismo equivalente. Filtro de tenant enviado pelo cliente ou aplicado somente após a busca não atende ao controle.

**Rationale**

Filtros manipuláveis ou pós-busca permitem recuperação e inferência cruzada entre clientes ou áreas.

**Impact**

Pode exigir particionamento adicional ou recursos avançados do store.

**Audit**

1. Identificar a origem do tenant utilizado na consulta.
2. Confirmar que o store aplica isolamento antes de executar similaridade ou busca.
3. Alterar o tenant no payload e executar consultas para conteúdo conhecido de outro tenant; nenhum resultado ou sinal de existência deve ser retornado.
4. Reprovar se a aplicação buscar globalmente e filtrar resultados após a recuperação.

**Remediation**

Derivar tenant de identidade autenticada, aplicar isolamento no store e eliminar filtros controlados pelo cliente.

**Evidence**

Claims de identidade, policies do store, queries de teste e resultados sem vazamento.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-3, AC-4; OWASP LLM Top 10 LLM02

---

### 3.4 Certifique-se de que o modelo de embedding e seus parâmetros estejam fixados por índice

**Control ID:** BAS-003.3.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Índices vetoriais e pipelines que produzam ou consultem embeddings.

**Description**

Cada índice deve registrar modelo de embedding, versão, dimensão, normalização, tokenizer e parâmetros relevantes. O runtime deve rejeitar vetores produzidos por configuração diferente e não pode alterar silenciosamente o modelo associado a uma coleção existente.

**Rationale**

Mistura de modelos e parâmetros produz resultados inconsistentes, facilita poisoning e impede reprodutibilidade.

**Impact**

Atualizações de modelo exigirão novo índice ou reindexação controlada.

**Audit**

1. Consultar metadados do índice e do pipeline de geração.
2. Confirmar correspondência exata de modelo, versão, dimensão e normalização.
3. Tentar inserir vetor de dimensão ou versão divergente; a operação deve ser rejeitada.
4. Reprovar se o modelo puder ser trocado sem criar nova versão de índice ou reindexação completa.

**Remediation**

Fixar modelo e parâmetros na configuração da coleção, validar compatibilidade em ingestão e consulta e criar novo índice para mudanças.

**Evidence**

Configuração do índice, metadados do pipeline e teste de inserção incompatível.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 CM-2, CM-3, SI-7; NIST AI RMF MEASURE

---

### 3.5 Certifique-se de que interfaces administrativas do store não sejam acessíveis por identidades de consulta

**Control ID:** BAS-003.3.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Vector stores, search engines, bancos, knowledge graphs e serviços gerenciados com operações administrativas.

**Description**

Identidades de runtime utilizadas para consulta devem possuir somente permissões de leitura estritamente necessárias e não podem criar coleções, alterar schema, modificar ACLs, executar exportação global, apagar índices ou acessar consoles administrativos. Escrita de ingestão deve utilizar identidade separada.

**Rationale**

Comprometimento do runtime de consulta não deve permitir poisoning, destruição ou exportação completa da base.

**Impact**

Exige identidades distintas para consulta, ingestão e administração.

**Audit**

1. Enumerar permissões das identidades de consulta, ingestão e administração.
2. Tentar criar, alterar, exportar e excluir coleção com identidade de consulta; todas as operações devem ser negadas.
3. Confirmar que a identidade de ingestão não altera ACLs ou configurações administrativas.
4. Reprovar se uma única credencial de aplicação possuir leitura, escrita e administração ampla.

**Remediation**

Separar identidades por função e remover privilégios administrativos das identidades de runtime e ingestão.

**Evidence**

Matriz de permissões, policies e resultados de testes negativos.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-5, AC-6; OWASP LLM Top 10 LLM02

---

### 3.6 Certifique-se de que backups e réplicas preservem segregação, criptografia e exclusões

**Control ID:** BAS-003.3.6
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Stores que possuam backup, snapshot, réplica, exportação ou restauração.

**Description**

Backups e réplicas devem utilizar criptografia, IAM e isolamento equivalentes ao store primário. Exclusões e revogações devem ser aplicadas por expiração, purge ou restauração filtrada dentro do prazo técnico definido. Não pode existir exportação global desprotegida usada como backup informal.

**Rationale**

Cópias secundárias frequentemente permanecem após expurgo e podem reintroduzir dados removidos ou expor múltiplos tenants.

**Impact**

Pode exigir políticas de backup específicas e procedimentos de restauração seletiva.

**Audit**

1. Enumerar snapshots, réplicas e exportações do store.
2. Comparar criptografia, acesso e segregação com o primário.
3. Excluir item de teste, executar backup/restauração conforme desenho e confirmar que o item não retorna ao conjunto ativo após o prazo definido.
4. Reprovar se houver exportação não inventariada ou cópia sem criptografia e controle de acesso equivalentes.

**Remediation**

Migrar backups para serviço gerenciado, restringir exportações, aplicar criptografia/IAM equivalentes e implementar purge ou restauração seletiva.

**Evidence**

Configuração de backup, inventário de cópias e teste documentado de exclusão/restauração.

**Mappings**

CIS Controls v8 3 e 11; NIST SP 800-53 CP-9, CP-10, SC-28

---

## 4. Autorização, segregação e recuperação permitida

Controles para garantir que somente o conjunto autorizado seja pesquisado, ranqueado e retornado para cada identidade, tenant e finalidade.

### 4.1 Certifique-se de que a autorização seja aplicada antes da busca e do cálculo de similaridade

**Control ID:** BAS-003.4.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Qualquer mecanismo de busca semântica, lexical, híbrida, graph retrieval ou consulta de conhecimento com conteúdo restrito.

**Description**

O conjunto candidato deve ser limitado pelas permissões efetivas do usuário, workload, tenant, ambiente e finalidade antes do ranking, similaridade, reranking ou agregação. Resultados não autorizados não podem ser recuperados e depois descartados pela aplicação.

**Rationale**

Mesmo quando o conteúdo é filtrado depois, scores, latência, contagem ou logs podem revelar existência e permitir vazamento por canal lateral.

**Impact**

Alguns mecanismos exigirão filtros pré-busca, índices particionados ou integração com policy engine.

**Audit**

1. Revisar a ordem de execução da consulta e identificar onde os filtros de autorização são aplicados.
2. Executar consulta para termo conhecido presente apenas em conteúdo não autorizado.
3. Confirmar que o item não entra no conjunto candidato, reranker, cache nem log de resultado.
4. Reprovar se a aplicação receber resultados não autorizados e filtrá-los posteriormente.

**Remediation**

Aplicar filtros de autorização no store ou particionar índices antes da busca. Remover filtros pós-recuperação como mecanismo principal de segurança.

**Evidence**

Plano de execução da consulta, policies e teste com conteúdo conhecido não autorizado.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-3, AC-4; OWASP LLM Top 10 LLM02

---

### 4.2 Certifique-se de que permissões da fonte sejam propagadas para documentos, chunks e índices

**Control ID:** BAS-003.4.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Fontes que possuam ACL, grupos, owner, classificação, RLS ou regras de acesso próprias.

**Description**

O pipeline deve capturar as permissões efetivas da fonte e associá-las a cada derivado. Alterações de permissão na fonte devem atualizar o índice. Ausência, erro ou ambiguidade de ACL deve impedir a publicação do item para recuperação.

**Rationale**

Perder ACL durante transformação torna conteúdo restrito acessível a todos os usuários da base.

**Impact**

Sincronização de ACL pode aumentar carga e exigir integração específica por fonte.

**Audit**

1. Selecionar documentos com diferentes ACLs e comparar fonte e índice.
2. Confirmar correspondência de usuários, grupos ou atributos em todos os chunks derivados.
3. Remover permissão na fonte e verificar atualização do índice dentro do prazo técnico configurado.
4. Reprovar se item sem ACL válida for publicado ou tratado como público.

**Remediation**

Implementar extração e sincronização de ACL, schema obrigatório de permissões e bloqueio de publicação quando a ACL não puder ser determinada.

**Evidence**

Comparação de ACL fonte/índice, logs de sincronização e teste de revogação.

**Mappings**

CIS Controls v8 3, 5 e 6; NIST SP 800-53 AC-2, AC-3, AC-4

---

### 4.3 Certifique-se de que a finalidade e o caso de uso restrinjam tecnicamente o escopo recuperável

**Control ID:** BAS-003.4.3
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Plataformas compartilhadas em que a mesma identidade possua acesso amplo, mas casos de uso devam consultar subconjuntos diferentes.

**Description**

Além da autorização de identidade, a consulta deve aplicar policy de finalidade ou caso de uso que limite fontes, domínios, classificações e campos permitidos. A aplicação não pode escolher livremente outra finalidade ou ampliar o escopo por parâmetro de entrada.

**Rationale**

Permissão ampla do usuário não significa que todo dado acessível seja necessário ou adequado para cada processamento de IA.

**Impact**

Exige modelagem de políticas por aplicação e finalidade.

**Audit**

1. Selecionar identidade com acesso a múltiplos domínios e executar consultas por dois casos de uso distintos.
2. Confirmar que cada aplicação recupera somente as fontes e classificações previstas para sua finalidade.
3. Alterar parâmetro de finalidade ou origem no payload; o valor deve ser ignorado ou rejeitado.
4. Reprovar se a aplicação puder consultar qualquer fonte acessível à identidade sem policy adicional.

**Remediation**

Implementar policy por workload/caso de uso, derivada de identidade confiável, com allowlist de fontes, domínios e classificações.

**Evidence**

Policies por aplicação, claims utilizadas e testes de tentativa de ampliação de escopo.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-3, AC-6, PL-8; NIST AI RMF GOVERN

---

### 4.4 Certifique-se de que filtros de autorização não possam ser substituídos por filtros fornecidos pelo usuário

**Control ID:** BAS-003.4.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** APIs de busca ou RAG que aceitem filtros, metadata queries, namespaces, SQL, DSL ou parâmetros equivalentes.

**Description**

Filtros de segurança devem ser construídos no servidor a partir da identidade autenticada e combinados por interseção com filtros funcionais do usuário. O cliente não pode remover, sobrescrever ou redefinir tenant, ACL, classificação, ambiente ou finalidade.

**Rationale**

Parâmetros manipuláveis permitem bypass direto da segregação e acesso a conteúdo não autorizado.

**Impact**

Pode limitar consultas avançadas oferecidas diretamente ao usuário.

**Audit**

1. Inspecionar a construção final da consulta enviada ao store.
2. Enviar filtros que tentem remover ou alterar tenant, ACL, classificação e ambiente.
3. Confirmar que os filtros obrigatórios permanecem presentes e prevalecem por interseção.
4. Reprovar se o cliente puder enviar consulta raw ou operador que anule a policy de segurança.

**Remediation**

Construir filtros obrigatórios no servidor, bloquear consultas raw e validar operadores e campos permitidos.

**Evidence**

Código/configuração de construção de query, query final registrada e testes de bypass bloqueados.

**Mappings**

CIS Controls v8 6 e 16; NIST SP 800-53 AC-3, SI-10; OWASP API Security 2023 API1

---

### 4.5 Certifique-se de que consultas administrativas e de depuração não ignorem controles de acesso

**Control ID:** BAS-003.4.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Consoles, notebooks, interfaces de troubleshooting, dashboards, APIs internas e ferramentas de suporte que consultem a base de conhecimento.

**Description**

Ferramentas administrativas devem usar identidades individuais, autorização explícita e filtros de escopo. Modos debug, preview, similarity explorer, export e raw query não podem fornecer acesso global por padrão nem reutilizar credenciais do serviço.

**Rationale**

Interfaces auxiliares frequentemente contornam a autorização da aplicação e expõem conteúdo integral.

**Impact**

Pode reduzir conveniência operacional e exigir PAM ou ambientes controlados.

**Audit**

1. Enumerar interfaces administrativas e de depuração conectadas ao store.
2. Confirmar identidade individual e escopo mínimo para cada interface.
3. Executar consulta com operador sem privilégio de dados; o conteúdo deve ser negado mesmo em modo debug.
4. Reprovar se existir console compartilhado, credencial estática ou função de export global acessível sem controle reforçado.

**Remediation**

Remover credenciais compartilhadas, integrar federação/PAM, aplicar escopo e desabilitar funções de raw query ou exportação não necessárias.

**Evidence**

Inventário de interfaces, matriz de acesso e teste de consulta administrativa negada.

**Mappings**

CIS Controls v8 5, 6 e 8; NIST SP 800-53 AC-6, IA-2, AU-12

---

### 4.6 Certifique-se de que a revogação de acesso interrompa novas recuperações dentro do prazo técnico definido

**Control ID:** BAS-003.4.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Fontes e índices com permissões mutáveis, usuários desligados, grupos alterados ou conteúdo revogado.

**Description**

Mudanças de identidade, grupo, ACL ou status do documento devem impedir novas recuperações após o intervalo máximo configurado. Caches de autorização e resultados devem expirar ou ser invalidados dentro do mesmo prazo.

**Rationale**

Permissões antigas em índice ou cache mantêm acesso mesmo após revogação na fonte ou no diretório.

**Impact**

Intervalos menores aumentam chamadas de sincronização e invalidação.

**Audit**

1. Revogar acesso de usuário de teste na fonte ou diretório.
2. Executar consultas repetidas até o limite de propagação configurado.
3. Confirmar que após o prazo nenhuma resposta, cache ou referência ao conteúdo seja retornada.
4. Reprovar se a revogação depender de reindexação manual ou se caches permanecerem válidos além do prazo.

**Remediation**

Implementar sincronização incremental de ACL, invalidação de cache e TTL compatível com o prazo de revogação.

**Evidence**

Configuração de sincronização/TTL, timestamps de revogação e resultado do teste temporal.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-2, AC-3; ISO/IEC 27001 A.5.18

---

## 5. Retrieval, ranking e montagem de contexto

Controles sobre consulta, top-k, reranking, grounding, referências e separação entre instruções e dados recuperados.

### 5.1 Certifique-se de que limites de top-k, tamanho e tokens de contexto sejam impostos pelo servidor

**Control ID:** BAS-003.5.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Endpoints de busca, RAG, agentes e aplicações que montem contexto para o modelo.

**Description**

O servidor deve impor valores máximos de top-k, número de fontes, tamanho por item, total de caracteres/tokens e quantidade de iterações de recuperação. O cliente pode solicitar valores menores, mas não ampliar os limites.

**Rationale**

Recuperação excessiva aumenta vazamento, custo, negação de serviço e probabilidade de incluir conteúdo irrelevante ou malicioso.

**Impact**

Limites restritivos podem reduzir completude em consultas complexas.

**Audit**

1. Consultar a configuração de limites do serviço.
2. Enviar requisições acima de cada limite e confirmar rejeição ou redução para o máximo permitido.
3. Verificar nos logs que o contexto final não ultrapassa os valores configurados.
4. Reprovar se top-k ou tokens puderem ser aumentados livremente pelo cliente.

**Remediation**

Definir limites server-side por rota e classificação, validar parâmetros e truncar ou rejeitar requisições excedentes.

**Evidence**

Configuração de limites, requisições de teste e metadados do contexto final.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 SC-5, SI-10; OWASP LLM Top 10 LLM10

---

### 5.2 Certifique-se de que a consulta seja normalizada e validada antes da busca

**Control ID:** BAS-003.5.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Mecanismos que aceitem texto, filtros, operadores, expressões, SQL/DSL, embeddings enviados pelo cliente ou consultas híbridas.

**Description**

A consulta deve ser normalizada para representação canônica, validada por tamanho e encoding, e restrita a operadores, campos e sintaxes permitidos. SQL/DSL raw, wildcards ilimitados, regex custosa e vetores arbitrários do cliente devem ser bloqueados quando não forem estritamente necessários.

**Rationale**

Consultas malformadas ou expressivas podem causar bypass de filtro, enumeração, DoS ou exploração do mecanismo de busca.

**Impact**

Recursos avançados de busca podem precisar de endpoints controlados separados.

**Audit**

1. Revisar schema e allowlist de operadores do endpoint.
2. Enviar encoding alternativo, operador não permitido, regex custosa, wildcard amplo e query raw.
3. Confirmar rejeição antes da execução no store.
4. Reprovar se o cliente puder fornecer consulta nativa integral ao mecanismo de busca.

**Remediation**

Canonicalizar entrada, aplicar parser seguro e allowlist de campos/operadores e remover suporte a queries raw.

**Evidence**

Schema da API, configuração de validação e respostas de testes rejeitados.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 SI-10; OWASP API Security 2023 API8

---

### 5.3 Certifique-se de que rerankers recebam somente candidatos já autorizados

**Control ID:** BAS-003.5.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pipelines que utilizem reranking por modelo, serviço externo ou componente separado.

**Description**

O reranker deve receber apenas candidatos previamente filtrados por autorização. Conteúdo não autorizado não pode ser enviado ao reranker, mesmo que a saída final seja filtrada. Quando o reranker for externo, os mesmos controles de dados e retenção do modelo principal devem ser aplicados.

**Rationale**

O reranker pode registrar, processar ou vazar candidatos que nunca deveriam sair do store autorizado.

**Impact**

Pode limitar reranking global e exigir execução local ou particionada.

**Audit**

1. Inspecionar a sequência do pipeline e o payload enviado ao reranker.
2. Executar consulta que tenha candidatos autorizados e não autorizados semelhantes.
3. Confirmar que o payload do reranker contém somente os autorizados.
4. Reprovar se o filtro de autorização ocorrer depois do reranking.

**Remediation**

Mover autorização para antes do reranker e aplicar ao serviço de reranking os mesmos controles de provider, retenção e rede.

**Evidence**

Diagrama de sequência, payload capturado e teste com candidatos mistos.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-4, SC-7; OWASP LLM Top 10 LLM02

---

### 5.4 Certifique-se de que contexto recuperado seja delimitado como dado não confiável

**Control ID:** BAS-003.5.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pipelines que incluam documentos, páginas, tickets, e-mails, resultados de busca ou conteúdo externo no prompt.

**Description**

O contexto deve ser encapsulado em estrutura separada das instruções de sistema e desenvolvedor, com delimitadores inequívocos e instrução explícita para não executar comandos presentes no conteúdo. O contexto não pode ser concatenado em posição de instrução privilegiada nem alterar tools, policies ou parâmetros protegidos.

**Rationale**

Documentos podem conter instruções maliciosas que o modelo interpreta como comandos, produzindo prompt injection indireto.

**Impact**

A separação pode exigir templates específicos e reduzir flexibilidade do prompt.

**Audit**

1. Inspecionar o template final enviado ao modelo.
2. Confirmar separação estrutural entre system/developer instructions e contexto recuperado.
3. Inserir documento com instrução para ignorar políticas e solicitar segredo; o modelo não deve cumprir a instrução nem alterar tool/policy.
4. Reprovar se o contexto for concatenado diretamente às instruções privilegiadas sem delimitação e policy.

**Remediation**

Separar contexto em campo ou bloco dedicado, usar delimitadores e instruções de tratamento como dado, e impedir que altere configurações privilegiadas.

**Evidence**

Template de prompt, payload capturado e resultado de teste de indirect prompt injection.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SI-10; OWASP LLM Top 10 LLM01

---

### 5.5 Certifique-se de que o contexto preserve referências verificáveis à fonte e versão

**Control ID:** BAS-003.5.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Soluções que apresentem respostas fundamentadas em conteúdo recuperado.

**Description**

Cada trecho enviado ao modelo deve carregar identificador da fonte, item, versão, localização ou fragmento e classificação. A resposta ou registro técnico deve permitir associar cada citação ao trecho efetivamente utilizado. Referências não podem ser geradas livremente pelo modelo sem validação.

**Rationale**

Sem referência verificável, não é possível confirmar grounding, investigar conteúdo incorreto ou identificar documento contaminado.

**Impact**

Exige metadados adicionais no contexto e validação de citações.

**Audit**

1. Executar consultas com múltiplas fontes e capturar contexto e resposta.
2. Confirmar que cada trecho possui identificador e versão e que cada citação resolve para item existente e autorizado.
3. Induzir o modelo a citar fonte inexistente; a aplicação deve remover ou marcar a referência como não verificada.
4. Reprovar se citações não puderem ser mapeadas ao trecho real utilizado.

**Remediation**

Adicionar IDs e versões aos trechos, validar referências no servidor e rejeitar citações inexistentes ou não autorizadas.

**Evidence**

Payload de contexto, resposta com citações e validação de resolução das referências.

**Mappings**

CIS Controls v8 8 e 16; NIST SP 800-53 AU-3, SI-10; NIST AI RMF MEASURE

---

### 5.6 Certifique-se de que resultados abaixo do limiar mínimo de relevância não sejam enviados ao modelo

**Control ID:** BAS-003.5.6
**Profile Applicability:** Level 1
**Criticality:** Média
**Applicability:** Sistemas que utilizem score de similaridade, reranking ou confiança para selecionar contexto.

**Description**

O pipeline deve definir limiar mínimo por mecanismo e tipo de consulta. Itens abaixo do limiar devem ser descartados; quando nenhum item atingir o mínimo, o sistema deve retornar ausência de contexto ou usar resposta segura, sem preencher o prompt com resultados fracos.

**Rationale**

Contexto irrelevante aumenta alucinação, exposição desnecessária e suscetibilidade a documentos maliciosos com baixa similaridade.

**Impact**

Consultas vagas podem retornar menos respostas e exigir refinamento.

**Audit**

1. Consultar a configuração de thresholds por rota.
2. Executar consultas sem correspondência e confirmar que nenhum conteúdo abaixo do limiar é enviado ao modelo.
3. Executar consulta com itens em ambos os lados do limiar e confirmar seleção correta.
4. Reprovar se o pipeline sempre preencher top-k independentemente da relevância.

**Remediation**

Definir e testar thresholds por mecanismo, implementar resposta sem contexto e impedir preenchimento forçado do top-k.

**Evidence**

Configuração de thresholds, scores de teste e payload de contexto vazio ou filtrado.

**Mappings**

CIS Controls v8 16; NIST AI RMF MEASURE; OWASP LLM Top 10 LLM09

---

## 6. Proteção contra poisoning e conteúdo adversarial

Controles para detectar, segregar, bloquear e reverter conteúdo malicioso ou manipulador em fontes e índices.

### 6.1 Certifique-se de que fontes com níveis de confiança diferentes permaneçam separadas

**Control ID:** BAS-003.6.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Bases que combinem conteúdo corporativo, público, colaborativo, enviado por usuários ou obtido da Internet.

**Description**

Conteúdo deve possuir atributo de confiança derivado da origem. Fontes externas, colaborativas ou não verificadas devem usar coleção/namespace distinto ou filtro obrigatório e não podem receber o mesmo peso, precedência ou capacidade de citação de fontes corporativas autoritativas.

**Rationale**

Misturar fontes permite que conteúdo de baixa confiança suplante documentos oficiais e facilite poisoning.

**Impact**

A separação aumenta complexidade de ranking e pode reduzir cobertura de pesquisa aberta.

**Audit**

1. Enumerar categorias de confiança e como são armazenadas.
2. Confirmar segregação física/lógica ou filtro obrigatório por confiança.
3. Inserir conteúdo externo contraditório e verificar que não substitui fonte autoritativa em consulta equivalente.
4. Reprovar se a origem ou confiança não influenciar seleção e ranking.

**Remediation**

Adicionar classificação de confiança, separar fontes e configurar ranking/policy que priorize ou restrinja fontes autoritativas.

**Evidence**

Schema de confiança, configuração de coleção/filtro e teste de conteúdo contraditório.

**Mappings**

CIS Controls v8 3 e 16; NIST SP 800-53 SI-10; OWASP LLM Top 10 LLM04 e LLM08

---

### 6.2 Certifique-se de que alterações anômalas na fonte ou no índice sejam detectadas antes da publicação

**Control ID:** BAS-003.6.2
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Pipelines que sincronizem grande volume de documentos, páginas ou registros.

**Description**

A publicação deve ser interrompida quando a execução exceder thresholds de inclusão, exclusão, alteração, mudança de classificação, origem nova ou distribuição de conteúdo em relação ao histórico. A comparação deve ocorrer antes de tornar a nova versão consultável.

**Rationale**

Comprometimento de fonte ou erro de conector pode substituir grande parte da base e disseminar poisoning rapidamente.

**Impact**

Mudanças legítimas em massa podem exigir ajuste de thresholds ou execução controlada.

**Audit**

1. Revisar thresholds e métricas de comparação entre versões.
2. Simular alteração em massa acima do limite e confirmar que a publicação fica bloqueada.
3. Confirmar que a versão anterior permanece ativa e consultável durante o bloqueio.
4. Reprovar se alterações anômalas forem publicadas automaticamente antes da detecção.

**Remediation**

Implementar comparação de delta, thresholds por fonte e publicação atômica somente após validação.

**Evidence**

Configuração de thresholds, logs de execução bloqueada e evidência de permanência da versão anterior.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 SI-4, SI-7; NIST AI RMF MEASURE

---

### 6.3 Certifique-se de que conteúdo contenha detecção de instruções adversariais antes da indexação

**Control ID:** BAS-003.6.3
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Fontes externas, colaborativas, uploads de usuários e documentos que possam conter linguagem instrucional.

**Description**

O pipeline deve analisar conteúdo para padrões de prompt injection indireto, exfiltração, solicitação de segredos, alteração de policies, seleção de tools ou instruções dirigidas ao modelo. Conteúdo suspeito deve ser bloqueado, saneado ou marcado e segregado para que não seja usado como contexto privilegiado.

**Rationale**

Documentos podem carregar comandos concebidos para manipular o modelo durante a recuperação.

**Impact**

Detecção heurística pode gerar falsos positivos e não elimina a necessidade de isolamento no prompt.

**Audit**

1. Ingerir corpus de teste contendo instruções adversariais explícitas e ofuscadas.
2. Confirmar que os itens são bloqueados, saneados ou marcados e segregados conforme policy.
3. Executar busca e verificar que itens bloqueados não entram no contexto normal.
4. Reprovar se a detecção apenas registrar alerta sem alterar a disponibilidade do conteúdo.

**Remediation**

Adicionar análise de conteúdo adversarial, classificação de suspeita e política de bloqueio/segregação antes da publicação.

**Evidence**

Ruleset, corpus de teste, resultados de classificação e consulta comprovando segregação.

**Mappings**

CIS Controls v8 13 e 16; NIST SP 800-53 SI-3, SI-4; OWASP LLM Top 10 LLM01 e LLM08

---

### 6.4 Certifique-se de que conteúdo recuperado não possa alterar tools, modelos, rotas ou políticas

**Control ID:** BAS-003.6.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** RAG integrado a agentes, tool calling, roteamento dinâmico, seleção de modelo ou decisões de segurança.

**Description**

Campos e instruções provenientes do conteúdo recuperado devem ser tratados somente como dados. Não podem definir nome de tool, argumentos privilegiados, destino de rede, modelo, provider, prompt de sistema, role, política, credencial ou decisão de autorização. Esses valores devem vir de configuração confiável ou validação determinística.

**Rationale**

Poisoning do conhecimento pode transformar um documento em mecanismo de execução ou bypass de controle.

**Impact**

Pode limitar arquiteturas altamente dinâmicas baseadas em conteúdo.

**Audit**

1. Inserir documento que solicite troca de modelo, chamada de tool ou alteração de policy.
2. Executar consulta que recupere o documento.
3. Confirmar que nenhum parâmetro protegido seja alterado e nenhuma tool seja chamada por causa da instrução do conteúdo.
4. Reprovar se campos de configuração forem derivados diretamente do texto recuperado.

**Remediation**

Separar dados recuperados de configuração, aplicar allowlists e validação determinística e bloquear parâmetros protegidos originados no contexto.

**Evidence**

Template/fluxo de execução, logs da consulta e teste adversarial sem alteração de configuração.

**Mappings**

CIS Controls v8 6 e 16; NIST SP 800-53 AC-3, SI-10; OWASP LLM Top 10 LLM01 e LLM06

---

### 6.5 Certifique-se de que o pipeline impeça SSRF e acesso a endereços internos durante captura de conteúdo

**Control ID:** BAS-003.6.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Crawlers, fetchers, URL loaders, conectores web e parsers que resolvam links ou baixem recursos.

**Description**

O componente de captura deve permitir somente esquemas e domínios autorizados, resolver DNS antes e durante redirecionamentos, bloquear IPs privados, loopback, link-local, metadata services, Unix sockets e protocolos não HTTP(S). Deve limitar redirecionamentos e impedir DNS rebinding.

**Rationale**

URLs maliciosas podem fazer o pipeline acessar serviços internos, metadata cloud, consoles ou arquivos locais.

**Impact**

Algumas fontes internas legítimas exigirão allowlist específica e rota dedicada.

**Audit**

1. Revisar allowlist de esquemas/domínios e faixas bloqueadas.
2. Tentar acessar loopback, RFC1918, link-local, metadata cloud, file:// e URL com redirecionamento para endereço interno.
3. Confirmar bloqueio antes da conexão ao destino final.
4. Reprovar se a validação ocorrer apenas sobre a URL inicial ou aceitar IP resolvido após redirecionamento.

**Remediation**

Implementar egress proxy/fetcher seguro, resolução e validação de IP a cada redirecionamento e bloqueio de protocolos e faixas internas.

**Evidence**

Configuração de egress, logs e resultados de testes SSRF bloqueados.

**Mappings**

CIS Controls v8 12, 13 e 16; NIST SP 800-53 SC-7, SI-10; OWASP SSRF Prevention Cheat Sheet

---

### 6.6 Certifique-se de que versões de índice possam ser comparadas e revertidas sem mesclar conteúdo suspeito

**Control ID:** BAS-003.6.6
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Bases críticas, multi-tenant ou alimentadas por fontes com risco de poisoning.

**Description**

Publicações devem gerar versão imutável ou snapshot lógico do índice e permitir promover ou reverter a versão completa. O rollback não pode combinar automaticamente itens da versão suspeita com a versão anterior, e os eventos de ingestão associados devem permanecer identificáveis.

**Rationale**

Sem versionamento, remover poisoning exige reconstrução longa e pode deixar artefatos contaminados ativos.

**Impact**

Snapshots e blue/green index aumentam consumo de armazenamento.

**Audit**

1. Identificar mecanismo de versionamento e promoção do índice.
2. Publicar item de teste em nova versão, ativá-la e executar rollback.
3. Confirmar que o item desaparece de consultas e caches e que a versão anterior retorna integralmente.
4. Reprovar se rollback exigir edição manual de itens ou mantiver derivados da versão suspeita.

**Remediation**

Implementar índices versionados, alias atômico ou blue/green, preservar eventos de ingestão e invalidar caches na troca.

**Evidence**

Inventário de versões, logs de promoção/rollback e consulta antes/depois do teste.

**Mappings**

CIS Controls v8 11 e 16; NIST SP 800-53 CP-10, CM-3, SI-7

---

## 7. Memória, caches e dados derivados em execução

Controles para impedir vazamento por memória, caches, temporários e metadados de resposta.

### 7.1 Certifique-se de que memória conversacional seja isolada por usuário, sessão, tenant e aplicação

**Control ID:** BAS-003.7.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Soluções com memória de curto ou longo prazo, histórico conversacional, personalização ou estado persistente.

**Description**

Cada registro de memória deve estar vinculado à identidade autenticada, aplicação, tenant e sessão. A chave não pode ser composta somente por identificador fornecido pelo cliente. Consultas e gravações devem aplicar os mesmos controles de autorização da fonte.

**Rationale**

Colisão ou manipulação de chaves pode expor histórico e dados de outro usuário ou tenant.

**Impact**

Pode exigir namespaces adicionais e limpeza de estados antigos.

**Audit**

1. Inspecionar a composição das chaves e policies de memória.
2. Criar memórias para dois usuários/tenants e tentar recuperar a memória do outro alterando IDs no payload.
3. Confirmar bloqueio e ausência de sinal sobre a existência da memória alheia.
4. Reprovar se a seleção depender apenas de session_id ou user_id enviado pelo cliente.

**Remediation**

Derivar chaves da identidade autenticada, aplicar namespace e policy por aplicação/tenant e migrar memórias compartilhadas.

**Evidence**

Schema de chave, policies e resultado de testes cruzados.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-3, AC-4; OWASP LLM Top 10 LLM02

---

### 7.2 Certifique-se de que somente campos explicitamente permitidos sejam gravados em memória persistente

**Control ID:** BAS-003.7.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Soluções que persistam preferências, fatos, resumos de conversa ou estado do usuário.

**Description**

A gravação deve usar schema e allowlist de categorias. Prompt completo, output integral, credenciais, segredos, dados de pagamento, dados sensíveis não necessários e conteúdo recuperado de terceiros não podem ser persistidos por padrão. O modelo não pode escolher livremente quais campos armazenar.

**Rationale**

Memória automática amplia retenção e pode registrar informações que o usuário não pretendia armazenar.

**Impact**

A personalização pode ser menos abrangente e exigir regras específicas por caso.

**Audit**

1. Revisar schema e allowlist da memória.
2. Enviar conversa com segredo e dado sensível e induzir o modelo a memorizar ambos.
3. Confirmar que somente campos permitidos sejam persistidos e que dados proibidos sejam descartados.
4. Reprovar se texto arbitrário gerado pelo modelo for gravado sem validação.

**Remediation**

Definir schema de memória, validar no servidor, aplicar DLP e remover persistência automática de texto integral.

**Evidence**

Schema, conteúdo persistido em teste e logs de bloqueio de campos proibidos.

**Mappings**

CIS Controls v8 3 e 16; NIST SP 800-53 SI-10, DM-2; OWASP LLM Top 10 LLM02

---

### 7.3 Certifique-se de que caches semânticos sejam particionados e autorizados antes do retorno

**Control ID:** BAS-003.7.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Soluções que armazenem respostas, embeddings de consultas, contexto ou resultados de recuperação em cache.

**Description**

A chave e a partição do cache devem incluir aplicação, tenant, identidade ou grupo de autorização, classificação, versão da policy e versão do índice/modelo relevantes. Um cache hit deve passar por autorização antes de retornar conteúdo. Cache global baseado apenas em similaridade não é permitido para dados não públicos.

**Rationale**

Caches podem devolver resposta ou contexto produzido para usuário mais privilegiado a outro usuário com consulta semelhante.

**Impact**

Particionamento reduz taxa de acerto e aumenta armazenamento.

**Audit**

1. Inspecionar composição da chave e processo de autorização do cache.
2. Gerar resposta sensível com usuário autorizado e repetir consulta semelhante com usuário não autorizado.
3. Confirmar que não ocorre cache hit compartilhado nem exposição de conteúdo.
4. Reprovar se o cache for global para dados internos ou se a autorização ocorrer somente na geração inicial.

**Remediation**

Particionar cache por domínio de autorização, incluir versões relevantes na chave e revalidar autorização em cada hit.

**Evidence**

Configuração do cache, chaves anonimizadas e teste de consulta cruzada.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-3, AC-4; OWASP LLM Top 10 LLM02

---

### 7.4 Certifique-se de que TTL e invalidação de cache não excedam a validade da fonte ou da autorização

**Control ID:** BAS-003.7.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Caches de consulta, contexto, resposta, autorização e embeddings temporários.

**Description**

O TTL efetivo deve ser igual ou inferior ao menor prazo entre validade da fonte, SLA de revogação de acesso, versão de policy e retenção permitida. Mudança de ACL, exclusão, nova versão do índice ou incidente deve invalidar entradas relacionadas.

**Rationale**

Cache antigo pode continuar expondo conteúdo removido, revogado ou corrigido.

**Impact**

TTL menor reduz desempenho e aumenta chamadas ao store/modelo.

**Audit**

1. Comparar TTLs configurados com os prazos de revogação e validade.
2. Popular cache, revogar acesso ou atualizar a fonte e confirmar invalidação dentro do prazo.
3. Confirmar que troca de versão do índice/policy altera a chave ou limpa o cache.
4. Reprovar se entradas permanecerem acessíveis após expiração da fonte ou autorização.

**Remediation**

Reduzir TTLs, vincular chaves a versões e implementar invalidação por eventos de ACL, exclusão e publicação.

**Evidence**

Configuração de TTL, eventos de invalidação e teste temporal.

**Mappings**

CIS Controls v8 3 e 4; NIST SP 800-53 AC-2, SI-10

---

### 7.5 Certifique-se de que dados temporários sejam removidos após a conclusão da execução

**Control ID:** BAS-003.7.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Workers de ingestão, notebooks, jobs, funções, containers e serviços que criem arquivos temporários, staging, spool ou scratch space.

**Description**

Arquivos originais, textos extraídos, imagens renderizadas, OCR, chunks intermediários e payloads temporários devem ser armazenados em diretório isolado, criptografado quando persistente, e removidos automaticamente após sucesso, falha ou timeout. Volumes temporários não podem ser compartilhados entre tenants ou execuções.

**Rationale**

Dados temporários são frequentemente omitidos da retenção e podem permanecer expostos em disco, snapshot ou worker reutilizado.

**Impact**

A limpeza pode dificultar troubleshooting se não houver evidência mínima separada.

**Audit**

1. Executar ingestão bem-sucedida, falha e timeout com arquivos identificáveis.
2. Verificar filesystem, volumes, buckets de staging e filas após a janela de limpeza.
3. Confirmar ausência dos conteúdos originais e derivados temporários.
4. Reprovar se workers reutilizados mantiverem arquivos de execução anterior ou compartilharem diretório entre tenants.

**Remediation**

Usar storage temporário isolado por execução, configurar lifecycle curto e cleanup em finally/dead-letter, e eliminar volumes compartilhados.

**Evidence**

Configuração de staging/lifecycle e varredura após cenários de sucesso e falha.

**Mappings**

CIS Controls v8 3 e 4; NIST SP 800-53 MP-6, SC-28

---

### 7.6 Certifique-se de que respostas não exponham contexto bruto, scores ou metadados restritos

**Control ID:** BAS-003.7.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** APIs e interfaces que retornem citações, snippets, debug information, scores, IDs, metadados ou contexto utilizado.

**Description**

A resposta deve usar allowlist de campos e retornar apenas trechos autorizados necessários. Embeddings, vetores, prompts internos, scores detalhados, ACLs, caminhos internos, nomes de índices, queries nativas e metadados de segurança não podem ser expostos a consumidores comuns.

**Rationale**

Informações auxiliares permitem enumeração, inferência de conteúdo e exploração da arquitetura de busca.

**Impact**

Pode reduzir recursos de debugging disponíveis ao usuário final.

**Audit**

1. Inspecionar schemas de resposta de produção e modos de debug.
2. Executar consultas com e sem resultado e verificar campos retornados.
3. Confirmar ausência de vetores, ACLs, caminhos, query raw, nomes internos e prompts.
4. Reprovar se parâmetro do cliente habilitar debug ou retorno de contexto integral sem autorização separada.

**Remediation**

Aplicar schema de resposta por perfil, remover campos internos e separar interfaces de debugging com controle reforçado.

**Evidence**

Schemas, respostas capturadas e teste de tentativa de habilitar debug.

**Mappings**

CIS Controls v8 3 e 16; NIST SP 800-53 AC-3, SI-11; OWASP API Security 2023 API3

---

## 8. Retenção, exclusão, sincronização e recuperação

Controles para expiração, purge, atualização consistente, falha fechada e restauração sem reintrodução de conteúdo revogado ou contaminado.

### 8.1 Certifique-se de que cada tipo de artefato possua retenção técnica configurada

**Control ID:** BAS-003.8.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Documentos, chunks, embeddings, índices, caches, memória, staging, snapshots e outros derivados.

**Description**

A plataforma deve configurar TTL, lifecycle ou política de retenção para cada tipo de artefato. Retenção indefinida não é permitida por ausência de configuração. O prazo do derivado não pode exceder o da fonte ou da finalidade técnica associada.

**Rationale**

Artefatos derivados permanecem após a necessidade e ampliam exposição e volume a ser eliminado em incidentes.

**Impact**

Prazos menores podem exigir reingestão e reduzir capacidade histórica.

**Audit**

1. Enumerar todos os tipos de armazenamento e artefatos do pipeline.
2. Confirmar que cada tipo possui política de retenção explícita e não infinita.
3. Comparar os prazos com a fonte e verificar que derivados não possuem prazo superior.
4. Reprovar se qualquer store, cache, memória ou staging depender de limpeza manual recorrente.

**Remediation**

Configurar lifecycle/TTL por artefato, alinhar ao prazo da fonte e remover dados vencidos existentes.

**Evidence**

Inventário de stores, políticas de lifecycle e amostra de itens expirados.

**Mappings**

CIS Controls v8 3; NIST SP 800-53 SI-12, MP-6; ISO/IEC 27001 A.8.10

---

### 8.2 Certifique-se de que exclusões na fonte removam todos os derivados relacionados

**Control ID:** BAS-003.8.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pipelines que copiem ou derivem conteúdo em chunks, embeddings, índices, caches, memória, resumos ou backups ativos.

**Description**

A exclusão ou expurgo da fonte deve identificar e remover todos os derivados por lineage, incluindo versões anteriores ativas, caches e referências. O mecanismo deve ser determinístico e não depender de busca textual ou conhecimento manual dos stores.

**Rationale**

Excluir somente o documento original mantém representações consultáveis e pode violar revogação, privacidade e sigilo.

**Impact**

Pode exigir índice reverso de lineage e tombstones.

**Audit**

1. Criar item de teste e identificar todos os derivados gerados.
2. Excluir a fonte e executar o mecanismo de propagação.
3. Confirmar ausência do item em documentos, chunks, embeddings, busca lexical, caches, memória e versões ativas.
4. Reprovar se algum derivado permanecer consultável ou se a remoção depender de identificação manual.

**Remediation**

Implementar lineage reverso, tombstone/evento de exclusão e purge em todos os stores e caches.

**Evidence**

Mapa de lineage, logs de purge e consultas comprovando ausência em todos os derivados.

**Mappings**

CIS Controls v8 3; NIST SP 800-53 MP-6, SI-12; ISO/IEC 27001 A.8.10

---

### 8.3 Certifique-se de que correções e novas versões não mantenham conteúdo obsoleto ativo

**Control ID:** BAS-003.8.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Fontes versionadas ou mutáveis sincronizadas com bases de conhecimento.

**Description**

Quando uma nova versão for publicada, chunks, embeddings e referências da versão anterior devem ser desativados atomicamente ou marcados como não recuperáveis. A busca normal não pode retornar simultaneamente versões incompatíveis sem indicação explícita.

**Rationale**

Conteúdo antigo pode gerar respostas incorretas e ser explorado para manter instruções maliciosas removidas.

**Impact**

Atualizações podem exigir publicação por versão e troca atômica de alias.

**Audit**

1. Publicar versão 1 de item, depois versão 2 com conteúdo diferente.
2. Confirmar que consultas normais retornam somente a versão 2 após a publicação.
3. Verificar que a versão 1 não permanece em cache ou índice ativo.
4. Reprovar se as duas versões forem recuperadas sem controle explícito de histórico.

**Remediation**

Usar versionamento e upsert/alias atômico, invalidar caches e desativar derivados da versão anterior.

**Evidence**

Metadados de versão, resultados de consulta antes/depois e logs de invalidação.

**Mappings**

CIS Controls v8 3, 4 e 8; NIST SP 800-53 CM-3, SI-10

---

### 8.4 Certifique-se de que falhas de sincronização não publiquem estado parcial ou permissões desatualizadas

**Control ID:** BAS-003.8.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Pipelines incrementais, batch ou event-driven que atualizem conteúdo e ACLs.

**Description**

Conteúdo, metadados e permissões devem ser publicados como unidade consistente. Falha de ACL, classificação ou transformação deve impedir ativação do item. Atualizações em lote devem usar staging e promoção atômica ou mecanismo equivalente para evitar estado parcialmente atualizado.

**Rationale**

Estado parcial pode publicar conteúdo sem ACL, manter versão antiga com permissão nova ou expor dados durante transição.

**Impact**

Pode exigir staging duplicado e transações ou aliases.

**Audit**

1. Simular falha após atualização do conteúdo e antes da ACL, e o cenário inverso.
2. Confirmar que o item ativo permanece na última versão consistente ou fica indisponível, nunca parcialmente atualizado.
3. Interromper lote no meio e verificar que a coleção ativa não contém mistura não controlada.
4. Reprovar se itens sem metadados ou ACL completos puderem ser recuperados.

**Remediation**

Implementar staging, validação de completude e promoção atômica por item ou versão de índice. Configurar fail closed.

**Evidence**

Diagrama de publicação, logs dos testes de falha e consulta ao estado ativo.

**Mappings**

CIS Controls v8 4, 8 e 16; NIST SP 800-53 CP-10, SI-10, SI-17

---

### 8.5 Certifique-se de que a perda da fonte de autorização resulte em bloqueio da recuperação

**Control ID:** BAS-003.8.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Soluções que consultem diretório, policy engine, fonte de ACL ou serviço externo para autorizar a recuperação.

**Description**

Quando a fonte de identidade, ACL ou policy estiver indisponível, expirada ou inconsistente, o sistema deve negar a recuperação de conteúdo restrito. Não pode reutilizar indefinidamente permissões antigas nem assumir acesso público.

**Rationale**

Falha aberta durante indisponibilidade transforma problema de disponibilidade em exposição de dados.

**Impact**

Usuários legítimos podem ficar temporariamente sem acesso durante a falha.

**Audit**

1. Interromper ou simular erro da fonte de autorização.
2. Executar consultas a conteúdo restrito e confirmar bloqueio antes da busca.
3. Verificar que caches de autorização expiram no limite configurado e não concedem acesso indefinido.
4. Reprovar se o sistema assumir permissão, remover filtros ou continuar com ACL antiga além do TTL.

**Remediation**

Configurar fail closed, TTL curto para decisão de autorização e circuito separado para conteúdo público quando necessário.

**Evidence**

Configuração de failover/TTL e resultados de teste com serviço de autorização indisponível.

**Mappings**

CIS Controls v8 6 e 13; NIST SP 800-53 AC-3, SC-7; Zero Trust principles

---

### 8.6 Certifique-se de que a restauração reconstrua índices a partir de fontes e configurações verificadas

**Control ID:** BAS-003.8.6
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Bases críticas que exijam recuperação após corrupção, poisoning, perda ou desastre.

**Description**

A recuperação deve utilizar snapshot íntegro conhecido ou reconstrução a partir de fontes verificadas, versões de transformação registradas e ACLs atuais. A restauração não pode ativar automaticamente conteúdo cuja fonte foi excluída, permissão revogada ou integridade não verificada.

**Rationale**

Restaurar snapshot antigo pode reintroduzir dados removidos, ACL obsoleta ou conteúdo contaminado.

**Impact**

A reconstrução completa pode aumentar o tempo de recuperação.

**Audit**

1. Executar teste de restauração em ambiente isolado.
2. Confirmar verificação de integridade, aplicação das ACLs atuais e exclusão de itens revogados antes da ativação.
3. Comparar uma amostra de lineage e versões com as fontes autoritativas.
4. Reprovar se snapshot antigo for promovido diretamente sem reconciliação de exclusões, ACLs e versões.

**Remediation**

Definir restauração com verificação de integridade e reconciliação de fontes, ACLs e tombstones antes da promoção.

**Evidence**

Relatório de restauração, hashes, comparação de ACLs e consultas de itens revogados ausentes.

**Mappings**

CIS Controls v8 11; NIST SP 800-53 CP-9, CP-10, SI-7

---
