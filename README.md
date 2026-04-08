# agente-portos-navegacao
Sistema de inteligência de mercado para navegação e cabotagem
## Arquitetura

Coleta (AIS + line-up + web) → Processamento (regras + custos) → Banco de dados (histórico) → Relatórios (CSV/JSON)

---

## Regras de Inferência de Disponibilidade

O sistema não identifica disponibilidade confirmada, mas sim **navios potencialmente disponíveis, com base nos seguintes critérios:

- Navio em porto conhecido (ex: Suape, Santos, Ilha D’Água)
- Status: "Moored", "At Anchor" ou baixa velocidade
- Tempo parado superior a X horas
- Ausência de destino definido ou destino genérico
- Tipo de navio compatível (ex: tanker químico)

A cada navio é atribuído um **score de disponibilidade**, conforme regras heurísticas.

---

## Fluxo de dados detalhado

1. Coleta de dados AIS e line-ups
2. Consolidação e limpeza dos dados
3. Aplicação de regras de inferência
4. Cálculo de custos e viabilidade
5. Geração de relatórios
---

## Limitações

- Dados AIS são públicos e podem ter atraso ou inconsistências
- Destino informado nem sempre reflete instrução comercial real
- Não há acesso a fixtures, contratos ou decisões do armador
- O modelo é baseado em heurística e inferência, não confirmação operacional

---

## Objetivo do Sistema

Apoiar a tomada de decisão comercial e operacional, reduzindo o tempo de identificação de navios candidatos para cabotagem de etanol.
