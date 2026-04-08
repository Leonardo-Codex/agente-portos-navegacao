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
