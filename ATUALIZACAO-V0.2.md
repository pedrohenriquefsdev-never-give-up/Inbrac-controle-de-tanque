# INBRAC FROTA — V0.2 (Demonstração)

## Atualizações visuais
- Logotipo obtido da imagem original INBRAC enviada, com recorte para fundo transparente.
- Placas personalizadas laranja menores e com tipografia e proporção mais contidas.
- Cards dos veículos, menus, tanque e indicadores com espaçamento e acabamento refinados.
- Layout responsivo e identidade preta, amarela e laranja.

## O que foi preservado
- Navegação e formulários existentes da V0.1.
- Dados exclusivamente demonstrativos em localStorage, usando a mesma chave da V0.1.
- Indicador gráfico do tanque e cálculo visual de estoque.

## Atualização do GitHub
1. Descompacte o ZIP.
2. Abra a pasta `inbrac-frota-v1` e envie o conteúdo (incluindo `public/inbrac-logo.png`) para a raiz do repositório GitHub.
3. Confirme que `src/main.jsx`, `src/style.css`, `package.json` e `public/inbrac-logo.png` foram atualizados.
4. Faça commit na branch `main`; acompanhe a nova implantação da Cloudflare.
5. Atualize a aplicação com Ctrl+F5 caso a tela antiga permaneça em cache.

## Segurança e limitações
**Não usar com dados reais.** Não há login real nem backend, e o localStorage é acessível no navegador. Para uma demonstração com cliente, prefira dados fictícios e faça uma cópia de segurança dos registros de teste relevantes.

## Validação
A instalação das dependências não terminou neste ambiente; portanto, a compilação da V0.2 não pôde ser confirmada localmente. É necessário conferir o resultado do build na Cloudflare após o commit.
