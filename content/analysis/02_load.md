---
Title: 02_load.md
Description: Load time analysis
---

Analys av tre webbplatsers laddningstider.
=======================

Detta kursmoments analys handlar om att undersöka olika sidors laddningstider, vad variationer i tiderna kan ha för orsak samt hur eventuella problem med laddningstider kan hanteras.

Urval
-----------------------

Jag fortsätter med webbplatserna jag använde för förra kursmomentets färg-analys men fokuserar denna vecka på tre subpages för varje webbplats:
- [Colleen Darnell](https://www.colleendarnell.com)
    - [about](https://www.colleendarnell.com/about)
    - [media](https://www.colleendarnell.com/media)
    - [blog](https://www.colleendarnell.com/blog)


<picture>
<source media="(min-width: 668px)" srcset="%base_url%/image/colleen.png">
<source media="(min-width: 376px)" srcset="%base_url%/image/colleen.png?w=667">
<img src="%base_url%/image/colleen.png?w=375" alt="Screenshot of colleendarnell.com">
</picture>

- [Stephen Fry](https://www.stephenfry.com)
    - [podcasts](https://www.stephenfry.com/7deadlysins/)
    - [store](https://www.stephenfry.com/store)
    - [events](https://www.stephenfry.com/events)

<picture>
<source media="(min-width: 668px)" srcset="%base_url%/image/steve.png">
<source media="(min-width: 376px)" srcset="%base_url%/image/steve.png?w=667">
<img src="%base_url%/image/steve.png?w=375" alt="Screenshot of stephenfry.com">
</picture>

- [Arnold](https://schwarzenegger.com/)
    - [film](https://schwarzenegger.com/film)
    - [fitness](https://schwarzenegger.com/fitness)
    - [arnoldTv](https://schwarzenegger.com/arnoldtv)

<picture>
<source media="(min-width: 668px)" srcset="%base_url%/image/arnie.png">
<source media="(min-width: 376px)" srcset="%base_url%/image/arnie.png?w=667">
<img src="%base_url%/image/arnie.png?w=375" alt="Screenshot of schwarzenegger.com">
</picture>

Metod
-----------------------

För att mäta sidornas laddningstider använde jag verktyget [Page Speed Insights](https://pagespeed.web.dev/) som sätter betyg på sidor utifrån hur snabbt de laddas i webbläsaren, tillgänglighet, bästa metoder och sökmotoroptimering. Man skriver helt enkelt in adressen till sidan man vill ha mätdata för och får tillbaka en rapport som delvis bygger på insamlad data om webbplatsen över tid, dels på en simulering av hur sidan presterar i en standardiserad miljö. [*](#reference)

Även i denna analys är "inspect" användbart - under fliken "network" kan man utläsa siffror såsom hur mycket data som begärts och överförts och hur lång tid detta tagit. För jämförelsen använder jag ett medelvärde av tre direkt på varandra följande [mätningar](#reference).

Resultat
-----------------------

#### Betyg Page Speed Insights: colleendarnell.com

<div class="tables">
<table class="load">
    <tr>
        <th colspan="4">colleendarnell.com (mobil)</th>
    </tr>
    <tr>
        <th></th>
        <th>/about</th>
        <th>/media</th>
        <th>/blog</th>
    </tr>
    <tr>
        <td>Prestanda</td>
        <td style="background-color: red;">49</td>
        <td style="background-color: red;">28</td>
        <td style="background-color: orange;">52</td>
    </tr>
    <tr>
        <td>Tillgänglighet</td>
        <td style="background-color: limegreen;">100</td>
        <td style="background-color: limegreen;">96</td>
        <td style="background-color: limegreen;">100</td>
    </tr>
    <tr>
        <td>Bästa metoder</td>
        <td style="background-color: limegreen;">100</td>
        <td style="background-color: orange;">79</td>
        <td style="background-color: limegreen;">100</td>
    </tr>
    <tr>
        <td>SEO</td>
        <td style="background-color: limegreen;">100</td>
        <td style="background-color: limegreen;">100</td>
        <td style="background-color: limegreen;">92</td>
    </tr>
</table>
<table class="load">
    <tr>
        <th colspan="4">colleendarnell.com (dator)</th>
    </tr>
    <tr>
        <th></th>
        <th>/about</th>
        <th>/media</th>
        <th>/blog</th>
    </tr>
    <tr>
        <td>Prestanda</td>
        <td style="background-color: orange;">69</td>
        <td style="background-color: red;">48</td>
        <td style="background-color: orange;">55</td>
    </tr>
    <tr>
        <td>Tillgänglighet</td>
        <td style="background-color: limegreen;">100</td>
        <td style="background-color: limegreen;">96</td>
        <td style="background-color: limegreen;">100</td>
    </tr>
    <tr>
        <td>Bästa metoder</td>
        <td style="background-color: limegreen;">100</td>
        <td style="background-color: orange;">78</td>
        <td style="background-color: limegreen;">100</td>
    </tr>
    <tr>
        <td>SEO</td>
        <td style="background-color: limegreen;">100</td>
        <td style="background-color: limegreen;">100</td>
        <td style="background-color: limegreen;">92</td>
    </tr>
</table>
<table class="load">
    <tr>
        <th colspan="4">colleendarnell.com</th>
    </tr>
    <tr>
        <th></th>
        <th>/about</th>
        <th>/media</th>
        <th>/blog</th>
    </tr>
    <tr>
        <td>Inladdning medeltal (sekunder)</td>
        <td>1.98</td>
        <td>3.97</td>
        <td>2.48</td>
    </tr>
    <tr>
        <td>Resurser (antal)</td>
        <td>6</td>
        <td>59</td>
        <td>3</td>
    </tr>
    <tr>
        <td>Sidans storlek (MB)</td>
        <td>3</td>
        <td>3.8</td>
        <td>10.9</td>
    </tr>
</table>
</div>

Colleen Darnells sidor får bra betyg i både tillgänglighet och SEO över alla tre sidorna. Bästa metoder står sig hyfsat men på sidan /media drar framför allt inbäddade youtube-videos ner betyget. Prestandan är dålig för alla tre sidor med bottennoteringen 28 för mobilversionen av /media.

***

#### Betyg Page Speed Insights: stephenfry.com

<div class="tables">
<table class="load">
    <tr>
        <th colspan="4">stephenfry.com (mobil)</th>
    </tr>
    <tr>
        <th></th>
        <th>/podcasts</th>
        <th>/store</th>
        <th>/events</th>
    </tr>
    <tr>
        <td>Prestanda</td>
        <td style="background-color: red;">43</td>
        <td style="background-color: orange;">64</td>
        <td style="background-color: orange;">64</td>
    </tr>
    <tr>
        <td>Tillgänglighet</td>
        <td style="background-color: orange;">88</td>
        <td style="background-color: limegreen;">92</td>
        <td style="background-color: limegreen;">92</td>
    </tr>
    <tr>
        <td>Bästa metoder</td>
        <td style="background-color: limegreen;">93</td>
        <td style="background-color: orange;">71</td>
        <td style="background-color: limegreen;">93</td>
    </tr>
    <tr>
        <td>SEO</td>
        <td style="background-color: limegreen;">92</td>
        <td style="background-color: limegreen;">92</td>
        <td style="background-color: limegreen;">92</td>
    </tr>
</table>
<table class="load">
    <tr>
        <th colspan="4">stephenfry.com (dator)</th>
    </tr>
    <tr>
        <th></th>
        <th>/podcasts</th>
        <th>/store</th>
        <th>/events</th>
    </tr>
    <tr>
        <td>Prestanda</td>
        <td style="background-color: orange;">80</td>
        <td style="background-color: limegreen;">92</td>
        <td style="background-color: limegreen;">90</td>
    </tr>
    <tr>
        <td>Tillgänglighet</td>
        <td style="background-color: orange;">88</td>
        <td style="background-color: limegreen;">92</td>
        <td style="background-color: limegreen;">92</td>
    </tr>
    <tr>
        <td>Bästa metoder</td>
        <td style="background-color: limegreen;">96</td>
        <td style="background-color: orange;">74</td>
        <td style="background-color: limegreen;">96</td>
    </tr>
    <tr>
        <td>SEO</td>
        <td style="background-color: limegreen;">92</td>
        <td style="background-color: limegreen;">92</td>
        <td style="background-color: limegreen;">92</td>
    </tr>
</table>
<table class="load">
    <tr>
        <th colspan="4">stephenfry.com</th>
    </tr>
    <tr>
        <th></th>
        <th>/podcasts</th>
        <th>/store</th>
        <th>/events</th>
    </tr>
    <tr>
        <td>Inladdning medeltal (sekunder)</td>
        <td>1.58</td>
        <td>1.23</td>
        <td>1.03</td>
    </tr>
    <tr>
        <td>Resurser (antal)</td>
        <td>3</td>
        <td>2</td>
        <td>2</td>
    </tr>
    <tr>
        <td>Sidans storlek (MB)</td>
        <td>2.3</td>
        <td>1.9</td>
        <td>2.2</td>
    </tr>
</table>
</div>

Det som mest verkar sakta ned sidorna på Stephen Fry's sidor är hans egna annonser och tredjepartskod, på sidan med podcasts är det framför allt script från Acast som ska läsas in och tar mycket tid. Även här föreslår PSI förbättringar i form av effektivare bildhantering och -format.

***

#### Betyg Page Speed Insights: schwarzenegger.com

<div class="tables">
<table class="load">
    <tr>
        <th colspan="4">schwarzenegger.com (mobil)</th>
    </tr>
    <tr>
        <th></th>
        <th>/film</th>
        <th>/fitness</th>
        <th>/arnoldTv</th>
    </tr>
    <tr>
        <td>Prestanda</td>
        <td style="background-color: red;">40</td>
        <td style="background-color: red;">47</td>
        <td style="background-color: orange;">61</td>
    </tr>
    <tr>
        <td>Tillgänglighet</td>
        <td style="background-color: orange;">64</td>
        <td style="background-color: orange;">63</td>
        <td style="background-color: orange;">54</td>
    </tr>
    <tr>
        <td>Bästa metoder</td>
        <td style="background-color: orange;">50</td>
        <td style="background-color: orange;">54</td>
        <td style="background-color: orange;">50</td>
    </tr>
    <tr>
        <td>SEO</td>
        <td style="background-color: orange;">73</td>
        <td style="background-color: orange;">82</td>
        <td style="background-color: orange;">73</td>
    </tr>
</table>
<table class="load">
    <tr>
        <th colspan="4">schwarzenegger.com (dator)</th>
    </tr>
    <tr>
        <th></th>
        <th>/film</th>
        <th>/fitness</th>
        <th>/arnoldTv</th>
    </tr>
    <tr>
        <td>Prestanda</td>
        <td style="background-color: orange;">64</td>
        <td style="background-color: orange;">69</td>
        <td style="background-color: orange;">75</td>
    </tr>
    <tr>
        <td>Tillgänglighet</td>
        <td style="background-color: orange;">58</td>
        <td style="background-color: orange;">57</td>
        <td style="background-color: orange;">54</td>
    </tr>
    <tr>
        <td>Bästa metoder</td>
        <td style="background-color: orange;">52</td>
        <td style="background-color: orange;">56</td>
        <td style="background-color: orange;">52</td>
    </tr>
    <tr>
        <td>SEO</td>
        <td style="background-color: orange;">73</td>
        <td style="background-color: orange;">82</td>
        <td style="background-color: orange;">73</td>
    </tr>
</table>
<table class="load">
    <tr>
        <th colspan="4">schwarzenegger.com</th>
    </tr>
    <tr>
        <th></th>
        <th>/film</th>
        <th>/fitness</th>
        <th>/arnoldTv</th>
    </tr>
    <tr>
        <td>Inladdning medeltal (sekunder)</td>
        <td>4.74</td>
        <td>3.51</td>
        <td>3.59</td>
    </tr>
    <tr>
        <td>Resurser (antal)</td>
        <td>71</td>
        <td>62</td>
        <td>63</td>
    </tr>
    <tr>
        <td>Sidans storlek (MB)</td>
        <td>2.3</td>
        <td>1.6</td>
        <td>1.4</td>
    </tr>
</table>
</div>

Layoutförskjutningar drog ner betyget för Arnold, på både mobil- och datorversionerna av sidorna. Det varnades även för lång svarstid från servern, men det kanske var något tillfälligt - jag har inte undersökt saken närmare. Animationer tog mycket tid i anspråk, samt javascript och bildformat. Inte bara prestandan fick låga betyg, de andra bedömningskategorierna lyser orange, även de.

Analys
-----------------------

Med god hjälp av diagnostiken från Page Speed Insights blir min analys att Darnells dåliga prestanda mycket beror på resurserna, speciellt olika javascript-resurser som körs långsamt eller laddas in i onödan, men även bildstorlekar och -format som inte är optimala. När jag själv öppnar sidorna på dagorn märker jag inte av någon onormal fördröjning, möjligtvis känns det lite segt på telefonen. De fantastiska bilderna är en såpass viktig del av innehållet att jag skulle säga att eventuella förbättringsåtgärder kanske i första hand skulle fokusera på problemen med javascript för att undvika att prestandan förbättras på bekostnad av bildkvalitén, men kan det gå att lösa båda utan märkbar försämring är det såklart bra.

Även i fallet Stephen Fry kan tidsvinster göras genom att uppdatera bildformat och komprimera bilderna, men det som drar ner betyget mest ser ut att vara den inbäddade Acast-spelaren på podcast-sidan. Ett förslag från PSI är att låta sidan läsa in huvudinnehållet innan tredjepartskoden börjar laddas, vilket låter vettigt.

Att en person med Arnold Schwarzeneggers resurser och 
ställning har en webbplats som presterar så dåligt i PSI's bedömning är förvånande, för att inte säga förbluffande. Vid tillfället då jag besökte sidan var den märkbart långsam i inladdning, och på sidan /arnoldTv fungerade inte ens mediaspelaren - den laddade aldrig färdigt utan var bara en vit ruta oavsett omladdningar.

I en jämförelse mellan de tre vinner Stephen Fry i laddningstider, även den långsammaste av hans sidor laddar snabbare än Colleen Darnells snabbaste. Arnolds tider är flera sekunder sämre än de båda andras, i vissa fall utan att ens ladda in viktiga delar... Darnells sidor får dock högst betyg i tillgänglighet, vilket ju är sympatiskt. Hon får nog sägas tillhöra en annan generation än de andra två - en som kanske är mer medveten om tillgänglighetsperspektiv - och hennes publik/målgrupp är förmodligen också den yngre och med högre förväntningar på sådant. Men om det inte är förvånande att dinosaurien Schwarzenegger personligen inte har den förståelsen är det ändå anmärkningsvärt att hans webbplats inte har bättre tillgänglighet, då han jämförelsevis har absolut mest resurser och störst räckvidd.

För att sammanfatta - av de tre webbplatserna är det Arnolds som sticker ut. De andra två får även de anmärkningar hos PSI men för en användare som jag som använder en hyfsad dator och uppkoppling är det inte något som är anmärkningsvärt segt eller konstigt. På schwarzenegger.com märks det däremot. Men vem vet - kanske är det ett medvetet drag. Växte man upp med hans filmer växte man ju även upp med ett helt annat internet än dagens, med laddtider som skulle framkalla panikattacker och existentiella kriser hos dagens ungdom. Nostalgi i all ära - även om jag själv tillhör dem som ser om Terminator-filmerna sisådär vartannat år eller så tvivlar jag på att någon som känner igen netscape-loggan eller minns ljudet när man "ringde upp" internet saknar just de delarna av barndomen...
<figure>
<img src="%base_url%/image/netscape.png?w=150" alt="Netscape logo">
<figcaption>Tänk ändå - att bokstaven N kan framkalla så många känslor.</figcaption>
</figure>

Referenser
-----------------------

<a id="reference">
[PSI docs](https://developers.google.com/speed/docs/insights/v5/about)
</a>

<div class="tables">
<table class="load">
<tr>
    <td>
        colleendarnell.com/about
    </td>
</tr>
<tr>
    <td>
        Inladdningstider:
    </td>
</tr>
<tr>
    <td>
        2.10
    </td>
</tr>
<tr>
    <td>
        1.93
    </td>
</tr>
<tr>
    <td>
        1.92
    </td>
</tr>
<tr>
    <td>
        Medelvärde:
    </td>
</tr>
<tr>
    <td>
        1.98
    </td>
</tr>
</table>
<table class="load">
<tr>
    <td>
        colleendarnell.com/media
    </td>
</tr>
<tr>
    <td>
        Inladdningstider:
    </td>
</tr>
<tr>
    <td>
        4.22
    </td>
</tr>
<tr>
    <td>
        4
    </td>
</tr>
<tr>
    <td>
        3.69
    </td>
</tr>
<tr>
    <td>
        Medelvärde:
    </td>
</tr>
<tr>
    <td>
        3.97
    </td>
</tr>
</table>
<table class="load">
<tr>
    <td>
        colleendarnell.com/blog
    </td>
</tr>
<tr>
    <td>
        Inladdningstider:
    </td>
</tr>
<tr>
    <td>
        2.10
    </td>
</tr>
<tr>
    <td>
        2.23
    </td>
</tr>
<tr>
    <td>
        3.10
    </td>
</tr>
<tr>
    <td>
        Medelvärde:
    </td>
</tr>
<tr>
    <td>
        2.48
    </td>
</tr>
</table>
</div>
<div class="tables">
<table class="load">
<tr>
    <td>
        stephenfry.com/podcasts
    </td>
</tr>
<tr>
    <td>
        Inladdningstider:
    </td>
</tr>
<tr>
    <td>
        1.84
    </td>
</tr>
<tr>
    <td>
        1.55
    </td>
</tr>
<tr>
    <td>
        1.35
    </td>
</tr>
<tr>
    <td>
        Medelvärde:
    </td>
</tr>
<tr>
    <td>
        1.58
    </td>
</tr>
</table>
<table class="load">
<tr>
    <td>
        stephenfry.com/store
    </td>
</tr>
<tr>
    <td>
        Inladdningstider:
    </td>
</tr>
<tr>
    <td>
        1.29
    </td>
</tr>
<tr>
    <td>
        1.17
    </td>
</tr>
<tr>
    <td>
        1.24
    </td>
</tr>
<tr>
    <td>
        Medelvärde:
    </td>
</tr>
<tr>
    <td>
        1.23
    </td>
</tr>
</table>
<table class="load">
<tr>
    <td>
        stephenfry.com/events
    </td>
</tr>
<tr>
    <td>
        Inladdningstider:
    </td>
</tr>
<tr>
    <td>
        0.94
    </td>
</tr>
<tr>
    <td>
        1.20
    </td>
</tr>
<tr>
    <td>
        0.94
    </td>
</tr>
<tr>
    <td>
        Medelvärde:
    </td>
</tr>
<tr>
    <td>
        1.03
    </td>
</tr>
</table>
</div>
<div class="tables">
<table class="load">
<tr>
    <td>
        schwarzenegger.com/film
    </td>
</tr>
<tr>
    <td>
        Inladdningstider:
    </td>
</tr>
<tr>
    <td>
        4.09
    </td>
</tr>
<tr>
    <td>
        4.33
    </td>
</tr>
<tr>
    <td>
        5.79
    </td>
</tr>
<tr>
    <td>
        Medelvärde:
    </td>
</tr>
<tr>
    <td>
        4.74
    </td>
</tr>
</table>
<table class="load">
<tr>
    <td>
        schwarzenegger.com/fitness
    </td>
</tr>
<tr>
    <td>
        Inladdningstider:
    </td>
</tr>
<tr>
    <td>
        3.48
    </td>
</tr>
<tr>
    <td>
        3.34
    </td>
</tr>
<tr>
    <td>
        3.70
    </td>
</tr>
<tr>
    <td>
        Medelvärde:
    </td>
</tr>
<tr>
    <td>
        3.51
    </td>
</tr>
</table>
<table class="load">
<tr>
    <td>
        schwarzenegger.com/arnoldTv
    </td>
</tr>
<tr>
    <td>
        Inladdningstider:
    </td>
</tr>
<tr>
    <td>
        2.37
    </td>
</tr>
<tr>
    <td>
        5.34
    </td>
</tr>
<tr>
    <td>
        3.04
    </td>
</tr>
<tr>
    <td>
        Medelvärde:
    </td>
</tr>
<tr>
    <td>
        3.59
    </td>
</tr>
</table>
</div>

Övrigt
-----------------------

Rapport författad och sammanställd av Emma Widengård