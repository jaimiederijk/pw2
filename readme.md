# Bundlin

The beauty of the web, bundled.

## Usability issues

### Niet duidelijk waar focus ligt

Ongebruiks vriendelijk voor de toetsenbordgebruikers.
Oplossing is weer een outline toevoegen aan links en buttons die is nu verwijderd met outline:none.

Ook loopt de focus door niet zichtbare elementen zoals de video speler. Niet zichtbare elementen zouden moeten worden opgevangen met een display:none. Dan worden ze niet gefocust en leest een screenreader ze ook niet. 

### Semantische HTML
Voor meer structuur en duidelijkheid ten behoeve van screenreaders. Er wordt een grote hoeveelheid divs gebruikt op plekken waar het niet handig is. Zoals onderstaande div die eigenlijk een button zou moeten zijn.
```
<div class="playbutton bln-button bln-button-invert bln-button-stop" ng-click="stopVideo()" ng-show="playvideo">
  <span class="bln-icon bln-icon-stop-button"></span>
  Stop video
</div>
```


### login

[bundlin](https://bundlin.com/)

Log in signup knop brengt je verderop in de pagina naar een andere log in /signup knop

sign up alleen mogelijk met twitter account.
Opent een popup om met twitter in te loggen.

Ik heb toen een twitter account gemaakt en die gebruikt voor de sign up. Vreemd genoeg werd dit nieuw gemaakte twitter account vergrendelt na deze stap. dus bundlin doet het wel met dit twitter account maar twitter zelf zegt dat ik regels overtreed en kan twitter dus niet gebruiken. Niet dat ik dit erg vindt. Na verder onderzoek blijkt dat een twitter account waaraan een app gekoppeld wordt altijd een nummer verificatie wil. Dit is dus verkeerde berichtgeving van twitter. 

Na signup vraagt bundlin om een email adress voor password recovery. Maar dat gaat toch via twitter?


### profilebar
![Alt text](/bundlinbugs/profile.png)

Hover effect op lege link naar persoonlijke website

lege plekken voor info die de gebruiker niet heeft ingevuld. Het is beter om deze gewoon niet te late zien tot ze zijn ingevuld. Het is toch maar extra informatie en niet noodzakkelijk.


### new bundle

Zodra je op new bundle klik wordt er meteen een nieuwe bundle aangemaakt. Het lijkt mij beter om deze pas aan te maken als er iets geedit is in de bundle. Dan heeft een gebruiker zoals ik die een beetje aan het verkennen is niet meteen drie lege bundles.

Op mobiel is maken en editen van bundles nog niet beschikbaar maar de knop maakt nog wel steeds een nieuwe bundle aan. 
De terug knop die hier op het scherm staat lijd vervolgens naar deze nieuw gemaakte bundle. Dit wordt niet verwacht en zou ook echt als terugknop moeten werken.


### Bundles Verwijderen

Ik kan geen knop vinden om een van mijn bundles te verwijderen. Deze knop bestaat wel maar wordt verstop door de suggestie om content toe te voegen. De bundle kan dus pas verwijderd worden als er content is toegevoegd dit lijkt mij niet handig. 

### Bundle upload Cover photo

Geen indicatie hoe groot een foto moet zijn. Krijg een rode pop up waarschuwing dat ik een te kleine foto probeerde te uploaden. Een hover over de uploadknop zou een licht grijze tekst met "Photo must be atleast 800x800" kunnen tonen als indicatie. 
Als de gebruiker na deze waarschuwing dezelfde foto probeert te uploaden dan gebeurd er niks. Dus de foto wordt serverside geweigerd maar de waarschuwing waarom komt niet weer te voorschijn. Dus als je de eerste mist weet de gebruiker niet wat er fout gaat.

### Bundle Cover photo by tag

Je krijgt suggesties voor cover foto's aan de hand van de tags die je invoert maar deze suggesties komen maar met een tegelijk binnen en zijn erg langzaam. Het zou beter zijn om meerdere plaatjes te laten zien of in iedergeval de volgende suggestie alvast in te laden. Dus nadat het huidige plaatje is ingeladen meteen de volgende klaarzetten en niet tonen. Dit heeft wel als gevolg dat er meer data verbruik is dus dit zou niet op mobiel moeten plaatsvinden. 



### Bundle tags

Als er maar een tag is dan kan deze niet verwijderd worden. Visuel verdwijnt hij wel maar als de pagina herlaad wordt verschijnt hij opnieuw. In de console verschijnen dan ook errors.

### Meer bundles inladen 

Bundles worden alleen ingeladen door het scrollen van de muis. Dus niet wanneer de scrolbalk op een andere manier op het einde komt zoals bijvoorbeeld via de pijltoetsen. Dit kan worden opgelost door te kijken naar de scrolbalk en niet naar de muis scroll of beter nog doormiddel van pagination door de content heengaan. 

## Performance 

110 requests
## timeline
![Alt text](/bundlinstart/3g.bundlin.com.timeline.png)


### Kleinere Images
Grunt imagemin levert 50kb

### Nutteloze gif van bijna 1mb
![Alt text](/bundlinbugs/ill-be-back.gif)
Deze gif voegt niet veel toe behalve meer om te downloaden. Verwijderen zou goed zijn.

### Inloggen via twitter 
Na het Inloggen via twitter worden animaties afgespeeld op content die niet veranderd. Bundles komen inwaaien terwijl ze niet weg zijn geweest. Mijn advies zou hier zijn om alleen nieuwe content te animeren. 
![Alt text](/bundlinbugs/twitter.png)
