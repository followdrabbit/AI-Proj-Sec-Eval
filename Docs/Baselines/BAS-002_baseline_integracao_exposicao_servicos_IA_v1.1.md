# BAS-002 — Baseline de Controles Técnicos para Integração e Exposição de Serviços de Inteligência Artificial

| Campo | Valor |
|---|---|
| **Código** | BAS-002 |
| **Nome** | Baseline de Controles Técnicos para Integração e Exposição de Serviços de IA |
| **Tipo documental** | Baseline técnico |
| **Classificação da informação** | Uso Interno |
| **Status** | Minuta para revisão |
| **Versão** | 1.1 |
| **Data** | 13/07/2026 |
| **Owner institucional** | Segurança da Informação / Segurança de IA |
| **Custodiante técnico** | Arquitetura de Segurança da Informação / AppSec |
| **Quantidade de controles** | 48 |

## 1. Objetivo

Estabelecer recomendações técnicas mínimas, verificáveis e auditáveis para a integração, intermediação, publicação e exposição segura de serviços e capacidades de Inteligência Artificial. O documento segue a estrutura de recomendações dos CIS Benchmarks e contém somente controles técnicos. Fluxos de homologação, aprovação, gestão de risco, exceções, contratação, RACI, change management e resposta processual a incidentes estão fora do escopo.

## 2. Escopo

Aplica-se a aplicações web, mobile, desktop e backend, APIs internas e externas, chatbots, voicebots, automações, jobs, gateways corporativos de IA, AI Firewalls, model routers, proxies, brokers e demais camadas que consumam, intermedeiem, publiquem ou exponham serviços de IA. Este baseline não deve ser aplicado isoladamente: complementa o BAS-001 e deve ser combinado cumulativamente com os demais baselines especializados aplicáveis à arquitetura avaliada.

## 3. Modelo de classificação

### 3.1 Profile Applicability

- **Level 1:** configuração fundamental para aplicações, APIs e gateways no escopo deste baseline. Deve reduzir a superfície de ataque sem impedir a função principal.
- **Level 2:** defesa em profundidade para serviços críticos, externos, multi-tenant, com dados sensíveis, alta disponibilidade ou impacto material. Pressupõe conformidade com os controles Level 1 aplicáveis.

### 3.2 Criticidade

| Criticidade | Critério |
|---|---|
| **Crítica** | A ausência permite diretamente bypass de autenticação/autorização, exposição de dados, acesso entre tenants, execução ou roteamento não autorizado, ou impossibilidade de contenção. |
| **Alta** | A ausência enfraquece significativamente uma fronteira de segurança, facilita abuso ou reduz materialmente resiliência e capacidade de proteção. |
| **Média** | Controle de hardening ou defesa em profundidade cuja ausência normalmente requer outra falha para produzir impacto material. |
| **Baixa** | Otimização técnica com impacto limitado. Esta versão não contém recomendações de criticidade Baixa. |

## 4. Regras de interpretação

1. O BAS-001 é pré-requisito e continua aplicável a todos os componentes cobertos por este documento.
2. Cada recomendação deve ser avaliada de forma independente.
3. Um controle é **Conforme** somente quando todos os critérios descritos em **Audit** forem atendidos.
4. Implementação parcial deve ser registrada como **Não Conforme**; não existe conformidade parcial neste baseline.
5. Quando uma recomendação não se aplicar tecnicamente, a justificativa deve indicar a característica arquitetural inexistente.
6. Controles processuais ou aprovações administrativas não substituem os requisitos técnicos deste documento.

## Sumário

- [1. Arquitetura de integração e fronteiras](#1-arquitetura-de-integracao-e-fronteiras)
  - [1.1 Certifique-se de que chamadas produtivas de IA utilizem um gateway ou ponto de enforcement aprovado](#11-certifique-se-de-que-chamadas-produtivas-de-ia-utilizem-um-gateway-ou-ponto-de-enforcement-aprovado)
  - [1.2 Certifique-se de que clientes web, mobile e desktop não se conectem diretamente ao provider de IA](#12-certifique-se-de-que-clientes-web-mobile-e-desktop-nao-se-conectem-diretamente-ao-provider-de-ia)
  - [1.3 Certifique-se de que os planos de controle e de dados do gateway estejam segregados](#13-certifique-se-de-que-os-planos-de-controle-e-de-dados-do-gateway-estejam-segregados)
  - [1.4 Certifique-se de que configurações, credenciais e políticas sejam isoladas por aplicação, ambiente e tenant](#14-certifique-se-de-que-configuracoes-credenciais-e-politicas-sejam-isoladas-por-aplicacao-ambiente-e-tenant)
  - [1.5 Certifique-se de que rotas alternativas para providers e endpoints de IA estejam bloqueadas](#15-certifique-se-de-que-rotas-alternativas-para-providers-e-endpoints-de-ia-estejam-bloqueadas)
  - [1.6 Certifique-se de que interfaces administrativas do gateway não sejam expostas na mesma superfície pública das APIs de consumo](#16-certifique-se-de-que-interfaces-administrativas-do-gateway-nao-sejam-expostas-na-mesma-superficie-publica-das-apis-de-consumo)
- [2. Autenticação e identidade](#2-autenticacao-e-identidade)
  - [2.1 Certifique-se de que cada aplicação utilize identidade de workload exclusiva para acessar o gateway](#21-certifique-se-de-que-cada-aplicacao-utilize-identidade-de-workload-exclusiva-para-acessar-o-gateway)
  - [2.2 Certifique-se de que tokens de acesso sejam validados integralmente pelo gateway](#22-certifique-se-de-que-tokens-de-acesso-sejam-validados-integralmente-pelo-gateway)
  - [2.3 Certifique-se de que a identidade do usuário originador seja propagada em claims assinadas](#23-certifique-se-de-que-a-identidade-do-usuario-originador-seja-propagada-em-claims-assinadas)
  - [2.4 Certifique-se de que claims de identidade e tenant não possam ser sobrescritas pelo payload da requisição](#24-certifique-se-de-que-claims-de-identidade-e-tenant-nao-possam-ser-sobrescritas-pelo-payload-da-requisicao)
  - [2.5 Certifique-se de que integrações críticas utilizem autenticação vinculada ao canal ou à chave do cliente](#25-certifique-se-de-que-integracoes-criticas-utilizem-autenticacao-vinculada-ao-canal-ou-a-chave-do-cliente)
  - [2.6 Certifique-se de que acesso anônimo esteja desabilitado em rotas não públicas](#26-certifique-se-de-que-acesso-anonimo-esteja-desabilitado-em-rotas-nao-publicas)
- [3. Autorização e segregação](#3-autorizacao-e-segregacao)
  - [3.1 Certifique-se de que a autorização de negócio ocorra antes do envio de dados ou prompts à IA](#31-certifique-se-de-que-a-autorizacao-de-negocio-ocorra-antes-do-envio-de-dados-ou-prompts-a-ia)
  - [3.2 Certifique-se de que elegibilidade de modelos, rotas e capacidades seja calculada no servidor](#32-certifique-se-de-que-elegibilidade-de-modelos-rotas-e-capacidades-seja-calculada-no-servidor)
  - [3.3 Certifique-se de que policies e contexto de execução sejam isolados por tenant e aplicação](#33-certifique-se-de-que-policies-e-contexto-de-execucao-sejam-isolados-por-tenant-e-aplicacao)
  - [3.4 Certifique-se de que credenciais de serviço não ampliem as permissões do usuário originador](#34-certifique-se-de-que-credenciais-de-servico-nao-ampliem-as-permissoes-do-usuario-originador)
  - [3.5 Certifique-se de que permissões administrativas e de runtime sejam segregadas](#35-certifique-se-de-que-permissoes-administrativas-e-de-runtime-sejam-segregadas)
  - [3.6 Certifique-se de que escopos desconhecidos ou não mapeados sejam negados por padrão](#36-certifique-se-de-que-escopos-desconhecidos-ou-nao-mapeados-sejam-negados-por-padrao)
- [4. Roteamento, modelos e policies](#4-roteamento-modelos-e-policies)
  - [4.1 Certifique-se de que o gateway utilize allowlist de providers, modelos, versões, regiões e features por aplicação](#41-certifique-se-de-que-o-gateway-utilize-allowlist-de-providers-modelos-versoes-regioes-e-features-por-aplicacao)
  - [4.2 Certifique-se de que novos modelos, versões e features permaneçam bloqueados por padrão](#42-certifique-se-de-que-novos-modelos-versoes-e-features-permanecam-bloqueados-por-padrao)
  - [4.3 Certifique-se de que regras de roteamento preservem restrições de dados e residência](#43-certifique-se-de-que-regras-de-roteamento-preservem-restricoes-de-dados-e-residencia)
  - [4.4 Certifique-se de que failover utilize somente destinos equivalentes e previamente permitidos](#44-certifique-se-de-que-failover-utilize-somente-destinos-equivalentes-e-previamente-permitidos)
  - [4.5 Certifique-se de que parâmetros de inferência protegidos sejam impostos pelo servidor](#45-certifique-se-de-que-parametros-de-inferencia-protegidos-sejam-impostos-pelo-servidor)
  - [4.6 Certifique-se de que rulesets de gateway sejam versionados, validados e aplicados de forma atômica](#46-certifique-se-de-que-rulesets-de-gateway-sejam-versionados-validados-e-aplicados-de-forma-atomica)
- [5. Entrada, prompt e payload](#5-entrada-prompt-e-payload)
  - [5.1 Certifique-se de que content type, tamanho e schema do payload sejam validados antes do processamento](#51-certifique-se-de-que-content-type-tamanho-e-schema-do-payload-sejam-validados-antes-do-processamento)
  - [5.2 Certifique-se de que entradas sejam canonicalizadas antes da aplicação de regras de segurança](#52-certifique-se-de-que-entradas-sejam-canonicalizadas-antes-da-aplicacao-de-regras-de-seguranca)
  - [5.3 Certifique-se de que prompts sistêmicos e instruções de desenvolvedor sejam mantidos no servidor e protegidos por integridade](#53-certifique-se-de-que-prompts-sistemicos-e-instrucoes-de-desenvolvedor-sejam-mantidos-no-servidor-e-protegidos-por-integridade)
  - [5.4 Certifique-se de que conteúdo não confiável seja isolado de instruções privilegiadas](#54-certifique-se-de-que-conteudo-nao-confiavel-seja-isolado-de-instrucoes-privilegiadas)
  - [5.5 Certifique-se de que arquivos e URLs sejam obtidos somente de origens permitidas e inspecionados antes do uso](#55-certifique-se-de-que-arquivos-e-urls-sejam-obtidos-somente-de-origens-permitidas-e-inspecionados-antes-do-uso)
  - [5.6 Certifique-se de que tentativas de prompt injection e jailbreak sejam submetidas a policy explícita](#56-certifique-se-de-que-tentativas-de-prompt-injection-e-jailbreak-sejam-submetidas-a-policy-explicita)
- [6. Saída e uso downstream](#6-saida-e-uso-downstream)
  - [6.1 Certifique-se de que cada endpoint imponha um contrato de resposta explícito](#61-certifique-se-de-que-cada-endpoint-imponha-um-contrato-de-resposta-explicito)
  - [6.2 Certifique-se de que outputs sejam inspecionados para segredos e dados sensíveis antes da entrega](#62-certifique-se-de-que-outputs-sejam-inspecionados-para-segredos-e-dados-sensiveis-antes-da-entrega)
  - [6.3 Certifique-se de que conteúdo gerado seja codificado de acordo com o destino](#63-certifique-se-de-que-conteudo-gerado-seja-codificado-de-acordo-com-o-destino)
  - [6.4 Certifique-se de que conteúdo gerado não controle metadados ou decisões de segurança da API](#64-certifique-se-de-que-conteudo-gerado-nao-controle-metadados-ou-decisoes-de-seguranca-da-api)
  - [6.5 Certifique-se de que comunicações externas sensíveis utilizem templates e campos permitidos](#65-certifique-se-de-que-comunicacoes-externas-sensiveis-utilizem-templates-e-campos-permitidos)
  - [6.6 Certifique-se de que mensagens de erro não revelem detalhes internos de IA](#66-certifique-se-de-que-mensagens-de-erro-nao-revelem-detalhes-internos-de-ia)
- [7. Exposição, sessão e abuso](#7-exposicao-sessao-e-abuso)
  - [7.1 Certifique-se de que rate limits sejam aplicados por usuário, sessão, aplicação, tenant e origem](#71-certifique-se-de-que-rate-limits-sejam-aplicados-por-usuario-sessao-aplicacao-tenant-e-origem)
  - [7.2 Certifique-se de que streaming, uploads e ações possuam limites independentes de inferência simples](#72-certifique-se-de-que-streaming-uploads-e-acoes-possuam-limites-independentes-de-inferencia-simples)
  - [7.3 Certifique-se de que operações com efeito colateral sejam protegidas contra replay e duplicidade](#73-certifique-se-de-que-operacoes-com-efeito-colateral-sejam-protegidas-contra-replay-e-duplicidade)
  - [7.4 Certifique-se de que serviços externos estejam protegidos por WAF, API Gateway, anti-bot e mitigação DDoS](#74-certifique-se-de-que-servicos-externos-estejam-protegidos-por-waf-api-gateway-anti-bot-e-mitigacao-ddos)
  - [7.5 Certifique-se de que sessões web utilizem cookies e políticas de origem seguras](#75-certifique-se-de-que-sessoes-web-utilizem-cookies-e-politicas-de-origem-seguras)
  - [7.6 Certifique-se de que caches de resposta sejam isolados e não armazenem conteúdo sensível indevidamente](#76-certifique-se-de-que-caches-de-resposta-sejam-isolados-e-nao-armazenem-conteudo-sensivel-indevidamente)
- [8. Resiliência e comportamento de falha](#8-resiliencia-e-comportamento-de-falha)
  - [8.1 Certifique-se de que chamadas possuam timeout, cancelamento, retry limitado e backoff](#81-certifique-se-de-que-chamadas-possuam-timeout-cancelamento-retry-limitado-e-backoff)
  - [8.2 Certifique-se de que falha de autenticação, autorização, policy ou DLP resulte em bloqueio](#82-certifique-se-de-que-falha-de-autenticacao-autorizacao-policy-ou-dlp-resulte-em-bloqueio)
  - [8.3 Certifique-se de que circuit breakers sejam aplicados por provider, modelo e rota](#83-certifique-se-de-que-circuit-breakers-sejam-aplicados-por-provider-modelo-e-rota)
  - [8.4 Certifique-se de que fallback preserve contrato, controles e restrições de segurança](#84-certifique-se-de-que-fallback-preserve-contrato-controles-e-restricoes-de-seguranca)
  - [8.5 Certifique-se de que health checks validem dependências de segurança e não apenas disponibilidade do processo](#85-certifique-se-de-que-health-checks-validem-dependencias-de-seguranca-e-nao-apenas-disponibilidade-do-processo)
  - [8.6 Certifique-se de que rotas, modelos e providers possam ser desabilitados imediatamente sem nova implantação da aplicação](#86-certifique-se-de-que-rotas-modelos-e-providers-possam-ser-desabilitados-imediatamente-sem-nova-implantacao-da-aplicacao)

## 1. Arquitetura de integração e fronteiras

Controles para garantir que aplicações e gateways utilizem caminhos governados, superfícies administrativas isoladas e fronteiras técnicas explícitas.

### 1.1 Certifique-se de que chamadas produtivas de IA utilizem um gateway ou ponto de enforcement aprovado

**Control ID:** BAS-002.1.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Aplicações, APIs, automações e serviços que consumam modelos ou capacidades de IA em produção.

**Description**

Toda chamada produtiva que processe dados corporativos deve atravessar um gateway de IA, API Gateway, proxy de segurança ou ponto de enforcement equivalente capaz de aplicar autenticação, autorização, restrições de rota, limites e telemetria. A aplicação não pode selecionar livremente um endpoint de provider fora dessa camada.

**Rationale**

Sem um ponto central de enforcement, cada aplicação implementa controles de forma diferente, permitindo rotas não governadas, bypass de políticas, uso de modelos não aprovados e perda de rastreabilidade.

**Impact**

A implementação pode adicionar latência, dependência de plataforma e necessidade de alta disponibilidade para a camada de enforcement.

**Audit**

1. Mapear todas as chamadas produtivas de IA realizadas pela aplicação.
2. Confirmar que 100% das chamadas passam por um ponto de enforcement aprovado antes de alcançar o provider ou runtime.
3. Executar tentativa de chamada direta ao provider a partir da identidade da aplicação; a conexão deve ser negada por rede, IAM ou política.
4. Reprovar se existir rota alternativa capaz de processar dados corporativos sem aplicar os mesmos controles do gateway.

**Remediation**

Redirecionar integrações para o gateway corporativo ou implementar ponto de enforcement equivalente. Bloquear rotas diretas por rede, IAM e configuração da aplicação.

**Evidence**

Diagrama de fluxo, configuração de rotas, políticas de rede/IAM e resultado de teste negativo de acesso direto.

**Mappings**

CIS Controls v8 4, 12 e 13; NIST SP 800-53 AC-4, SC-7; OWASP API Security 2023 API8

---

### 1.2 Certifique-se de que clientes web, mobile e desktop não se conectem diretamente ao provider de IA

**Control ID:** BAS-002.1.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Aplicações com front-end executado em navegador, dispositivo móvel, desktop ou ambiente controlado pelo usuário.

**Description**

O cliente deve chamar um backend corporativo autenticado. Chaves de provider, tokens de serviço, prompts sistêmicos, regras de roteamento e políticas internas não podem ser embarcados no cliente nem enviados a ele para que realize a chamada ao modelo.

**Rationale**

Código e configuração presentes no cliente podem ser inspecionados, alterados ou reutilizados fora da aplicação, expondo credenciais e permitindo bypass de controles, abuso de quota e extração de instruções internas.

**Impact**

A aplicação precisará manter um backend ou gateway intermediário e poderá consumir recursos adicionais de infraestrutura.

**Audit**

1. Inspecionar código, bundles, artefatos mobile/desktop e tráfego de rede do cliente.
2. Confirmar que o cliente chama apenas endpoints corporativos e não contém hostname, chave, token ou SDK configurado para acesso direto ao provider.
3. Tentar alterar o endpoint ou extrair credenciais do cliente; nenhuma credencial funcional de provider deve estar disponível.
4. Reprovar se o cliente conseguir invocar diretamente o modelo ou alterar prompts sistêmicos e parâmetros protegidos.

**Remediation**

Mover chamadas para backend corporativo. Remover credenciais e prompts protegidos do cliente, revogar segredos expostos e restringir o provider para aceitar somente identidades do backend/gateway.

**Evidence**

Arquitetura cliente-backend, análise de bundle, captura de tráfego e varredura sem credenciais de provider.

**Mappings**

CIS Controls v8 3, 6 e 16; NIST SP 800-53 IA-5, SC-8; OWASP API Security 2023 API2

---

### 1.3 Certifique-se de que os planos de controle e de dados do gateway estejam segregados

**Control ID:** BAS-002.1.3
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Gateways e plataformas que possuam interfaces administrativas, APIs de configuração ou consoles de gestão.

**Description**

Interfaces usadas para configurar providers, modelos, policies, secrets, rotas e usuários devem ser separadas das interfaces de inferência. O plano de controle deve utilizar rede, hostname, autenticação, autorização e logging distintos e não deve ser acessível por consumidores comuns.

**Rationale**

A exposição do plano de controle no mesmo caminho do tráfego de dados aumenta a chance de exploração, elevação de privilégio e alteração de políticas por identidades de runtime.

**Impact**

A segregação pode exigir endpoints, redes, roles e pipelines de implantação adicionais.

**Audit**

1. Identificar endpoints e interfaces de controle e de inferência.
2. Confirmar que consumidores de runtime não possuem rota nem permissão para APIs administrativas.
3. Executar tentativa de acesso administrativo com identidade de aplicação; a resposta deve ser negada antes da execução da operação.
4. Confirmar que mudanças de configuração utilizam credenciais e trilhas distintas das chamadas de inferência.
5. Reprovar se uma mesma credencial ou endpoint permitir inferência e alteração de configuração privilegiada.

**Remediation**

Separar endpoints, redes e roles do plano de controle e do plano de dados. Aplicar políticas de negação explícita para identidades de runtime nas APIs administrativas.

**Evidence**

Diagrama de planos, regras de rede, matriz de permissões e evidência de teste negativo.

**Mappings**

CIS Controls v8 4, 5 e 6; NIST SP 800-53 AC-5, SC-7

---

### 1.4 Certifique-se de que configurações, credenciais e políticas sejam isoladas por aplicação, ambiente e tenant

**Control ID:** BAS-002.1.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Gateways compartilhados por múltiplas aplicações, ambientes, clientes ou tenants.

**Description**

Cada aplicação e ambiente deve possuir identidade, quota, policy, secret, namespace e registro de telemetria próprios. Quando houver múltiplos tenants, decisões de roteamento, contexto e cache devem incluir um identificador de tenant derivado de identidade confiável e não do payload controlado pelo usuário.

**Rationale**

Compartilhamento de credenciais ou policies permite que uma aplicação consuma recursos, dados ou rotas de outra, causando vazamento entre tenants e perda de accountability.

**Impact**

A segregação aumenta a quantidade de objetos de configuração e exige automação para evitar divergência.

**Audit**

1. Selecionar amostra de aplicações, ambientes e tenants configurados no gateway.
2. Confirmar que cada combinação possui identidade e policy próprias e não compartilha secrets de runtime.
3. Executar requisição de um tenant tentando informar o identificador de outro no payload; o valor deve ser ignorado ou rejeitado.
4. Confirmar que quotas, cache e logs são atribuídos ao tenant autenticado.
5. Reprovar se uma credencial puder acessar rotas ou dados de outra aplicação/tenant sem autorização explícita.

**Remediation**

Criar namespaces e identidades separados, vincular tenant e aplicação a claims confiáveis e particionar policies, quotas, caches e logs.

**Evidence**

Exportação de configuração por aplicação/tenant, claims utilizados e resultados de testes de isolamento.

**Mappings**

CIS Controls v8 3, 5 e 6; NIST SP 800-53 AC-3, AC-4; OWASP API Security 2023 API1

---

### 1.5 Certifique-se de que rotas alternativas para providers e endpoints de IA estejam bloqueadas

**Control ID:** BAS-002.1.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Aplicações e workloads com conectividade de rede para providers, runtimes ou APIs de IA.

**Description**

A rede e o IAM devem permitir acesso somente aos endpoints corporativos definidos. Endpoints públicos alternativos, proxies paralelos, credenciais pessoais, URLs regionais não aprovadas e rotas diretas para o provider devem ser negados.

**Rationale**

Mesmo quando a aplicação usa o gateway por padrão, uma rota alternativa mantém a possibilidade de bypass de inspeção, quotas, DLP e allowlists.

**Impact**

Pode ser necessário manter allowlists de DNS, FQDN, IP, service endpoints e identidades de provider.

**Audit**

1. Enumerar regras de egress, DNS, proxy, service endpoints e permissões de API da identidade da aplicação.
2. Confirmar que somente o gateway ou endpoints explicitamente aprovados são alcançáveis.
3. Executar testes contra endpoint público e endpoint regional alternativo do provider; ambos devem ser bloqueados.
4. Reprovar se o bloqueio depender apenas de configuração no código da aplicação.

**Remediation**

Aplicar egress filtering, DNS controlado, proxy obrigatório, private endpoints e políticas IAM que neguem APIs/recursos fora do caminho aprovado.

**Evidence**

Regras de rede e IAM, lista de destinos permitidos e resultados de testes de conectividade negada.

**Mappings**

CIS Controls v8 4, 12 e 13; NIST SP 800-53 AC-4, SC-7

---

### 1.6 Certifique-se de que interfaces administrativas do gateway não sejam expostas na mesma superfície pública das APIs de consumo

**Control ID:** BAS-002.1.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Gateways, proxies e plataformas de IA com APIs ou consoles administrativos.

**Description**

Consoles e APIs administrativas devem utilizar hostname, rota e controle de rede distintos das APIs de consumo. O acesso deve ser limitado a redes corporativas ou mecanismos de acesso privilegiado e não pode ser publicado por WAF, CDN ou API Gateway voltado a clientes.

**Rationale**

A exposição administrativa amplia a superfície de ataque e permite tentativa direta de alteração de rotas, policies, secrets e modelos.

**Impact**

Pode exigir DNS privado, private endpoint ou canal administrativo dedicado.

**Audit**

1. Enumerar todos os hostnames e rotas administrativas.
2. Confirmar que não resolvem ou não aceitam conexão a partir da Internet pública.
3. Confirmar que regras de publicação externa não incluem paths administrativos.
4. Testar acesso externo não autorizado; a conexão deve ser bloqueada antes da autenticação.
5. Reprovar se apenas ocultação de URL separar a administração do consumo.

**Remediation**

Mover interfaces administrativas para rede privada, remover publicação externa e restringir acesso por VPN, ZTNA ou bastion/PAM.

**Evidence**

Configuração DNS/rede, inventário de rotas e resultado de teste externo bloqueado.

**Mappings**

CIS Controls v8 4, 6 e 12; NIST SP 800-53 AC-17, SC-7

---

## 2. Autenticação e identidade

Controles para autenticação de workloads, validação de tokens, propagação da identidade originadora e proteção contra impersonação.

### 2.1 Certifique-se de que cada aplicação utilize identidade de workload exclusiva para acessar o gateway

**Control ID:** BAS-002.2.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Aplicações, APIs, jobs, funções e automações que chamem o gateway ou serviço de IA.

**Description**

Cada aplicação e ambiente deve autenticar-se com identidade de workload exclusiva. Chaves compartilhadas entre aplicações, ambientes ou equipes não atendem ao controle. A identidade deve ser emitida por IAM corporativo ou mecanismo equivalente e possuir audiência e escopo limitados ao gateway.

**Rationale**

Identidades compartilhadas impedem atribuição de consumo, dificultam revogação seletiva e permitem que o comprometimento de uma aplicação afete outras.

**Impact**

A implementação pode exigir integração com workload identity, managed identity, service account, SPIFFE ou OAuth client credentials.

**Audit**

1. Listar todas as identidades autorizadas no gateway.
2. Confirmar correspondência um-para-um entre identidade, aplicação e ambiente.
3. Verificar que nenhuma credencial é utilizada por mais de uma aplicação ou por produção e não produção.
4. Reprovar se houver API key genérica compartilhada ou credencial sem owner técnico identificável.

**Remediation**

Criar identidade de workload por aplicação e ambiente, migrar permissões e revogar chaves compartilhadas.

**Evidence**

Inventário de identidades, configuração de autenticação e correlação identidade-aplicação-ambiente.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 IA-4, IA-5, AC-2

---

### 2.2 Certifique-se de que tokens de acesso sejam validados integralmente pelo gateway

**Control ID:** BAS-002.2.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Gateways e APIs que aceitem JWT, OAuth 2.0, OIDC ou tokens equivalentes.

**Description**

O gateway deve validar assinatura, algoritmo permitido, issuer, audience, expiração, not-before e escopos. Tokens sem assinatura, com algoritmo none, assinatura desconhecida, audience genérica ou fora da janela temporal devem ser rejeitados. Chaves de validação devem ser obtidas de fonte confiável e armazenadas em cache com expiração controlada.

**Rationale**

Validação incompleta permite uso de tokens forjados, emitidos para outra aplicação, expirados ou provenientes de emissor não confiável.

**Impact**

A validação pode exigir configuração específica por emissor e rotação de chaves.

**Audit**

1. Revisar a configuração de validação de token do gateway.
2. Testar tokens com assinatura inválida, issuer incorreto, audience incorreta, expirado e nbf futuro.
3. Todos os tokens alterados devem ser rejeitados com código de autenticação e sem encaminhamento ao backend/provider.
4. Confirmar que somente algoritmos criptográficos explicitamente permitidos são aceitos.
5. Reprovar se qualquer claim crítica for apenas decodificada sem validação criptográfica.

**Remediation**

Configurar validadores JWT/OAuth completos, allowlist de issuers, audiences e algoritmos, e rejeitar tokens que não atendam a todos os critérios.

**Evidence**

Configuração do autenticador e resultados de testes negativos para cada claim/assinatura.

**Mappings**

CIS Controls v8 6; NIST SP 800-53 IA-2, IA-5; OWASP API Security 2023 API2

---

### 2.3 Certifique-se de que a identidade do usuário originador seja propagada em claims assinadas

**Control ID:** BAS-002.2.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Funcionalidades de IA iniciadas por usuário e que acessem dados, contexto ou funções associadas à identidade humana.

**Description**

A aplicação deve propagar ao gateway uma identidade do usuário derivada da sessão autenticada e protegida por token assinado ou canal autenticado. O gateway deve registrar e usar essa identidade nas decisões aplicáveis. Identificadores enviados livremente em headers ou payloads não são confiáveis.

**Rationale**

Sem propagação confiável, ações e consultas são atribuídas apenas à conta técnica, permitindo bypass de autorização e reduzindo a capacidade de investigação.

**Impact**

A integração pode exigir token exchange, on-behalf-of, claims adicionais ou serviço de autorização intermediário.

**Audit**

1. Rastrear uma chamada desde a sessão do usuário até o gateway e backend.
2. Confirmar que o identificador do usuário deriva do token/sessão autenticada e está coberto por assinatura ou mTLS.
3. Alterar manualmente headers e payloads de identidade; a identidade efetiva não deve mudar.
4. Confirmar que os logs registram usuário originador e workload executor.
5. Reprovar se o gateway confiar em X-User, user_id ou campo equivalente sem autenticação criptográfica.

**Remediation**

Implementar token exchange/on-behalf-of ou claim assinada emitida pelo backend autenticador. Remover headers de identidade controláveis pelo cliente.

**Evidence**

Fluxo de identidade, configuração de claims e teste de tentativa de spoofing.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-3, IA-2; OWASP API Security 2023 API1

---

### 2.4 Certifique-se de que claims de identidade e tenant não possam ser sobrescritas pelo payload da requisição

**Control ID:** BAS-002.2.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** APIs e gateways que recebam user_id, tenant_id, account_id, role, scope ou identificador equivalente.

**Description**

Claims de segurança devem ser derivadas do contexto autenticado. Quando o payload contiver campos de mesma finalidade, o gateway deve ignorá-los ou validar igualdade exata com a identidade autenticada. Divergência deve resultar em rejeição.

**Rationale**

Aceitar identificadores controlados pelo cliente permite impersonação, acesso horizontal e recuperação de dados de outro tenant.

**Impact**

Pode exigir remoção de campos legados do contrato de API e adaptação de clientes.

**Audit**

1. Identificar todos os campos de identidade/tenant aceitos pela API.
2. Enviar requisições com valores divergentes dos claims autenticados.
3. Confirmar que o gateway rejeita a requisição ou substitui o campo pelo valor autenticado antes do processamento.
4. Verificar que a divergência é registrada como evento de segurança.
5. Reprovar se o valor do payload determinar a identidade efetiva.

**Remediation**

Derivar identidade e tenant exclusivamente de claims validadas, remover campos desnecessários e aplicar validação de consistência no gateway.

**Evidence**

Contrato de API, policy de transformação e resultados de teste de spoofing.

**Mappings**

CIS Controls v8 6; NIST SP 800-53 AC-3; OWASP API Security 2023 API1

---

### 2.5 Certifique-se de que integrações críticas utilizem autenticação vinculada ao canal ou à chave do cliente

**Control ID:** BAS-002.2.5
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Integrações servidor-a-servidor críticas, externas ou que processem dados sensíveis.

**Description**

Além do bearer token, a integração deve utilizar mTLS, DPoP, private_key_jwt, token binding ou mecanismo equivalente que comprove posse de chave pelo cliente. Certificados e chaves devem ser exclusivos por aplicação e ambiente.

**Rationale**

Bearer tokens roubados podem ser reutilizados de qualquer origem. Vincular o token ou sessão a uma chave reduz replay e uso fora do cliente autorizado.

**Impact**

A implementação aumenta a complexidade de emissão, rotação e observabilidade de certificados/chaves.

**Audit**

1. Verificar o método de autenticação das integrações classificadas como críticas.
2. Confirmar que o gateway exige prova de posse de chave ou certificado do cliente.
3. Tentar reutilizar token válido sem a chave/certificado correspondente; a chamada deve ser rejeitada.
4. Confirmar que certificados/chaves são exclusivos por aplicação e ambiente.
5. Reprovar se apenas bearer token reutilizável proteger a integração crítica.

**Remediation**

Habilitar mTLS ou mecanismo de proof-of-possession, emitir credenciais exclusivas e configurar validação no gateway.

**Evidence**

Configuração mTLS/DPoP/private_key_jwt, inventário de certificados e resultado de teste de replay.

**Mappings**

CIS Controls v8 6 e 12; NIST SP 800-53 IA-3, SC-8; RFC 8705/RFC 9449

---

### 2.6 Certifique-se de que acesso anônimo esteja desabilitado em rotas não públicas

**Control ID:** BAS-002.2.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** APIs, chatbots, endpoints de inferência e rotas de gateway que não sejam explicitamente públicas.

**Description**

Toda rota não pública deve exigir autenticação antes de aceitar payload, iniciar streaming ou consumir quota do provider. Rotas públicas devem ser separadas por hostname/path e não podem compartilhar credenciais, cache ou permissões com rotas autenticadas.

**Rationale**

Acesso anônimo permite abuso de custo, enumeração, coleta de respostas, prompt injection e exploração de dados ou funções internas.

**Impact**

Endpoints deliberadamente públicos precisarão de arquitetura e limites específicos.

**Audit**

1. Enumerar rotas publicadas e sua configuração de autenticação.
2. Realizar chamadas sem credencial e com credencial inválida.
3. Confirmar que rotas não públicas retornam 401/403 antes de processar a requisição ou chamar o modelo.
4. Confirmar que rotas públicas estão isoladas e possuem escopo funcional mínimo.
5. Reprovar se uma rota interna aceitar chamada anônima ou consumir tokens antes da autenticação.

**Remediation**

Exigir autenticação no gateway para rotas não públicas, separar rotas públicas e remover permissões herdadas ou defaults de anonymous access.

**Evidence**

Inventário de rotas, configuração de autenticação e resultados de testes sem credencial.

**Mappings**

CIS Controls v8 6; NIST SP 800-53 AC-3, IA-2; OWASP API Security 2023 API2

---

## 3. Autorização e segregação

Controles para autorização determinística, isolamento entre tenants/aplicações e prevenção de ampliação de privilégios por contas técnicas.

### 3.1 Certifique-se de que a autorização de negócio ocorra antes do envio de dados ou prompts à IA

**Control ID:** BAS-002.3.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Funcionalidades que utilizem dados, documentos, transações ou recursos protegidos.

**Description**

A aplicação deve validar a permissão do usuário para acessar o recurso e executar a finalidade antes de recuperar dados, montar contexto ou chamar o modelo. O modelo ou gateway não pode ser usado como mecanismo para decidir se o usuário possui acesso.

**Rationale**

Enviar dados antes da autorização expõe informações ao modelo/provider e pode permitir inferência sobre recursos não autorizados, mesmo que o resultado final seja posteriormente bloqueado.

**Impact**

Pode exigir mover consultas e composição de contexto para depois do policy enforcement.

**Audit**

1. Selecionar fluxos que utilizem dados protegidos.
2. Confirmar no código/arquitetura que a autorização é executada antes da consulta e da chamada de IA.
3. Executar tentativa com usuário sem permissão e verificar que nenhum dado é recuperado e nenhuma chamada ao modelo é realizada.
4. Confirmar por logs/trace que o bloqueio ocorre antes do gateway/provider.
5. Reprovar se a aplicação enviar dados e apenas filtrar o output.

**Remediation**

Inserir policy enforcement antes da recuperação de dados e da montagem do prompt. Encerrar o fluxo sem chamar IA quando a autorização falhar.

**Evidence**

Diagrama/trace de sequência, código ou policy e teste negativo sem chamada ao modelo.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-3, AC-6; OWASP API Security 2023 API1

---

### 3.2 Certifique-se de que elegibilidade de modelos, rotas e capacidades seja calculada no servidor

**Control ID:** BAS-002.3.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** APIs que permitam selecionar modelo, provider, região, feature, modo de execução ou capability.

**Description**

O cliente pode solicitar uma opção, mas a decisão final deve ser calculada por policy no backend/gateway com base em identidade, aplicação, tenant, classificação dos dados e ambiente. Parâmetros enviados pelo cliente não podem habilitar rota ou capability não autorizada.

**Rationale**

Confiar em seleção do cliente permite acesso a modelos mais permissivos, regiões proibidas, features não homologadas ou modos com retenção incompatível.

**Impact**

Pode limitar flexibilidade de clientes e exigir catálogo de opções por perfil.

**Audit**

1. Identificar parâmetros de seleção de modelo/provider/feature recebidos pela API.
2. Executar requisições solicitando opções fora do escopo da identidade.
3. Confirmar que o gateway rejeita ou substitui a opção por rota autorizada.
4. Confirmar que a policy usa claims e classificação confiáveis.
5. Reprovar se o cliente puder habilitar capability apenas alterando o payload.

**Remediation**

Implementar allowlist e policy server-side por identidade/aplicação/tenant. Validar e sobrescrever parâmetros de seleção antes do roteamento.

**Evidence**

Policy de elegibilidade, catálogo por perfil e resultados de testes de seleção indevida.

**Mappings**

CIS Controls v8 6; NIST SP 800-53 AC-3, AC-6; OWASP API Security 2023 API1/API5

---

### 3.3 Certifique-se de que policies e contexto de execução sejam isolados por tenant e aplicação

**Control ID:** BAS-002.3.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Gateways multi-tenant ou compartilhados por múltiplas aplicações.

**Description**

A policy aplicada, o system prompt, as tools, os limites, os destinos e o contexto devem ser selecionados usando identidade autenticada e namespace isolado. Objetos de um tenant/aplicação não podem ser enumerados, referenciados ou reutilizados por outro.

**Rationale**

Falhas de isolamento podem aplicar prompt, tool ou rota de outro tenant e causar exposição de dados, privilégios e comportamento inesperado.

**Impact**

A configuração isolada aumenta a quantidade de policies e exige testes de regressão por tenant.

**Audit**

1. Revisar o mecanismo de seleção de policy e contexto.
2. Tentar referenciar IDs, nomes ou versões pertencentes a outro tenant/aplicação.
3. Confirmar que a requisição é negada e que objetos de outro namespace não são enumeráveis.
4. Confirmar que caches e pools não misturam contexto entre tenants.
5. Reprovar se o isolamento depender apenas de prefixo controlável pelo cliente.

**Remediation**

Criar namespaces e controles de acesso por tenant/aplicação, derivar o namespace de claims confiáveis e particionar cache e configuração.

**Evidence**

Configuração de namespaces, matriz de acesso e testes de referência cruzada.

**Mappings**

CIS Controls v8 3 e 6; NIST SP 800-53 AC-3, SC-4; OWASP API Security 2023 API1

---

### 3.4 Certifique-se de que credenciais de serviço não ampliem as permissões do usuário originador

**Control ID:** BAS-002.3.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Fluxos em que uma aplicação use conta técnica para acessar dados, APIs ou tools em nome de usuário.

**Description**

A aplicação deve aplicar interseção entre as permissões da conta técnica e as permissões do usuário. Quando on-behalf-of não existir, uma camada determinística deve validar usuário, ação, recurso e finalidade antes de usar a credencial de serviço.

**Rationale**

Uma conta técnica privilegiada pode transformar uma consulta de baixo privilégio em acesso amplo e produzir bypass de RBAC, ABAC ou regras de negócio.

**Impact**

Pode exigir serviço de autorização e redução de permissões de contas técnicas.

**Audit**

1. Selecionar ações executadas com conta técnica em nome de usuário.
2. Comparar permissões da conta técnica com as do usuário.
3. Executar ação solicitada por usuário sem permissão; o backend deve negar antes de usar a credencial técnica.
4. Confirmar registro de usuário, conta executora, recurso, ação e decisão.
5. Reprovar se a conta técnica puder acessar qualquer recurso solicitado pelo modelo sem validação do usuário.

**Remediation**

Implementar on-behalf-of ou policy enforcement intermediário e reduzir a conta técnica ao menor privilégio necessário.

**Evidence**

Matriz de permissões, policy de autorização e teste negativo de privilege expansion.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-3, AC-6

---

### 3.5 Certifique-se de que permissões administrativas e de runtime sejam segregadas

**Control ID:** BAS-002.3.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Gateways e aplicações com usuários administradores, operadores, suporte e identidades de runtime.

**Description**

Roles de configuração de rotas/policies/secrets devem ser separadas de roles que apenas invocam inferência, consultam métricas ou leem logs. Identidades de runtime não devem criar, alterar ou excluir configuração administrativa.

**Rationale**

Acumulação de permissões facilita alteração não autorizada e permite que comprometimento de runtime modifique o próprio controle de segurança.

**Impact**

Pode exigir revisão de roles e criação de grupos separados.

**Audit**

1. Exportar roles e bindings do gateway/aplicação.
2. Confirmar ausência de identidade de runtime com ações administrativas.
3. Confirmar que operadores de consumo não podem alterar policies ou secrets.
4. Executar tentativa administrativa usando identidade de runtime; deve ser negada.
5. Reprovar se uma role genérica conceder inferência e administração.

**Remediation**

Criar roles distintas para administração, operação, suporte, auditoria e runtime; remover permissões acumuladas e adicionar deny explícito quando suportado.

**Evidence**

Exportação de roles/bindings e resultado de teste de operação administrativa negada.

**Mappings**

CIS Controls v8 5 e 6; NIST SP 800-53 AC-5, AC-6

---

### 3.6 Certifique-se de que escopos desconhecidos ou não mapeados sejam negados por padrão

**Control ID:** BAS-002.3.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** APIs e gateways que utilizem scopes, roles, entitlements ou claims para autorizar rotas e capacidades.

**Description**

O mecanismo de autorização deve utilizar allowlist explícita de escopos conhecidos. Claims ausentes, desconhecidas, vazias, duplicadas ou não mapeadas não podem resultar em permissão implícita nem em perfil padrão privilegiado.

**Rationale**

Comportamentos permissivos para claims inesperadas permitem privilege escalation após erro de emissão, manipulação ou introdução de novos escopos.

**Impact**

Clientes com claims legadas poderão precisar de correção.

**Audit**

1. Revisar a tabela de mapeamento de scopes/roles para rotas.
2. Testar token sem scope, com scope desconhecido, duplicado e com combinação não prevista.
3. Confirmar que todos os casos são negados ou recebem apenas acesso público explicitamente definido.
4. Reprovar se o sistema aplicar role default com acesso maior que o mínimo.

**Remediation**

Configurar deny-by-default, allowlist de scopes e validação estrita de claims antes do policy evaluation.

**Evidence**

Mapeamento de scopes e resultados de testes com claims ausentes/desconhecidas.

**Mappings**

CIS Controls v8 6; NIST SP 800-53 AC-3, AC-6

---

## 4. Roteamento, modelos e policies

Controles para allowlists, seleção segura de modelos/providers/regiões, parâmetros de inferência e gestão consistente de rulesets.

### 4.1 Certifique-se de que o gateway utilize allowlist de providers, modelos, versões, regiões e features por aplicação

**Control ID:** BAS-002.4.1
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Gateways e aplicações capazes de acessar mais de um provider, modelo, deployment, região ou feature.

**Description**

Cada aplicação deve possuir allowlist explícita contendo provider, modelo, versão/deployment, região, endpoint e features permitidas. O gateway deve negar qualquer combinação ausente da allowlist, mesmo que o provider a disponibilize automaticamente.

**Rationale**

Sem allowlist, atualizações do provider ou parâmetros do cliente podem direcionar dados a modelo, região ou feature não avaliada.

**Impact**

A manutenção do catálogo e das allowlists adiciona esforço operacional.

**Audit**

1. Exportar a configuração de rotas por aplicação.
2. Confirmar que todos os destinos estão explicitamente listados e vinculados à aplicação/ambiente.
3. Tentar usar modelo, versão, região e feature não cadastrados; todas as tentativas devem ser negadas.
4. Reprovar se existir wildcard, any model, latest ou seleção automática sem conjunto fechado.

**Remediation**

Criar allowlist por aplicação e ambiente, substituir wildcards e aliases mutáveis e aplicar deny-by-default.

**Evidence**

Configuração de rotas e resultados de testes com destinos não permitidos.

**Mappings**

CIS Controls v8 2, 4 e 6; NIST SP 800-53 CM-7, AC-3

---

### 4.2 Certifique-se de que novos modelos, versões e features permaneçam bloqueados por padrão

**Control ID:** BAS-002.4.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Gateways integrados a providers que adicionem automaticamente modelos, endpoints ou features.

**Description**

Descoberta ou disponibilidade no provider não deve tornar um recurso utilizável. Novos itens devem permanecer em estado disabled/deny até serem adicionados explicitamente à configuração versionada da aplicação.

**Rationale**

Ativação automática pode introduzir mudanças de comportamento, retenção, região, preço ou segurança sem avaliação.

**Impact**

A aplicação não receberá automaticamente novos recursos e dependerá de atualização controlada.

**Audit**

1. Revisar a política de descoberta/sincronização do provider.
2. Simular ou identificar item novo disponível no provider.
3. Confirmar que o item não aparece como rota utilizável antes de configuração explícita.
4. Reprovar se sincronização automática publicar novos recursos em produção.

**Remediation**

Desabilitar auto-enable, configurar catálogo local versionado e exigir inclusão explícita para cada recurso.

**Evidence**

Configuração de sincronização e evidência de recurso novo bloqueado.

**Mappings**

CIS Controls v8 2 e 4; NIST SP 800-53 CM-3, CM-7

---

### 4.3 Certifique-se de que regras de roteamento preservem restrições de dados e residência

**Control ID:** BAS-002.4.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Roteamento dinâmico por custo, latência, disponibilidade, capacidade ou balanceamento.

**Description**

O algoritmo de roteamento deve filtrar previamente destinos incompatíveis com classificação dos dados, região permitida, tenant, contrato e finalidade. Critérios de custo ou disponibilidade somente podem escolher entre destinos que já atendam às restrições de segurança.

**Rationale**

Roteamento otimizado apenas por desempenho pode transferir dados a região ou provider proibido.

**Impact**

Pode reduzir o conjunto de destinos e aumentar custo/latência em situações de contingência.

**Audit**

1. Revisar a ordem de avaliação das regras de roteamento.
2. Confirmar que filtros de segurança são aplicados antes de custo/latência.
3. Simular indisponibilidade do destino preferencial com dados classificados.
4. Confirmar que o gateway não seleciona destino incompatível e falha de forma segura se não houver alternativa.
5. Reprovar se qualquer fallback ignorar região, classificação ou provider permitido.

**Remediation**

Implementar filtros obrigatórios de segurança como pré-condição do roteamento e remover destinos incompatíveis do conjunto elegível.

**Evidence**

Ruleset, teste de falha por classificação/região e registro do destino selecionado.

**Mappings**

CIS Controls v8 3, 4 e 12; NIST SP 800-53 AC-4, SC-7

---

### 4.4 Certifique-se de que failover utilize somente destinos equivalentes e previamente permitidos

**Control ID:** BAS-002.4.4
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Soluções com failover automático entre modelos, deployments, providers ou regiões.

**Description**

Cada rota de failover deve indicar um conjunto fechado de destinos equivalentes quanto a região, proteção de dados, retenção, capabilities, formato de resposta e controles. O gateway não deve escolher qualquer modelo disponível apenas para manter disponibilidade.

**Rationale**

Failover para destino não equivalente pode alterar tratamento de dados, semântica, segurança do output e compatibilidade da aplicação.

**Impact**

O conjunto de contingência pode ser menor e exigir manutenção de capacidade ociosa.

**Audit**

1. Listar destinos primários e de failover por rota.
2. Comparar configurações de região, retenção, capabilities e contrato de resposta.
3. Simular falha do primário e observar o destino selecionado.
4. Confirmar que destino fora do conjunto fechado nunca é usado.
5. Reprovar se o failover usar wildcard, latest ou descoberta automática.

**Remediation**

Definir grupos explícitos de equivalência, fixar versões e testar failover com validação de contrato e segurança.

**Evidence**

Matriz de equivalência, configuração de failover e resultado de teste controlado.

**Mappings**

CIS Controls v8 4 e 11; NIST SP 800-53 CP-10, SC-6

---

### 4.5 Certifique-se de que parâmetros de inferência protegidos sejam impostos pelo servidor

**Control ID:** BAS-002.4.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** APIs que aceitem temperature, top_p, max_tokens, seed, response_format, tools, tool_choice, system prompt ou parâmetros equivalentes.

**Description**

O gateway deve definir valores fixos, intervalos permitidos ou allowlists por aplicação. Parâmetros fora do limite devem ser rejeitados ou sobrescritos. Clientes não podem habilitar tools, aumentar contexto/tokens ou substituir system prompt fora da policy.

**Rationale**

Parâmetros livres podem aumentar custo, reduzir previsibilidade, habilitar capacidades não autorizadas ou contornar guardrails.

**Impact**

Pode limitar experimentação e exigir endpoints separados para ambientes de desenvolvimento.

**Audit**

1. Exportar limites e valores permitidos por rota.
2. Enviar valores acima/abaixo dos limites e parâmetros desconhecidos.
3. Confirmar rejeição ou normalização antes do provider.
4. Tentar habilitar tool/system prompt não permitido e confirmar bloqueio.
5. Reprovar se o provider receber valores não autorizados.

**Remediation**

Definir schema e policy server-side, remover parâmetros desnecessários do contrato público e validar antes do roteamento.

**Evidence**

Schema de API, ruleset e captura de chamadas mostrando parâmetros normalizados.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 CM-6, SI-10

---

### 4.6 Certifique-se de que rulesets de gateway sejam versionados, validados e aplicados de forma atômica

**Control ID:** BAS-002.4.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Gateways com policies de roteamento, inspeção, limites, transformação ou bloqueio.

**Description**

Policies devem possuir versão imutável, validação de sintaxe e semântica, teste automatizado e implantação atômica. Uma atualização não pode deixar parte dos nós com policy antiga e parte com policy nova além de janela controlada. Deve existir rollback para versão conhecida.

**Rationale**

Policies inconsistentes criam resultados diferentes para a mesma chamada e podem abrir janelas de bypass.

**Impact**

A implantação atômica pode exigir pipeline, canary controlado e armazenamento versionado.

**Audit**

1. Selecionar mudanças recentes de policy.
2. Confirmar versão, hash, testes e mecanismo de promoção/rollback.
3. Verificar que todos os nós ativos reportam a mesma versão após a implantação.
4. Simular policy inválida e confirmar que a versão em produção não é substituída.
5. Reprovar se a edição direta em produção não gerar versão ou puder deixar estado parcial.

**Remediation**

Armazenar policies em repositório versionado, validar antes da promoção e usar implantação transacional/atômica com rollback.

**Evidence**

Histórico de versões, resultados de testes e evidência de consistência entre nós.

**Mappings**

CIS Controls v8 4 e 16; NIST SP 800-53 CM-3, CM-5, CM-6

---

## 5. Entrada, prompt e payload

Controles para validação de payloads, canonicalização, proteção de prompts e mitigação de conteúdo malicioso.

### 5.1 Certifique-se de que content type, tamanho e schema do payload sejam validados antes do processamento

**Control ID:** BAS-002.5.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** APIs de IA que recebam JSON, multipart, arquivos, áudio, imagem, texto ou payloads estruturados.

**Description**

A API deve aceitar somente métodos, content types, campos e tamanhos explicitamente permitidos. Campos adicionais, tipos incompatíveis, profundidade excessiva, arrays acima do limite e payloads maiores que o máximo devem ser rejeitados antes de qualquer parsing avançado, upload ou chamada ao modelo.

**Rationale**

Payloads não limitados facilitam DoS, parser confusion, deserialização insegura e consumo excessivo de tokens e storage.

**Impact**

Clientes incompatíveis precisarão corrigir contratos e limites.

**Audit**

1. Revisar o schema e os limites configurados por endpoint.
2. Enviar content type incorreto, campo desconhecido, tipo inválido, estrutura profunda e payload acima do limite.
3. Confirmar rejeição com 4xx antes de chamada ao modelo ou armazenamento persistente.
4. Confirmar que o tamanho é validado também para streaming/chunked uploads.
5. Reprovar se campos extras forem encaminhados silenciosamente ao provider.

**Remediation**

Implementar validação estrita de schema, content type, tamanho, profundidade e quantidade de itens no gateway/API.

**Evidence**

Schemas, limites configurados e resultados de testes negativos.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SI-10; OWASP API Security 2023 API8

---

### 5.2 Certifique-se de que entradas sejam canonicalizadas antes da aplicação de regras de segurança

**Control ID:** BAS-002.5.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Entradas textuais, URLs, filenames, headers e payloads sujeitos a filtros, DLP ou detecção de ataque.

**Description**

Decodificação, normalização Unicode, remoção de codificações múltiplas e canonicalização de URLs/paths devem ocorrer uma única vez antes da inspeção. A mesma representação canonicalizada deve ser usada pelo filtro e pelo componente que processará a entrada.

**Rationale**

Diferenças de interpretação entre filtro e backend permitem bypass por encoding, caracteres homoglyph, path traversal ou double decoding.

**Impact**

A normalização pode alterar entradas legítimas e exige testes por idioma e formato.

**Audit**

1. Revisar a ordem de parsing, decodificação e inspeção.
2. Testar payloads equivalentes usando URL encoding duplo, Unicode normalizado/não normalizado e separadores alternativos.
3. Confirmar que todas as variantes resultam na mesma representação inspecionada ou são rejeitadas.
4. Reprovar se o backend decodificar novamente conteúdo já aprovado pelo filtro.

**Remediation**

Implementar pipeline único de canonicalização antes de DLP/guardrails e impedir double decoding nos componentes posteriores.

**Evidence**

Diagrama do pipeline de parsing e resultados de testes com encodings alternativos.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SI-10; OWASP API Security 2023 API8

---

### 5.3 Certifique-se de que prompts sistêmicos e instruções de desenvolvedor sejam mantidos no servidor e protegidos por integridade

**Control ID:** BAS-002.5.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Aplicações que utilizem system prompts, developer prompts, templates ou regras internas.

**Description**

Prompts protegidos devem ser armazenados em repositório ou configuração server-side com controle de acesso e versão. O cliente pode fornecer somente campos previstos. A aplicação deve montar a mensagem final no backend e impedir que o usuário substitua role, prioridade ou conteúdo protegido.

**Rationale**

Exposição ou alteração de prompts protegidos permite bypass de políticas, extração de regras internas e mudança do comportamento da solução.

**Impact**

A centralização pode exigir pipeline de configuração e reduzir customização local.

**Audit**

1. Inspecionar cliente, API e backend para localizar prompts protegidos.
2. Confirmar que não estão presentes em bundle, código cliente ou payload retornado ao usuário.
3. Tentar enviar mensagens com role system/developer ou campo equivalente; devem ser rejeitadas ou tratadas como input de usuário.
4. Confirmar versionamento e controle de integridade do prompt em produção.
5. Reprovar se o usuário puder substituir total ou parcialmente instrução protegida.

**Remediation**

Mover prompts protegidos para configuração server-side versionada, restringir roles aceitas e reconstruir a sequência de mensagens no backend.

**Evidence**

Configuração/repositório do prompt, schema da API e teste de tentativa de substituição.

**Mappings**

CIS Controls v8 3, 6 e 16; NIST SP 800-53 CM-5, SI-10; OWASP LLM Prompt Injection

---

### 5.4 Certifique-se de que conteúdo não confiável seja isolado de instruções privilegiadas

**Control ID:** BAS-002.5.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Aplicações que enviem ao modelo conteúdo de usuários, arquivos, páginas web, e-mails, tickets ou fontes externas.

**Description**

Conteúdo não confiável deve ser marcado e inserido em campo, bloco ou mensagem separado das instruções sistêmicas. A aplicação deve declarar que o conteúdo é dado e não instrução e não pode concatená-lo diretamente em posição privilegiada ou template executável.

**Rationale**

Conteúdo externo pode conter instruções maliciosas que tentem alterar prioridade, exfiltrar dados ou induzir ações indevidas.

**Impact**

O isolamento não elimina totalmente prompt injection e pode reduzir flexibilidade de alguns templates.

**Audit**

1. Revisar como conteúdo externo é montado no prompt.
2. Confirmar separação estrutural entre instruções e dados, com delimitadores/roles estáveis.
3. Inserir conteúdo contendo tentativa de override e verificar que não é promovido a system/developer instruction.
4. Reprovar se o conteúdo for concatenado diretamente à instrução privilegiada ou puder fechar delimitadores sem escape.

**Remediation**

Separar conteúdo em mensagens/campos próprios, aplicar encoding/delimitação robusta e usar templates que não permitam alteração da estrutura.

**Evidence**

Template de prompt e resultados de teste com instrução maliciosa em conteúdo externo.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SI-10; OWASP LLM Prompt Injection

---

### 5.5 Certifique-se de que arquivos e URLs sejam obtidos somente de origens permitidas e inspecionados antes do uso

**Control ID:** BAS-002.5.5
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Aplicações que aceitem upload, URL, attachment, callback ou façam retrieval de conteúdo remoto.

**Description**

Uploads devem passar por validação de tipo real, tamanho, extensão, malware e conteúdo ativo. URLs devem usar protocolos permitidos, resolução DNS controlada, bloqueio de endereços privados/metadata e allowlist ou política de reputação. O conteúdo só pode seguir para processamento após aprovação.

**Rationale**

Arquivos e URLs podem explorar parsers, introduzir malware, executar SSRF ou fornecer conteúdo malicioso ao modelo.

**Impact**

A inspeção pode aumentar latência e impedir formatos não suportados.

**Audit**

1. Testar arquivo com extensão divergente do MIME, arquivo compactado excessivo e amostra de malware de teste.
2. Testar URL para localhost, ranges privados, metadata service, protocolo não permitido e redirecionamento para destino bloqueado.
3. Confirmar que todos são rejeitados antes do processamento pelo modelo.
4. Confirmar que redirecionamentos e resolução DNS são revalidados.
5. Reprovar se a aplicação baixar URL arbitrária ou confiar apenas na extensão do arquivo.

**Remediation**

Adicionar serviço de upload seguro, antivírus/sandbox, validação MIME e cliente HTTP com egress control, proteção SSRF e política de origem.

**Evidence**

Configuração de upload/retrieval e resultados de testes com malware e SSRF.

**Mappings**

CIS Controls v8 10, 12 e 16; NIST SP 800-53 SI-3, SI-10; OWASP API Security 2023 API7

---

### 5.6 Certifique-se de que tentativas de prompt injection e jailbreak sejam submetidas a policy explícita

**Control ID:** BAS-002.5.6
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Aplicações externas, críticas ou que utilizem dados sensíveis, RAG, tools ou decisões automatizadas.

**Description**

O gateway ou aplicação deve detectar padrões e comportamentos de prompt injection/jailbreak e executar ação definida por policy: block, sanitize, route to restricted model, require human review ou alert. Apenas registrar sem reduzir o risco não atende ao controle para fluxos críticos.

**Rationale**

Ataques podem manipular instruções, induzir vazamento e contornar regras de negócio ou segurança.

**Impact**

Detecção pode gerar falsos positivos e exige tuning e testes de regressão.

**Audit**

1. Revisar ruleset e ações associadas a categorias de prompt injection/jailbreak.
2. Executar conjunto de casos diretos, indiretos, encoding e multi-turn.
3. Confirmar que cada caso de severidade alta aciona a ação prevista antes do modelo ou impede uso perigoso do resultado.
4. Medir falsos negativos e confirmar inexistência de regra apenas informativa para ataques críticos.
5. Reprovar se a policy não possuir critério de bloqueio ou mitigação verificável.

**Remediation**

Implementar camada de detecção/guardrail, definir ações por severidade, criar testes de regressão e ajustar regras para o caso de uso.

**Evidence**

Ruleset versionado, corpus de testes e resultados com ação aplicada.

**Mappings**

CIS Controls v8 13 e 16; NIST SP 800-53 SI-4, SI-10; OWASP LLM Prompt Injection

---

## 6. Saída e uso downstream

Controles para contratos de resposta, prevenção de vazamento, encoding por contexto e separação entre conteúdo gerado e decisões de controle.

### 6.1 Certifique-se de que cada endpoint imponha um contrato de resposta explícito

**Control ID:** BAS-002.6.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** APIs que retornem JSON, eventos, streaming estruturado ou respostas consumidas por software.

**Description**

A API deve definir campos, tipos, enumerações, limites e content type permitidos. O backend deve rejeitar ou transformar respostas do modelo que não atendam ao contrato antes de enviá-las ao consumidor. Campos de controle não podem ser criados dinamicamente pelo modelo.

**Rationale**

Respostas fora do contrato causam parser confusion, injeção de campos, falha de automação e uso incorreto por sistemas downstream.

**Impact**

Respostas válidas semanticamente, mas fora do schema, serão descartadas ou precisarão de nova tentativa.

**Audit**

1. Obter o schema de resposta por endpoint.
2. Forçar o modelo a gerar campos adicionais, tipos incorretos, JSON inválido e payload acima do limite.
3. Confirmar que a API não retorna resposta fora do contrato e não repassa campos desconhecidos.
4. Confirmar que streaming possui framing e eventos permitidos.
5. Reprovar se o consumidor receber conteúdo bruto em campo usado como controle.

**Remediation**

Aplicar validação de schema e allowlist no backend/gateway, separar conteúdo gerado de metadados e retornar erro seguro quando inválido.

**Evidence**

Schema publicado, configuração de validação e resultados de testes com respostas malformadas.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SI-10; OWASP API Security 2023 API8

---

### 6.2 Certifique-se de que outputs sejam inspecionados para segredos e dados sensíveis antes da entrega

**Control ID:** BAS-002.6.2
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Aplicações externas, multi-tenant ou que processem dados pessoais, bancários, estratégicos ou segredos.

**Description**

Antes de retornar ao usuário ou sistema downstream, o output deve passar por detecção de secrets, identificadores sensíveis e padrões de dados proibidos. A policy deve bloquear, mascarar ou substituir o conteúdo de acordo com classificação e canal. A inspeção deve ocorrer também em streaming, antes da emissão de cada chunk quando tecnicamente viável.

**Rationale**

Modelos podem reproduzir dados do contexto, treinamento, memória ou prompt e expor informações não autorizadas.

**Impact**

Pode aumentar latência, produzir falsos positivos e exigir buffering de streaming.

**Audit**

1. Revisar categorias e ações da inspeção de output.
2. Executar testes com chaves de teste, identificadores sintéticos e conteúdo classificado inserido no contexto.
3. Confirmar bloqueio/mascaramento antes da resposta chegar ao cliente.
4. Confirmar cobertura de respostas normais e streaming.
5. Reprovar se a detecção ocorrer apenas após entrega ou apenas para logs.

**Remediation**

Adicionar DLP/secret scanning no caminho de resposta, definir ações por classe de dado e impedir emissão antes da decisão.

**Evidence**

Policy de output, corpus de teste e capturas demonstrando bloqueio/mascaramento.

**Mappings**

CIS Controls v8 3 e 13; NIST SP 800-53 SI-4, SC-28; OWASP LLM Sensitive Information Disclosure

---

### 6.3 Certifique-se de que conteúdo gerado seja codificado de acordo com o destino

**Control ID:** BAS-002.6.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Outputs inseridos em HTML, Markdown, e-mail, PDF, SQL, shell, configuração, headers ou outros contextos interpretáveis.

**Description**

A aplicação deve tratar output como dado não confiável e aplicar encoding/sanitização específica ao sink. HTML deve usar escaping/allowlist; URLs devem ser validadas; Markdown deve restringir HTML ativo; valores para SQL/shell não podem ser concatenados. Sanitização genérica única não atende a todos os destinos.

**Rationale**

Conteúdo gerado pode produzir XSS, injection, links maliciosos e execução em sistemas downstream.

**Impact**

A sanitização pode remover formatação ou funcionalidade desejada.

**Audit**

1. Listar sinks que recebem conteúdo gerado.
2. Confirmar uso de encoder/sanitizer específico para cada contexto.
3. Testar payloads de XSS, Markdown com HTML ativo, URL javascript e caracteres de shell/SQL.
4. Confirmar que o conteúdo é neutralizado e não executado.
5. Reprovar se houver concatenação direta em contexto interpretável.

**Remediation**

Usar bibliotecas de encoding por contexto, allowlist de HTML/Markdown e APIs parametrizadas para qualquer execução ou consulta.

**Evidence**

Código/configuração de sanitização e resultados de testes de injeção por sink.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SI-10; OWASP Top 10 A03 Injection

---

### 6.4 Certifique-se de que conteúdo gerado não controle metadados ou decisões de segurança da API

**Control ID:** BAS-002.6.4
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** APIs em que o modelo possa influenciar status, headers, redirects, destination, authorization decision, tool choice ou campos de controle.

**Description**

Status HTTP, headers, destinatários, IDs de recurso, flags de autorização e campos que determinam ações devem ser calculados por código/policy determinística. O modelo pode fornecer conteúdo, mas não deve determinar diretamente metadados de segurança ou controle.

**Rationale**

Permitir que o modelo controle metadados pode gerar redirects maliciosos, cache poisoning, header injection, autorização indevida e execução de ações.

**Impact**

Pode exigir separar o schema de conteúdo do schema de controle e implementar mapeamento adicional.

**Audit**

1. Identificar campos e metadados influenciados pelo modelo.
2. Confirmar que campos de controle são definidos por código ou allowlist independente.
3. Forçar o modelo a sugerir status, redirect, destinatário ou flag privilegiada.
4. Confirmar que a sugestão não altera o comportamento da API sem validação determinística.
5. Reprovar se qualquer campo gerado for usado diretamente em decisão de segurança.

**Remediation**

Separar conteúdo e controle em estruturas diferentes, remover campos privilegiados do schema do modelo e calcular metadados no backend.

**Evidence**

Schema de resposta, fluxo de decisão e teste de tentativa de manipulação de metadados.

**Mappings**

CIS Controls v8 6 e 16; NIST SP 800-53 AC-3, SI-10

---

### 6.5 Certifique-se de que comunicações externas sensíveis utilizem templates e campos permitidos

**Control ID:** BAS-002.6.5
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Mensagens a clientes, parceiros, reguladores ou público que possam produzir impacto financeiro, jurídico ou reputacional.

**Description**

Para comunicações sensíveis, o modelo deve preencher somente campos permitidos em template aprovado ou gerar rascunho submetido a validação. Informações obrigatórias, disclaimers, valores, datas, destinatários e instruções transacionais não podem ser livremente inventados.

**Rationale**

Texto totalmente livre pode omitir informação obrigatória, incluir orientação indevida ou transmitir dados incorretos.

**Impact**

Templates reduzem flexibilidade e podem exigir manutenção por produto/canal.

**Audit**

1. Selecionar tipos de comunicação sensível.
2. Confirmar que campos fixos e obrigatórios são fornecidos pelo sistema e não pelo modelo.
3. Tentar induzir o modelo a remover disclaimer, alterar valor/data ou inserir destinatário diferente.
4. Confirmar que a validação/template impede a alteração.
5. Reprovar se a mensagem sensível for enviada diretamente a partir de texto livre do modelo.

**Remediation**

Implementar templates com campos allowlisted, validação de conteúdo e etapa técnica de aprovação quando o risco exigir.

**Evidence**

Templates, schemas, regras de validação e resultados de testes de alteração indevida.

**Mappings**

CIS Controls v8 16; NIST AI RMF MANAGE; OWASP LLM Misinformation

---

### 6.6 Certifique-se de que mensagens de erro não revelem detalhes internos de IA

**Control ID:** BAS-002.6.6
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** APIs, chatbots e gateways acessíveis a usuários ou integrações externas.

**Description**

Respostas de erro não devem incluir stack trace, prompt sistêmico, policy, nome interno de modelo/provider, endpoint, token, payload completo, cabeçalho sensível ou detalhes de infraestrutura. O cliente deve receber código estável e mensagem genérica; detalhes técnicos devem permanecer em log restrito correlacionado.

**Rationale**

Erros detalhados facilitam enumeração, engenharia de ataques e exposição acidental de dados e segredos.

**Impact**

Mensagens genéricas podem reduzir capacidade de diagnóstico do cliente e exigem correlation ID.

**Audit**

1. Provocar erros de autenticação, schema, provider, timeout, policy e processamento.
2. Inspecionar corpo e headers retornados ao cliente.
3. Confirmar ausência de stack trace, prompts, secrets, hostnames internos e payload sensível.
4. Confirmar presença de código de erro estável e correlation ID.
5. Reprovar se detalhes internos forem retornados em qualquer ambiente produtivo.

**Remediation**

Configurar exception handler central, mapear erros internos para códigos públicos e mover detalhes para logs protegidos.

**Evidence**

Catálogo de erros e resultados de testes provocando falhas distintas.

**Mappings**

CIS Controls v8 3 e 16; NIST SP 800-53 SI-11; OWASP API Security 2023 API8

---

## 7. Exposição, sessão e abuso

Controles para rate limiting, proteção contra replay, segurança web, WAF/anti-bot e isolamento de caches.

### 7.1 Certifique-se de que rate limits sejam aplicados por usuário, sessão, aplicação, tenant e origem

**Control ID:** BAS-002.7.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** APIs internas ou externas que aceitem chamadas interativas ou automatizadas.

**Description**

Os limites devem combinar dimensões de identidade e origem, evitando que um único limite global ou apenas por IP seja suficiente. A resposta deve indicar throttling sem revelar quota de outros tenants. Limites devem ser aplicados antes da chamada ao provider.

**Rationale**

Sem limites multidimensionais, atacantes podem distribuir chamadas, esgotar orçamento, degradar serviço ou abusar de contas compartilhadas.

**Impact**

Usuários de alto volume podem precisar de quotas específicas e tratamento de bursts.

**Audit**

1. Revisar policies de rate limit e suas chaves de particionamento.
2. Executar bursts pelo mesmo usuário em IPs distintos e por usuários distintos no mesmo IP.
3. Confirmar aplicação dos limites por identidade e tenant, além de origem.
4. Confirmar que chamadas bloqueadas não alcançam o provider.
5. Reprovar se existir apenas limite global ou apenas por IP para serviço autenticado.

**Remediation**

Configurar quotas e rate limits combinando user/session/app/tenant/IP e aplicar no gateway antes do backend/provider.

**Evidence**

Policies de rate limit e resultados de testes de burst em múltiplas dimensões.

**Mappings**

CIS Controls v8 13; NIST SP 800-53 SC-5; OWASP API Security 2023 API4

---

### 7.2 Certifique-se de que streaming, uploads e ações possuam limites independentes de inferência simples

**Control ID:** BAS-002.7.2
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** APIs com streaming, upload de arquivos, long polling, geração extensa ou operações com efeito colateral.

**Description**

Devem existir limites separados para duração de streaming, bytes enviados/recebidos, arquivos por período, conexões simultâneas e operações de ação. Uma quota de requisições não substitui limites de duração e volume.

**Rationale**

Uma única conexão ou upload pode consumir recursos por longo período e contornar limites baseados apenas em contagem de chamadas.

**Impact**

Limites podem interromper respostas longas e exigir suporte a retomada ou paginação.

**Audit**

1. Identificar tipos de operação e limites específicos configurados.
2. Abrir conexões simultâneas, streaming prolongado e upload acima da quota.
3. Confirmar encerramento controlado sem chamada adicional ou consumo ilimitado.
4. Confirmar que ações possuem limite de frequência independente da geração textual.
5. Reprovar se todas as operações compartilharem somente um contador de requisições.

**Remediation**

Adicionar limites por duração, bytes, conexões, arquivos e ações, com cancelamento no gateway e backend.

**Evidence**

Configuração de limites e resultados de testes de streaming/upload/concorrência.

**Mappings**

CIS Controls v8 13; NIST SP 800-53 SC-5; OWASP API Security 2023 API4

---

### 7.3 Certifique-se de que operações com efeito colateral sejam protegidas contra replay e duplicidade

**Control ID:** BAS-002.7.3
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** APIs em que a resposta de IA resulte em criação, envio, alteração, pagamento, aprovação ou outra ação persistente.

**Description**

A API deve exigir idempotency key, nonce, timestamp ou identificador transacional vinculado ao usuário e à operação. A mesma chave não pode produzir a ação novamente e deve expirar após janela definida. O gateway deve rejeitar mensagens fora da janela ou com assinatura inválida.

**Rationale**

Retries, replay de token ou repetição maliciosa podem executar a mesma ação múltiplas vezes.

**Impact**

É necessário armazenar estado de idempotência e definir comportamento para conflitos.

**Audit**

1. Selecionar endpoint com efeito colateral.
2. Enviar a mesma requisição e idempotency key repetidamente.
3. Confirmar que somente a primeira execução altera estado e as demais retornam o resultado original ou conflito.
4. Testar chave reutilizada por outro usuário/operação e timestamp fora da janela; devem ser rejeitados.
5. Reprovar se retry puder repetir a ação.

**Remediation**

Implementar idempotency store, nonce/timestamp e vinculação criptográfica ou lógica à identidade e ao conteúdo da operação.

**Evidence**

Configuração e logs de testes de replay/idempotência.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SC-23, SI-10; OWASP API Security 2023 API4

---

### 7.4 Certifique-se de que serviços externos estejam protegidos por WAF, API Gateway, anti-bot e mitigação DDoS

**Control ID:** BAS-002.7.4
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** APIs, chatbots, voicebots e serviços de IA acessíveis pela Internet ou por parceiros externos.

**Description**

A exposição deve atravessar camada de proteção que aplique TLS, validação de protocolo, limites, reputação, detecção de bots, regras de ataque e mitigação volumétrica. O endpoint de provider ou backend não pode ser publicado diretamente.

**Rationale**

Serviços de IA possuem custo e recursos elevados e são alvos de scraping, automação maliciosa, credential stuffing e DoS.

**Impact**

Pode adicionar latência, custos e necessidade de tuning para tráfego legítimo.

**Audit**

1. Revisar o caminho público até o backend/provider.
2. Confirmar presença e configuração de WAF/API Gateway/bot/DDoS antes do serviço.
3. Testar acesso direto ao backend/provider a partir da Internet; deve ser bloqueado.
4. Executar testes controlados de bot/rate/assinatura malformada e confirmar bloqueio.
5. Reprovar se a camada de proteção estiver em modo somente monitoramento para ataques críticos.

**Remediation**

Publicar o serviço somente por camada de proteção aprovada, fechar acesso direto e configurar regras e limites específicos para o endpoint.

**Evidence**

Diagrama de exposição, configuração das proteções e resultados de testes de bloqueio.

**Mappings**

CIS Controls v8 12 e 13; NIST SP 800-53 SC-5, SC-7; OWASP API Security 2023 API4/API8

---

### 7.5 Certifique-se de que sessões web utilizem cookies e políticas de origem seguras

**Control ID:** BAS-002.7.5
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Aplicações web e chatbots autenticados que utilizem cookies, browser storage ou chamadas cross-origin.

**Description**

Cookies de sessão devem usar Secure, HttpOnly e SameSite apropriado; sessões devem expirar e ser rotacionadas após autenticação. CORS deve usar allowlist de origens e não combinar wildcard com credenciais. Operações de alteração devem possuir proteção CSRF quando baseadas em cookie.

**Rationale**

Configuração fraca permite roubo de sessão, CSRF e uso da API a partir de origem maliciosa.

**Impact**

Integrações legítimas cross-origin podem exigir configuração explícita adicional.

**Audit**

1. Inspecionar Set-Cookie, CORS e fluxo de sessão.
2. Confirmar Secure/HttpOnly/SameSite, expiração e rotação da sessão.
3. Testar Origin não permitido e requisição com credenciais; deve ser rejeitada sem ACAO permissivo.
4. Testar operação state-changing sem token/proteção CSRF quando aplicável.
5. Reprovar se houver CORS * com credenciais ou cookie de sessão sem flags obrigatórias.

**Remediation**

Configurar cookies seguros, allowlist de origens, CSRF token e rotação/expiração de sessão.

**Evidence**

Headers de resposta, configuração CORS/session e resultados de testes cross-origin/CSRF.

**Mappings**

CIS Controls v8 16; NIST SP 800-53 SC-23; OWASP ASVS Session Management

---

### 7.6 Certifique-se de que caches de resposta sejam isolados e não armazenem conteúdo sensível indevidamente

**Control ID:** BAS-002.7.6
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Aplicações, gateways, CDNs ou proxies que armazenem respostas, prompts ou resultados de IA em cache.

**Description**

A chave de cache deve incluir tenant, usuário ou escopo de autorização quando o conteúdo não for público. Respostas com dados sensíveis ou personalizados devem utilizar no-store/private conforme o canal. O cache não pode ser compartilhado entre ambientes ou tenants.

**Rationale**

Chaves incompletas podem entregar resposta de um usuário a outro e persistir conteúdo sensível fora da retenção prevista.

**Impact**

Reduzir cache pode aumentar latência e custo.

**Audit**

1. Identificar todas as camadas de cache e a composição das chaves.
2. Executar a mesma requisição com usuários/tenants distintos e confirmar que não há reutilização cruzada.
3. Inspecionar headers Cache-Control e configuração de CDN/proxy.
4. Confirmar que respostas sensíveis não permanecem armazenadas após logout/expiração.
5. Reprovar se user/tenant não fizer parte da chave para conteúdo personalizado.

**Remediation**

Particionar cache por identidade/tenant, aplicar no-store/private a conteúdo sensível e remover caches compartilhados não necessários.

**Evidence**

Configuração de cache, headers e resultados de testes entre usuários/tenants.

**Mappings**

CIS Controls v8 3 e 16; NIST SP 800-53 SC-4, SC-28; OWASP API Security 2023 API1

---

## 8. Resiliência e comportamento de falha

Controles para timeout, fail-closed, circuit breaker, fallback seguro, health checks e desativação emergencial.

### 8.1 Certifique-se de que chamadas possuam timeout, cancelamento, retry limitado e backoff

**Control ID:** BAS-002.8.1
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Aplicações e gateways que chamem providers, modelos, filtros ou serviços dependentes.

**Description**

Cada dependência deve possuir timeout de conexão e de resposta, propagação de cancelamento, quantidade máxima de retries e backoff com jitter. Retries não podem ser aplicados automaticamente a operações não idempotentes sem proteção de idempotência.

**Rationale**

Ausência de limites causa exaustão de threads/conexões, cascata de falhas, aumento de custo e repetição de ações.

**Impact**

Timeouts muito baixos podem aumentar falhas legítimas e precisam ser calibrados.

**Audit**

1. Revisar configuração de timeout/retry por dependência.
2. Simular latência e indisponibilidade.
3. Confirmar encerramento dentro do limite, propagação de cancelamento e número máximo de tentativas.
4. Confirmar uso de backoff/jitter e ausência de retry inseguro em operação não idempotente.
5. Reprovar se houver retry infinito ou timeout dependente apenas do cliente.

**Remediation**

Definir timeouts explícitos, cancellation tokens, retry limitado e backoff com jitter por tipo de operação.

**Evidence**

Configuração e resultado de teste de latência/indisponibilidade.

**Mappings**

CIS Controls v8 11 e 16; NIST SP 800-53 SC-5, CP-10

---

### 8.2 Certifique-se de que falha de autenticação, autorização, policy ou DLP resulte em bloqueio

**Control ID:** BAS-002.8.2
**Profile Applicability:** Level 1
**Criticality:** Crítica
**Applicability:** Fluxos que dependam de IAM, policy engine, guardrail, DLP ou classificação para autorizar processamento.

**Description**

Quando um controle obrigatório estiver indisponível, retornar erro, timeout ou estado indeterminado, a aplicação deve interromper a chamada ou entrega do output. Fail-open somente pode existir em rota explicitamente pública e sem dados/capacidades protegidas.

**Rationale**

Continuar processamento sem controle de segurança permite acesso, vazamento ou ação indevida justamente durante falha operacional.

**Impact**

A indisponibilidade do controle poderá indisponibilizar a funcionalidade de IA.

**Audit**

1. Identificar dependências de segurança obrigatórias por rota.
2. Simular indisponibilidade e respostas inválidas de IAM/policy/DLP.
3. Confirmar que a chamada é interrompida antes do provider ou antes da entrega do output.
4. Confirmar que não existe fallback que desative silenciosamente o controle.
5. Reprovar se a aplicação continuar em modo permissivo.

**Remediation**

Configurar fail-closed, tratar respostas indeterminadas como negação e remover bypass automático de controles obrigatórios.

**Evidence**

Configuração de falha e resultados de testes de indisponibilidade de controles.

**Mappings**

CIS Controls v8 6 e 13; NIST SP 800-53 AC-3, SI-4

---

### 8.3 Certifique-se de que circuit breakers sejam aplicados por provider, modelo e rota

**Control ID:** BAS-002.8.3
**Profile Applicability:** Level 1
**Criticality:** Alta
**Applicability:** Gateways com múltiplas dependências ou alto volume de chamadas.

**Description**

Falhas, latência e erros devem ser medidos separadamente por provider, modelo, deployment e rota. Ao atingir limiar definido, o circuit breaker deve interromper novas chamadas pelo período configurado e não pode bloquear indiscriminadamente destinos saudáveis.

**Rationale**

Sem isolamento, uma dependência degradada consome recursos e causa falha em cascata. Um breaker global pode indisponibilizar rotas saudáveis.

**Impact**

Configuração inadequada pode abrir/fechar circuitos com frequência e reduzir disponibilidade.

**Audit**

1. Revisar as chaves de particionamento e limiares dos circuit breakers.
2. Simular erro em um modelo/rota específico.
3. Confirmar abertura apenas do circuito afetado, sem chamadas adicionais durante o período.
4. Confirmar recuperação controlada em half-open e fechamento após sucesso.
5. Reprovar se não houver breaker ou se um erro isolado bloquear todos os destinos.

**Remediation**

Implementar circuit breaker particionado por destino/rota, com limiares, janela, half-open e telemetria definidos.

**Evidence**

Configuração e resultado de teste de falha isolada/recuperação.

**Mappings**

CIS Controls v8 11 e 13; NIST SP 800-53 SC-5, CP-10

---

### 8.4 Certifique-se de que fallback preserve contrato, controles e restrições de segurança

**Control ID:** BAS-002.8.4
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Soluções que usem fallback de modelo, provider, modo local, resposta cacheada ou operação degradada.

**Description**

O fallback deve manter autenticação, autorização, classificação, inspeção, região e schema de resposta exigidos pela rota original. Quando não for possível manter controles equivalentes, o fallback deve retornar indisponibilidade ou resposta estática segura, e não usar destino menos protegido.

**Rationale**

Fallback inseguro transforma incidente de disponibilidade em vazamento, bypass de policy ou comportamento incompatível.

**Impact**

Pode resultar em menor disponibilidade funcional quando não existir alternativa equivalente.

**Audit**

1. Listar todos os fallbacks por rota e a condição de acionamento.
2. Comparar controles e contrato entre primário e fallback.
3. Simular falha do primário e observar autenticação, roteamento, inspeção e schema no fallback.
4. Confirmar que ausência de destino equivalente resulta em falha segura.
5. Reprovar se fallback ignorar gateway, DLP, região ou validação de resposta.

**Remediation**

Restringir fallback a destinos equivalentes e implementar resposta estática/erro seguro quando equivalência não puder ser garantida.

**Evidence**

Matriz primário-fallback e resultados de testes de falha com validação dos controles.

**Mappings**

CIS Controls v8 11; NIST SP 800-53 CP-10, SC-6

---

### 8.5 Certifique-se de que health checks validem dependências de segurança e não apenas disponibilidade do processo

**Control ID:** BAS-002.8.5
**Profile Applicability:** Level 2
**Criticality:** Alta
**Applicability:** Gateways e aplicações com orquestração, load balancer ou autoscaling.

**Description**

Readiness deve considerar acesso ao policy engine, autenticador, secrets, DLP/guardrails e configuração de rota necessária. Uma instância sem policy válida ou incapaz de validar identidade não pode receber tráfego, mesmo que o processo responda ao liveness check.

**Rationale**

Health checks superficiais mantêm instâncias funcionalmente inseguras no pool de atendimento.

**Impact**

Checks adicionais podem aumentar dependências e exigir distinção entre liveness e readiness.

**Audit**

1. Revisar endpoints de liveness/readiness e dependências verificadas.
2. Simular ausência de policy, chave de validação ou serviço de autorização.
3. Confirmar que readiness falha e a instância é removida do tráfego.
4. Confirmar que liveness não reinicia desnecessariamente por dependência externa transitória.
5. Reprovar se a instância permanecer ready sem controles obrigatórios.

**Remediation**

Separar liveness de readiness e incluir validações de configuração/policy/identidade obrigatórias no readiness.

**Evidence**

Definição dos health checks e resultado de teste com dependência de segurança indisponível.

**Mappings**

CIS Controls v8 11 e 13; NIST SP 800-53 SI-4, CP-10

---

### 8.6 Certifique-se de que rotas, modelos e providers possam ser desabilitados imediatamente sem nova implantação da aplicação

**Control ID:** BAS-002.8.6
**Profile Applicability:** Level 2
**Criticality:** Crítica
**Applicability:** Gateways e aplicações críticas ou expostas externamente.

**Description**

Deve existir mecanismo técnico central para desabilitar uma rota, modelo, provider, feature ou aplicação e revogar sua capacidade de chamada em tempo compatível com incidente. A desativação deve propagar a todos os nós e negar novas requisições sem depender de recompilar ou republicar cada consumidor.

**Rationale**

Durante vazamento, comprometimento ou comportamento inseguro, demora na contenção amplia impacto e custo.

**Impact**

O mecanismo central é componente crítico e exige proteção contra uso indevido.

**Audit**

1. Identificar o mecanismo de disable/kill switch e seus escopos.
2. Em ambiente de teste, desabilitar uma rota e medir propagação.
3. Confirmar que novas chamadas são negadas em todos os nós e que conexões/streams são encerrados conforme policy.
4. Confirmar que o mecanismo exige autenticação privilegiada e gera trilha.
5. Reprovar se a contenção depender apenas de deploy de código ou alteração manual em cada aplicação.

**Remediation**

Implementar feature flag/policy central deny, propagação rápida e revogação de credenciais/rotas associadas, com acesso privilegiado restrito.

**Evidence**

Configuração do mecanismo e resultado de teste de desativação e propagação.

**Mappings**

CIS Controls v8 13; NIST SP 800-53 IR-4, AC-2; NIST AI RMF MANAGE

---
