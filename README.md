# logs-vpn-splunk
# Case – Investigação de Acessos VPN Suspeitos

## 1. Visão Geral
Análise de logs de autenticação VPN com foco na identificação de comportamentos anômalos e possível comprometimento de credenciais.

## 2. Cenário
Logs indicaram:
- Alto volume de acessos
- Origem de múltiplos IPs
- Localizações incomuns

---

## 3. Análise Técnica

### Padrão de Acesso
Usuários apresentaram múltiplas autenticações em curto período de tempo.

---

### Origem de IP
Foi identificado uso de diferentes IPs para o mesmo usuário, indicando possível uso indevido.

---

### Localização
Acessos foram originados de regiões não compatíveis com o contexto do ambiente.

---

## 4. Correlação (Visão do Ataque)

1. Uso de credenciais válidas  
2. Acesso via múltiplos IPs  
3. Conexões fora do padrão geográfico  

---

## 5. Análise de Risco

O comportamento é consistente com:
- Credenciais comprometidas
- Acesso não autorizado
- Possível automação de login

---

## 6. Conclusão

A análise indicou forte desvio de comportamento, sugerindo comprometimento de conta.

Ações recomendadas:
- Reset de senha
- Implementação de MFA
- Monitoramento contínuo

---

## 7. Habilidades Demonstradas

- Análise de Logs  
- Detecção de Anomalias  
- Investigação de Acessos  
- Correlação de Eventos  
