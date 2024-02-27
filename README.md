# KlasseStudentenverwerking

Deze toepassing maakt gebruik van een tekstbestand "studenten.txt"
waarin de studentengegevens zijn opgenomen. Eerste records uit het
bestand:

IVandenbossche Els Kroonweg 2 3500V36

IVan Summeren Koen Kerkstraat 7 3500M53

GLeys Kristel Lelielaan 4 3600V

GHox Peter Krekelstraat 11 3500M

IDaems Greta Sparrenhof 18 3290V66

GVaes Marcel Valleilaan 4 3290M

GJacobs Jan Luikse steenweg 124 3500M

IMaes Jean Sparstraat 12 3800M62

GWillems Patrick Kerkstraat 14 3290M

GKuppers Joke Putstraat 6 3600V

GLambrechts Inge Lange straat 365 3500V

GMichiels Jaak Putsteeg 5 3000M

GPauwels Nico Djef Antenstraat 56 3500M

ILaeremans Claudia Runkstersteenweg 12 3500V25

GBoonen Tanja Krekelstraat 4 3700V

GHeuts Diederik Grote baan 47 3500M

GPelemans Jeanne Leuvensesteenweg 144 3200V

GHonings Linda Aarschotse steenweg 456 3000V

GPeeters Ellen Djef Swennenstraat 89 3500V ...

In de eerste positie staat het type van de student (G 🡪 gewoon student
of I 🡪 student met individueel traject, volgt geen standaardlespakket,
maar individueel gekozen vakken). Dan volgt de naam van de student (20
posities), de voornaam van de student (20 posities), de straat van de
student (30 posities), de postcode van de student (4 posities). Op de
76ste positie het geslacht, dan volgt op de 77ste en 78ste positie
het aantal studiepunten. Dit is alleen van toepassing voor studenten met
een individueel traject en geeft de zwaarte van hun vakkenpakket aan
(voor een gewone student bedraagt dit 60. Voor de IT-studenten wijkt dit
hiervan af: kan minder zijn, kan zelf iets meer zijn)

Je mag er van uitgaan dat bij deze structuur nooit fouten zijn en dat
het bestand "studenten.txt" aanwezig is op de door u bepaalde locatie.
Het aantal records in het tekstbestand is niet vast.

Je maakt voor deze toepassing de (basisklasse) **STUDENT** met als
eigenschappen **TypeStudent**, **Naam**, **Voornaam**, **Straat**,
**Postcode, Geslacht** en **Studiepunten.**

Deze eigenschappen zijn allemaal van het type string, behalve
Studiepunten. Dat is een integer (getal van minimum nul tot maximum 99).

Er is bijkomend de (uitsluitend te lezen) eigenschap
**Inschrijvingsbedrag**. Deze eigenschap geeft het door de student te
betalen "standaard" inschrijvingsbedrag. Dit bedraagt 520€ voor de
gewone studenten. Voor studenten met een individueel traject bedraagt
het inschrijvingsbedrag 50€, vermeerderd met 8,66€ (520 / 60) per
opgenomen studiepunt.

Tevens is er de (uitsluitend te lezen) eigenschap **Financierbaarheid.**
De waarde hiervan staat op 100 voor de normale studenten (die zijn 100%
financierbaar). Voor de IT-studenten is de financierbaarheid ook
afhankelijk van het aantal opgenomen studiepunten: 100%
financierbaarheid vanaf 45 studiepunten, tussen 30 en 44 studiepunten is
de financierbaarheid 75%, tussen 15 en 29 studiepunten is de
financierbaarheid 50%. Onder 15 studiepunten is de financierbaarheid 0%.

Ten slotte is er nog de functie **NaamVolledig**. Het resultaat is een
string beginnend met de tekst "Standaardstudent " of \"Student met
individueel traject \", gevolgd door de voornaam en de naam.

Maak een venster STUDENTENVERWERKING_START dat dient als startvenster
voor deze toepassing. Het venster ziet er als volgt uit:

![Afbeelding met tekst, software, scherm, Multimediasoftware Automatisch
gegenereerde
beschrijving](./media/image1.png)

[Dit venster bevat:]{.underline}

A.  Een **menustructuur** met 2 hoofdkeuzes:

**1. Bestand** : bevat een keuze *Openen* om studentengegevens in te
lezen uit het tekstbestand "Studenten.txt" (zie eerder) en een keuze
*Opslaan* om gewijzigde studentengegevens te kunnen wegschrijven. (deze
keuze wordt pas mogelijk nadat minstens één keer gegevens zijn
ingelezen).

Bij het kiezen van *Opslaan* worden de studentengegevens in
"Studenten.txt" overschreven (dezelfde naam!). Pas dan bevat dit
tekstbestand de eventueel gemaakte wijzigingen.

**2. Info** : roept een modaal venster op dat informatie weergeeft:

![Afbeelding met tekst, schermopname, Lettertype Automatisch
gegenereerde
beschrijving](./media/image2.png)

B.  Een Listbox **LstStudentenlijst**

Deze wordt gevuld bij het inlezen met studentengegevens van alle
studenten uit het tekstbestand "studenten.txt.

*Venstervoorbeeld:*

![Afbeelding met tekst, schermopname, Lettertype, nummer Automatisch
gegenereerde
beschrijving](./media/image3.png)

Een opdrachtknop **BtnVerwijderen.** Bij het drukken op deze knop wordt
eerst getest of de gebruiker een bepaalde student geselecteerd heeft. Zo
nee, dan verschijnt de foutmelding \"Geen student geselecteerd!\",
anders wordt met een messagebox een bevestiging gevraagd. Indien "Ja"
geantwoord wordt, dan wordt de betreffende student verwijderd (uit het
geheugen en uit de listbox, wijzigingen in het tekstbestand gebeuren
alleen door de eerder beschreven menukeuze "Bestand -- Opslaan").

Een opdrachtknop **BtnWijzigen.** Bij het drukken op deze knop wordt
eerst getest of de gebruiker een bepaalde student geselecteerd heeft. Zo
nee, dan verschijnt de foutmelding \"Geen student geselecteerd!\",
anders wordt een 2^de^ (modaal) venster **INGAVEFORM** geopend.
Onmiddellijk worden de gegevens van de selecteerde student getoond. In
geval van een IT-student kan de gebruiker het aantal studiepunten
ingeven (dus bij gewone studenten is dit niet beschikbaar). Merk op dat
dit venster uitsluitend verlaten kan worden met de OK-knop of de
CANCEL-knop. Bij het drukken op OK worden de wijzigingen aanvaard (in
het geheugen en in de listbox LstStudentenlijst, wijzigingen in het
tekstbestand gebeuren alleen door de eerder beschreven menukeuze
"Bestand -- Opslaan").

Objecten in het venster (behalve de labels):

-   **CboTypekeuze**: keuzelijst met 2 keuzes ("Gewoon student" en
    "Student met individueel traject")

-   **TxtNaam, TxtVoornaam, TxtPostcode, TxtStraat, TxtGeslacht**:
    tekstvakken voor de ingave of wijziging van de betreffende gegevens
    van de student.

-   **TxtStudiepunten:** tekstvak voor de ingave of wijziging van het
    aantal studiepunten. Dit kan alleen bij studenten met een
    individueel traject. Bij de andere (normale) studenten is dit
    tekstvak onzichtbaar (bijhorende label ook). OPM: de zichtbaarheid /
    onzichtbaarheid van dit object wijzigt ook als het type van de
    student veranderd wordt (wijziging keuzelijst cboTypekeuze).

-   **BtnOK**: button om het venster te sluiten en de gegevens te
    bewaren.

-   **BtnCancel**: button om het venster te sluiten zonder de gegevens
    te bewaren.

Je moet geen controles op ingaven doen. Je mag dus veronderstellen dat
de gebruiker juiste gegevens ingeeft. (dus bv. voor studiepunten een
getal van 1 tot maximum 99).

Dit venster zou er als volgt kunnen uitzien. (bv. voor wijziging van het
huisnummer van de student Kristel Leys van 4 naar 41:

![Afbeelding met tekst, schermopname, scherm, software Automatisch
gegenereerde
beschrijving](./media/image4.png)

Merk ook op dat bij wijziging van het type student van "Gewoon student"
naar "Student met individueel traject" er dan een bijkomend tekstvak
TxtStudiepunten zichtbaar wordt. (en omgekeerd onzichtbaar zou worden)
Bv.:

![Afbeelding met tekst, schermopname, scherm, nummer Automatisch
gegenereerde
beschrijving](./media/image5.png)

Er is ook een opdrachtknop **BtnToevoegen.** Bij het drukken op deze
knop wordt eveneens het venster **INGAVEFORM** opgeroepen. (type student
op "Gewoon student", postcode op "3500" en geslacht op "M"). De
gebruiker kan nu de gegevens van de nieuwe student ingeven en indien
gewenst bewaren (OK-knop) of vergeten (CANCEL-knop).

In geval van bewaring, worden de gegevens van de nieuwe student in het
geheugen bewaard en toegevoegd in de lijst LstStudentenlijst.
(wijzigingen in het tekstbestand gebeuren niet automatisch. Zie eerder)

Tenslotte is er in het venster Studentenverwerking_start een
opdrachtknop **BtnOverzicht** om een 2^de^ (modaal) venster
**Resultaten** op te roepen. Dit 2^de^ venster geeft een overzicht van
de studenten in 2 tabbladen.

Tabblad overzicht:

![Afbeelding met tekst, schermopname, scherm, software Automatisch
gegenereerde
beschrijving](./media/image6.png)

Dit tabblad bevat 5 (niet wijzigbare) tekstvakken:

-   **TxtAantStud**: geeft het aantal studenten weer.

-   **TxtAantGewoon**: geeft het aantal gewone studenten weer.

-   **TxtAantIT**: geeft het aantal IT-studenten weer.

-   **TxtSomFinancierbaarheid**: geeft de som van percentages van
    financierbaarheid van alle studenten samen weer. Deze som wordt door
    100 gedeeld. Het bedrag 44,5 in het schermvoorbeeld betekent dus dat
    de in werkelijkheid 47 ingeschreven studenten samen eigenlijk maar
    voor 44,5 studenten volledig financierbaar zijn. (omdat de
    IT-studenten dikwijls niet voor 100% tellen)

-   **TxtSomInschrijvingsbedrag**: geeft de som van de
    inschrijvingsbedragen van alle studenten weer.

Tabblad details:

![Afbeelding met tekst, schermopname, nummer, Lettertype Automatisch
gegenereerde
beschrijving](./media/image7.png)

Dit tabblad bevat het (niet wijzigbare) tekstvak **TxtDetails**. Dit
tekstvak geeft per student het resultaat van de functie NaamVolledig,
gevolgd door het inschrijvingsbedrag van de betreffende student.

**[Opmerking:]{.underline}**

Gebruik een list met studentenobjecten om de gegevens die ingelezen zijn
te bewaren!
