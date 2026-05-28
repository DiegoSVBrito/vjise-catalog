# Guia de Gastronomia — V JISE 2026 (UNEMAT / Câmpus de Cáceres)

Página web estática, mobile-first e trilíngue (PT / EN / ES) com os pontos de
alimentação do evento. Cada estabelecimento tem um botão **"Como chegar"** que
abre o Google Maps traçando a rota a pé **a partir da localização atual** de
quem abriu o link — sem API key, sem backend, sem custo.

Inclui também uma aba **"QR Codes para imprimir"** que gera, no próprio
navegador, um QR mestre (abre o guia) + um QR por estabelecimento (rota direta).

## Publicar no GitHub Pages

1. Crie um repositório público (ex.: `vjise-guia`) e suba estes arquivos
   (`index.html`, `404.html`, `README.md`).
2. Vá em **Settings › Pages**.
3. Em *Source*, escolha **Deploy from a branch** → `main` → `/ (root)` → **Save**.
4. Em ~1 min o site fica no ar em:
   `https://SEU-USUARIO.github.io/vjise-guia/`

> Para servir na raiz da conta (`https://SEU-USUARIO.github.io/`), nomeie o
> repositório exatamente como `SEU-USUARIO.github.io`.

Toda atualização (novo commit ou upload) republica o site automaticamente.

## Depois de publicar

Abra a URL pública no celular → **"QR Codes para imprimir"**. O QR mestre se
gera lendo o endereço real da página, então já aponta para o link definitivo.
Imprima ou salve em PDF e distribua nos crachás e pontos de apoio.

## Como manter / editar

- **Estabelecimentos:** edite a lista `PLACES` no `index.html`. Cada item tem
  `name`, `lat`, `lng`, `pid` (Google Place ID), `area`, `rating`, `phone`,
  `hours` (Seg→Dom) e `desc` (pt/en/es). Para adicionar um lugar, copie um bloco
  existente e troque os dados.
- **Coordenadas / Place ID:** abra o local no Google Maps, copie a URL; o Place
  ID também pode ser obtido em https://developers.google.com/maps/documentation/places/web-service/place-id
- **Modo de rota:** está fixo em `travelmode=walking` na função `dirUrl()`.
  Troque por `driving`, `transit` ou `bicycling` se preferir.
- **Idiomas:** os textos de interface ficam no objeto `T` (pt/en/es).
- **Logo oficial UNEMAT:** salve o PNG branco ao lado do `index.html` (ex.:
  `unemat-branco.png`), ajuste o `src` da tag `<img id="ulogo">` e remova o
  `display:none` da classe `.ulogo` no CSS.

## Identidade visual

Cores institucionais da UNEMAT (bandeira de Mato Grosso):
azul `#003b5c` (Pantone 2955 C), verde `#1c4c0d` (Pantone 349 C),
amarelo `#ffcb05` (Pantone 116 C), preto `#231f20`.
