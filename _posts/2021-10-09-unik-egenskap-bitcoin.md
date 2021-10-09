---
layout: post
title: En unik egenskap hos Bitcoin (och andra PoW kryptovalutor)
comments: true
---
<script src="https://www.desmos.com/api/v1.6/calculator.js?apiKey=dcb31709b452b1cf9dc26972add0fda6"></script>

Bitcoin är en digital produkt med många unika egenskaper, här tänkte jag berätta lite mer om en unik egenskap som jag inte ser diskuteras särksilt mycket.
![Bitcoinlogga](https://bitcoin.org/img/home/bitcoin-img.svg)


# Fasta och rörliga kostnader
När man pratar om produktion av produkter eller tjänster brukar man prata om olika kostnadsslag. Ett exempel på detta är fasta och rörliga kostnader. Fasta kostnader är kostnader som alltid finns oberoende av produktionsvolym. Rörliga kostnader är kostnader som beror på produktionsvolym. En stoltillverkare kan ha fasta kostnader i form av lokalhyra, ritnings-ritande och inköp av verktyg. Samma stoltillverkares rörliga kostnader kan bestå av material, arbetstimmar och underhåll av verktyg. 

## Fasta kostnader
Lokalhyra, ritnings-ritande och inköp av verktyg är fasta kostnader eftersom en ritning kostar lika mycket att göra oavsett om man tillverkar en eller 100 stolar, lokalhyran är densamma oavsett om man tillverkar en eller 100 stolar och verktygen kostar lika mycket oavsett om man tillverkar en eller 100 stolar. Du fattar poängen. (Som en avstickare kan det sägas att detta är lite sanning med modifikation, tillverkas det 1000 stolar kanske snickaren behöver en större lokal och/eller bättre verktyg. Dessa kostnader är halv-fasta)

## Rörliga kostnader
Material, arbetstimmar och underhåll kostar väldigt olika beroende på hur många stolar som tillverkas. Materialet till en stol är självklart billigare än materialet till 100 stolar. Arbetskostnaden för en stol är också självklart billigare än arbetskostnaden för 100 stolar. Du fattar poängen här med. 

## Marginalkostnad
Ett till begrepp är marginalkostnad. Det brukar beskrivas som kostnaden för att tillverka en till enhet. Om det kostar stoltillverkaren 10 000 kr att tillverka 100 stolar och det kostar 10 005 kr att tillverka 101 stolar är marginalkostnaden 5 kr. Vi kan alltså anta att det kostar 10 010 att tillverka 102 stolar, 10 015 att tillverka 103 och så vidare.

## Sammanfattning
Detta kan grovt sammanfattas som en formel:
![ekvation](https://latex.codecogs.com/svg.latex?x%3D%5Cfrac%7B-b%5Cpm%5Csqrt%7Bb%5E2-4ac%7D%7D%7B2a%7D)

Allt detta är såklart en grov förenkling av verkligheten, fasta kostnader är aldrig helt fasta och det tar inte heller hänsyn till vissa skalfördelar så som mängdrabatter för material. Verkligheten är komplicerad, den här modellen är inte det alltså beskriver den inte verkligheten perfekt heller. 

I grafen nedan presenteras en grafisk representation av allt detta. Y-värdet är kostnaden och x-värdet är producerad mängd. f (fixed costs, fasta) och v (variable costs, rörliga) kan ändras med hjälp av sliders.

De ursprungliga inställningarna, f = 40 och v = 4, skulle betyda vi har 40 kr i fasta kostnader och 4 kr/enhet i rörliga kostnader. Produceras det fem enheter kan vi utläsa att kostnaden blir 60 kr i grafen.  
<div id="calculator-physical" style="width: 600px; height: 400px;"></div>
<script>
  var elt = document.getElementById('calculator-physical');
  var calculator = Desmos.GraphingCalculator(elt);
  calculator.setExpression({ id: 'fk', latex: 'f=40' });
  calculator.setExpression({ id: 'rk', latex: 'v=4' });
  calculator.setExpression({ id: 'fk', sliderBounds: { min: 0, max:100, step:10 }});
  calculator.setExpression({ id: 'rk', sliderBounds: { min: 0, max:10, step:1 }});
  calculator.setExpression({ id: 'graph1', latex: 'y= f + vx' });
  calculator.setMathBounds({
      left: -2,
      right: 10,
      bottom: -10,
      top: 150
  })
</script>

# Digitala produkter
Som du kanske kan gissa har digitala produkter och fysiska produkter väldigt olika kostnadsstruktur. Fysiska produkter har ofta väldigt varierande fasta och rörliga kostnader. Dock är de rörliga kostnaderna nästan alltid en stor del av totalkostnaden. Detta beror på att de kräver material, arbetstimmar och maskintimmar för tillverkning av varje enhet. Att producera två stolar kräver dubbelt så mycket material som att producera en. 

Digitala produkter har dock en helt annan kostnadsstruktur. Digitala produkter är näst intill gratis att kopiera. Detta gör att de rörliga kostnaderna för digitala produker är väldigt låga, eller näst intill försumbara. Marginalkostnaden blir låg. Det är alltså väldigt liten skillnad på att producera 1000 enheter och att producera 1001 enheter. Tänk själv om du hade en textfil och du vill skapa 1000 kopior av den, inte ett så särskilt stort arbete. Jämför sedan detta med att skapa 1000 kopior av en stol så ser man tydligt att marginalkostnaden för digitala produkter är låg. De är billiga att kopiera, sälja, distribuera och lagra. 

De fasta kostnaderna för digitala produkter är därför en stor del av kostnaderna. Ta ett spel som exempel, att planera, designa, programmera och marknadsföra kostar massvis med pengar. Men att sedan sälja spelet är nära på gratis i jämförelse. Det som krävs är i grund och botten ett sätt att ta emot betalning från kunden och ett sätt att föra över data till kunden, två saker som är relativt billiga i nuläget. 

Detta ger oss den viktiga skillnaden:

|                   | Digitala produkter | Fysiska produkter | 
| ----------------- | ------------------ | ----------------- |
| Rörliga kostnader | Billiga/försumbara | Dyrt              |
| Fasta kostnader   | Dyrt               | Dyrt              |

I grafen illustreras det ett exempel på hur kostnadsstrukturen för en digital produkt kan se ut. Notera att det kostar nästan lika mycket att producera en enhet som det kostar att producera 10.
<div id="calculator-digital" style="width: 600px; height: 400px;"></div>
<script>
  var elt = document.getElementById('calculator-digital');
  var calculator = Desmos.GraphingCalculator(elt);
  calculator.setExpression({ id: 'fk', latex: 'f=40' });
  calculator.setExpression({ id: 'rk', latex: 'v=0.3' });
  calculator.setExpression({ id: 'fk', sliderBounds: { min: 0, max:100, step:10 }});
  calculator.setExpression({ id: 'rk', sliderBounds: { min: 0, max:10, step:0.1 }});
  calculator.setExpression({ id: 'graph1', latex: 'y= f + vx' });
  calculator.setMathBounds({
      left: -2,
      right: 10,
      bottom: -10,
      top: 150
  })
</script>

# Bitcoin som digital produkt
Nu kanske du undrar vad Bitcoin (eller valfri kryptovaluta) har att göra med det här. Bitcoin skapas, väldigt kortfattat och förenklat, genom att användare löser pussel med hjälp av sin datorkraft. Lyckas du lösa pusslet belönas du med ett bestämt antal bitcoins. Detta fyller ett syfte som jag inte kommer att disktuera nu, det viktiga är att det krävs datorkraft för skapandet av Bitcoins. Det krävs ganska stora mängder elektricitet för att köra den kraftfulla hårdvaran som krävs för att lösa dessa pussel och sedan skapa Bitcoins. Skapandet av Bitcoins får därför en kostnadsstruktur som mer liknar traditionella fysiska produkter, med en stor marginalkostnad. Det kostar en del att köpa in hårdvaran och det kostar en del att ha en plats att köra den på. Detta blir fasta kostnader för skapandet av Bitcoins. Till det kommer en betydande summa elkostander som kan ses som rörliga kostnader för brytandet. Det finns alltså en betydande skillnad i pris att bryta 1000 bitcoins och 1001 bitcoins. Detta gör Bitcoin till en unik digital produkt ur det avseendet.