---
layout: post
title: Koch-kurvor och ett verktyg jag programmerade förra sommaren 
comments: true
---
von Kochs kurva är en kontinuerlig kurva som saknar tangent i alla punkter. Den beskrevs av någon gammal svensk gubbe (Helge von Koch för den intresserade läsaren) i början på 1900-talet, kul! Här berättar jag lite mer om kurvan och en liten webapp som jag har gjort för att rita kurvor.
![kurva](/images/koch.png)


Själva kurvan kan konstrueras genom att börja med den första kurvan i figuren nedan:

![iterationer](/images/koch2.png)

Sedan ersätts varje rakt streck med en förminskad kopia roterad så att *basen*, alltså de två strecken, överlappar det ursprungliga strecket, gör man det får man något som ser ut som den andra kurvan i figuren ovan. Itereras denna process tillräckligt många gånger så får man till slut något som ser ut som sista kurvan i bilden ovan. Fun stuff!

Som du kanske förstår kan samma sak göras, men med andra kurvor för att uppnå andra resultat. Lämnar som uppgift till läsaren att fundera på hur den första bilden i bloggposten är konstruerad.

## Webbappen
Länk till webbappen: [isakalmq.se/koch-js](https://isakalmq.se/koch-js/)

Iallafall, förra sommaren hade jag ett riktigt knegarjobb där jag klippte gräs och sånt och kände att jag behövde lite mental stimulans. Vad är då bättre än ett litet programmeringsprojekt? Det jag gjorde var en liten webbapp som låter användaren iterativt rita koch-kurvor och andra liknande kurvor direkt i webbläsaren. 

Kort fattat trycker man på knappen **Iterate!** för att iterera, **Reset** för att återställa, **+** och **-** för att zooma (går även att göra med scrollhjulet eller med fingertopparna på mobiler) och klickar och drar för att förflytta kurvan. Vill man använda någon annan kurva som ursprungskurva eller ersättningskurva väljer man det i drop-down-menyerna.

## Schyssta bilder

![screenshot](/images/koch3.png)

![screenshot](/images/koch4.png)

![screenshot](/images/koch5.png)