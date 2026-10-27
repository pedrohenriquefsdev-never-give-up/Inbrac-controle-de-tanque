# Roadmap até produção

## Etapa 1 — Frontend e validação de UX (esta entrega)
- [x] Painel e navegação
- [x] Tanque SVG reativo
- [x] Placas estilizadas
- [x] Cadastros e fluxo de abastecimento local
- [x] Fechamento demonstrativo e exportação CSV

## Etapa 2 — Backend e integridade
- [ ] Firebase Auth e perfis ADMIN, GESTOR, OPERADOR
- [ ] Modelo Firestore com collections: unidades, tanques, bombas, veiculos, motoristas, postos, abastecimentos, movimentos, leituras, fechamentos, auditoria
- [ ] APIs privadas para comandos via Cloud Functions
- [ ] Operações idempotentes com transações de estoque e totalizador
- [ ] Regras Firestore que bloqueiem gravações diretas do cliente em saldos/auditoria
- [ ] Validação real de funções, limites, odômetro e sequência de totalizador
- [ ] Custo médio ponderado atualizado com compras, histórico de custo por lançamento
- [ ] Estorno reversível auditado; bloqueio de alterações em período fechado
- [ ] Configuração formal de corte ao mudar método de medição
- [ ] Fechamento por período com leitura acumulada inicial/final (se disponível)
- [ ] Medição física e ajuste autorizado do estoque

## Etapa 3 — Operação
- [ ] Multiunidade e autorização por base
- [ ] Comprovantes no R2 e URLs assinadas
- [ ] Relatórios com filtros/períodos e exportação completa
- [ ] Backup, restauração testada e monitoramento
- [ ] Testes multiusuário/concorrência e de segurança
- [ ] Deploy GitHub → Cloudflare com domínio corporativo
