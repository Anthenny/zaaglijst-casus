## Lokaal installeren

Om deze applicatie lokaal op te zetten kan je de volgende stappen volgen:
1. Fork het project. Zie [hier](https://docs.github.com/en/get-started/quickstart/fork-a-repo) meer informatie over 
het forken van een project.
2. Doe `composer install` om alle benodigde packages van laravel te installeren. Heb je nog geen composer op 
jouw machine staan dan kan je [hier](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-macos) lezen 
hoe je het kan installeren.
3. Doe `php artisan serve` en de applicatie is dan te benaderen op localhost.

## Casus

We gaan een casus maken die sollicitanten (en liefhebbers) kunnen maken. Dit wordt een repo die mensen allemaal mogen 
forken en lekker los gaan op de code. Op basis van deze casus krijgen we een beter inzicht van de skills van de devs 
die hier solliciteren.

### Vraagstuk

In hal 3 worden er dagelijks profielen gepickt die de productie heel de dag moet kunnen bevoorraden. Een deur bestaat 
uit verschillende profielen. Een profiel wordt aangeduid met de letter “G“ als prefix (dus wij hebben profielen G01 
tot en met G72). Er zijn dus 72 verschillende profielen die gebruikt worden om onze deuren te maken. Elk profiel is 
ook in al onze 12 kleuren beschikbaar.

De orderpicker kijkt in de huidige situatie naar alle deuren die die dag gemaakt moeten worden en op basis daarvan 
maakt diegene een inschatting wat er aan profielen nodig is die dag. Dit is een proces wat inefficiënt is en enorm 
veel tijd kost om uit te rekenen wat er op een dag nodig is.

### Wat is de oplossing?

Wat de orderpicker in hal 3 enorm kan helpen is een lijst met hoeveel profielen in welke kleur diegene die dag moet 
picken om aan de vraag te kunnen voldoen van de productie. Hier een voorbeeld van het resultaat:

```json
{
   "G01": {
      "PROFIELKLEUR: RAL 9005 Gitzwart": 5,
      "PROFIELKLEUR: Brons": 4,
      "PROFIELKLEUR: RAL 7021 Zwartgrijs": 1
   },
   "G45": {
      "PROFIELKLEUR: RAL 9005 Gitzwart": 8,
      "PROFIELKLEUR: Wit": 2,
   },
   "G70": {
      "PROFIELKLEUR: RAL 9005 Gitzwart": 8,
      "PROFIELKLEUR: Wit": 2,
      "PROFIELKLEUR: Brons": 4,
   } 
}
```

