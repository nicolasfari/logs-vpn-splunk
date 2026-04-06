# logs-vpn-splunk
# Investigação de Acessos VPN Suspeitos com Splunk

## 1. Visão Geral
Análise de logs de VPN com foco na identificação de comportamentos anômalos, incluindo acessos fora de padrão geográfico e possíveis indícios de comprometimento de conta.

## 2. Ferramentas
- Splunk
- SPL (Search Processing Language)

## 3. Cenário
Foi disponibilizado um dataset contendo logs de autenticação VPN. O objetivo foi identificar padrões suspeitos de acesso e possíveis indicadores de comprometimento.

## 4. Análise Técnica

### Ingestão de Dados
- Upload do arquivo de logs no Splunk
- Criação de índice dedicado: vpn_logs

### Análise de Volume por Usuário

    index=vpn_logs 
    | stats count by user 
    | sort -count

Objetivo: identificar usuários com volume de acessos acima do padrão.

---

### Análise de Origem de Acesso

    index=vpn_logs 
    | stats count by src_ip, user 
    | sort -count

Objetivo: correlacionar usuários com múltiplos IPs ou IPs incomuns.

---

### Análise Geográfica

    index=vpn_logs 
    | stats count by Country 
    | sort -count

Objetivo: identificar acessos fora da região esperada.

---

## 5. Principais Achados

- Alto volume de autenticações concentrado em poucos usuários
- Múltiplos IPs associados a um mesmo usuário em curto período
- Acessos originados de países não relacionados ao ambiente corporativo
- Desvio do comportamento esperado (baseline)

---

## 6. Análise de Risco

Os padrões identificados são consistentes com:
- Uso de credenciais comprometidas
- Possível atividade automatizada (credential stuffing)
- Acesso indevido via VPN corporativa

---

## 7. Conclusão

A análise indicou comportamento anômalo relevante em acessos VPN, com evidências que justificariam:
- Investigação aprofundada dos usuários afetados
- Reset de credenciais
- Aplicação de MFA (caso não implementado)

---

## 8. Habilidades Demonstradas

- Análise de Logs
- SPL
- Detecção de Anomalias
- Correlação de Eventos
- Investigação de Acessos
