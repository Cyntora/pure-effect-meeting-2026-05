# Regler för mötesunderlag, Pure Effect 2026-05-08

Reglerna nedan är en samling av allt som bestämdes i prompten. Sparas så att nästa deck för Pure Effect (eller liknande klient) kan följa samma standard.

## 1. Innehåll och fokus

- Decken bygger på den agenda kunden skickat. Sektionerna ska följa agendan i ordning, inte agenturens egen struktur.
- All data ska vara verifierbar. Källtagga per metric (GA4, Google Ads, GSC, etc.) på samma sätt som i workspace-guardrails.
- PMax-analysen som låg som kontext i prompten ska verifieras mot GA4 innan den används i decken. Avvikelser mellan plattformar nämns explicit.
- Decken ska kunna läsas i ett möte på 30 minuter. Varje sektion ska ge 1 till 3 huvudtagningar.

## 2. Ton

- Skriv som Filip skriver i Gmail och Slack: direkt, korta meningar, "ni"-form i offerter.
- Cyntoras egen offerttext är referens.
- INGA tankstreck (—). Använd komma, punkt eller "och" istället.
- INGA AI-marknadsförarklichéer. Förbjudna fraser inkluderar (men är inte begränsade till):
  - "lågt hängande frukter"
  - "B2B-guld"
  - "edge inte svaghet"
  - "snabba vinster och långsiktig pipeline"
  - "italiensk kvalitet möter svensk ambition"
  - "vi bryr oss med hjärna och med hjärta"
- INGA fauxpoetiska rubriker med italics-emfas. Rubriker beskriver vad sektionen handlar om, punkt.
- Inga triadiska konstruktioner ("X, Y och Z") som används bara för retorisk effekt. Listor är OK om de är riktiga listor.

## 3. Design

- Single-file HTML med inbäddad CSS. Ingen build-process, ingen JS-bundling.
- Matcha kundens brand. Hämta färger, känsla och typografi-feel från kundens hemsida innan du börjar bygga.
- Cyntoras logotyp (SVG) ska finnas både i nav och i hero. Hämta SVG från cyntora.se och använd inline.
- Cormorant Garamond för rubriker, Inter för brödtext. Premium-känsla, lugn färgsättning.
- Scroll-deck. Varje sektion har min-height 100vh och fyller sin egen vy. Naturlig scroll, ingen forced snap.
- Pure Effects palett (cream/sage/warm peach) plus Cyntoras ink (#1B1B1F) som typografi.

## 4. Publicering

- Publik GitHub-repo via gh CLI. Ligger under Cyntoras organisation.
- index.html i root. README.md med kort beskrivning.
- GitHub Pages aktiveras på main branch / root.
- `<meta name="robots" content="noindex, nofollow">` ska finnas i head så Google inte indexerar prisuppgifter eller intern strategi.
- URL returneras till Filip när den är live.

## 5. Leverans

Per möte ska följande lämnas över:

- HTML-fil lokalt i `clients/<slug>/meetings/<datum>/index.html`
- 16:9 PDF (1600 × 900) som backup, samma mapp
- Live URL på github.io
- Förslag på kort mejl till kunden med länken
- RULES.md (den här filen) i samma mapp som index.html
- Repository under cyntora-org

## 6. Hård regel: read-only mot ad accounts

Vi pausar inte kampanjer eller ändrar budgetar i deckens egen process. Decken är ett mötesunderlag. Faktiska kontoändringar kräver explicit OK från kunden i mötet.

## 7. Verifiering innan publicering

Innan decken publiceras till github.io:

- Stickprov på alla siffror mot källa (GA4, Ads, GSC) — minst 5 random siffror i decken ska kunna återskapas direkt från MCP-pull.
- Sökläsning för förbjudna ord och tankstreck.
- Manuell open-i-browser för att se att scroll-deck fungerar och att inget bryter på 1280px och 1600x900.
