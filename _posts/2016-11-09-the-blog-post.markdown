---
layout: post
comments: true
title:  "Mina reflektioner"
date:   2016-11-09 11:32:31 +0000
categories: jekyll update
---
Nu är det dags att reflektera över vad jag har gjort.

<h4>Sass</h4>

Jag tyckte till en början att Sass var krångligt, eftersom att jag är mer van vid att skriva vanlig CSS utan variabler, mixins och beräkningar. Att dessutom dela upp CSS-dokumenten i flera mindre gjorde det svårt att hålla reda på i vilken av alla filer jag skulle lägga styling av ett visst element. Här fick jag bra hjälp genom att utgå från exemplet <a href="https://1dv022.github.io">`1dv022.github.io`</a>. Jag ser dock många fördelar med Sass jämfört med vanlig CSS, just för att man kan vara flera som jobbar med styling av en website samtidigt i olika dokument och alla kan använda sig av fördefinierade variabler som bakgrunds- och textfärg och färdiga mixins. Det är också bra att det, förhoppningsvis, blir mindre CSS att skriva. Så länge man döper sina stylesheets till något som sammanfattar innehållet på ett bra sätt, så löser man också problemet med att behöva leta fram och tillbaka i alla dokument.

Innan jag började använda Sass läste jag igenom <a href="https://sass-lang.com/guide">`sass-lang.com/guide`</a> för att se vad som var möjligt att göra. Därefter implementerade jag allt i guiden i mina scss-dokument. Jag använder mig alltså av variabler, nesting, partials som importeras in i main.scss, mixins för olika typer av devices och en mixin för gradient-bakgrunder, extend för att dela med mig av egenskaper och operators för att göra beräkningar.

Fördelar och nackdelar har jag nämnt innan, men för att sammanfatta fördelarna så är det att man slipper upprepningar och därmed förhoppningsvis behöver skriva mindre kod, man kan göra beräkningar på redan satta variabler och att det blir lättare att organisera sin kod i olika filer. För att sammanfatta nackdelarna är det att det kan bli svårare att debugga sin kod, Sass kräver mer verktyg och mer setup och det kan ta lång tid att bygga upp sin kod.

<h4>SSG</h4>

Den enda erfarenheten jag har av SSG är det lilla jag har lärt mig om Jekyll under examinationsuppgiften. Jag har läst igenom <a href="https://jekyllrb.com/docs/home/">`jekyllrb.com`</a>, vilket har varit till stor hjälp för att komma på hur jag skulle komma igång med uppgiften. Jag tycker att Jekyll verkar vara väldigt bra och användarvänligt, så länge man följer den guide som finns tror jag inte att det är så svårt att lära sig. Det enda jag känner mig lite osäker på just nu är hur `_site` mappen bara kan skapas av sig självt, utan att jag behöver göra något. Jag antar att det sker av sig självt eller på grund av något som följde med i den bundle vi installerade i början av uppgiften. Hur som helst var det väldigt skönt att den skötte hela pusslet med att sätta ihop min website, så att jag slapp göra det själv.

SSG är bra att använda i de projekt där man bara vill ha en statisk website att visa upp för en kund, för att ha en website som behöver klara av många anrop, om man oroar sig för säkerheten och när man bara har en enkel webbserver att tillgå.

<h4>robots.txt</h4>

Jag utgick från guiden på <a href="http://www.robotstxt.org/">`robotstxt.org`</a> när jag skulle lägga till en robots.txt för min website. robots.txt är en textfil med instruktioner till för de robotar som besöker en website. Utvecklaren specifierar om robotar är tillåtna att komma in på websiten eller inte och vad de får och inte får tillgång till när de besöker websiten. Många robotar ignorerar dock robots.txt och gör vad de vill ändå. Jag valde att tillåta Googles robotar att komma in på min website och att "förbjuda" övriga robotar tillträde. Jag har helt enkelt för dålig koll på vilka robotar man vill ha in på sin website och vilka man absolut inte vill ha in, därför valde jag att ta det säkra före det osäkra och bara tillåta Googles robotar tillträde. Trots "förbudet" för de andra robotarna tror jag att de struntar fullständigt i vad de får och inte får göra, så det spelar kanske ingen större roll att man satt upp ett förbud.

<h4>humans.txt</h4>

Jag utgick från guiden på <a href="http://humanstxt.org/">`humanstxt.org`</a> när jag skulle lägga till en humans.txt för min website. humans.txt är en textfil som innehåller information om skaparna bakom en website. Min humans.txt innehåller mitt namn, studentmail och location. Information om websiten så som adress, datum för senaste uppdateringen, vilket språk som används på sidan och vilka språk och verktyg jag använt mig av. Jag har även lagt till ett tack till John Häggerud för jekyll-boilerplate och ett tack till Johan Leitet för exemplet för hur en website i kursen kan se ut.

<h4>Kommentarer på blogginlägg</h4>

Jag valde att använda mig av Disqus som föreslogs i examinationsuppgiften och utgick från guiden på <a href="https://help.disqus.com/customer/portal/articles/472138-jekyll-installation-instructions">`Disqus`</a>. Jag började med att skapa ett Disqus-konto och lägga till <a href="https://professorpotatis.github.io">`min website`</a>. Därefter lade jag till variabeln comments: true i YAML Front Matter på de blogginlägg som skulle vara möjliga att kommentera. Sen kopierade jag in Universal Embed Code i min layout post.html inom de angivna taggarna `if page.comments endif`. I Universal Embed Code var jag tvungen att ange page-url, identifier och shortname. I page-urlen kunde jag använda mig av den fördefinierade variabeln i config.yml-filen page.url, identifiern lät jag vara en tom sträng, jag lade till page.title och satte shortname till det shortname jag fått från när jag först skapade ett Disqus-konto. I bloggen har jag satt på kommentarer för alla inlägg utom "Test utan kommentarer".

<h4>Open Graph</h4>

Open Graph är ett verktyg för att omvandla sina webbsidor till grafiska objekt för en snyggare presentation när ens website delas på sociala medier. I implementeringen av Open Graph utgick jag från guiden på <a href="http://ogp.me/">`ogp.me`</a>. Jag valde att endast implementera de obligatoriska egenskaperna title, type, url och image och lade dem i min includes head.html för att de ska finnas med på samtliga sidor på min website. I title använde jag mig av page.title, i type skrev jag website, i url använde jag page.url och på image valde jag att använda en bild på en potatis från wikimedia commons.
