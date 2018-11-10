# Korte installatie handleiding hass.io op een RPI 3B+

Wat heb je (minimaal) nodig:
- Een Rasberry Pi 3B+ (een oudere kan ook, maar dan is je systeem wel trager en kan minder)
- Een 8Gb (minimaal) of 16Gb SD kaartje voor in je Pi
- Een stabiele voeding voor je Pi (2,5A)

De volledige installatie staat beschrebven op de volgende URL: https://www.home-assistant.io/hassio/installation/

Maar in het kort komt het hier op neer:
- Download en installeer Etcher, dit is een tool om disk images te schrijven. Zie https://etcher.io
- Download de juiste image voor jouw RPI van de _hass.io_ installatie pagina
- Pak het `hass.io` image uit en zet deze met `Etcher` op het SD kaartje (minimaal 8 Gb)

## Netwerk instellen

De meest stabiele oplossing om je Home-Assistant aan te sluiten op jouw netwerk is nog steeds via een netwerk kabel en zo mogelijk direct op jouw wifi router.
Echter via Wifi kan ook. Je kan ook beide netwerken actief maken, maar dat levert soms wat issues op (welke verbinding heeft prioriteit?)

Een volledige beschrijving van het instellen van de netwerk verbindingen vindt je hier:

https://github.com/home-assistant/hassos/blob/dev/Documentation/network.md

Als je alle netwerk instellingen het gedaan, dan kun je jouw Pi aansluiten (bedraad als je dat ingesteld hebt) en opstarten.
Bij de eerste keer opstarten van home-assistant kan het even duren omdat het file-system op het sd-kaartje 'uitgepakt' moet worden.

Als alles goed gaat, kun je na enkele minuten via de webbrowser op jouw laptop/PC naar http://hassio.local:8123 gaan en de aanwijzingen op het scherm volgen om een account voor jezelf aan te maken.
(Soms werkt dit niet, en dan moet je naar http://<ip-adres-rpi>:8123) gaan.

Verder is het handig om ervoor te zorgen dat je hass.io Pi altijd hetzelfde IP adres krijgt van jouw router. Dit kan je door een vast ip adres op de pi te zetten of door een
permanente DHCP lease toe te kennen aan jouw Pi. Dit laatste doe je op jouw Wifi router/modem en vindt je meestal terug in de geavanceerde instellingen.
Een permanente DHCP lease kan je pas toekennen als je Pi de eerste keer is opgestart, of als je het MAC-adddress van je Pi weet.

Een permanente DHCP lease kan je meestal als volgt toekennen:
- Noteer het MAC address van je Pi als je dit al weet
- Log in op je Wifi router
- Zoek naar de DHCP instellingen (meestal onder de geavanceerde instellingen)
- Bij de DHCP instellingen vindt je een overzicht van de verbonden en actieve devices.
- Zoek jouw hass.io pi op in die lijst, en daar vindt je ook het MAC-address van je pi. Meestal kan je van uit die lijst gelijk een permanente lease aanmaken.
- Zo niet, neem dan het MAC-address en huidige IP-address over van je pi en zoek in de instellingen van je router waar je DHCP leases kan toekennen.
- Maak een permanente DHCP lease aan met het MAC-address en huidige IP-address van je PI.
- Als je pi een keertje uit gaat en weer herstart, dan weet je zeker dat je PI weer hetzelfde IP adres krijgt.

