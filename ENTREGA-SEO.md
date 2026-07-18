# Entrega — Landing Page Ateliê Sertão Profundo

Arquivo principal: `index.html` (HTML único, responsivo, pronto para publicação — sem dependência de build).
Todas as informações comerciais (preços, parcelamento, frete, trocas, contatos) foram verificadas em
https://atelie.sertaoprofundo.com em 18/07/2026.

---

## 1. Title tag e meta description

- **Title (54 caracteres):** `Camisetas Nordestinas Autorais | Ateliê Sertão Profundo`
- **Meta description (151 caracteres):** `Camisetas com estampas nordestinas autorais, inspiradas na arte, na música e na poesia do Sertão. Parcele em até 6x e receba em todo o Brasil.`

## 2. Hierarquia de títulos

- **H1 (único):** Camisetas autorais que vestem as histórias do Sertão
- **H2:** Um Sertão que não se vê apenas. Um Sertão que se sente. · Coleções para cada canto do imaginário nordestino · Camisetas do Sertão para começar a viagem · Moda nordestina autoral, feita para durar na memória · Da imaginação do Sertão para o tecido · Histórias de quem já atravessou para o Sertão Profundo · Presentes que carregam histórias · Tudo o que você precisa saber antes de vestir o Sertão · Qual história do Sertão você vai vestir?
- **H3:** nomes das coleções (5), nomes dos produtos (8), títulos dos benefícios (8), etapas do processo (4), títulos de colunas do rodapé.

## 3. Palavras-chave utilizadas (distribuição natural)

- **Principal:** camisetas com estampas nordestinas (H1 implícito + lead do hero + FAQ)
- **Secundárias presentes no texto:** camisetas nordestinas autorais (title), camisetas autorais (H1), roupas com temática nordestina (manifesto), camisetas do Sertão (H2 de produtos), estampas inspiradas no Nordeste (coleções), moda nordestina autoral (H2 de benefícios), camisetas de São João / forró (coleções e FAQ), presente nordestino criativo (seção presentes), vestuário autoral do Nordeste (sobretítulo do hero), loja em Campina Grande (manifesto, rodapé, FAQ, dados estruturados).

## 4. Imagens reais — IMPLEMENTADO em 18/07/2026

As fotos oficiais dos produtos foram baixadas da loja, otimizadas (WebP, 585×600 para cards e 800×820 para o hero, 12–61 KB cada) e salvas em `img/`. Hero sem lazy loading e com `fetchpriority="high"`; demais imagens com `loading="lazy"` e `width`/`height` definidos. Alt texts descritivos escritos a partir da conferência visual de cada estampa. A tabela abaixo fica como referência do plano original:

| Local | Imagem sugerida | Dimensão | Alt text sugerido |
|---|---|---|---|
| Hero | Foto de camiseta da marca em uso, estampa visível (ex.: Fé na Festa) | ~1200×1500 | Camiseta autoral com estampa inspirada nas festas do Sertão nordestino. |
| Manifesto | Close da estampa sobre o tecido | ~900×1000 | Detalhe de estampa autoral impressa em camiseta de algodão. |
| Coleção São João | Foto da peça mais vendida da coleção | 800×600 | Camiseta da coleção São João no Sertão com estampa de festa junina. |
| Coleção Música e Tradição | Foto de peça da coleção | 800×600 | Camiseta com estampa de sanfona e instrumentos de forró. |
| Coleção Cactos e Poesia | Foto de peça da coleção | 800×600 | Camiseta com estampa de mandacaru florido. |
| Coleção Arte e Misticismo | Foto de peça da coleção | 800×600 | Camiseta com estampa inspirada nas crenças e visagens do Sertão. |
| Coleção Carnaval do Sertão | Foto de peça da coleção | 800×600 | Camiseta com estampa de carnaval de rua nordestino. |
| Produtos (8 cards) | Foto oficial de cada produto na loja | 600×600 | "Camiseta [nome da estampa], estampa autoral do Ateliê Sertão Profundo" — variando a descrição do desenho (ex.: "Camiseta O Voo do Carcará, com pássaro sobre o sol"). |
| Presentes | Peça adulto + infantil juntas, ou peça embalada | 800×700 | Camisetas adulto e infantil com estampas do Sertão, ideais para presente. |
| Prova social | Fotos de clientes **somente com autorização** | 400×400 | "[Nome], cliente, vestindo a camiseta [produto]." |
| OG image | Composição 1200×630 com peça + logotipo | 1200×630 | — (definida via meta tag) |

## 5. Dados estruturados incluídos (JSON-LD)

- `Organization` (endereço Campina Grande/PB, WhatsApp, Instagram)
- `WebSite` e `WebPage`
- `ItemList` com 8 `Product` reais (nome, categoria, URL e preço confirmados; **adicionar `image` quando as fotos forem definidas**)
- `FAQPage` com as 10 perguntas visíveis na página
- `BreadcrumbList` **não** foi incluído: a página é a porta de entrada, sem trilha de navegação — incluir apenas se a landing virar página interna.

## 6. Recomendações finais de SEO técnico

1. **Canonical/OG URL:** o arquivo usa `https://atelie.sertaoprofundo.com/` como placeholder. Ajustar para a URL definitiva da landing antes de publicar.
2. **Fontes:** a fonte Fraunces é carregada do Google Fonts com `display=swap`. Em produção, self-hostear os arquivos WOFF2 com `<link rel="preload" as="font">` elimina a dependência de terceiros e melhora o LCP.
3. **Minificação:** minificar HTML/CSS/JS no deploy (ex.: `html-minifier-terser`). O JS já é mínimo (~30 linhas) e roda no fim do body.
4. **Imagens:** ao inserir as fotos reais, gerar WebP/AVIF em 2 tamanhos (1x/2x) com `srcset` e comprimir com qualidade ~80.
5. **Sitemap e robots:** incluir a URL da landing no sitemap.xml do domínio e conferir o robots.txt.
6. **Google Search Console:** enviar a URL, validar os rich results (FAQ e Product) em search.google.com/test/rich-results.
7. **Core Web Vitals:** a página não tem bloqueio de renderização além da folha de fontes; medir no PageSpeed Insights após inserir as fotos (elas serão o novo LCP).
8. **Cache/CDN:** servir com compressão brotli/gzip e cache longo para assets.
9. **Link building local:** cadastrar a marca no Google Business Profile (Campina Grande) reforça a busca local "loja de camisetas em Campina Grande".

## 7. Informações que precisam ser confirmadas pelo responsável da marca

1. **URL definitiva da landing page** (para canonical, og:url e JSON-LD).
2. **Imagem social (og:image)** — hoje usa a foto real do produto Fé na Festa (800×820); recomenda-se criar uma arte dedicada em 1200×630 px para melhor recorte nas redes.
3. ~~Fotos oficiais~~ — concluído: fotos reais da loja implementadas em 18/07/2026 (hero, 5 coleções e 8 produtos). As seções "manifesto" e "presentes" mantêm ilustrações decorativas próprias; se desejarem, podem receber fotos de bastidores/close das estampas.
4. **Slug da coleção "Carnaval do Sertão"** — o menu do site aponta para `/collections/presentes-do-sertao`; confirmar se é esse mesmo o destino correto.
5. **E-mail de atendimento** — o site menciona suporte por e-mail, mas o endereço não está publicado; se houver, incluir no rodapé.
6. **CNPJ** — o site exibe "CNPJ 06089920460" (11 dígitos, formato de CPF). Confirmar o número correto antes de exibi-lo na landing; por isso foi omitido.
7. **Depoimentos de clientes** — a seção de prova social está estruturada e vazia por decisão de honestidade; preencher apenas com avaliações reais e autorizadas.
8. **Texto "Primeira troca sem custo"** — confirmado no site; confirmar se vale para qualquer motivo (tamanho/arrependimento) para eventualmente detalhar mais.
9. **Preços** — todos os produtos listados estavam a R$ 106,90 (R$ 103,70 no Pix, 6x de R$ 17,82) em 18/07/2026; revalidar antes de publicar e sempre que houver reajuste.
10. **Selo "produção sob demanda em 2 a 5 dias úteis"** — confirmado no FAQ da loja; manter sincronizado se o prazo mudar.
