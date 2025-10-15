# Azure Honeypot - Threat Intelligence Map
Projeto de honeypot desenvolvido na nuvem Azure para atrair, capturar e analisar tentativas de ataque cibernético em tempo real. A solução utiliza uma máquina virtual deliberadamente exposta na internet como isca, com um sistema de coleta e enriquecimento de dados que transforma logs brutos em inteligência acionável, visualizada através de um mapa de calor geográfico no Microsoft Sentinel.

## 📐 Arquitetura da Solução
https://github.com/NicholasPerezSI/Azure-Honeypot-Threat-Intelligence-Map/blob/main/Arquitetura%20da%20Solu%C3%A7%C3%A3o.png?raw=true
## 🔧 Componentes e Tecnologias Utilizadas

### 🔹 Plataforma Azure
- **Azure Virtual Machine** - Honeypot exposto na internet
- **Microsoft Sentinel** - SIEM para análise e visualização de ameaças  
- **Log Analytics Workspace** - Agregação e processamento de logs
- **Custom Logs** - Ingestão de dados personalizados

### 🔹 Scripting e Automação
- **PowerShell ISE** - Coleta e processamento de logs de segurança
- **API ipgeolocation.io** - Enriquecimento de dados com geolocalização
- **Windows Event Logs** - Fonte primária de dados de segurança

### 🔍 Captura de Ameaças
- Monitoramento contínuo de tentativas de acesso não autorizado**Período Mais Ativo:** 02:00-04:00 UTC (42.6% dos ataques)
- Coleta automatizada de logs de eventos do Windows Security
- Detecção de varreduras de portas e ataques de força bruta

### 🌎 Mapa de Inteligência de Ameaças
- Visualização geográfica em tempo real dos ataques
- Plotagem de coordenadas de latitude e longitude
- Heatmap de densidade de ataques por região

## 📎 Metodologia de Implementação

### Fase 1: Configuração do Honeypot
- Provisionamento de VM Azure com segurança reduzida
- Exposição controlada de portas e serviços
- Configuração de políticas de logging aprimoradas

### Fase 2: Coleta e Enriquecimento
- Desenvolvimento de script PowerShell para parsing de logs
- Integração com API de geolocalização para enriquecimento de dados
- Criação de campos customizados para coordenadas geográficas

### Fase 3: Visualização e Análise
- Configuração de workspace no Log Analytics
- Criação de workbook customizado no Microsoft Sentinel
- Implementação de mapa interativo com plotagem de ataques

## Evolução do ataque em tempo real
🔹 **Fase Inicial (1ª Hora):** https://github.com/NicholasPerezSI/Azure-Honeypot-Threat-Intelligence-Map/blob/main/hora01.png?raw=true

🔹 **Cenário Completo (24 Horas):** https://github.com/NicholasPerezSI/Azure-Honeypot-Threat-Intelligence-Map/blob/main/hora24.png?raw=true

## 📊 Métricas de Segurança Coletadas (24h)

### 🎯 Estatísticas de Ataque

| Métrica | Valor | Análise |
|---------|-------|---------|
| **Tentativas de Ataque Detectadas** | 2.503 | Total de tentativas de RDP bloqueadas |
| **Atacantes Únicos** | 31 IPs | Origem distinta dos ataques |
| **Taxa Média de Ataques** | 104.3/hora | Intensidade do ataque |
| **Eficiência por Atacante** | ~81 tentativas/IP | Padrão de bots automatizados |

### 🌎 Distribuição Geográfica

**Países com Maior Volume:**
- 🥇 **Ucrânia** - 1.530 ataques (61.1%)
- 🥈 **Coreia do Sul** - 677 ataques (27.0%)
- 🥉 **Rússia** - 242 ataques (9.7%)
- 4️⃣ **França** - 18 ataques (0.7%)
- 5️⃣ **Holanda** - 12 ataques (0.5%)
> **Destaque:** Análise geográfica revelou que 97.8% dos ataques originaram-se de apenas 3 países, com a Ucrânia respondendo por 61% do volume total, indicando possível operação coordenada de bots.
### 🔐 Padrões de Ataque

**Usuários Mais Tentados:**
- 🥇 ADMINISTRATOR: 787 tentativas (31.4%)
- 🥈 Administrator: 330 tentativas (13.2%)
- 🥉 //: 216 tentativas (8.6%)
- 4️⃣ 的用户帐户: 168 tentativas (6.7%)
- 5️⃣ admin: 137 tentativas (5.5%)

### ⏰ Análise Temporal

**Horário de Pico:** 02:00 UTC com 750 ataques concentrados  
**Período Mais Ativo:** 02:00-04:00 UTC (42.6% dos ataques)

---

### 📈 Insights Obtidos

- Ucrânia dominou com 61% de todos os ataques
- Top 3 países concentram 97.8% dos ataques
- Padrão geográfico claro: Leste Europeu + Ásia Oriental
- Distribuição muito concentrada - típico de bots especializados

> **Destaque:** Ambiente exposto na internet recebe ataques constantes de bots especializados em força bruta RDP, demonstrando a importância de honeypots para inteligência de ameaças.

## 👨‍🎓 Aprendizados Técnicos
### ⚔ Segurança Ofensiva
- Compreensão de táticas, técnicas e procedimentos (TTPs) de atacantes
- Análise de padrões de comportamento de bots e scripts maliciosos
- Identificação de ferramentas de automatização de ataques

### ☁ Azure e Cloud Security
- Configuração de componentes de segurança na nuvem Azure
- Implementação de pipelines de dados de segurança
- Customização do Microsoft Sentinel para casos de uso específicos

### 🛠 Desenvolvimento e Automação
- Criação de scripts PowerShell para coleta de logs
- Integração com APIs REST para enriquecimento de dados
- Processamento e transformação de dados de segurança
