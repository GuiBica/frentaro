# frentaro

Plataforma de arrendamento residencial em Portugal — ligando proprietários e inquilinos de forma directa, sem intermediários e sem comissões.

🌐 **Live:** [frentaro.vercel.app](https://frentaro.vercel.app) <!-- substituir pelo URL real -->

-----

## Sobre o projecto

A frentaro é uma single-page application construída num único ficheiro HTML, com Supabase como backend e deploy automático via Vercel. O objectivo é oferecer uma experiência simples e transparente para quem quer arrendar ou encontrar casa em Portugal.

-----

## Stack

|Camada        |Tecnologia                                                   |
|--------------|-------------------------------------------------------------|
|Frontend      |HTML + CSS + JavaScript (vanilla)                            |
|Base de dados |[Supabase](https://supabase.com) (PostgreSQL)                |
|Autenticação  |Supabase Auth                                                |
|Storage       |Supabase Storage (fotos de imóveis e avatares)               |
|Mapas         |[Leaflet.js](https://leafletjs.com) + OpenStreetMap / CartoDB|
|Geocodificação|[Nominatim](https://nominatim.openstreetmap.org)             |
|Icons         |[Tabler Icons](https://tabler-icons.io)                      |
|Deploy        |[Vercel](https://vercel.com)                                 |

-----

## Funcionalidades

**Para proprietários**

- Publicação de imóveis com fotos, localização automática por geocodificação e todas as características relevantes
- Dashboard com métricas por anúncio (visualizações, favoritos, mensagens)
- Edição e remoção de anúncios
- Sistema de mensagens com inquilinos

**Para arrendatários**

- Pesquisa e filtragem por cidade, tipo, preço, área e características
- Ordenação por mais recentes, preço e área
- Vista em lista ou mapa inline
- Sistema de favoritos
- Mensagens directas ao proprietário

**Geral**

- Autenticação com email/password
- Perfil de utilizador com foto
- Páginas institucionais (Sobre nós, Como funciona)
- Links partilháveis por anúncio via hash URL
- Design responsivo

-----

## Estrutura do projecto

```
frentaro/
└── index.html    # Toda a aplicação num único ficheiro
```

A arquitectura single-file foi uma escolha deliberada para simplicidade de deploy e manutenção nesta fase inicial.

-----

## Base de dados (Supabase)

As principais tabelas são:

```
profiles         — dados de utilizador (role, nome, avatar, contacto)
listings         — anúncios de imóveis
messages         — mensagens entre proprietários e inquilinos
favourites       — imóveis guardados por arrendatários
listing_views    — registo de visualizações por anúncio
```

O storage utiliza dois buckets: `listing-images` e `avatars`.

-----

## Deploy

O projecto faz deploy automático via Vercel a cada push para `main`.

```bash
# Clonar
git clone https://github.com/[guibica]/frentaro.git
cd frentaro

# Não há dependências — abrir directamente no browser
open index.html
```

Para configurar o teu próprio Supabase, substitui as variáveis no topo do `index.html`:

```js
var SB_URL  = "https://[teu-projecto].supabase.co";
var SB_ANON = "[tua-anon-key]";
```

-----

## Roadmap

- [ ] Notificações por email (novas mensagens)
- [ ] Verificação de identidade de proprietários
- [ ] Filtro por raio geográfico no mapa
- [ ] Página de anúncio com URL própria (SEO)
- [ ] Upload de documentos (certificado energético, etc.)
- [ ] Avaliações mútuas após contrato

-----

## Licença

MIT
