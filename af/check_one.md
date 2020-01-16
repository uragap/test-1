---
$title: Skep u AMP HTML-bladsy
$order: '1'
description: G
author: pbakaus
contributors:
- bpaduch
---

Die volgende opmerking is 'n ordentlike beginpunt of ketelplaat. Kopieer dit en stoor dit in 'n lêer met 'n HTML-uitbreiding.

[sourcecode: html] <! docttype html>

<meta charset="utf-8">     #cdata-section>#cdata-section>#cdata-section><script async="" src="https://cdn.ampproject.org/v0.js"><#cdata-section> </div></script>

Die inhoud van die liggaam is tot dusver redelik eenvoudig. Maar daar is heelwat bykomende kodes in die kop van die bladsy wat miskien nie onmiddellik voor die hand liggend is nie. Kom ons dekonstrueer die vereiste winsopslag.

Gebruik HTTPS: Wanneer u AMP-bladsye en -inhoud skep, moet u dit sterk oorweeg om die HTTPS-protokol (vs. HTTP) te gebruik. Alhoewel HTTPS nie nodig is vir die AMP-dokument self of vir beelde en lettertipes nie, is daar baie AMP-funksies wat HTTPS benodig (bv. Video, iframes, en meer). Gebruik die HTTPS-protokol om te verseker dat u AMP-bladsye die volle voordeel trek uit alle AMP-funksies. U kan meer leer oor HTTPS in ["Waarom HTTPS-aangeleenthede"](https://developers.google.com/web/fundamentals/security/encrypt-in-transit/why-https) .

[tip type = "tip"] Gebruik die [AMP Boilerplate Generator](/boilerplate) om vinnig aan die [gang](/boilerplate) te kom met die skep van nuwe AMP-bladsye. [/ Wenk]

## Vereiste opruiming

AMP HTML-dokumente MOET:

reël | beskrywing
--- | ---
Begin met die `<!doctype html>` doctype. | Standaard vir HTML.
Bevat 'n boonste vlak `<html ⚡>` <br> ( `<html amp>` word ook aanvaar). | Identifiseer die bladsy as AMP-inhoud.
Bevat `<head>` en `<body>` etikette. | Opsioneel in HTML, maar nie in AMP nie.
Bevat 'n `<meta charset="utf-8">` etiket as die eerste kind van hul `<head>` -etiket. | Identifiseer die kodering van die bladsy.
Bevat 'n `<script async src="https://cdn.ampproject.org/v0.js"></script>` -merk in hul `<head>` -etiket. As beste praktyk, moet u die skrif so vroeg as moontlik in die `<head>` . | Sluit en laai die AMP JS-biblioteek in.
Bevat 'n `<link rel="canonical" href="$SOME_URL">` etiket in hul `<head>` . | Wys op die gewone HTML-weergawe van die AMP HTML-dokument of op homself as daar nie so 'n HTML-weergawe bestaan nie. Lees meer in [Maak u bladsy ontdekbaar](../../../../documentation/guides-and-tutorials/optimize-measure/discovery.md) .
Bevat 'n `<meta name="viewport" content="width=device-width,minimum-scale=1">` etiket in hul `<head>` tag. Dit word ook aanbeveel om `initial-scale=1` . | Spesifiseer 'n responsiewe aansig. Kom meer te wete in [Skep responsiewe AMP-bladsye](../../../../documentation/guides-and-tutorials/develop/style_and_layout/responsive_design.md) .
Bevat die [AMP-ketelplaatkode](../../../../documentation/guides-and-tutorials/learn/spec/amp-boilerplate.md) in hul `<head>` -etiket. | CSS-ketelplaat om die inhoud aanvanklik te verberg totdat AMP JS gelaai is.

## Opsionele metadata

Behalwe vir die blote vereistes, bevat ons voorbeeld ook 'n definisie van Schema.org in die kop, wat nie 'n streng vereiste vir AMP is nie, maar dit is 'n vereiste dat u inhoud op sekere plekke versprei word (byvoorbeeld op Google Soek topverhale-karrousel).

[tip type = "read-on"] Besoek hierdie bronne om meer te wete te kom:

- [Aan die begin met AMP op Google Search](https://developers.google.com/amp/docs) - leer om jou AMP-bladsye voor te berei vir Google Search.
- [Metadata-monsters](https://github.com/ampproject/amphtml/tree/master/examples/metadata-examples) - kom meer te wete oor al die metadata wat u op verskillende plekke benodig (bv. Twitter). [/ Wenk]

<hr>

Goeie nuus! Dit is al wat ons nodig het om ons eerste AMP-bladsy te skep, maar daar gebeur natuurlik nog nie veel in die liggaam nie. In die volgende afdeling bespreek ons hoe om basiese beginsels soos prente, pasgemaakte AMP-elemente by te voeg, hoe om u bladsy te styl en 'n responsiewe uitleg uit te werk.
