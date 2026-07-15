# BAS-001 — Baseline de Controles Técnicos Transversais para Soluções de Inteligência Artificial

| Campo | Valor |
|---|---|
| **Código** | BAS-001 |
| **Nome** | Baseline de Controles Técnicos Transversais para Soluções de IA |
| **Tipo documental** | Baseline técnico |
| **Classificação da informação** | Uso Interno |
| **Status** | Minuta para revisão |
| **Versão** | 1.3 |
| **Data** | 13/07/2026 |
| **Owner institucional** | Segurança da Informação / Segurança de IA |
| **Custodiante técnico** | Arquitetura de Segurança da Informação |
| **Quantidade de controles** | 42 |

## 1. Objetivo

Estabelecer recomendações técnicas transversais, verificáveis e auditáveis para configuração e operação segura de soluções corporativas de Inteligência Artificial. O documento segue a estrutura de recomendações dos CIS Benchmarks e contém somente controles técnicos comuns a diferentes arquiteturas. Fluxos de aprovação, onboarding, gestão de risco, exceções, contratação, RACI e resposta processual a incidentes estão fora do escopo.

## 2. Escopo

Aplica-se transversalmente a aplicações consumidoras de IA, APIs, gateways, modelos, runtimes, serviços gerenciados, pipelines, ambientes locais ou cloud, consoles administrativos, prompts, outputs, logs e componentes de integração. Este baseline não representa isoladamente o conjunto completo de requisitos de segurança. Deve ser aplicado cumulativamente com todos os baselines especializados compatíveis com as características técnicas da solução.

## 3. Modelo de classificação

### 3.1 Profile Applicability

- **Level 1:** configuração fundamental para qualquer solução corporativa de IA. Deve reduzir a superfície de ataque sem impedir a função principal da tecnologia.
- **Level 2:** defesa em profundidade para soluções críticas, externas, com dados sensíveis, alta autonomia ou impacto material. Pressupõe conformidade com todos os controles Level 1 aplicáveis.

### 3.2 Criticidade

| Criticidade | Critério |
|---|---|
| **Crítica** | A ausência permite diretamente acesso não autorizado, execução indevida, exposição de dados/segredos, bypass de controle ou perda da capacidade de contenção. |
| **Alta** | A ausência enfraquece significativamente uma fronteira de segurança, aumenta materialmente a superfície de ataque ou reduz detecção e recuperação. |
| **Média** | Controle de hardening ou defesa em profundidade cuja ausência aumenta risco, mas normalmente exige falha adicional para produzir impacto material. |
| **Baixa** | Otimização técnica com impacto limitado. Esta versão do baseline não contém recomendações de criticidade Baixa. |

## 4. Regras de interpretação

1. Cada recomendação deve ser avaliada de forma independente.
2. Um controle é **Conforme** somente quando todos os critérios descritos em **Audit** forem atendidos.
3. Implementação parcial deve ser registrada como **Não Conforme**; não existe conformidade parcial neste baseline.
4. Quando uma recomendação não se aplicar tecnicamente, a justificativa deve indicar o componente inexistente ou a condição técnica que impede a aplicação.
5. Controles processuais e administrativos não devem ser usados para substituir os requisitos técnicos deste documento.

## Sumário

- [1. Arquitetura e configuração segura](#1-arquitetura-e-configuracao-segura)
  - [1.1 Certifique-se de que os componentes de IA implantados exponham identificação única e metadados de versão](#11-certifique-se-de-que-os-componentes-de-ia-implantados-exponham-identificacao-unica-e-metadados-de-versao)
  - [1.2 Certifique-se de que os ambientes de desenvolvimento, teste e produção de IA estejam isolados](#12-certifique-se-de-que-os-ambientes-de-desenvolvimento-teste-e-producao-de-ia-estejam-isolados)
  - [1.3 Certifique-se de que endpoints internos de IA não estejam acessíveis publicamente](#13-certifique-se-de-que-endpoints-internos-de-ia-nao-estejam-acessiveis-publicamente)
  - [1.4 Certifique-se de que os fluxos de rede de IA utilizem allowlists explícitas de entrada e saída](#14-certifique-se-de-que-os-fluxos-de-rede-de-ia-utilizem-allowlists-explicitas-de-entrada-e-saida)
  - [1.5 Certifique-se de que modelos, endpoints, conectores, plugins e interfaces de IA não utilizados estejam desabilitados](#15-certifique-se-de-que-modelos-endpoints-conectores-plugins-e-interfaces-de-ia-nao-utilizados-estejam-desabilitados)
- [2. Identidade, acesso e segredos](#2-identidade-acesso-e-segredos)
  - [2.1 Certifique-se de que o acesso humano utilize federação corporativa e proíba contas compartilhadas ou pessoais](#21-certifique-se-de-que-o-acesso-humano-utilize-federacao-corporativa-e-proiba-contas-compartilhadas-ou-pessoais)
  - [2.2 Certifique-se de que a autenticação multifator seja obrigatória para acessos privilegiados de IA](#22-certifique-se-de-que-a-autenticacao-multifator-seja-obrigatoria-para-acessos-privilegiados-de-ia)
  - [2.3 Certifique-se de que cada workload de IA utilize identidade exclusiva por aplicação e ambiente](#23-certifique-se-de-que-cada-workload-de-ia-utilize-identidade-exclusiva-por-aplicacao-e-ambiente)
  - [2.4 Certifique-se de que as permissões de IA sigam menor privilégio e negação por padrão](#24-certifique-se-de-que-as-permissoes-de-ia-sigam-menor-privilegio-e-negacao-por-padrao)
  - [2.5 Certifique-se de que a autorização seja determinística e independente do output do modelo](#25-certifique-se-de-que-a-autorizacao-seja-deterministica-e-independente-do-output-do-modelo)
  - [2.6 Certifique-se de que a identidade do solicitante original seja propagada de ponta a ponta](#26-certifique-se-de-que-a-identidade-do-solicitante-original-seja-propagada-de-ponta-a-ponta)
  - [2.7 Certifique-se de que segredos sejam armazenados em serviço de gestão aprovado e nunca expostos ao modelo](#27-certifique-se-de-que-segredos-sejam-armazenados-em-servico-de-gestao-aprovado-e-nunca-expostos-ao-modelo)
  - [2.8 Certifique-se de que credenciais e tokens tenham curta duração e rotação automática](#28-certifique-se-de-que-credenciais-e-tokens-tenham-curta-duracao-e-rotacao-automatica)
  - [2.9 Certifique-se de que a administração privilegiada de IA utilize PAM e elevação just-in-time](#29-certifique-se-de-que-a-administracao-privilegiada-de-ia-utilize-pam-e-elevacao-just-in-time)
- [3. Proteção de dados, prompts e outputs](#3-protecao-de-dados-prompts-e-outputs)
  - [3.1 Certifique-se de que as comunicações de IA utilizem TLS 1.2 ou superior](#31-certifique-se-de-que-as-comunicacoes-de-ia-utilizem-tls-12-ou-superior)
  - [3.2 Certifique-se de que os dados de IA estejam criptografados em repouso](#32-certifique-se-de-que-os-dados-de-ia-estejam-criptografados-em-repouso)
  - [3.3 Certifique-se de que prompts e inputs utilizem allowlist explícita de campos de dados](#33-certifique-se-de-que-prompts-e-inputs-utilizem-allowlist-explicita-de-campos-de-dados)
  - [3.4 Certifique-se de que conteúdo sensível em prompts e uploads seja detectado e removido ou bloqueado automaticamente](#34-certifique-se-de-que-conteudo-sensivel-em-prompts-e-uploads-seja-detectado-e-removido-ou-bloqueado-automaticamente)
  - [3.5 Certifique-se de que treinamento pelo provider, revisão humana e retenção desnecessária estejam desabilitados](#35-certifique-se-de-que-treinamento-pelo-provider-revisao-humana-e-retencao-desnecessaria-estejam-desabilitados)
  - [3.6 Certifique-se de que prompts, outputs, uploads, caches e dados temporários possuam retenção e exclusão forçadas](#36-certifique-se-de-que-prompts-outputs-uploads-caches-e-dados-temporarios-possuam-retencao-e-exclusao-forcadas)
  - [3.7 Certifique-se de que sessões, tenants, usuários e memória persistente estejam logicamente isolados](#37-certifique-se-de-que-sessoes-tenants-usuarios-e-memoria-persistente-estejam-logicamente-isolados)
- [4. Modelos, runtime e cadeia de fornecimento](#4-modelos-runtime-e-cadeia-de-fornecimento)
  - [4.1 Certifique-se de que o acesso em produção seja restrito a allowlist explícita de modelos, providers, regiões e endpoints](#41-certifique-se-de-que-o-acesso-em-producao-seja-restrito-a-allowlist-explicita-de-modelos-providers-regioes-e-endpoints)
  - [4.2 Certifique-se de que versões de modelo, API, runtime e dependências de produção estejam fixadas](#42-certifique-se-de-que-versoes-de-modelo-api-runtime-e-dependencias-de-producao-estejam-fixadas)
  - [4.3 Certifique-se de que artefatos de IA self-hosted sejam verificados por hash criptográfico ou assinatura antes do carregamento](#43-certifique-se-de-que-artefatos-de-ia-self-hosted-sejam-verificados-por-hash-criptografico-ou-assinatura-antes-do-carregamento)
  - [4.4 Certifique-se de que runtimes de produção não baixem dinamicamente modelos, código, plugins ou dependências](#44-certifique-se-de-que-runtimes-de-producao-nao-baixem-dinamicamente-modelos-codigo-plugins-ou-dependencias)
  - [4.5 Certifique-se de que runtimes de IA executem sem root, com menor privilégio e acesso restrito ao sistema operacional](#45-certifique-se-de-que-runtimes-de-ia-executem-sem-root-com-menor-privilegio-e-acesso-restrito-ao-sistema-operacional)
- [5. Segurança de aplicação e integrações](#5-seguranca-de-aplicacao-e-integracoes)
  - [5.1 Certifique-se de que inputs de IA e conteúdos enviados sejam validados antes do processamento](#51-certifique-se-de-que-inputs-de-ia-e-conteudos-enviados-sejam-validados-antes-do-processamento)
  - [5.2 Certifique-se de que instruções de sistema e desenvolvedor, input do usuário e contexto recuperado estejam separados e protegidos](#52-certifique-se-de-que-instrucoes-de-sistema-e-desenvolvedor-input-do-usuario-e-contexto-recuperado-estejam-separados-e-protegidos)
  - [5.3 Certifique-se de que outputs estruturados de IA sejam validados contra schema estrito e allowlist](#53-certifique-se-de-que-outputs-estruturados-de-ia-sejam-validados-contra-schema-estrito-e-allowlist)
  - [5.4 Certifique-se de que o output de IA seja codificado ou sanitizado para o contexto de destino](#54-certifique-se-de-que-o-output-de-ia-seja-codificado-ou-sanitizado-para-o-contexto-de-destino)
  - [5.5 Certifique-se de que código, queries, comandos e configurações gerados não sejam executados diretamente](#55-certifique-se-de-que-codigo-queries-comandos-e-configuracoes-gerados-nao-sejam-executados-diretamente)
  - [5.6 Certifique-se de que limites de requisição, tokens, concorrência e custo sejam aplicados por identidade](#56-certifique-se-de-que-limites-de-requisicao-tokens-concorrencia-e-custo-sejam-aplicados-por-identidade)
  - [5.7 Certifique-se de que chamadas de IA utilizem timeout, retries limitados, backoff e circuit breaker](#57-certifique-se-de-que-chamadas-de-ia-utilizem-timeout-retries-limitados-backoff-e-circuit-breaker)
- [6. Logging, auditoria e monitoramento](#6-logging-auditoria-e-monitoramento)
  - [6.1 Certifique-se de que eventos de segurança de IA sejam registrados com campos obrigatórios](#61-certifique-se-de-que-eventos-de-seguranca-de-ia-sejam-registrados-com-campos-obrigatorios)
  - [6.2 Certifique-se de que identificadores de trace e correlação sejam propagados de ponta a ponta com tempo sincronizado em UTC](#62-certifique-se-de-que-identificadores-de-trace-e-correlacao-sejam-propagados-de-ponta-a-ponta-com-tempo-sincronizado-em-utc)
  - [6.3 Certifique-se de que logs de IA estejam protegidos contra alteração e com acesso restrito](#63-certifique-se-de-que-logs-de-ia-estejam-protegidos-contra-alteracao-e-com-acesso-restrito)
  - [6.4 Certifique-se de que segredos e conteúdo sensível não sejam gravados em logs de IA](#64-certifique-se-de-que-segredos-e-conteudo-sensivel-nao-sejam-gravados-em-logs-de-ia)
  - [6.5 Certifique-se de que eventos críticos de IA sejam centralizados e gerem alertas acionáveis](#65-certifique-se-de-que-eventos-criticos-de-ia-sejam-centralizados-e-gerem-alertas-acionaveis)
- [7. Resiliência e recuperação](#7-resiliencia-e-recuperacao)
  - [7.1 Certifique-se de que o processamento de IA falhe de forma fechada quando autorização, policy ou DLP estiver indisponível](#71-certifique-se-de-que-o-processamento-de-ia-falhe-de-forma-fechada-quando-autorizacao-policy-ou-dlp-estiver-indisponivel)
  - [7.2 Certifique-se de que health checks e fallback seguro impeçam o uso de componentes de IA degradados](#72-certifique-se-de-que-health-checks-e-fallback-seguro-impecam-o-uso-de-componentes-de-ia-degradados)
  - [7.3 Certifique-se de que configurações, prompts, policies e artefatos de deployment sejam versionados, copiados e passíveis de rollback](#73-certifique-se-de-que-configuracoes-prompts-policies-e-artefatos-de-deployment-sejam-versionados-copiados-e-passiveis-de-rollback)
  - [7.4 Certifique-se de que um kill switch de emergência possa interromper o processamento de IA e revogar credenciais associadas](#74-certifique-se-de-que-um-kill-switch-de-emergencia-possa-interromper-o-processamento-de-ia-e-revogar-credenciais-associadas)
- [8. Referências gerais](#8-referencias-gerais)

## 1. Arquitetura e configuração segura

### 1.1 Certifique-se de que os componentes de IA implantados exponham identificação única e metadados de versão

**Control ID:** BAS-001.1.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Todos os componentes de IA implantados em desenvolvimento, homologação ou produção.

**Description**

Cada endpoint, deployment, modelo, runtime, gateway ou serviço de IA deve expor ou registrar, em fonte consultável, no mínimo: identificador único, nome do componente, ambiente, versão do modelo, versão do runtime ou API, provider, região quando aplicável e data/hora da última alteração. Valores genéricos como latest, default, current ou equivalentes não atendem ao controle em produção.

**Rationale**

Sem identificação e versão inequívocas, não é possível determinar qual componente processou uma requisição, correlacionar incidentes, reproduzir resultados, avaliar vulnerabilidades ou executar rollback confiável.

**Impact**

A inclusão de metadados pode exigir ajuste em tags, labels, headers, variáveis de ambiente, manifestos ou registros de deployment.

**Audit**

1. Consultar todos os deployments e endpoints ativos.
2. Confirmar que 100% possuem identificador único não reutilizado entre ambientes.
3. Confirmar que modelo, runtime/API, provider e ambiente possuem valores explícitos e não utilizam aliases mutáveis como latest.
4. Reprovar se qualquer componente ativo não puder ser associado de forma determinística à sua versão e ambiente.

**Remediation**

Adicionar metadados obrigatórios ao manifesto, catálogo técnico ou configuração do deployment. Substituir aliases mutáveis por versões explícitas e garantir que os metadados sejam incluídos nos eventos de execução.

**Evidence**

Exportação de deployments ou manifestos contendo identificador, ambiente, modelo, versão, provider/região e timestamp de alteração.

**Mappings**

CIS Controls v8 1 e 4; NIST SP 800-53 CM; NIST AI RMF GOVERN e MAP

---

### 1.2 Certifique-se de que os ambientes de desenvolvimento, teste e produção de IA estejam isolados

**Control ID:** BAS-001.1.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Soluções que possuam mais de um ambiente.

**Description**

Desenvolvimento, testes, homologação e produção devem utilizar identidades, credenciais, endpoints, dados, storage, índices, filas, redes e configurações segregadas. É proibido utilizar credenciais de produção em ambientes não produtivos ou permitir que componentes não produtivos escrevam em recursos produtivos.

**Rationale**

A ausência de segregação facilita movimentação lateral, exposição de dados reais, alterações não autorizadas e promoção acidental de configurações ou artefatos não testados.

**Impact**

A segregação pode elevar o custo de infraestrutura e exigir duplicação de recursos, identidades e configurações.

**Audit**

1. Revisar o diagrama e as configurações de cada ambiente.
2. Confirmar que identidades e credenciais não são compartilhadas entre produção e não produção.
3. Executar teste negativo comprovando que uma identidade de desenvolvimento não consegue ler nem alterar recursos de produção.
4. Confirmar que dados produtivos não estão presentes em ambientes inferiores, salvo dados mascarados ou sintetizados.
5. Reprovar se qualquer fronteira depender apenas de convenção de nomes sem enforcement técnico.

**Remediation**

Separar contas, subscriptions, projects, namespaces, redes, identidades, cofres e stores por ambiente. Criar políticas que neguem acesso cruzado e substituir dados reais por dados sintéticos ou mascarados.

**Evidence**

Diagrama por ambiente, matrizes de acesso, políticas de negação cruzada e resultados de testes negativos.

**Mappings**

CIS Controls v8 4, 5 e 6; NIST SP 800-53 AC, CM e SC

---

### 1.3 Certifique-se de que endpoints internos de IA não estejam acessíveis publicamente

**Control ID:** BAS-001.1.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Endpoints, gateways, APIs, consoles e runtimes classificados como internos.

**Description**

Componentes internos de IA não devem possuir endereço público, rota direta a partir da Internet, regra de firewall aberta para 0.0.0.0/0 ou ::/0, anonymous access ou mecanismo equivalente. O acesso deve ocorrer por rede privada, VPN, proxy, gateway corporativo ou serviço de acesso autenticado.

**Rationale**

A exposição pública de endpoints internos permite enumeração, abuso de recursos, tentativa de roubo de credenciais, extração de modelos, vazamento de dados e negação de serviço.

**Impact**

O controle pode exigir private endpoints, DNS privado, alterações de roteamento ou componentes adicionais de acesso.

**Audit**

1. Enumerar todos os endpoints e interfaces de administração.
2. Confirmar que endpoints internos não possuem IP público, public access ou rota de Internet.
3. Confirmar que regras de entrada não aceitam 0.0.0.0/0 ou ::/0.
4. Testar conexão a partir de rede externa não autorizada; o resultado deve ser bloqueio de rede antes da autenticação.
5. Reprovar se a proteção depender somente de segredo em URL ou chave de API.

**Remediation**

Desabilitar public access, remover IPs públicos, criar private endpoints e restringir regras de firewall ou security groups às origens corporativas aprovadas.

**Evidence**

Exportação de configuração de rede, regras de firewall/security group e resultado de teste externo bloqueado.

**Mappings**

CIS Controls v8 4, 12 e 13; NIST SP 800-53 AC-4, SC-7

---

### 1.4 Certifique-se de que os fluxos de rede de IA utilizem allowlists explícitas de entrada e saída

**Control ID:** BAS-001.1.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Todos os componentes que realizem comunicação de rede.

**Description**

O tráfego de entrada e saída deve ser limitado a origens, destinos, portas e protocolos explicitamente autorizados. Egress irrestrito para Internet não é permitido em runtimes que processem dados corporativos. DNS, proxies e service endpoints devem impedir conexão com providers, registries, URLs ou serviços não aprovados.

**Rationale**

Egress irrestrito permite exfiltração, download de artefatos maliciosos, contato com command-and-control e bypass do catálogo corporativo.

**Impact**

A aplicação de allowlists exige manutenção dos destinos e pode afetar integrações dinâmicas.

**Audit**

1. Extrair regras de firewall, security groups, network policies, proxy e DNS.
2. Confirmar inexistência de regras any/any para workloads de produção.
3. Confirmar que os destinos externos correspondem apenas a endpoints aprovados.
4. Testar acesso a um destino não autorizado; a conexão deve ser bloqueada e registrada.
5. Reprovar se o runtime puder acessar livremente a Internet.

**Remediation**

Aplicar network policies, firewall, proxy autenticado e DNS controlado. Definir allowlist por aplicação e ambiente e remover regras amplas.

**Evidence**

Regras exportadas, lista de destinos autorizados e evidência de teste de bloqueio de egress.

**Mappings**

CIS Controls v8 4, 12 e 13; NIST SP 800-53 SC-7

---

### 1.5 Certifique-se de que modelos, endpoints, conectores, plugins e interfaces de IA não utilizados estejam desabilitados

**Control ID:** BAS-001.1.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Plataformas, aplicações e serviços com funcionalidades configuráveis.

**Description**

Somente modelos, endpoints, APIs, conectores, plugins, ferramentas, interfaces administrativas e protocolos necessários ao caso de uso devem permanecer habilitados. Componentes de demonstração, playgrounds, anonymous access, public sharing, feedback público, browsing, code execution, file upload ou memória devem ser desabilitados quando não forem requisito técnico documentado.

**Rationale**

Funcionalidades não utilizadas ampliam a superfície de ataque e podem permitir caminhos de acesso ou processamento não cobertos pelos controles da solução.

**Impact**

A desativação pode remover conveniências de desenvolvimento e exigir habilitação controlada para testes específicos.

**Audit**

1. Obter a lista completa de capabilities habilitadas na plataforma.
2. Comparar com a arquitetura técnica do caso de uso.
3. Confirmar que cada capability habilitada possui consumidor técnico identificado.
4. Reprovar se playground, compartilhamento público, anonymous access ou execução de código estiver habilitado sem uso requerido.
5. Confirmar que componentes desativados não podem ser invocados por API.

**Remediation**

Desabilitar capabilities não utilizadas, remover endpoints e plugins, bloquear APIs de administração desnecessárias e aplicar default deny para novos recursos.

**Evidence**

Exportação das capabilities habilitadas, arquitetura do caso de uso e teste de invocação de recurso desativado.

**Mappings**

CIS Controls v8 4; NIST SP 800-53 CM-7

---

## 2. Identidade, acesso e segredos

### 2.1 Certifique-se de que o acesso humano utilize federação corporativa e proíba contas compartilhadas ou pessoais

**Control ID:** BAS-001.2.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Acesso humano a consoles, gateways, notebooks, IDEs, portais e APIs administrativas.

**Description**

Todo acesso humano deve utilizar identidade corporativa federada e individual. Contas compartilhadas, contas pessoais, tenants pessoais e credenciais genéricas não devem autenticar em recursos corporativos de IA. Contas locais de emergência devem permanecer desabilitadas para uso normal.

**Rationale**

Identidades não individuais impedem atribuição de ações, revogação seletiva, aplicação de políticas corporativas e investigação confiável.

**Impact**

A integração com o provedor de identidade pode exigir configuração de SAML, OIDC, SCIM ou mecanismo equivalente.

**Audit**

1. Listar métodos de autenticação e todas as contas com acesso.
2. Confirmar que o método primário é federação corporativa.
3. Confirmar que cada conta humana está associada a uma pessoa identificável.
4. Confirmar inexistência de contas pessoais ou compartilhadas habilitadas.
5. Reprovar se uma conta local puder ser usada rotineiramente sem federação.

**Remediation**

Configurar federação com o IdP corporativo, migrar permissões para grupos corporativos, desabilitar contas pessoais/compartilhadas e restringir contas locais a break-glass.

**Evidence**

Configuração de federação, lista de contas e grupos e evidência de contas locais desabilitadas ou restritas.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 IA e AC

---

### 2.2 Certifique-se de que a autenticação multifator seja obrigatória para acessos privilegiados de IA

**Control ID:** BAS-001.2.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Administradores, operadores privilegiados, proprietários de chaves e usuários com capacidade de alterar modelos, policies, endpoints ou dados.

**Description**

MFA deve ser obrigatório para todo acesso humano privilegiado. O fluxo não pode permitir bypass por autenticação legada, token de longa duração, conta local comum, protocolo sem MFA ou recuperação de conta sem controle equivalente.

**Rationale**

O comprometimento de uma única senha privilegiada pode permitir alteração de modelos, extração de dados, desativação de logs e criação de chaves persistentes.

**Impact**

MFA pode exigir dispositivos ou métodos adicionais e alterar fluxos de automação inadequadamente baseados em contas humanas.

**Audit**

1. Listar todos os papéis e grupos privilegiados.
2. Confirmar política de MFA obrigatória para 100% dos membros.
3. Confirmar que protocolos legados ou contas locais não permitem bypass.
4. Testar autenticação privilegiada sem segundo fator; o acesso deve ser negado.
5. Reprovar se houver qualquer administrador ativo sem MFA.

**Remediation**

Habilitar MFA no IdP e na plataforma, bloquear autenticação legada, remover exceções permanentes e migrar automações para workload identities.

**Evidence**

Política de MFA, lista de papéis privilegiados, relatório de cobertura e teste de acesso negado sem segundo fator.

**Mappings**

CIS Controls v8 6; NIST SP 800-53 IA-2

---

### 2.3 Certifique-se de que cada workload de IA utilize identidade exclusiva por aplicação e ambiente

**Control ID:** BAS-001.2.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Aplicações, gateways, pipelines, notebooks, jobs, agentes e serviços.

**Description**

Cada workload deve utilizar identidade técnica exclusiva por aplicação, finalidade e ambiente. Uma mesma identidade não deve ser reutilizada por sistemas distintos ou entre desenvolvimento e produção. A identidade deve ser revogável sem impactar workloads não relacionados.

**Rationale**

Identidades compartilhadas ampliam o impacto de comprometimento e impedem atribuição precisa das ações.

**Impact**

A criação de identidades adicionais aumenta o número de objetos IAM a administrar.

**Audit**

1. Listar workloads e respectivas identidades técnicas.
2. Confirmar relação um-para-um entre workload/finalidade/ambiente e identidade.
3. Confirmar que não há reutilização da identidade de produção em não produção.
4. Reprovar se uma credencial ou principal for compartilhado por aplicações independentes.

**Remediation**

Criar workload identities separadas, migrar permissões e credenciais, atualizar configurações e revogar identidades compartilhadas.

**Evidence**

Matriz workload-identidade-ambiente, configurações IAM e evidência de revogação das identidades antigas.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-2 e IA-4

---

### 2.4 Certifique-se de que as permissões de IA sigam menor privilégio e negação por padrão

**Control ID:** BAS-001.2.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Todas as identidades humanas e técnicas.

**Description**

Permissões devem ser concedidas por recurso, ação, ambiente e finalidade, com default deny. Papéis curinga, administrador global, owner permanente, permissões all/* ou equivalentes não devem ser usados por workloads ou operadores comuns. Permissões de leitura, inferência, administração, publicação e acesso a dados devem ser separadas.

**Rationale**

Permissões amplas permitem escalonamento de privilégio, acesso a dados fora da finalidade e alterações destrutivas.

**Impact**

A granularidade pode exigir criação de papéis personalizados e manutenção de políticas adicionais.

**Audit**

1. Revisar todas as políticas associadas às identidades da solução.
2. Identificar ações ou recursos com wildcard.
3. Confirmar separação entre inferência, administração, publicação e acesso a dados.
4. Executar testes negativos para ações fora do escopo; todas devem ser negadas.
5. Reprovar se workload ou usuário comum possuir papel administrativo amplo.

**Remediation**

Substituir papéis amplos por funções específicas, limitar recursos e ações, remover permissões não utilizadas e aplicar explicit deny quando suportado.

**Evidence**

Políticas IAM, matriz de permissões e resultados dos testes negativos.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-3 e AC-6

---

### 2.5 Certifique-se de que a autorização seja determinística e independente do output do modelo

**Control ID:** BAS-001.2.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Qualquer solução em que o modelo solicite acesso a dados, ferramentas, funções ou ações.

**Description**

A decisão de autorização deve ser executada por mecanismo determinístico externo ao modelo. Texto gerado pelo modelo, prompt sistêmico, classificação sem enforcement ou decisão probabilística não pode conceder permissão. O enforcement deve considerar principal efetivo, ação, recurso, ambiente, finalidade e limites aplicáveis.

**Rationale**

Modelos podem ser manipulados, alucinar ou interpretar incorretamente instruções; tratá-los como mecanismo de autorização permite bypass de controles.

**Impact**

A implementação exige integração com IAM, policy engine, API gateway ou autorização no sistema-alvo.

**Audit**

1. Identificar todas as operações que leem dados ou executam ações após resposta do modelo.
2. Confirmar que existe verificação de autorização fora do modelo imediatamente antes da operação.
3. Executar tentativa com principal sem permissão; a operação deve ser bloqueada mesmo que o modelo a solicite.
4. Confirmar que o bloqueio é registrado com principal, ação, recurso e decisão.
5. Reprovar se a autorização depender exclusivamente de prompt, guardrail ou classificação do LLM.

**Remediation**

Implementar policy enforcement determinístico no gateway, aplicação ou sistema-alvo. Aplicar default deny e validar cada operação com a identidade efetiva.

**Evidence**

Diagrama do fluxo de autorização, policy, testes positivos/negativos e logs de decisão.

**Mappings**

CIS Controls v8 6; NIST SP 800-53 AC-3; OWASP GenAI Excessive Agency

---

### 2.6 Certifique-se de que a identidade do solicitante original seja propagada de ponta a ponta

**Control ID:** BAS-001.2.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Soluções em que um backend, gateway ou agente acessa recursos em nome de usuário ou sistema originador.

**Description**

A identidade do solicitante original deve ser propagada por on-behalf-of, token exchange ou contexto assinado. Quando o destino não suportar delegação, a camada intermediária deve registrar de forma imutável o solicitante, identidade executora, recurso, ação, política aplicada e resultado. Contas técnicas não podem apagar a identidade originadora.

**Rationale**

Sem identidade originadora, ações diferentes parecem ter sido executadas pela mesma conta técnica, inviabilizando autorização contextual e investigação.

**Impact**

Pode exigir token exchange, claims adicionais, signed context ou broker de identidade.

**Audit**

1. Rastrear uma requisição de teste do usuário até o recurso final.
2. Confirmar que usuário/sistema originador está presente em todos os pontos de decisão e logs.
3. Confirmar que o destino ou broker valida a integridade do contexto delegado.
4. Executar duas requisições de usuários diferentes e verificar atribuição distinta.
5. Reprovar se apenas a conta técnica for registrada.

**Remediation**

Implementar OAuth/OIDC on-behalf-of, token exchange ou contexto assinado. Adicionar os campos de identidade originadora aos logs e às decisões de autorização.

**Evidence**

Trace ponta a ponta, claims/tokens mascarados, logs correlacionados e teste com múltiplos usuários.

**Mappings**

CIS Controls v8 6 e 8; NIST SP 800-53 AC e AU

---

### 2.7 Certifique-se de que segredos sejam armazenados em serviço de gestão aprovado e nunca expostos ao modelo

**Control ID:** BAS-001.2.7
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Chaves de API, tokens, certificados, senhas e credenciais usadas pela solução.

**Description**

Segredos devem ser armazenados em cofre ou serviço corporativo de secrets e injetados em tempo de execução. É proibido armazená-los em código, notebooks, prompts, system prompts, arquivos de configuração em texto claro, imagens, variáveis expostas no client, logs ou outputs. O modelo não deve receber o valor do segredo no contexto.

**Rationale**

Segredos expostos ao modelo, código ou logs podem ser extraídos, versionados inadvertidamente ou utilizados fora da solução.

**Impact**

A integração com cofre pode exigir alteração de deployment, identidade e pipeline.

**Audit**

1. Executar secrets scanning em código, notebooks, prompts, configurações e imagens.
2. Inspecionar variáveis e mounts do runtime e confirmar origem em serviço de secrets.
3. Confirmar que front-end e modelo não recebem o valor do segredo.
4. Confirmar que logs e traces não contêm segredos.
5. Reprovar em qualquer detecção de segredo válido fora do cofre.

**Remediation**

Migrar segredos para cofre aprovado, utilizar workload identity para leitura, remover valores hardcoded, reemitir credenciais expostas e aplicar scanning no pipeline.

**Evidence**

Relatório de secrets scanning, configuração do cofre, policy de acesso e evidência de rotação dos segredos expostos.

**Mappings**

CIS Controls v8 3, 4 e 16; NIST SP 800-53 IA-5 e SC-12

---

### 2.8 Certifique-se de que credenciais e tokens tenham curta duração e rotação automática

**Control ID:** BAS-001.2.8
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Credenciais técnicas, tokens de acesso, chaves e certificados.

**Description**

Sempre que suportado, workloads devem utilizar credenciais temporárias emitidas dinamicamente. Tokens devem possuir expiração definida e mínima compatível com a operação. Credenciais estáticas devem possuir rotação automática, data de validade e mecanismo de revogação. Tokens sem expiração não são permitidos em produção.

**Rationale**

Credenciais de longa duração ampliam a janela de exploração após vazamento e dificultam revogação segura.

**Impact**

Pode exigir adaptação de SDKs, automações e processos de renovação.

**Audit**

1. Listar credenciais, tokens e certificados utilizados pela solução.
2. Confirmar data de emissão, expiração e rotação automática.
3. Confirmar inexistência de tokens sem expiração.
4. Confirmar que a aplicação renova credenciais sem indisponibilidade.
5. Reprovar se credencial estática não tiver validade e rotação definidas.

**Remediation**

Migrar para workload identity ou STS, reduzir TTL, habilitar rotação automática e implementar revogação. Reemitir credenciais antigas.

**Evidence**

Inventário de credenciais com TTL, configuração de rotação e teste de renovação/revogação.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 IA-5

---

### 2.9 Certifique-se de que a administração privilegiada de IA utilize PAM e elevação just-in-time

**Control ID:** BAS-001.2.9
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Ambientes críticos, dados sensíveis ou acesso com capacidade de alterar modelos, policies, identidades, logs ou endpoints.

**Description**

Acesso privilegiado deve ser concedido por PAM ou mecanismo equivalente, com elevação just-in-time, duração limitada, sessão registrada e credenciais não conhecidas pelo usuário quando suportado. Papéis privilegiados permanentes devem ser restritos a contas de emergência.

**Rationale**

Privilégio permanente aumenta a exposição a comprometimento de conta e abuso interno.

**Impact**

A implementação pode aumentar o tempo para atividades administrativas e exigir integração com PAM.

**Audit**

1. Listar papéis privilegiados e respectivos membros permanentes.
2. Confirmar que atividades administrativas comuns exigem elevação temporária.
3. Confirmar expiração automática e registro da sessão.
4. Confirmar que contas de emergência não são usadas rotineiramente.
5. Reprovar se administradores mantiverem privilégio permanente sem necessidade técnica.

**Remediation**

Integrar a plataforma ao PAM, remover atribuições permanentes, configurar elevação JIT com prazo curto e registrar sessões administrativas.

**Evidence**

Relatório PAM/JIT, lista de papéis permanentes, sessões registradas e teste de expiração.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-2 e AC-6

---

## 3. Proteção de dados, prompts e outputs

### 3.1 Certifique-se de que as comunicações de IA utilizem TLS 1.2 ou superior

**Control ID:** BAS-001.3.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Todas as comunicações entre cliente, aplicação, gateway, provider, modelo, storage e ferramentas.

**Description**

Todas as conexões devem utilizar TLS 1.2 ou superior com validação de certificado e hostname. Protocolos em texto claro, TLS 1.0/1.1, certificados expirados, self-signed não confiáveis ou validação desabilitada não são permitidos em produção.

**Rationale**

Tráfego não protegido permite interceptação, alteração de prompts/outputs e roubo de tokens.

**Impact**

Componentes legados podem precisar de atualização ou substituição.

**Audit**

1. Enumerar endpoints e conexões da solução.
2. Executar teste de protocolo e confirmar rejeição de TLS inferior a 1.2.
3. Confirmar validação de cadeia e hostname.
4. Confirmar ausência de flags que desabilitem verificação de certificado.
5. Reprovar em qualquer conexão em texto claro ou TLS obsoleto.

**Remediation**

Habilitar TLS 1.2/1.3, instalar certificados confiáveis, remover ciphers/protocolos obsoletos e corrigir clientes que ignorem validação.

**Evidence**

Relatório de scan TLS, configuração de endpoints e teste de conexão rejeitada com protocolo obsoleto.

**Mappings**

CIS Controls v8 3 e 12; NIST SP 800-53 SC-8 e SC-13

---

### 3.2 Certifique-se de que os dados de IA estejam criptografados em repouso

**Control ID:** BAS-001.3.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Storage, bancos, filas, caches, logs, datasets, artefatos, embeddings e backups.

**Description**

Dados e artefatos persistidos pela solução devem ser criptografados em repouso com mecanismo corporativo aprovado. Criptografia deve abranger volumes, objetos, databases, vector stores, logs e backups. Chaves não podem ser armazenadas junto aos dados em texto claro.

**Rationale**

Criptografia reduz exposição em caso de acesso indevido ao storage, snapshot, mídia ou backup.

**Impact**

Pode exigir gerenciamento de chaves e impactar custos ou desempenho.

**Audit**

1. Listar todos os stores persistentes e backups.
2. Confirmar encryption at rest habilitado em 100% dos recursos.
3. Confirmar algoritmo e chave gerenciada aprovados.
4. Confirmar que snapshots e réplicas também estão criptografados.
5. Reprovar se qualquer store com dados corporativos estiver sem criptografia.

**Remediation**

Habilitar criptografia, migrar ou recriar recursos não criptografados, proteger chaves em KMS/HSM e reemitir backups.

**Evidence**

Exportação de configurações de criptografia, inventário de stores e configuração de KMS/HSM.

**Mappings**

CIS Controls v8 3; NIST SP 800-53 SC-12, SC-13 e SC-28

---

### 3.3 Certifique-se de que prompts e inputs utilizem allowlist explícita de campos de dados

**Control ID:** BAS-001.3.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Aplicações que constroem prompts, payloads, anexos ou contexto a partir de dados corporativos.

**Description**

O payload enviado à IA deve ser construído por allowlist explícita de campos necessários. Enviar objetos completos, registros completos, dumps, tabelas inteiras ou contexto adicional por conveniência não atende ao controle. Cada campo transmitido deve ser necessário para a função técnica da chamada.

**Rationale**

Payloads excessivos aumentam risco de vazamento, retenção indevida, exposição por logs e uso fora da finalidade.

**Impact**

Pode exigir transformação de payload e manutenção da allowlist quando o schema mudar.

**Audit**

1. Revisar o código ou configuração que monta o prompt/payload.
2. Comparar campos enviados com os campos tecnicamente necessários.
3. Confirmar que o código seleciona campos explicitamente e não serializa o objeto de origem completo.
4. Executar teste com campo sensível adicional na origem e confirmar que ele não é transmitido.
5. Reprovar se a seleção depender apenas de exclusão pontual ou blacklist.

**Remediation**

Implementar DTO/schema específico para IA, selecionar somente campos permitidos, remover anexos e metadados desnecessários e adicionar testes de regressão.

**Evidence**

Trecho de código/configuração da allowlist, schema do payload e teste comprovando exclusão de campo não autorizado.

**Mappings**

CIS Controls v8 3 e 16; NIST SP 800-53 PT e SC

---

### 3.4 Certifique-se de que conteúdo sensível em prompts e uploads seja detectado e removido ou bloqueado automaticamente

**Control ID:** BAS-001.3.4
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Soluções que possam receber dados pessoais, bancários, segredos, código sensível ou arquivos de usuários.

**Description**

Antes do envio ao modelo ou provider, prompts, anexos, URLs e conteúdo extraído devem passar por mecanismo automático de detecção. Dados não permitidos devem ser removidos, mascarados, tokenizados ou bloqueados. O mecanismo deve operar no caminho de execução e não apenas como orientação ao usuário.

**Rationale**

Usuários e sistemas podem inserir dados sensíveis por erro ou manipulação; controles apenas documentais não impedem transmissão.

**Impact**

Pode gerar falsos positivos e exigir ajuste contínuo das regras.

**Audit**

1. Confirmar que o mecanismo DLP/redaction está no fluxo antes do provider.
2. Testar dados de cartão, identificador pessoal, segredo e token de API de laboratório.
3. Confirmar bloqueio ou mascaramento antes da transmissão.
4. Confirmar geração de evento de segurança sem registrar o segredo integral.
5. Reprovar se o dado chegar ao provider sem transformação.

**Remediation**

Implementar DLP, regex/classificadores e tokenização no gateway ou aplicação. Definir ação por categoria e bloquear em caso de falha do mecanismo.

**Evidence**

Configuração das regras, resultados de testes positivos/negativos e logs de bloqueio mascarados.

**Mappings**

CIS Controls v8 3 e 13; NIST SP 800-53 SI-4; OWASP Sensitive Information Disclosure

---

### 3.5 Certifique-se de que treinamento pelo provider, revisão humana e retenção desnecessária estejam desabilitados

**Control ID:** BAS-001.3.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Serviços gerenciados, SaaS, APIs e plataformas externas de IA.

**Description**

Configurações que permitam usar prompts, outputs, arquivos ou telemetria do tenant para treinamento, melhoria de serviço, feedback, human review ou retenção além do necessário devem permanecer desabilitadas. A configuração deve ser aplicada no tenant ou endpoint corporativo, não depender de escolha do usuário por sessão.

**Rationale**

O uso secundário de dados pode causar perda de confidencialidade, exposição a revisores e retenção incompatível com a finalidade.

**Impact**

Algumas funcionalidades de suporte ou melhoria podem ficar indisponíveis.

**Audit**

1. Consultar configurações do tenant, projeto e endpoint.
2. Confirmar que training/data sharing/feedback/human review estão desabilitados.
3. Confirmar que a retenção está no menor valor suportado compatível com o serviço.
4. Confirmar que novos deployments herdam a configuração segura.
5. Reprovar se o usuário final puder habilitar compartilhamento sem controle administrativo.

**Remediation**

Desabilitar opções de treinamento, compartilhamento, feedback e human review; configurar política organizacional para impedir reativação e selecionar endpoint/contrato com retenção adequada.

**Evidence**

Captura ou exportação das configurações do tenant/endpoint e teste de herança em novo deployment.

**Mappings**

CIS Controls v8 3 e 15; NIST AI RMF GOVERN; NIST SP 800-53 SA-9

---

### 3.6 Certifique-se de que prompts, outputs, uploads, caches e dados temporários possuam retenção e exclusão forçadas

**Control ID:** BAS-001.3.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Componentes que persistam conteúdo ou metadados de interação.

**Description**

Cada store deve possuir retenção técnica configurada e expurgo automático. Retenção indefinida não é permitida. O expurgo deve abranger prompts, outputs, uploads, históricos, caches, filas temporárias, traces completos, snapshots e cópias derivadas. A exclusão deve ser verificável.

**Rationale**

Dados esquecidos em caches ou stores temporários permanecem expostos além da necessidade e podem reaparecer após exclusão no sistema principal.

**Impact**

A retenção curta pode reduzir capacidade de troubleshooting e avaliação histórica.

**Audit**

1. Inventariar stores e identificar o TTL configurado.
2. Confirmar que nenhum store possui retenção indefinida.
3. Inserir registro de teste e confirmar exclusão automática após o prazo.
4. Confirmar que backups, caches e filas seguem regra compatível.
5. Reprovar se a exclusão depender exclusivamente de ação manual recorrente.

**Remediation**

Configurar lifecycle/TTL, jobs automáticos de expurgo e políticas para objetos temporários. Remover dados legados fora do prazo.

**Evidence**

Políticas de lifecycle/TTL, inventário de stores e evidência de registro de teste expirado.

**Mappings**

CIS Controls v8 3; NIST SP 800-53 SI-12 e MP-6

---

### 3.7 Certifique-se de que sessões, tenants, usuários e memória persistente estejam logicamente isolados

**Control ID:** BAS-001.3.7
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Soluções multiusuário, multitenant ou com histórico/memória.

**Description**

Contexto, histórico, cache e memória persistente devem ser associados a identificador de tenant e principal autenticado, e recuperados somente quando ambos corresponderem à sessão atual. Chaves de cache globais, memória compartilhada e histórico acessível por identificador fornecido pelo cliente não são permitidos.

**Rationale**

Falhas de isolamento permitem vazamento entre usuários, clientes, áreas ou sessões.

**Impact**

Pode exigir particionamento, row-level security ou namespaces separados.

**Audit**

1. Revisar como session_id, tenant_id e principal_id são gerados e validados.
2. Confirmar que identificadores são definidos pelo servidor e vinculados à identidade autenticada.
3. Executar testes cruzados entre dois usuários e dois tenants.
4. Confirmar que histórico e cache de um contexto não aparecem em outro.
5. Reprovar em qualquer recuperação cruzada ou se o cliente puder escolher livremente tenant/session de terceiros.

**Remediation**

Particionar stores, aplicar RLS/ABAC, gerar IDs no servidor, vincular memória à identidade autenticada e limpar caches compartilhados.

**Evidence**

Arquitetura de isolamento, políticas RLS/ABAC e resultados de testes cross-user/cross-tenant.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-4; OWASP Sensitive Information Disclosure

---

## 4. Modelos, runtime e cadeia de fornecimento

### 4.1 Certifique-se de que o acesso em produção seja restrito a allowlist explícita de modelos, providers, regiões e endpoints

**Control ID:** BAS-001.4.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Todos os ambientes produtivos.

**Description**

A aplicação ou gateway deve aceitar somente identificadores explícitos de modelos, providers, regiões e endpoints aprovados. Parâmetros fornecidos pelo usuário não podem selecionar livremente modelo, região ou URL. O default deve ser deny para itens não cadastrados.

**Rationale**

Seleção dinâmica não controlada permite bypass de restrições, envio de dados a região inadequada e uso de modelos inseguros.

**Impact**

A allowlist exige manutenção quando modelos são adicionados ou removidos.

**Audit**

1. Extrair a configuração de roteamento e modelos permitidos.
2. Confirmar que a seleção é server-side e não controlada diretamente pelo cliente.
3. Tentar invocar modelo, endpoint e região não cadastrados; todas as tentativas devem ser bloqueadas.
4. Confirmar que novos modelos não são automaticamente permitidos.
5. Reprovar se houver fallback para modelo arbitrário.

**Remediation**

Implementar catálogo/allowlist no gateway ou aplicação, validar parâmetros contra IDs aprovados e aplicar default deny.

**Evidence**

Configuração de allowlist, teste de modelo não autorizado e logs de bloqueio.

**Mappings**

CIS Controls v8 2, 4 e 15; NIST SP 800-53 CM-7 e SA-9

---

### 4.2 Certifique-se de que versões de modelo, API, runtime e dependências de produção estejam fixadas

**Control ID:** BAS-001.4.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Deployments produtivos e pipelines de build/deploy.

**Description**

Produção deve utilizar versões explícitas e imutáveis de modelo, API, SDK, runtime, container e dependências críticas. Aliases mutáveis como latest, stable, default ou auto-update não atendem ao controle. Atualização silenciosa de modelo ou runtime deve ser desabilitada quando configurável.

**Rationale**

Mudanças não controladas podem alterar comportamento, segurança, formato de output e compatibilidade sem teste ou rollback.

**Impact**

Fixar versões exige manutenção e atualização planejada.

**Audit**

1. Inspecionar manifestos, lockfiles, imagens e configurações de endpoint.
2. Confirmar que todos os componentes críticos usam versão ou digest explícito.
3. Confirmar que auto-upgrade/silent upgrade está desabilitado.
4. Confirmar existência da versão anterior para rollback.
5. Reprovar em qualquer referência mutável em produção.

**Remediation**

Fixar versões, usar digests de imagem, lockfiles e deployment IDs versionados. Desabilitar atualizações automáticas e registrar a versão anterior.

**Evidence**

Manifestos, lockfiles, digests, configuração de modelo/API e resultado de scan de referências mutáveis.

**Mappings**

CIS Controls v8 2 e 4; NIST SP 800-53 CM-2, CM-3 e SI-2

---

### 4.3 Certifique-se de que artefatos de IA self-hosted sejam verificados por hash criptográfico ou assinatura antes do carregamento

**Control ID:** BAS-001.4.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Modelos, adapters, tokenizers, plugins ou artefatos hospedados pela organização.

**Description**

O runtime deve verificar hash criptográfico esperado ou assinatura confiável antes de carregar artefatos. Download ou cópia sem verificação não é permitido. O valor esperado deve vir de fonte protegida e versionada, separada do artefato.

**Rationale**

Artefatos adulterados podem executar código malicioso, alterar comportamento ou exfiltrar dados.

**Impact**

A verificação adiciona etapa ao pipeline e exige gestão dos valores confiáveis.

**Audit**

1. Identificar todos os artefatos carregados em produção.
2. Confirmar que o pipeline calcula e compara hash ou valida assinatura antes do deployment/runtime.
3. Alterar um artefato de teste e confirmar que o carregamento é bloqueado.
4. Confirmar que hashes esperados estão versionados e protegidos.
5. Reprovar se a integridade for verificada apenas após o carregamento.

**Remediation**

Publicar hashes/assinaturas em repositório confiável, adicionar verificação antes do carregamento e bloquear o deployment em caso de divergência.

**Evidence**

Pipeline de verificação, registro de hashes/assinaturas e teste com artefato adulterado.

**Mappings**

CIS Controls v8 2 e 16; NIST SP 800-53 SI-7 e SA-12

---

### 4.4 Certifique-se de que runtimes de produção não baixem dinamicamente modelos, código, plugins ou dependências

**Control ID:** BAS-001.4.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Runtimes produtivos, containers, notebooks e agentes.

**Description**

Runtimes produtivos devem utilizar artefatos previamente validados e não podem baixar dinamicamente modelos, código, plugins, packages ou weights da Internet durante inicialização ou execução. Registries e repositórios permitidos devem ser internos ou explicitamente aprovados.

**Rationale**

Download dinâmico permite supply-chain attacks, mudança não rastreada e execução de artefato não testado.

**Impact**

Pode aumentar tamanho de imagens e exigir repositório interno.

**Audit**

1. Revisar entrypoints, scripts de inicialização e dependências.
2. Confirmar ausência de comandos de download/instalação em runtime.
3. Bloquear egress e iniciar o serviço; ele deve operar com artefatos locais aprovados.
4. Confirmar que imagens/deployments são imutáveis.
5. Reprovar se o serviço depender de download externo para iniciar.

**Remediation**

Incluir artefatos validados no build, utilizar registry interno, remover instalações em runtime e restringir egress.

**Evidence**

Imagem/manifesto, logs de inicialização sem download e teste com egress bloqueado.

**Mappings**

CIS Controls v8 2, 4 e 16; NIST SP 800-53 CM-7 e SA-12

---

### 4.5 Certifique-se de que runtimes de IA executem sem root, com menor privilégio e acesso restrito ao sistema operacional

**Control ID:** BAS-001.4.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Containers, VMs, endpoints e runtimes locais que executem modelos ou processamento de IA.

**Description**

O processo deve executar como usuário não-root/não-administrador, sem privileged mode, sem host network/PID, sem mount amplo do host e com filesystem read-only quando tecnicamente possível. Capabilities de sistema devem ser removidas e egress deve seguir allowlist.

**Rationale**

Comprometimento do runtime pode resultar em controle do host, roubo de credenciais e movimentação lateral.

**Impact**

Restrições podem exigir volumes específicos e ajustes para bibliotecas que gravam cache.

**Audit**

1. Inspecionar configuração do container/VM/processo.
2. Confirmar usuário não privilegiado e ausência de privileged mode.
3. Confirmar capabilities mínimas, mounts restritos e filesystem read-only ou diretórios graváveis explícitos.
4. Tentar gravar fora dos diretórios permitidos e acessar recurso do host; deve falhar.
5. Reprovar se o runtime executar como root/administrador sem justificativa técnica incontornável.

**Remediation**

Criar usuário dedicado, remover privilégios/capabilities, restringir mounts, habilitar read-only root filesystem e limitar rede.

**Evidence**

Manifesto do runtime, resultado de scanner de container e testes de acesso negado.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 AC-6 e CM-7

---

## 5. Segurança de aplicação e integrações

### 5.1 Certifique-se de que inputs de IA e conteúdos enviados sejam validados antes do processamento

**Control ID:** BAS-001.5.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Entradas de usuário, APIs, arquivos, URLs, imagens, áudio e documentos.

**Description**

A aplicação deve validar tipo, tamanho, encoding, formato, schema, extensão e magic bytes. Arquivos devem passar por malware scanning e extração segura antes de chegar ao modelo. URLs devem usar allowlist de protocolos e proteção contra SSRF. Dados inválidos devem ser rejeitados antes da chamada à IA.

**Rationale**

Conteúdo malformado ou malicioso pode explorar parsers, causar DoS, SSRF, injection ou processamento indevido.

**Impact**

Validações podem rejeitar formatos não previstos e aumentar latência de upload.

**Audit**

1. Revisar schemas e limites configurados.
2. Enviar payload acima do limite, tipo não permitido, arquivo com extensão divergente e URL para endereço interno.
3. Confirmar rejeição antes da chamada ao modelo.
4. Enviar arquivo de teste antimalware e confirmar bloqueio.
5. Reprovar se o modelo ou provider receber conteúdo não validado.

**Remediation**

Implementar validação server-side, magic-byte checking, limites, malware scanning, URL allowlist e proteção SSRF. Processar arquivos em ambiente isolado.

**Evidence**

Configuração de schemas/limites, resultados de testes negativos e logs de bloqueio.

**Mappings**

CIS Controls v8 10 e 16; NIST SP 800-53 SI-10; OWASP API Security

---

### 5.2 Certifique-se de que instruções de sistema e desenvolvedor, input do usuário e contexto recuperado estejam separados e protegidos

**Control ID:** BAS-001.5.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Aplicações que constroem prompts compostos ou usam contexto externo.

**Description**

Instruções de sistema e desenvolvedor devem ser armazenadas fora do input do usuário, possuir controle de acesso e serem inseridas por canal ou estrutura distinta. Conteúdo de usuário e contexto recuperado deve ser delimitado e tratado como não confiável. O usuário não pode sobrescrever diretamente instruções internas ou alterar policy por parâmetro.

**Rationale**

Mistura de instruções confiáveis e não confiáveis facilita prompt injection, exposição de system prompt e mudança de comportamento.

**Impact**

Pode exigir templates estruturados e refatoração do prompt builder.

**Audit**

1. Revisar o prompt builder e a API usada.
2. Confirmar separação estrutural entre system/developer/user/context.
3. Tentar inserir instrução para alterar ou revelar o system prompt.
4. Confirmar que o conteúdo não modifica a configuração interna e que campos administrativos não são aceitos do cliente.
5. Reprovar se o prompt final for simples concatenação de texto confiável e não confiável sem delimitação.

**Remediation**

Armazenar instruções internas em repositório protegido, utilizar papéis/canais nativos, delimitar conteúdo não confiável e rejeitar parâmetros administrativos do cliente.

**Evidence**

Código do prompt builder, configuração de acesso e resultados de testes de override/exfiltração.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SI-10; OWASP Prompt Injection

---

### 5.3 Certifique-se de que outputs estruturados de IA sejam validados contra schema estrito e allowlist

**Control ID:** BAS-001.5.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Outputs usados por aplicações, automações, APIs ou sistemas downstream.

**Description**

Outputs estruturados devem ser parseados e validados contra schema fechado com tipos, campos obrigatórios, limites, enums e additionalProperties=false ou equivalente. Campos desconhecidos, valores fora da faixa ou parsing parcial devem causar rejeição. Regex isolada não substitui validação de schema para objetos estruturados.

**Rationale**

Modelos podem produzir campos inesperados, instruções ou valores maliciosos que alteram a lógica downstream.

**Impact**

Validação estrita pode rejeitar respostas que antes eram aceitas de forma tolerante.

**Audit**

1. Obter o schema utilizado para cada output estruturado.
2. Confirmar tipos, limites, enums e bloqueio de propriedades adicionais.
3. Testar campo extra, tipo incorreto, valor fora da faixa e JSON parcial.
4. Confirmar que todos são rejeitados antes do uso downstream.
5. Reprovar se a aplicação consumir objeto parcialmente válido.

**Remediation**

Definir schema fechado, validar server-side, rejeitar respostas inválidas e solicitar nova geração somente com limite de tentativas.

**Evidence**

Schema, código de validação e resultados dos testes de campos e tipos inválidos.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SI-10; OWASP Improper Output Handling

---

### 5.4 Certifique-se de que o output de IA seja codificado ou sanitizado para o contexto de destino

**Control ID:** BAS-001.5.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Outputs exibidos em HTML, Markdown, e-mail, logs, documentos, templates, SQL, shell ou outros destinos interpretáveis.

**Description**

O output deve ser tratado como entrada não confiável e receber encoding/sanitização específica para o destino. HTML deve ser escapado ou sanitizado por allowlist; Markdown deve bloquear links/esquemas perigosos; valores para queries ou comandos devem usar APIs parametrizadas, nunca concatenação.

**Rationale**

Output malicioso pode causar XSS, injection, link malicioso, execução de template ou alteração de comandos.

**Impact**

A sanitização pode remover formatação ou conteúdo funcional.

**Audit**

1. Identificar todos os destinos de output.
2. Confirmar uso de encoding/sanitizer adequado a cada contexto.
3. Testar payloads de XSS, Markdown com javascript:, template injection e caracteres de query.
4. Confirmar que são neutralizados e não executados.
5. Reprovar se output for inserido por innerHTML, concatenação SQL/shell ou mecanismo equivalente.

**Remediation**

Aplicar encoding contextual, sanitizers por allowlist, APIs parametrizadas e componentes seguros de renderização. Remover concatenação direta.

**Evidence**

Código de renderização, configuração do sanitizer e resultados de testes de injection.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SI-10; OWASP Improper Output Handling

---

### 5.5 Certifique-se de que código, queries, comandos e configurações gerados não sejam executados diretamente

**Control ID:** BAS-001.5.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Soluções que gerem código, SQL, shell, IaC, políticas, scripts ou comandos.

**Description**

Conteúdo gerado não deve ser executado diretamente no host ou sistema-alvo. A execução, quando necessária, deve ocorrer após validação determinística e em sandbox com identidade mínima, filesystem/rede restritos, limites de recursos e aprovação humana para alterações materiais. Confirmação textual do modelo não constitui validação.

**Rationale**

Código gerado pode conter comandos destrutivos, exfiltração, backdoors ou erro operacional.

**Impact**

O controle reduz automação integral e pode exigir revisão ou sandbox adicional.

**Audit**

1. Mapear todos os caminhos de execução de conteúdo gerado.
2. Confirmar existência de validação determinística e ambiente isolado.
3. Testar comando destrutivo, acesso a segredo e conexão externa; todos devem ser bloqueados.
4. Confirmar que a identidade do sandbox não possui acesso amplo.
5. Reprovar se o output for enviado diretamente a eval, shell, database ou API de alteração.

**Remediation**

Remover execução direta, implementar parser/allowlist, sandbox efêmero, limites de recursos e aprovação humana antes de ações materiais.

**Evidence**

Diagrama de execução, configuração do sandbox, policies de allowlist e testes de comandos bloqueados.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 AC-6 e SI-10; OWASP Excessive Agency

---

### 5.6 Certifique-se de que limites de requisição, tokens, concorrência e custo sejam aplicados por identidade

**Control ID:** BAS-001.5.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** APIs, gateways e aplicações consumidoras.

**Description**

Limites devem ser aplicados por usuário, workload, cliente ou tenant, e não apenas globalmente. Devem existir limites de requisições, concorrência, tamanho de input, tokens de input/output e orçamento/custo. Ao exceder o limite, a requisição deve ser rejeitada ou adiada sem gerar consumo adicional.

**Rationale**

Sem limites, credenciais comprometidas ou erros de aplicação podem causar negação de serviço e custos elevados.

**Impact**

Limites podem afetar picos legítimos e exigir capacity planning.

**Audit**

1. Extrair configurações de rate, token, concurrency e budget.
2. Confirmar escopo por identidade/tenant.
3. Executar teste acima de cada limite e confirmar resposta de bloqueio sem chamada ao provider.
4. Confirmar geração de métrica/evento.
5. Reprovar se houver apenas limite global ou alerta sem enforcement.

**Remediation**

Configurar quotas no gateway/aplicação, impor tamanho máximo antes da inferência e estabelecer budgets com hard limit.

**Evidence**

Configurações de quotas, teste de excesso e logs/métricas de bloqueio.

**Mappings**

CIS Controls v8 4 e 13; NIST SP 800-53 SC-5 e SI-4

---

### 5.7 Certifique-se de que chamadas de IA utilizem timeout, retries limitados, backoff e circuit breaker

**Control ID:** BAS-001.5.7
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Chamadas síncronas ou assíncronas a modelos, providers, gateways e ferramentas.

**Description**

Toda chamada deve possuir timeout explícito. Retries devem ter quantidade máxima, exponential backoff e jitter. Erros de autorização, validação e policy não devem ser repetidos. Circuit breaker deve interromper chamadas quando a taxa de falha ultrapassar o limiar definido.

**Rationale**

Retries ilimitados e ausência de timeout causam cascata de falhas, custo excessivo e esgotamento de recursos.

**Impact**

Parâmetros restritivos podem aumentar falhas aparentes em períodos de instabilidade.

**Audit**

1. Revisar configurações de client e filas.
2. Confirmar timeout finito e retries limitados.
3. Confirmar que 4xx de autorização/validação não são repetidos.
4. Simular falhas e verificar abertura do circuit breaker e backoff.
5. Reprovar se houver loop de retry ilimitado ou timeout ausente.

**Remediation**

Definir timeout, número máximo de tentativas, backoff com jitter e circuit breaker. Classificar erros retryable e non-retryable.

**Evidence**

Configuração do client/gateway e logs do teste de falha mostrando tentativas limitadas e circuit aberto.

**Mappings**

CIS Controls v8 4; NIST SP 800-53 SC-5 e CP

---

## 6. Logging, auditoria e monitoramento

### 6.1 Certifique-se de que eventos de segurança de IA sejam registrados com campos obrigatórios

**Control ID:** BAS-001.6.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Todos os componentes produtivos.

**Description**

Devem ser registrados, no mínimo: timestamp UTC, event_type, outcome, environment, application_id, principal_id ou workload_id, session/transaction ID, model/provider/deployment/version, source, target, policy/rule ID quando aplicável, action e error_code. Devem existir eventos para autenticação, autorização, inferência, bloqueio de policy, administração, alteração de configuração e falha crítica.

**Rationale**

Eventos incompletos impedem atribuição, correlação, investigação e detecção.

**Impact**

A inclusão de campos aumenta volume e requer padronização entre componentes.

**Audit**

1. Selecionar uma amostra de cada tipo obrigatório de evento.
2. Confirmar presença e preenchimento dos campos mandatórios.
3. Confirmar que principal e versão do modelo são inequívocos.
4. Executar autenticação negada, inferência, bloqueio e alteração de configuração e verificar eventos correspondentes.
5. Reprovar se qualquer evento crítico não puder ser correlacionado ao principal e componente.

**Remediation**

Padronizar schema, adicionar middleware/telemetria e instrumentar eventos ausentes. Rejeitar eventos sem campos obrigatórios no pipeline de logs quando possível.

**Evidence**

Amostra de eventos para cada categoria e validação do schema obrigatório.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 AU; NIST AI RMF MEASURE

---

### 6.2 Certifique-se de que identificadores de trace e correlação sejam propagados de ponta a ponta com tempo sincronizado em UTC

**Control ID:** BAS-001.6.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Fluxos que atravessem aplicação, gateway, provider, tools ou serviços downstream.

**Description**

Cada transação deve possuir trace_id e correlation_id gerados ou aceitos de fonte confiável, propagados por todos os componentes e registrados nos eventos. Sistemas devem utilizar relógio sincronizado e timestamps em UTC com precisão suficiente para ordenar eventos. IDs fornecidos pelo cliente devem ser validados ou substituídos para evitar colisão/injection.

**Rationale**

Sem correlação e tempo consistente, eventos do mesmo fluxo não podem ser reunidos de forma confiável.

**Impact**

Requer propagação de headers/contexto e configuração de sincronização de tempo.

**Audit**

1. Executar uma transação ponta a ponta.
2. Consultar logs de todos os componentes e confirmar os mesmos trace_id/correlation_id.
3. Confirmar timestamps UTC e diferença de relógio dentro do limite corporativo.
4. Enviar ID malformado ou duplicado e confirmar normalização/substituição.
5. Reprovar se algum salto perder a correlação.

**Remediation**

Implementar contexto distribuído, gerar IDs no primeiro componente confiável, propagar por headers assinados ou padrão de tracing e habilitar sincronização de tempo.

**Evidence**

Logs correlacionados de uma transação, configuração de time sync e teste com ID malformado.

**Mappings**

CIS Controls v8 8; NIST SP 800-53 AU-8 e AU-12

---

### 6.3 Certifique-se de que logs de IA estejam protegidos contra alteração e com acesso restrito

**Control ID:** BAS-001.6.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Logs de segurança, auditoria, inferência e administração.

**Description**

Logs devem ser enviados para store central separado do workload, com criptografia, controle de acesso somente leitura para consumidores, retenção configurada e proteção contra exclusão/alteração pelo próprio serviço ou seus administradores comuns. O runtime não deve conseguir apagar os registros já exportados.

**Rationale**

Um invasor ou operador indevido pode apagar evidências e ocultar ações se controlar também o store de logs.

**Impact**

Pode exigir armazenamento imutável ou conta/projeto separado.

**Audit**

1. Confirmar que logs são exportados para store central.
2. Confirmar que a identidade do workload não possui delete/update no destino.
3. Tentar alterar ou excluir evento com identidade operacional; a ação deve ser negada.
4. Confirmar criptografia e retenção.
5. Reprovar se os únicos logs estiverem no filesystem local do componente.

**Remediation**

Configurar exportação central, separar funções, remover delete/update do workload, habilitar imutabilidade/WORM quando disponível e proteger chaves.

**Evidence**

Policies do store, teste de exclusão negada e configuração de retenção/imutabilidade.

**Mappings**

CIS Controls v8 8; NIST SP 800-53 AU-9 e AU-11

---

### 6.4 Certifique-se de que segredos e conteúdo sensível não sejam gravados em logs de IA

**Control ID:** BAS-001.6.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Logs, traces, errors, analytics e telemetry.

**Description**

Chaves, tokens, cookies, senhas, authorization headers e segredos devem ser removidos integralmente. Prompts, outputs, documentos e contexto sensível devem ser omitidos ou mascarados por padrão; quando conteúdo integral for tecnicamente indispensável, deve usar store segregado com acesso e retenção específicos. Stack traces não podem expor payloads ou headers sensíveis.

**Rationale**

Logs possuem ampla replicação e acesso; conteúdo sensível neles pode causar vazamento em larga escala.

**Impact**

Mascaramento pode reduzir detalhes de troubleshooting.

**Audit**

1. Gerar requisição contendo segredos e dados sensíveis de teste.
2. Consultar logs em aplicação, gateway, APM, SIEM e provider.
3. Confirmar ausência dos valores integrais em todos os destinos.
4. Confirmar que erros e stack traces também estão mascarados.
5. Reprovar em qualquer ocorrência integral do valor de teste.

**Remediation**

Aplicar redaction antes da emissão do log, bloquear headers sensíveis, desabilitar body logging por padrão e corrigir mensagens de erro.

**Evidence**

Resultado de busca pelos valores de teste, regras de redaction e configuração de logging.

**Mappings**

CIS Controls v8 3 e 8; NIST SP 800-53 AU-3 e SI-12

---

### 6.5 Certifique-se de que eventos críticos de IA sejam centralizados e gerem alertas acionáveis

**Control ID:** BAS-001.6.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Ambientes produtivos.

**Description**

Eventos críticos devem ser enviados ao monitoramento central e possuir alertas para, no mínimo: falhas repetidas de autenticação/autorização, uso de modelo/provider não permitido, bloqueios de DLP/policy, alteração de configuração ou versão, aumento anômalo de tokens/custo, falha de logging e indisponibilidade do enforcement. Alertas devem identificar componente, ambiente e principal afetado.

**Rationale**

Sem centralização e alerta, abuso e falhas podem permanecer sem detecção até gerar impacto.

**Impact**

Alertas podem exigir ajuste para reduzir falso positivo.

**Audit**

1. Confirmar ingestão dos eventos no SIEM ou ferramenta central.
2. Listar regras de alerta e verificar cobertura das categorias mínimas.
3. Executar um teste controlado para cada categoria.
4. Confirmar geração do alerta com campos suficientes e sem dados sensíveis.
5. Reprovar se houver apenas dashboard sem mecanismo de alerta.

**Remediation**

Integrar fontes ao SIEM, criar regras com limiares e correlação, configurar severidade e testar o disparo periodicamente.

**Evidence**

Configuração de integração, regras de alerta e evidência de testes controlados.

**Mappings**

CIS Controls v8 8 e 13; NIST SP 800-53 SI-4 e AU-6

---

## 7. Resiliência e recuperação

### 7.1 Certifique-se de que o processamento de IA falhe de forma fechada quando autorização, policy ou DLP estiver indisponível

**Control ID:** BAS-001.7.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Soluções que dependam de IAM, policy engine, gateway, DLP ou guardrail para permitir processamento.

**Description**

Quando o mecanismo de autorização, policy, DLP ou enforcement não responder, retornar erro ou não puder confirmar a decisão, a requisição deve ser bloqueada. Não é permitido encaminhar ao modelo/provider em modo permissivo, ignorar a policy ou utilizar cache de autorização vencido.

**Rationale**

Fail-open transforma indisponibilidade do controle em bypass de segurança.

**Impact**

O bloqueio pode reduzir disponibilidade durante falha do componente de segurança.

**Audit**

1. Simular indisponibilidade de cada mecanismo de enforcement.
2. Enviar requisição que normalmente seria permitida.
3. Confirmar que ela é bloqueada antes do provider ou ação downstream.
4. Confirmar geração de evento e ausência de fallback permissivo.
5. Reprovar se a aplicação continuar processando sem decisão válida.

**Remediation**

Alterar lógica para default deny, definir timeout curto do enforcement, invalidar caches vencidos e retornar erro seguro.

**Evidence**

Resultado dos testes de indisponibilidade, logs e configuração de fail-closed.

**Mappings**

CIS Controls v8 4 e 13; NIST SP 800-53 SC-7 e SI-4

---

### 7.2 Certifique-se de que health checks e fallback seguro impeçam o uso de componentes de IA degradados

**Control ID:** BAS-001.7.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Soluções com dependência operacional de modelo, gateway, provider ou runtime.

**Description**

Devem existir health checks que avaliem conectividade e capacidade mínima de resposta. Componentes unhealthy devem ser removidos do pool. O fallback deve utilizar somente modelo/provider/endpoint previamente permitido e não pode reduzir controles de autenticação, dados, logging ou policy. Na ausência de fallback seguro, a função deve degradar ou interromper de forma explícita.

**Rationale**

Encaminhar tráfego a componente degradado pode produzir erros, outputs incorretos e perda de rastreabilidade; fallback inseguro pode enviar dados a destino não aprovado.

**Impact**

Health checks e fallback podem aumentar complexidade e custo.

**Audit**

1. Identificar health checks e condições de unhealthy.
2. Simular falha do endpoint primário.
3. Confirmar remoção automática do pool.
4. Confirmar que fallback usa item da allowlist e mantém todos os controles.
5. Reprovar se o fallback selecionar modelo/provider arbitrário ou desabilitar policy/logging.

**Remediation**

Implementar health checks, remoção automática, fallback explícito e modo de degradação segura. Validar fallback contra a mesma allowlist e policies.

**Evidence**

Configuração de health check/fallback e logs do teste de falha controlada.

**Mappings**

CIS Controls v8 11 e 13; NIST SP 800-53 CP e SC-5

---

### 7.3 Certifique-se de que configurações, prompts, policies e artefatos de deployment sejam versionados, copiados e passíveis de rollback

**Control ID:** BAS-001.7.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Componentes produtivos e suas configurações.

**Description**

System prompts, policies, route tables, allowlists, schemas, model/deployment references e infraestrutura devem estar versionados em repositório protegido. Deve existir backup ou artefato imutável da última versão conhecida como boa e procedimento técnico testado de rollback. Alterações manuais não versionadas em produção não são permitidas.

**Rationale**

Sem versão e rollback, uma mudança insegura pode permanecer ativa e a configuração anterior pode não ser reconstruída.

**Impact**

Exige disciplina de configuração como código e armazenamento de artefatos.

**Audit**

1. Selecionar uma configuração produtiva e identificar sua versão no repositório.
2. Comparar o estado implantado com a versão registrada.
3. Confirmar existência do artefato anterior e backup.
4. Executar rollback em ambiente de teste e validar restauração funcional.
5. Reprovar se houver configuração produtiva alterada somente por console sem registro versionado.

**Remediation**

Migrar configuração para repositório e pipeline, criar backups imutáveis, impedir drift manual e testar rollback.

**Evidence**

Repositório, histórico de versões, artefatos de backup e resultado de teste de rollback.

**Mappings**

CIS Controls v8 4 e 11; NIST SP 800-53 CM-2, CM-3 e CP-9

---

### 7.4 Certifique-se de que um kill switch de emergência possa interromper o processamento de IA e revogar credenciais associadas

**Control ID:** BAS-001.7.4
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Soluções críticas, externas, com dados sensíveis ou capacidade de ação.

**Description**

Deve existir mecanismo técnico para interromper novas inferências e ações, desabilitar endpoints ou rotas e revogar credenciais/tokens associados sem depender de alteração de código. O kill switch deve possuir escopo definido por aplicação, modelo, provider ou ambiente e não pode apagar evidências existentes.

**Rationale**

Em incidente ou comportamento inseguro, a incapacidade de interromper rapidamente o processamento amplia o impacto.

**Impact**

Acionamento pode causar indisponibilidade imediata do serviço.

**Audit**

1. Identificar o mecanismo e seu escopo.
2. Acionar em ambiente controlado.
3. Confirmar bloqueio de novas inferências e ações.
4. Confirmar revogação das credenciais previstas e preservação dos logs.
5. Confirmar possibilidade de reativação somente com configuração autorizada.
6. Reprovar se a interrupção exigir novo deployment ou intervenção do fornecedor sem alternativa local.

**Remediation**

Implementar flag/policy de deny no gateway, capacidade de desabilitar endpoint/deployment, revogação automatizada de credenciais e documentação técnica de reativação.

**Evidence**

Configuração do kill switch, resultado do teste, logs preservados e evidência de revogação.

**Mappings**

CIS Controls v8 13 e 17; NIST SP 800-53 IR-4 e CP-2

---

## 8. Referências gerais

- CIS Benchmarks — estrutura de recomendações e Profile Applicability.
- CIS Controls v8.
- NIST AI Risk Management Framework.
- NIST SP 800-53 Rev. 5.
- ISO/IEC 27001 e ISO/IEC 42001.
- OWASP Generative AI Security Project e OWASP API Security.
