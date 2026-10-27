# INBRAC FROTA — protótipo funcional V0.1

Interface web responsiva em React + Vite. Protótipo de validação visual e operacional para evoluir à versão de produção V1.0.

## O que funciona nesta entrega

- Dashboard, indicadores e tanque ilustrado em SVG com preenchimento atualizado pelo saldo calculado.
- Tanques e entradas de combustível com validação de capacidade.
- Cadastro de bombas e três modalidades: volume informado, totalizador e dupla conferência.
- Abastecimentos internos (baixa de estoque) e externos (não alteram estoque interno).
- Cadastro de veículos com identificação visual inspirada em placa Mercosul com faixa **laranja INBRAC**. **Não é uma reprodução de placa oficial**.
- Motoristas, movimentos, fechamento documental ou com volume apurado, relatórios por veículo e exportação CSV.
- Estorno simples auditado no protótipo (com limitações para bomba com totalizador).
- Persistência **local no navegador** via localStorage e dados iniciais fictícios.

## Atenção — não utilizar em produção

Esta é a **primeira versão demonstrativa**, não o sistema de produção. **Não usar dados reais**, pois ainda não existem autenticação real, regras de segurança no servidor, transações Firestore, anexos, backups, aprovação de fechamento, controle multiusuário ou infraestrutura de API. O histórico local pode ser alterado ou apagado pelo navegador. Operações concorrentes entre usuários NÃO estão protegidas.

O custo interno usa custo inicial de referência do tanque, **ainda não há custo médio ponderado recalculado nas entradas**. Em produção, ajustes, estornos e mudanças de totalizador devem passar por um fluxo transacional de autorização; este protótipo tem apenas parte das restrições. A conferência de fechamento aceita *volume medido no período*, não a leitura acumulada bruta. A integração física com a bomba não existe nesta etapa.

## Começar

Requisitos: Node.js 20.19+ ou 22.12+.

```bash
npm install
npm run dev
```

Abra a URL exibida pelo terminal (normalmente http://localhost:5173).

Para gerar a versão estática:

```bash
npm run build
```

A pasta `dist` poderá ser hospedada como SPA estática em Cloudflare Workers Static Assets / Pages ou Vercel. **Publicar este protótipo publicamente não o torna seguro para dados reais.**

## GitHub

1. Crie um repositório **privado** chamado `inbrac-frota`.
2. Descompacte todos os arquivos na raiz do repositório (sem a pasta ZIP extra).
3. Faça o primeiro commit e push para `main`.
4. Instale as dependências e rode `npm run dev` para revisar a interface.

```bash
git init
git add .
git commit -m "feat: prototipo inicial INBRAC Frota"
git branch -M main
git remote add origin URL_DO_REPOSITORIO.git
git push -u origin main
```

## Arquitetura prevista para a V1.0 de produção

- React + Vite + TypeScript (migração de JSX para TSX) para frontend.
- Firebase Authentication com perfis e permissões no backend.
- Firestore com transações atômicas para saldo de tanque, totalizador e abastecimentos.
- Firebase Cloud Functions (Admin SDK) para regras financeiras, estornos, autorização e idempotência.
- Cloudflare para hospedagem do frontend e Cloudflare R2 para arquivos.
- Logs, backups, índices, políticas de retenção, testes de concorrência e relatórios consolidados.

O deploy e o esquema Firebase **não estão integrados** neste protótipo. Não incluir segredos em código cliente.

## Testes funcionais manuais recomendados

1. Criar veículo e verificar placa laranja no card.
2. Registrar entrada de 100 L e conferir aumento do desenho e do saldo do tanque.
3. Registrar abastecimento interno de 50 L e conferir queda do saldo e criação do movimento.
4. Registrar abastecimento externo e confirmar que o tanque não diminuiu.
5. Abrir Fechamentos e concluir conferência documental.
6. Configurar modo totalizador, informar leitura atual coerente com volume e conferir histórico.
7. Exportar CSV de abastecimentos e relatórios.
8. Restaurar dados de exemplo em Administração.

## Escopo de entrega

Protótipo de interface e fluxo local. Não confundir com aceitação final do controle real do estoque da INBRAC.
