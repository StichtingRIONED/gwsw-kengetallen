# GWSW-Kengetallen

<style>
  .symbolSmall{width:20px;height:20px;margin-right:1em;vertical-align:middle}
  .symbol{width:30px;height:30px;margin-right:1em;vertical-align:middle}
</style>

<a id="werkgroep"></a>
De module GWSW-Kengetallen is ontwikkeld door Jordie Netten (Nelen & Schuurmans, thans Netten Wateradvies), in samenwerking met de werkgroep GWSW-Kengetallen, bestaande uit:
- Marco van Bijnen, Duopp 
- Wim de Blecourt, Waterschap Drents en Overijsselse Delta
- André Hammenga, Waterschap Hunze en Aa’s
- Marianne Kruger, Duopp 
- Mark Lamers, Hoogheemraadschap Hollands Noorderkwartier
- Johan Post, Partners4UrbanWater
- Wouter van Riel, Infralytics
- Guido Schaepman, Hoogheemraadschap van Rijnland 
- Dirk Smolenaars, Waterschapsbedrijf Limburg
- Fred Tacke, Waterschap Rijn en IJssel 
- Wijnand Turkensteen, Waterschap Aa en Maas
- Marc van der Wulp, Waterschap Hollandse Delta

Vanuit Stichting RIONED is Eric Oosterom de verantwoordelijk projectmanager. Vragen over de module en de totstandkoming en vaststelling ervan kunt u stellen via gwsw@rioned.org. 

Gelieve de inhoudsopgave als leeswijzer te beschouwen.

# Inleiding

Kengetallen van rioolstelsels en rioleringsgebieden en afvoerrelaties tussen stelsels en gebieden zijn essentieel voor het opstellen van afvalwaterprognoses. Om deze informatie bij elkaar te krijgen, is vaak een forse inspanning nodig. De benodigde gegevens zijn in beheer bij gemeenten en waterschappen. Daar worden de gegevens op verschillende plekken en in verschillende formaten opgeslagen. Door gebruik te maken van gestandaardiseerde open data en eenduidige terminologie is het mogelijk om op een efficiënte en vergelijkbare wijze de afvoerrelaties en kengetallen te beschrijven en uit te wisselen. Dit vereenvoudigt en verbetert het opstellen van afvalwaterprognoses.

De afkorting GWSW staat voor GegevensWoordenboek Stedelijk Water, de open standaard waar Stichting RIONED met alle relevante partijen aan werkt. Met het GWSW worden komende jaren alle objecten en hun gegevens, hun onderlinge relaties, en de beheeractiviteiten binnen het domein stedelijk water eenduidig gedefinieerd en vastgelegd ten behoeve van soepele gegevensuitwisseling en beter beheer. Meer informatie daarover vindt u via [www.riool.net/gwsw](https://www.riool.net/gwsw).

De riolering en een deel van de afvalwaterketen kan al worden beschreven met het GWSW (Basis, Rib en Hyd). In het GWSW ontbreekt echter de schematisering van het afvoernetwerk en de bijbehorende kengetallen. Vanuit de Community of Practice ‘Afvalwaterprognoses’ van de STOWA is aan Stichting RIONED gevraagd om het GWSW geschikt te maken om als bron te dienen voor het doorrekenen van afvoerscenario’s in de afvalwaterketen. Dit wordt beschreven in GWSW-Kengetallen.

De algemene beschrijving van het GWSW model vindt u op [data.gwsw.nl](https://data.gwsw.nl/). De datamodellen GWSW-Basis (operationeel beheer), GWSW-Rib (inspectie en reiniging van leidingen, putten en kolken) en GWSW-Hyd (hydraulische modellering) zijn al eerder vastgestelde onderdelen van het GWSW. De tools rondom GWSW vindt u op [apps.gwsw.nl](https://apps.gwsw.nl). Voor de details van het datamodel GWSW-Kengetallen, zie [data.gwsw.nl/Kengetallen](https://data.gwsw.nl/Kengetallen).

# Gegevensuitwisseling t.b.v. afvalwaterprognoses

## Inleiding

Het verzamelen van gegevens voor het doen van afvalwaterprognoses is vaak tijdrovend, omdat deze in verschillende formaten en bij verschillende partijen in beheer zijn. De beheerapplicaties van gemeenten en de kernregistraties van waterschappen (Damo-AWK) zijn daarvoor een belangrijke bron. Afvoerscenario’s worden daarna op verschillende manieren en met verschillende applicaties afgeleid. Dergelijke afvoerscenario's geven inzicht in de huidige en toekomstige belasting van, rioolgemalen, persleidingen en zuiveringsinstallaties en is belangrijk voor het optimaliseren van de afvalwaterketen.

### Programmaplan 'Afvalwaterprognoses - Naar een nieuwe praktijk'

Het verzamelen van gegevens voor het doen van afvalwaterprognoses is een complex proces. Het Waterschapshuis heeft dit samen met STOWA als Community of Practice Afvalwaterprognoses opgenomen in het [programmaplan 2022-2024](https://www.stowa.nl/sites/default/files/assets/PROJECTEN/Projecten%202023/Afvalwaterprognoses%202022/Prognoses%20Afvalwaterketenprogrammaplan%202.0_Update%204mei22.pdf) (Figuur 1).

<img src="media/programmaplan_awp2022-2024.png" style="width:100%;height:50%" />

*Figuur 1 - Afvalwaterprognoses naar een nieuwe praktijk (Bron: Het Waterschapshuis/STOWA)*  

## Gegevensstromen en gereedschappen rond het GWSW

Nu al worden door veel gemeenten en waterschappen de gegevens van rioolstelsels en afvoersystemen op de GWSW Server gepubliceerd. Deze gegevens komen 1) via de upload functionaliteit van de GWSW Server middels een OroX (.ttl) bestand vanuit het gemeentelijke beheerpakket of 2) via het GegevensKnooppunt Waterschappen (Het Waterschapshuis) terecht in de dataomgeving van de betreffende organisatie op de GWSW Server. 

De module GWSW-Kengetallen ondersteunt in de gegevensuitwisseling ten behoeve van het maken van afvalwaterprognoses. Het is dus van belang dat de OroX (gemeentelijk rioleringsbeheerpakket) en Damo-AWK (waterschapsdata) deze gegevens conform het datamodel GWSW-Kengetallen aan kunnen leveren. 

Op de GWSW-server worden de gegevens van de verschillende organisatie gecombineerd in een afvoernetwerk per zuiveringskring. Met de applicatie GWSW-Geo kan via het geo-thema Kengetallen de WFS-aanroep worden gegenereerd of een geobestand (geopackage / GML) worden gedownload, waarmee de applicatie voor het maken van afvalwaterprognoses de invoergegevens ontvangt. 

In Figuur 2 staan de gegevensstromen en gereedschappen weergegeven die gebruikt worden voor het maken van afvalwaterprognoses met GWSW-Kengetallen.

<img src="media/proces_datauitwisseling_kengetallen.jpg" style="width:100%;height:50%" />

*Figuur 2 - Gegevensstromen en gereedschappen voor het maken van afvalwaterprognoses*  

# Datamodel GWSW-Kengetallen

## Afvoernetwerk

Zie [data.gwsw.nl/Kengetallen/Afvoernetwerk](https://data.gwsw.nl/Kengetallen/Afvoernetwerk)

Binnen een zuiveringskring vormen rioleringsgebieden, rioolstelsels (vrijverval en mechanisch) en de zuivering samen met verschillende type leidingen een afvoernetwerk. Dit netwerk bestaat uit knooppunten (afvoerpunten) en verbindingen (afvoerrelaties).

In GWSW-Kengetallen wordt dit netwerk topologisch geschematiseerd (Figuur 3). Dat betekent dat het netwerk zonder geografische kenmerken kan worden gepresenteerd. Kenmerken die relevant en specifiek zijn voor het afvoerpunt of de afvoerrelatie worden aan dit netwerk gekoppeld. 

<img src="media/topologischnetwerk.jpg" style="width:100%;height:50%" />

*Figuur 3 - Afvoernetwerk in GWSW-Kengetallen*

## Afvoerpunt  

Zie [data.gwsw.nl/Kengetallen/Afvoerpunt](https://data.gwsw.nl/Kengetallen/Afvoerpunt)

Een *Afvoerpunt* is de topologische vertaling van de zuivering (met subtype *Afleveringspunt*) en van rioleringsgebieden, opvoergemalen, tussengemalen, boostergemalen of andere fysieke constructies (met subtype *Afvoerpunt gebied*). Daardoor is het mogelijk het afvoernetwerk ook op kaart te visualiseren. De kengetallen van een stelsel of gebied worden gekoppeld aan het betreffende afvoerpunt. 

Een *Afleveringspunt* is deel van *Afvoernetwerk* en *RWZI*. Voor een *Afleveringspunt* zijn geen specifieke kenmerken nodig.

Een *Afvoerpunt gebied* is deel van *Afvoernetwerk*, *Gebied*, *Gemaal*, *Leiding*, *Put*, *Rioleringsgebied*, *Stelsel* en *Systeem*. Een *Afvoerpunt gebied* kan onderdeel zijn van een fysieke afvoerconstructie (zoals een rioolgemaal, stuwput, leiding), maar dat is niet verplicht. In de meeste gevallen zal een rioolgemaal het afvoerpunt van een stelsel of gebied zijn. 

<a id="afvoerpunt_gebied"></a>
Voor *Afvoerpunt gebied* zijn de volgende kenmerken mogelijk:

**DWA-belasting**
- Aantal inwoners - Totaal aantal inwoners in het gebied.
- Aantal woningen - Totaal aantal woningen in het gebied.
- Aantal v.e. - Aantal vervuilingseenheden. Bij uitwisseling van kengetallen alleen vullen als één of meer details (Aantal v.e. inwoners, Aantal v.e. bedrijven, Aantal v.e. recreatie) onbekend zijn.
- Aantal v.e. inwoners - Aantal vervuilingseenheden afkomstig van inwoners.
- Aantal v.e. bedrijven - Aantal vervuilingseenheden afkomstig van bedrijven.
- Aantal v.e. recreatie - Aantal vervuilingseenheden afkomstig van recreatie.
- DWA debiet - Totaal DWA debiet in m<sup>3</sup>/uur. Bij uitwisseling van kengetallen alleen vullen als één of meer details (DWA debiet inwoners, DWA debiet bedrijven, DWA debiet recreatie) onbekend zijn.
- DWA debiet inwoners - DWA debiet in m<sup>3</sup>/uur afkomstig van inwoners. 
- DWA debiet bedrijven - DWA debiet in m<sup>3</sup>/uur afkomstig van bedrijven.
- DWA debiet recreatie - DWA debiet in m<sup>3</sup>/uur afkomstig van recreatie.

**HWA-belasting**
- Afvoerend oppervlak - Het oppervlak in m<sup>2</sup> van de bovenlaag dat water afvoert naar het object.

**Berging**  
- Maatgevend niveau voor berging - De hoogte (in m t.o.v. NAP) op basis waarvan de stelselberging is bepaald. Het maatgevende niveau ten opzichte van een referentiepeil.
- Netto berging - De netto onderdrempelberging (in m<sup>3</sup>), ook wel de statische berging genoemd. Rekening houdend met het bergingsverlies vanwege permanente vulling.
- Netto berging randvoorzieningen - De netto onderdrempelberging in randvoorzieningen (in m<sup>3</sup>), ook wel de statische berging genoemd. Rekening houdend met het bergingsverlies vanwege permanente vulling.
- Verloren berging - De inhoud (in m<sup>3</sup> van de riolering dat blijvend is gevuld en niet bijdraagt aan de effectieve berging.
- Vultijd - De tijd (in uur) waarin de riolering zich vult, vanaf het moment van uitschakeling gemaal tot het moment van uitstromen van afvalwater.
- Ledigingstijd - De tijd (in uur) die een rioolgemaal nodig heeft om een vol gevuld rioolstelsel te ledigen bij niet opeenvolgende buien in een rioleringsgebied.

**Volumes**
- Afvoercapaciteit - De capaciteit (in m<sup>3</sup>/uur) van de fysieke afvoerconstructie bij het *Afvoerpunt gebied*. Hierbij kan via *Wijze van Afleiden* gekozen worden voor *Capaciteit geïnstalleerd*, *Gemeten capaciteit*, *Normcapaciteit* of *Ontwerpcapaciteit*.
- Pompovercapaciteit - Het deel van de capaciteit van een rioolgemaal (in m<sup>3</sup>/uur) dat beschikbaar is voor de afvoer van ingezamelde neerslag. Hierbij kan via *Wijze van Afleiden* gekozen worden voor *Capaciteit geïnstalleerd*, *Gemeten capaciteit*, *Normcapaciteit* of *Ontwerpcapaciteit*.
- Invoer gebied - Som van alle invoeren (in m<sup>3</sup>/uur) van inprikkende gebieden en bovenstroomse afvoerconstructies. Dit veld kan ter controle worden ingevuld. De automatische berekening wordt in de prognosesoftware gedaan en niet op de GWSW-server. 

<a id="afvoerrelatie"></a>
## Afvoerrelatie

Zie [data.gwsw.nl/Kengetallen/Afvoerrelatie](https://data.gwsw.nl/Kengetallen/Afvoerrelatie)

Een *Afvoerrelatie* is de topologische verbinding tussen twee afvoerpunten, te weten het beginpunt en het eindpunt van de afvoerrelatie. De afvoer kan onder vrijverval (met subtype *Afvoerrelatie vrijverval*) of mechanisch (met subtype *Afvoerrelatie mechanisch*) plaatsvinden.

Voor *Afvoerrelatie* zijn de volgende kenmerken mogelijk:
- Afvoer DWA-situatie - DWA-debiet inclusief invoerend DWA-debiet in m<sup>3</sup>/uur. Hierbij kan via *Wijze van inwinning* gekozen worden voor o.a. *Afvalwaterakkoord* of *Debietmeter*.
- Afvoer HWA-situatie - Dit is de gesommeerde afvoer in m<sup>3</sup>/uur van DWA-debiet, pompovercapaciteit en invoeren. Hierbij kan via *Wijze van inwinning* gekozen worden voor o.a. *Afvalwaterakkoord* of *Debietmeter*.

## Voorbeeld
In Figuur 4 is een voorbeeld opgenomen van een topologisch netwerk.

<img src="media/topo_geo.jpg" style="width:80%;height:50%" />

*Figuur 4 - Voorbeeld van topologisch afvoernetwerk*

Rioleringsgebied A wordt in het topologische netwerk afvoerpunt A. Afvoerpunt A krijgt de kenmerken van rioleringsgebied A. Rioleringsgebied A voert af naar rioleringsgebied B. Rioleringsgebied B wordt in het topologische netwerk afvoerpunt B, met bijbehorende kenmerken. De afvoer tussen rioleringsgebied A (als afvoerpunt A) en rioleringsgebied B (als afvoerpunt B) is de afvoerrelatie.

# Totstandkoming GWSW-Kengetallen

Het GegevensWoordenboek Stedelijk Water (GWSW) is ontwikkeld onder de vlag van en wordt beheerd door Stichting RIONED. De Community of Practice Afvalwaterprognoses van de STOWA heeft in 2020 aan Stichting RIONED gevraagd om het GWSW geschikt te maken voor de uitwisseling van gegevens ten behoeve van afvalwaterprognoses. Hierop is Stichting RIONED begonnen met de ontwikkeling van GWSW-Kengetallen. 

Hiervoor is een [werkgroep](#werkgroep) samengesteld met potentiële gebruikers vanuit verschillende waterschappen/samenwerkingsverbanden. Tevens is vanuit Stichting RIONED een projectteam samengesteld voor de technische realisatie van GWSW-Kengetallen. 
Via een aantal praktijktoetsen ("proof of concepts") is gekomen tot de huidige conceptversie van GWSW-Kengetallen. De gevolgde roadmap (Figuur 6) richt zich op publicatie per januari 2023 van GWSW versie 1.6.

<img src="media/roadmap_maart2022.jpg" style="width:100%;height:50%" />

*Figuur 6 - Roadmap van de praktijktoetsen tot aan beoogde publicatie*

In de "Proof of Concept" zijn de volgende stappen doorlopen:

<a id="stap1"></a>
## Stap 1: Definiëren afvoernetwerk van een zuiveringskring

Tussen waterschap en gemeentes zijn afspraken nodig over de opbouw van het afvoernetwerk:

- Welke rioleringsgebieden (clusters van stelsels) onderscheiden we en wat zijn daarvan de afvoerpunten?
- Welke stelsels (mechanisch en vrijverval) worden met een apart afvoerpunt beschreven?
- Welke overige afvoerpunten (als representatie van een afleveringspunt, rioolgemalen) onderscheiden we?
- Van welke fysieke afvoerconstructie (zoals een rioolgemaal, stuwput, leiding) is het afvoerpunt onderdeel van?
- Wat zijn de resulterende afvoerrelaties (verbindingen van de afvoerpunten)?

Een afvoernetwerk bestaat doorgaans uit afvoerpunten en -relaties van één of meerdere gemeenten en uit afvoerpunten en -relaties van een waterschap (Figuur 7). Een zuiveringskring kan beschreven worden als afvoernetwerk. Er zal in het definiëren van het afvoernetwerk specifieke aandacht moeten zijn voor de 'overnamepunten'. Dit geldt voor:
- Uit de praktijk blijkt dat een gemeente het eindgemaal van een kern vaak in het beheerpakket heeft zitten, terwijl deze in eigendom en beheer van het waterschap is. Om de juiste kengetallen (vanuit het waterschap) mee te geven binnen GWSW-Kengetallen zal hier het waterschap als *Gegevenseigenaar* moeten worden opgegeven.
- Om het gemeentelijke afvoernetwerk goed te laten aansluiten op het afvoernetwerk van het waterschap moeten de ID's van de 'overnamepunten' in beide datasets gelijk zijn.

<img src="media/netwerk_overname.jpg" style="width:100%;height:50%" />

*Figuur 7 - Voorbeeld van gemeentelijk afvoernetwerk (blauw vlak) en afvoernetwerk van het waterschap (groen vlak)*

## Stap 2: Bepalen van de benodigde velden en bronnen om die velden te vullen

Nadat het afvoernetwerk was gedefinieerd is door de werkgroep en het projectteam bepaald:

- Welke kenmerken er voor de verschillende type afvoerpunten en afvoerrelaties beschikbaar moeten zijn voor het doorrekenen van afvoerscenario's?
- Op welke wijze die kenmerken het beste kunnen worden beschreven in GWSW-Kengetallen?
- Welke brongegevens daarvoor gebruikt kunnen worden? Als bronnen kan gedacht worden aan:
  - Beheersystemen
  - GIS
  - Hydrodynamische rekenmodellen voor vrijverval rioolstelsels
  - Rapportages (analoog/digitaal)

Stap 1 en 2 zijn door vier regio's verspreid over Nederland (HH Rijnland, HHNK, Zuid-Limburg en Groningen) zelfstandig uitgevoerd op verzoek van en in afstemming met Stichting RIONED. Op 13 april 2021 is er een evaluatie met de betrokkenen geweest. Het resultaat daarvan was het eerste concept van het datamodel GWSW-Kengetallen.

<a id="stap3"></a>
## Stap 3: Vullen dataset conform GWSW-Kengetallen

Doel van deze stap was om de technische uitwisseling van de gegevens in GWSW-Kengetallen te toetsen. Krijgen we de gegevens op de GWSW-server en krijgen we er die ook weer vanaf? De Community of Practice Afvalwaterprognoses (STOWA) heeft DUOPP gevraagd om in samenwerking met het projectteam van Stichting RIONED deze dataomgeving te vullen met een afvoernetwerk en bijbehorende kenmerken, en daarna de gegevens te ontsluiten op zuiveringskringniveau conform GWSW-Kengetallen. Als casussen zijn de zuiveringskringen van Heusden/Waterschap Aa en Maas en Edam-Volendam/HHNK gebruikt.

Na Stap 3 is er op 10 maart 2022 een evaluatie geweest. Het resultaat hiervan was een nieuwe conceptversie van het datamodel GWSW-Kengetallen en een aangepaste uitwisselarchitectuur op de GWSW-server. 

<a id="gwsw-download"></a>
## Stap 4: Doorrekenen afvoerscenario's

De laatste stap van de 'Proof of Concept' was het toepassen van GWSW-Kengetallen in de praktijk. Met andere woorden: Kunnen we GWSW-Kengetallen gebruiken om afvoerscenario's door te rekenen?

Waterschappen in Nederland hebben verschillende applicaties in gebruik voor het doorrekenen van afvoerscenario's. Die applicaties kunnen afgestemd worden op het gebruik van GWSW-datasets. Stichting RIONED biedt via [apps.gwsw.nl](https://apps.gwsw.nl) de mogelijkheid de benodigde dataset op te vragen (Figuur 8). Speciaal voor GWSW-Kengetallen is de mogelijkheid toegevoegd om de informatie op het niveau van zuiveringskring op te vragen (1) en zijn de zuiveringskringen in Nederland al in een lijst gezet (2). Daarna moet de dataset ingelezen worden (3).

<img src="media/opvragen1.jpg" style="width:100%;height:50%" />

*Figuur 8 - Selecteren van dataset op apps.gwsw.nl via selectievorm en zuiveringskring*

Via de applicatie GWSW-Geo (Figuur 9) kan daarna de geselecteerde dataset (1, wordt automatisch ingevuld) worden gekoppeld aan het geo-thema Kengetallen (2). Tot slot kan een geo-bestand of WFS-aanroep worden gemaakt (3). Het geo-bestand of de WFS-aanroep is de invoer voor de prognose-software.

<img src="media/opvragen2.jpg" style="width:100%;height:50%" />

*Figuur 9 - Kies het geo-thema Kengetallen en vraag de gegevens op via een geo-bestand of WFS-aanroep*

In deze stap konden de deelnemers (een brede groep gebruikers van verschillende prognosetools) zelfstandig aan de slag met een aangeleverde testdataset (WFS-aanroep) in hun eigen applicatie. Het verzoek was om de volgende vragen te beantwoorden:
- Wat gaat goed met het opstellen van een afvoerscenario met behulp van GWSW-Kengetallen?
- Wat gaat nog niet goed daarbij?
- Wat ontbreekt er nog aan het datamodel of is een wenselijke uitbreiding?
- Wat kan er nog verbeterd worden aan de uitwisseling vanaf de GWSW-server?
- Welke aanpassingen ga je uitvoeren in jouw applicatie om aan te sluiten op GWSW-Kengetallen?
- Wat heb je verder nog nodig vanuit de werkgroep?

Na Stap 4 is er eind juli 2022 met het projectteam een evaluatie geweest. Het resultaat hiervan was het gereedkomen van de conceptversie GWSW-Kengetallen die is voorgelegd aan de Werkgroep GWSW-Basis van Stichting RIONED. Na goedkeuring door de Werkgroep GWSW-Basis is conceptversie 1.1 van GWSW-Kengetallen gebruikt voor de publieke consultatie in oktober 2022. Enige aanpassing is de wijziging van naamgeving van GWSW-Kentallen in GWSW-Kengetallen. 
In november 2022 is GWSW-Kengetallen vastgesteld door de Centrale Commissie van Datastandaarden

## Onderbouwing van de keuzes die zijn gemaakt
In deze paragraaf staan de keuzes die zijn gemaakt in de totstandkoming van de GWSW-Kengetallen toegelicht. Hierbij is het criterium: "Is het nodig voor het maken van afvalwaterprognoses?" leidend geweest.

### Topologisch netwerk vs. Geografisch netwerk
In GWSW-Kengetallen wordt het afvoernetwerk (bestaande uit afvoerpunten en afvoerrelaties) topologisch, dus zonder geografische oriëntatie, beschreven. Dit is vergelijkbaar met het bekende blokkenschema. Hiervoor is gekozen, omdat nog niet elke organisatie de geografische informatie goed in beeld is en dat dat niet beperkend hoeft te zijn in het maken van afvalwaterprognoses. Omdat een afvoerpunt onderdeel kan zijn van een (riolerings-)gebied, fysiek object of stelsel, en die wel een geografische oriëntatie hebben, kan het afvoernetwerk via die weg door de geo-applicatie op de GWSW-server op kaart worden gevisualiseerd. 

Verder is er voor gekozen dat er meerdere afvoerrelaties vanuit één afvoerpunt mogelijk zijn binnen GWSW-Kengetallen. Denk aan een driewegkraan in een leiding, die onder de ene situatie naar gebied X afvoert en onder de andere situatie naar gebied Y afvoert. 

### Toekomstscenario’s 
Toekomstscenario’s zijn geen onderdeel van het GWSW. Deze zullen bepaald moeten worden binnen de prognosetool. Er worden ook geen scenario’s opgeslagen op de GWSW-server. 

### DWA-belasting
DWA-belasting kan op verschillende manieren worden bepaald. Dit kan meer uniform, maar dat is voor GWSW-Kengetallen niet van belang en zal door de CoP Afvalwaterprognoses van de STOWA verder worden uitgewerkt. 

### HWA-belasting
Voor de HWA-belasting is enkel *Afvoerend oppervlak* opgenomen in GWSW-Kengetallen. *Afgekoppeld oppervlak* en *Niet aangesloten oppervlak* zijn niet opgenomen in GWSW-Kengetallen. Deze informatie is niet nodig voor het maken van afvalwaterprognoses. Dit hoort elders te worden vastgelegd, e.g. BGT Inlooptabel. 
Het GWSW is bedoeld voor het vastleggen van de meest actuele informatie.  

Bij het *Afvoerend oppervlak*  kan binnen het GWSW geen onderscheid gemaakt worden tussen *Afvoerend oppervlak bedrijven* en *Afvoerend oppervlak woningen* i.v.m. de 150 m<sup>2</sup> per woning die door sommige waterschappen gehanteerd wordt. Hiervoor is gekozen omdat het een methodiek is die waterschapspecifiek is, waardoor het een maatwerkoplossing zou worden binnen een uniforme standaard. 

### Maatgevend niveau voor stelstelberging
Er is voor deze term gekozen omdat, met name in vrijafwaterend gebied, de berging in het stelsel niet altijd alleen afhankelijk is van de laagste overstortdrempel van het stelsel.

### Invoeren
Het debiet uit voorliggende stelsels (=invoeren) wordt binnen GWSW-Kengetallen niet automatisch meegenomen. Dit wordt normaliter binnen de prognosestool uitgevoerd. Wel heeft de gebruiker de mogelijkheid om in GWSW-Kengetallen de invoeren hardcopy mee te geven, zodat dit veld later gebruikt kan worden bij de controle van de invoeren in de prognosetool. 

### Berekeningen
Er wordt niets berekend op de GWSW-server. De data op de server zijn in die zin 'harde invoeren'. Berging kan worden berekend met andere applicaties, zoals sommige beheer- en rekenapplicaties. Ook zal de omrekening van bijvoorbeeld m<sup>3</sup>/uur naar mm/uur door de gebruiker zelf moeten worden gedaan, al dan niet in de prognosetool.

### Externe bronnen
Er worden op de GWSW-server geen externe bronnen bevraagd om kenmerken in te vullen (bijvoorbeeld voor het bepalen van het aantal inwoners op basis van CBS gegevens of het afleiden van afvoerend oppervlak met behulp van de BGT Inlooptabel).Deze gegevens dienen in het GWSW-uitwisselbestand aanwezig te zijn, dat wordt geüpload naar de GWSW-server.

# Handleiding
In deze handleiding staat beschreven hoe gebruik gemaakt kan worden van GWSW-Kengetallen voor de afvalwaterprognoses. De tekst is voor een deel overgenomen uit het eindrapport van de praktijktoets GWSW-Kengetallen (uitgevoerd door DUOPP in opdracht van de CoP Afvalwaterprognoses van de STOWA).

In onderstaande figuur staan de gegevensstromen en gereedschappen voor het maken van afvalwaterprognoses binnen het GWSW.

<img src="media/proces_datauitwisseling_kengetallen.jpg" style="width:100%;height:50%" />

*Figuur 10 - Gegevensstromen en gereedschappen voor het maken van afvalwaterprognoses*  

In de uitwisseling naar de GWSW-server wordt onderscheid gemaakt in twee type brondatasets: 1) van een gemeente en 2) van een waterschap. Als de gegevens op de GWSW-server van Stichting RIONED staan, dan kan er met de applicatie GWSW-geo een WFS-aanroep worden gemaakt of een geobestand (geopackage / GML) worden gedownload, waarmee de applicatie voor het maken van afvalwaterprognoses de invoergegevens ontvangt.

## Aandachtspunten vooraf
**Het GWSW is in ontwikkeling.** De implementatie en het gebruik ervan is daardoor ook in ontwikkeling. Het succesvol kunnen toepassen van GWSW-Kengetallen is mede afhankelijk van de implementatie van het GWSW in het algemeen en GWSW-Kengetallen in het bijzonder door beheerapplicaties (hierna beheerpakket genoemd). Enerzijds betekent dat dat GWSW-Kengetallen is opgenomen in het datamodel van het beheerpakket. Anderzijds betekent dat dat GWSW-Kengetallen wordt meegegeven in het [GWSW-uitwisselbestand (orox)](https://apps.gwsw.nl/doc/GWSW.orox%20Opbouw%20dataset.pdf) van het beheerpakket. Op dit moment zijn er nog verschillen tussen beheerpakketten wat betreft de mogelijkheid om de data conform het GWSW te geregistreren naar de GWSW-server te kunnen uploaden. Geen van de pakketten is nu al in staat een GWSW-uitwisselbestand mét Kengetallen mee te geven.
Naast de inspanningen van Stichting RIONED, zal ook de gebruiker de behoefte aan de implementatie van GWSW-Kengetallen nadrukkelijk moeten uitspreken richting de leverancier van zijn of haar beheerpakket.

**Wat er niet (goed) in staat, komt er ook niet uit.** Gegevens kunnen enkel uitgewisseld worden, als deze (goed) in het beheerpakket staan. Bestaat een veld niet in het datamodel van het beheerpakket, dan kan deze ook niet worden ingevuld door de gebruiker. Dit veld zal dan dus ook niet meegenomen worden in de uitwisseling. Is een veld leeg, dan zal dit veld ook als 'leeg' worden meegenomen in de uitwisseling. Is een veld ingevuld met een 'foute' waarde (bijv. 999 wat vaak gebruik wordt voor 'onbekend'), dan zal dit veld ook als waarde '999' worden meegenomen in de uitwisseling. De kwaliteit en volledigheid van de geregistreerde gegevens moet voldoende zijn om het gewenste resultaat te bereiken.

## Inrichten dataset van een gemeente
Gemeentes maken doorgaans gebruik van een beheerpakket om het areaal te registreren en beheren. De meeste beheerpakketten hebben een functionaliteit om de gegevens naar een GWSW-uitwisselbestand te vertalen en te exporteren. De functionaliteit is echter (nog) niet in staat om alle aanwezige gegevens in het beheerpakket conform de GWSW-standaard te vertalen. Ook is het (nog) niet mogelijk om aanvullende gegevens, die specifiek zijn voor GWSW-Kengetallen, te registreren in het beheerpakket. Denk hierbij aan informatie over DWA- en HWA-belasting of aan specifieke informatie uit een Systeemoverzicht Stedelijk Water, kenmerkenbladen of telemetriesystemen. Ook het registreren van een afvoernetwerk is in de beheerpakketten nu nog niet mogelijk. Hoe kunnen dan de gegevens die nodig zijn voor het maken van afvalwaterprognoses op de GWSW-server komen?

Dit wordt gedaan met door het verrijken van het GWSW-uitwisselbestand dat uit het beheerpakket komt (of er eentje 'from scratch' te maken). Zoals gesteld, zijn de meeste beheerpakketten in staat zo'n GWSW-uitwisselbestand te exporteren, maar bevat deze nog niet alle benodigde informatie ten aanzien van GWSW-Kengetallen. Dit GWSW-uitwisselbestand dient daarom handmatig verrijkt te worden met deze aanvullende informatie. Voor de Proof of Concept [stap 3](#stap3) zijn aan een gemeentelijke dataset uit de praktijk gegevens toegevoegd die nodig zijn voor het maken van afvalwaterprognoses. Deze dataset is vervolgens vertaald naar een GWSW-uitwisselbestand en naar de GWSW-server geüpload.

Het verrijken van zo'n GWSW-uitwisselbestand of deze 'from scratch' opbouwen is een taak voor een specialist, die kennis heeft van het GWSW. Eerst moet het **afvoernetwerk** worden opgesteld. Voor het maken van het afvoernetwerk moeten de voorzieningen en bijzondere constructies als overstorten, stuwputten en rioolgemalen conform de GWSW-standaard in het beheerpakket worden geschematiseerd. In het beheerpakket moet verder voor elk object worden aangegeven tot welk rioleringsgebied het object behoort. De afvoerpunten en afvoerrelaties kunnen (nog) niet als zodanig (als afvoernetwerk) in het beheerpakket worden geregistreerd. Dus de objectinformatie moet uit het beheerpakket worden geëxporteerd en aangevuld met afvoerpunten en afvoerrelaties. *Afvoerpunt gebied* wordt dan als onderdeel van het object of rioleringsgebied geregistreerd. Indien gewenst kan hier gekozen worden om het afvoernetwerk op kaart te laten weer te geven, door het netwerk te koppelen aan rioleringsgebieden of objecten met een geografische oriëntatie. Aan de *Afvoerpunten gebied* zijn in de dataset de [kenmerken van het afvoerpunt](#afvoerpunt_gebied) toegevoegd. Elk afvoerpunt is onderdeel van één of meerdere afvoerrelaties. De *afvoerrelaties* tussen de *afvoerpunten* moeten ook handmatig worden toegevoegd aan het GWSW-uitwisselbestand en worden voorzien van de [kenmerken van de afvoerrelatie](#afvoerrelatie). Tot slot dient het uitwisselbestand te worden geüpload naar de GWSW-server.

Het is niet noodzakelijk om alle gegevens van een areaal naar de GWSW-server te uploaden. Uploaden van het totale areaal inclusief het afvoernetwerk is mogelijk, maar het volstaat ook om enkel het afvoernetwerk te uploaden.

## Inrichten dataset van een waterschap
Waterschappen registreren hun areaal in een (ander type dan gemeenten) beheerpakket, zoals Geonis of Lis. Vanuit deze beheerpakketten vertalen zij hun data naar een registratie conform het [DAMO-AWK](https://damo.hetwaterschapshuis.nl/) en kunnen zij de data op het GegevensKnooppunt Waterschappen (GkW) plaatsen. Hier zijn gegevens van waterschappen te benaderen en te gebruiken. Ook zijn er waterschappen die rechtstreeks registreren in DAMO-AWK en vanuit daar doorleveren naar het GkW. De totale dataset van alle waterschappen op het GkW wordt periodiek doorgeleverd naar de GWSW-server. Om de data van waterschappen op de GWSW-server te krijgen, dienen zij dus hun data DAMO-AWK conform op het GkW te plaatsen. Nog niet alle waterschappen hebben dit gedaan. 

DAMO-AWK voorziet op dit moment nog niet in een registratie die geschikt is voor GWSW-Kengetallen. Om de gegevens te kunnen gebruiken voor het opstellen van afvalwaterprognoses dient het DAMO-AWK hierop te worden uitgebreid. Dit zal in de nabije toekomst in gezamenlijk overleg tussen het Waterschapshuis en de werkgroep DAMO-AWK worden uitgewerkt.

## Combineren van informatie van gemeente en waterschap
Om een afvoernetwerk van een zuiveringskring te maken is informatie nodig van zowel gemeente als waterschappen. In beide datasets zijn afvoerpunten en -relaties aanwezig die onderdeel uitmaken van het afvoernetwerk van een zuiveringskring. Daarnaast zijn in de gemeentelijke dataset veelal ook objecten aanwezig die eigendom zijn van het waterschap. De dataset van de eigenaar moet dan ook de bron zijn voor de meest actuele informatie van dit object. Om in het beheersysteem en voor het opstellen van afvalwaterprognoses altijd van de meest actuele gegevens van de eigenaar gebruik te kunnen maken, is het verstandig om voor deze objecten in beide datasets dezelfde unieke identificatie (Uniform Resource Identifier, URI) te gebruiken.

Op de GWSW-server is voor alle zuiveringskringen in Nederland al het afvoernetwerk vastgelegd. Elk afvoernetwerk is voorzien van een uniek ID en een unieke URI (zie Figuur 11). Daarnaast is beschreven welke datasets (van welke organisaties) onderdeel uitmaken van het betreffende afvoernetwerk. Op basis van deze informatie stelt de GWSW-server een afvoernetwerk samen. Daartoe dient in een dataset de URI van het afvoernetwerk te worden vastgelegd, zoals dat op de server bekend is. Voor deze gegevens kan contact worden opgenomen met het waterschap. Een query selecteert vervolgens op basis van de genoemde URI de afvoerpunten en -relaties van het betreffende afvoernetwerk uit de verschillende datasets. Het ophalen van de afvoerpunten en -relaties uit de gemeentelijke datasets en de dataset van het waterschap gebeurt direct uit de eigen data-omgeving van de betreffende organisaties op de GWSW-server.

<img src="media/voorbeeld_samenstellen.jpg" style="width:100%;height:50%" />

*Figuur 11 - Voorbeeld samenstellen afvoernetwerk op GWSW-server* 

Dit betekent wel dat indien een afvoerpunt in beide sets voorkomt als aanduiding voor hetzelfde object, deze ook beiden in het afvoernetwerk terecht komen. Indien deze beide afvoerpunten zijn voorzien van hetzelfde unieke ID, dan voegt de server beide items samen in één afvoerpunt. Zijn er verschillende kenmerken aanwezig, dan komen beide afvoerpunten als apart punt in het afvoernetwerk terecht. Op dit moment is het in dit geval nog niet mogelijk om op de server een keuze te maken voor één van de afvoerpunten. Hetzelfde geldt voor de afvoerrelaties. 

In de dataset is het al wel mogelijk om het kenmerk “Gegevenseigenaar” aan afvoerpunten of -relaties mee te geven. Dit kenmerk geeft aan wie er verantwoordelijk is voor het uploaden van een afvoerpunt en/of -relatie. Met dit kenmerk kunnen we in de toekomst op de server bepalen welke afvoerpunten en -relaties onderdeel uitmaken van een afvoernetwerk. Daarom is het noodzakelijk dat gemeenten en waterschappen duidelijke afspraken maken over welke organisatie verantwoordelijk is voor het uploaden van de afvoerpunten en -relaties die in beide datasets kunnen voorkomen.

## Opvragen gegevens voor het maken van afvalwaterprognoses
Als de gegevens op de GWSW-server van Stichting RIONED staan, dan kan er met de applicatie [GWSW-Geo](#gwsw-download) een WFS-aanroep worden gemaakt of een geobestand (geopackage / GML) worden gedownload, waarmee de applicatie voor het maken van afvalwaterprognoses de invoergegevens ontvangt.

Naast het ontsluiten van de gegevens via de selectievorm "Afvoernetwerken" is het ook mogelijk om een afvoernetwerk te ontsluiten via de omgeving van een specifieke organisatie (enkel de gemeente of enkel het waterschap). De aparte organisaties zijn te vinden via de selectievorm "GWSW-publicaties". Via deze route is het afvoernetwerk van de specifieke organisatie te vinden, zonder alle kenmerken van de afvoerpunten en -relaties. De afvoerpunten staat in de attributentabel van de layer "Default: Punt" en de afvoerrelaties staan in de attributentabel van de layer "Default: Lijn".

De WFS kan worden aangeroepen via een GIS-pakket. In onderstaande voorbeelden is daarvoor QGIS gebruikt. De gegevens van het afvoernetwerk zijn aanwezig in drie verschillende layers: afvoerpunt, afvoerrelatie en afvoergebied. De layer afvoergebieden bevat enkel informatie als het afvoerpunt onderdeel is van een gebied of stelsel en er een gebiedsgrens als polygoon aanwezig is in de dataset op de server. In het document [GWSW-Modelbeschrijving](https://data.gwsw.nl/Kengetallen) zijn per layer de aanwezige velden nader toegelicht.

<img src="media/wfs_afvoerpunt.jpg" style="width:100%;height:50%" />

*Figuur 12 - Resultaten ontsluiten gegevens van een afvoerpunt gebied van afvoernetwerk 's-Hertogenbosch met de WFS-aanroep van GWSW-Kengetallen* 

<img src="media/wfs_afvoerrelatie.jpg" style="width:100%;height:50%" />

*Figuur 13 - Resultaten ontsluiten gegevens van een afvoerrelatie van afvoernetwerk 's-Hertogenbosch met de WFS-aanroep van GWSW-Kengetallen*  

## Tot slot
Hoewel de huidige beperkingen in de beheerpakketten en DAMO-AWK ervoor zorgen dat de uitwisseling van de gegevens ten behoeve van het opstellen van afvalwaterprognoses nog niet helemaal vlekkeloos loopt, is er toch een mogelijkheid om deze informatie via een verrijkt GWSW-uitwisselbestand te uploaden naar de GWSW-server. Zo kunnen toch de afvalwaterprognoses al worden opgesteld.

# Geleerde lessen
In dit deel van de pagina zal in worden gegaan op de geleerde zaken door de gebruikers. Dit kan zijn procesmatig of technisch. Input kan geleverd worden via gwsw@rioned.org .

## Kan je een Afvoerpunt gebied koppelen aan zowel een gebied én een gemaal (tegelijkertijd)?
Ja, dat kan. Een Afvoerpunt kan deel zijn van meerdere objecten/gebieden/stelsels tegelijkertijd. Andersom kan een object/gebied/stelsel maximaal één Afvoerpunt als deel hebben. 

## Hoe kun je de afvoernetwerken van gemeente en waterschap 'aan elkaar knopen'?
Op zo'n overnamepunt moet een Afvoerpunt hetzelfde worden genoemd in zowel de gegevens van het waterschap als van de gemeente. Dit geldt ook voor overnamepunten tussen twee gemeenten of twee waterschappen. Het is zaak om voor zo'n overnamepunt dezelfde URI (Uniform Resource Identifier) te gebruiken (zie ook [Stap 1](#stap1)).

Het is voor de betreffende partijen (waterschappen en gemeenten) cruciaal om vooraf goed te overleggen hoe het afvoernetwerk vorm wordt gegeven en hoe zij de objecten gaan noemen. In gezamenlijk overleg zullen zij de URI's moeten bepalen. 

Momenteel is er helaas nog geen beheerapplicatie die goed overweg kan met URI's. Daarom zal er op het koppelvlak nog handmatig werk gedaan moeten worden.
