---
title: Inlämningsuppgift 3
code: da282a_da266a
---

# Inlämningsuppgift 3

Betyg: U/G

## Syfte

Syftet med den trejde inlämningen är att lära sig arbeta med användarinput, filer och [JSON](https://en.wikipedia.org/wiki/JSON). Att kombinera dessa är inget ovanligt och respektive koncept kommer du säkerligen att stöta på enskilt också (utanför inlämningsuppgifterna).

Inför denna uppgiften rekommenderas du starkt att läsa kapitel 13 och 14 i boken _Think Python_. Gör gärna övningarna också.

Du rekommenderas även starkt att ta en titt på följande källor:

* [Reading and Writing Files in Python](http://www.pythonforbeginners.com/files/reading-and-writing-files-in-python)
* [JSON](http://docs.python-guide.org/en/latest/scenarios/json/) (kort)
* [json - JavaScript Object Notation Serializer](https://pymotw.com/2/json/) (längre men mer ingående)

## Uppgiften

Denna uppgift är indelad i tre huvudsakliga delar: 1) input, 2) filhantering och 3) JSON, där del 3 har samma upplägg som del 2 förutom att vi kommer arbeta med filformatet JSON. Dessa uppgifterna kan lösas på många vis, så länge du åstadkommer och uppfyller de krav som listas (specifikt för uppgiften) så har du klarat av uppgiften. I denna uppgiften uppmuntras du att experimentera och utforska konceptet för att förstå hur det fungerar och för att finna lösningar som du tycker är bra.

**Tips:** Försök att skriva din Pythonkod på engelska, delvis för att det är en bra övning språkmässigt men framförallt så slipper du eventuella problem som kan uppstå med bokstäverna ÅÄÖ - om du inte stöter på dessa problem kan du bortse från detta tips.

**Glöm inte att läsa igenom kravspecifikationen innan du börjar, så du inte missar någonting eller får komplettera på grund av slarvfel.** Hähähä

Observera att i Pythonversion `3.x` sker utskrifter med `print(1)`, i Pythonversion `2.x` sker utskrifter med `print 1` - notera avsaknaden av parenteser
{: .info}

### Del 1: input

I den första delen ska du experimentera med användarinput, detta genom den inbyggda funktionen `input`. Denna fungerar på följande vis: den sträng du skickar med kommer att visas för användaren, sen kommer användaren ha möjlighet att skriva in en text - trycka enter - och sedan sparas detta innehåll i den variabel du angivit. Exempelvis kan det se ut så här: `name = print("What is your name? ")`.

Detta innebär att du själva bestämmer vad som görs med den input som kommer från en användare. Kanske sparar du det i en lista, en dictionary eller bara i en variabel - det är upp till dig och beror givetvis på vad du vill åstadkomma. För att experimentera med detta rekommenderas du starkt att utföra övningen nedan innan du går vidare med del 2.

#### Övning

Du ska skapa möjligheten för en användare att fylla i personers för- och efternamn (dvs. lägga till) och kunna lista alla personer (skriva ut). Varje person ska sparas som en dictionary i en lista, dvs. något i stil med `[{"firstname": "Jane", "lastname": "Doe"}, ...]`.

Detta innebär att du även behöver göra så att användaren får någon form av minimal meny presenterad för sig och ska kontinuerligt kunna lägga till nya personer eller lista alla befintliga personer. Nedan presenteras grunden för en sådan meny.

``` py
# Start a infinite loop
while True:
    # Store user choice in a variable
    choice = input("Choose: (1) Add person, (2) List all\n") # \n = newline

    if choice == "1":
        # Collect firstname + lastname from the user
        # store it in a list as a dictionary
        pass
    elif choice == "2":
        # Go through the list and print everyone
        pass
    else:
        print("Bye!")
        break
```

Om du endast skulle utgå från exemplet ovan får du en liten meny där du kan göra valen 1 och 2, utan att någonting händer, och om du skriver in något annat som ert val kommer programmet att sluta.

### Del 2: filhantering

I del två ska du skapa ett program, likt det i del 1, fast användaren ska kunna lägga till fotbollsspelare eller skriva ut alla fotbollsspelare som finns. Varje spelare ska ha ett förnamn, efternamn och information om vilket land den spelar för. Dessa spelare ska sparas i en fil med namnet `players.txt`. Detta innebär att om en användare lägger till tre spelare, stänger ner programmet och sedan öppnar det igen ska det gå att skriva ut alla dessa spelare. Detta innebär att spelarna alltid finns kvar till skillnad från del 1 där allt vårt innehåll försvinner när programmet avslutas. Naturligtvis medför detta att ditt program läser in filen - om den finns - när programmet startas.

Formatet på filen `players.txt` ska se ut på följande vis (exemplet har sex stycken spelare):

``` bash
Fraser,Forster,England
Joe,Hart,England
Tom,Heaton,England
Ryan,Bertrand,England
Gary,Cahill,England
Nathaniel,Clyne,England
```

För att ge dig en utgångspunkt kan du ta en titt på stubben (övergripande och ofullständig kod) nedan:

``` py
def add_player(firstname, lastname, country):
    """
    Open the file players.txt
    Add the new player (dont forget to add a newline \n)
    Close the file
    """
    pass

def print_players():
    """
    Open the file players.txt
    Go through each line and print the player
      firstname + lastname + country
    Close the file
    """
    pass

def start():
    """
    Create the while-loop for handling the main menu
    
    User choice 1:
      Fetch firstname, lastname and country with "input"
      call "add_player" with these
    
    User choice 2:
      call "print_players"
    
    Otherwise:
      Close the menu 
    """
    pass

start()
```

**Tips 1:** om du ska sätta ihop förnamn, efternamn och landet i en sträng i formatet `förnamn,efternamn,land` kan du använda dig av sträng-metoden `.join()`.

**Tips 2:** om du ska hämta delarna förnamn, efternamn och landet från en rad i filen (sträng) så kan du ta en titt på [split](https://docs.python.org/3.5/library/stdtypes.html#str.split).

### Del 3: JSON

Tanken med del 3 är samma sak som med del 2, dvs. att kunna lägga till spelare eller att skriva ut alla spelare. Dock med en skillnad - filformatet. Innehållet ska nu istället sparas i filen `players.json` och formatet kommer se ut som det visas nedan. Utöver detta är det samma princip som gäller som i del 2.

Exempel på `players.json` med 5 spelare.

``` py
{
    "players": [
        {"firstname": "Fraser", "lastname": "Forster", "country": "England"},
        {"firstname": "Joe", "lastname": "Hart", "country": "England"},
        {"firstname": "Tom", "lastname": "Heaton", "country": "England"},
        {"firstname": "Ryan", "lastname": "Bertrand", "country": "England"},
        {"firstname": "Gary", "lastname": "Cahill", "country": "England"}
    ]
}
```

Använd dig av [JSON-modulen](https://docs.python.org/3.4/library/json.html) för denna del. Glöm inte läsa de länkar som listas under "Syfte".
{: .info}

## Kravspecifikation

* Placera alla uppgifter i en och samma Pythonfil med namnet `assignment_3.py`
* Använd sunft förnuft och dokumentera din Pythonkod med kommentarer där det kan anses vara lämpligt, t.ex. beskrivning av hur en funktion fungerar och ska användas
* Din Pythonkod ska fungera, dvs. den får inte generera något felmeddelande
* Din Pythonkod ska ha logiska namn vad gäller variabler och funktioner, dvs. inte `a = 10` eller `def x():`
* Kontrollera att din Pythonkod inte innehåller kodexempel från uppgiftsbeskrivning eller gamla kommentarer

**Specifikt för uppgiften**

* En användare ska i del 2 och 3 kontinuerligt kunna välja val 1 eller 2. Detta betyder att programmet inte ska stängas av efter att användaren gjort ett val och metoden körts, utan att användaren ges möjlighet att välja metod om och om igen.

## Inlämning

**Glöm inte att kontrollera att du skickat med svar på alla uppgifter och att du följt kravspecifikationen.**

När du är färdig med din uppgift ska du ladda upp denna som en `.zip`-fil innehållande alla dina filer på It's Learning. Döp denna enligt formatet `inl3_lisa_a.zip`.

Lycka till!
