# Mellodata

En databas över låtarna och artisterna i Melodifestivalen 2002-2014.

#### Om databasen

Datat kommer från teamet bakom [Mellokollen.se](http://www.mellokollen.se): [LCHansson](https://github.com/LCHansson/), [Luminita](https://github.com/luminita) och [cperriard](https://github.com/cperriard).

Allt data tillhandahålls som både CSV och JSON. Filerna är döpta efter deras innehåll, så `texterna.json` och `texterna.csv` innehåller samma data fast i olika format.

Varje vecka fram till finalen i Melodifestivalen släpper vi nytt data. Datafilerna kan kopplas ihop via `id`-variabeln som finns i alla dataset.

Skälet till att vi valt just åren 2002-2014 är för att tävlingen sett ungefär likadan ut under de åren (2002 var året då deltävlingar och "andra chansen" infördes). Data är därför jämförbart på årsbasis under dessa år.

#### Licens

Datat i repot är fritt tillgängligt att ladda ned och använda, och vi blir såklart extra glada om du ger oss cred när du använder datat. Vi har försett det med en licens, [ODC Open Database License](http://opendatacommons.org/licenses/odbl/1.0/) som vi hoppas är så öppen som möjligt. En lättläst sammanfattning av vad licensen innebär finns [här](http://opendatacommons.org/licenses/odbl/summary/). I korthet kan man säga att du får använda datat hur du vill så länge du öppet tillhandahåller det under samma licens, och länkar tillbaka till detta repo.

# Variabler

## Texterna

- `id`: Ett unikt ID per låt, konstruerat på formen ÅR_DELTÄVLING_STARTPOSITION, alltså t.ex. `2003_2_6`
- `artist`: Namn på artisten
- `year`: År låten var med i Melodifestivalen
- `song_name`: Namn på låten
- `lyrics`: Låttexten, orensad
- `lyrics_cleaned`: Låttexten, rensad

Skillnaden på `lyrics` och `lyrics_cleaned` är att vi rensat bort lite interpunktion och annat skräp från `lyrics_cleaned` för att göra den lättare att analysera. Å andra sidan skulle det kunna tänkas att den innehåller några fel av den anledningen, då all bearbetning gjorts maskinellt.

#### Källor

- Låtnamn, artistnamn, år och placering kommer från [Wikipedias sidor om Melodifestivalen 2002-2014](http://sv.wikipedia.org/wiki/Melodifestivalen_2014).

# Datakvalitet

Vi tar såklart inget ansvar för fel i data - stora delar av data är crowdsourcade från början och innehåller en hel del fel som t.ex. felaktiga siffror, felstavningar, märkliga kommentarer och konstig interpunktion.

Vill du bidra till att förbättra våra data? Hurra! Skicka helst in en [pull request](https://help.github.com/articles/using-pull-requests/) så lägger vi in dina förändringar om vi bedömer att de förbättrar data. Om du inte vet hur Git fungerar men ändå vill bidra kan du även göra ändringar direkt i en CSV- eller JSON-fil och sen [maila den till oss](mailto:mail@mellokollen.se), men du får absolut inte förändra eller förstöra datats format (t.ex. vilka variabler som finns med, eller vilken `encoding` filen har) för då kan vi inte slå ihop det med tidigare data.
