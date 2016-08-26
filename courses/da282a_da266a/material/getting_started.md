---
title: "Kom igång"
code: da282a_da266a
---

# Kom igång

Att arbeta med Python är inte direkt det samma som med HTML och CSS. Med HTML och CSS räcker det med en textredigerare och en webbläsare för att komma igång - snabbt och enkelt. Med Python byter vi ut webbläsaren mot en terminal (OS X) / kommandotolk (Windows). En terminal är ett slags program som gör att vi kan komma åt andra program, som inte har ett grafiskt gränssnitt (dvs. att allt i en terminal är textbaserat). Det enda vi egentligen kommer göra med en terminal är att köra/exekvera en Pythonfil - vad innebär detta? Att köra/exekvera en Pythonfil kan ses som att öppna en HTML-fil i en webbläsare - vi får se resultatet av det vi programmerat. I vårt fall kan det t.ex. vara en utskrift så enkel som summan av 1 plus 1 eller att ta emot användarinput som sedan ska sparas i en fil osv. Eftersom Python är ett fullständigt programmeringsspråk är möjligheterna nästan oändliga.

Vad krävs för att komma igång med Python? Först och främst en textredigerare. Eftersom du redan arbetat med HTML och CSS har du säkert en som du känner dig bekväm med - fortsätt i så fall med den. Om inte så rekommenderar jag [Atom](https://atom.io/). Det andra som behövs är givetvis Python. Till skillnad från HTML och CSS måste vi faktiskt installera Python för att vi ska kunna köra våra Pythonfiler (så att datorn vet hur den ska tolka vår kod). Python är ofta förinstallerat på datorer idag så innan du går vidare och [laddar ner Python](https://www.python.org/downloads/) (version 3.5.x eller 2.7.x, vi rekommenderar 3.x), rekommenderas du att se efter om Python redan är installerat eller inte. Gå sedan vidare till nästa steg.

Nästa steg är att bekanta dig med din terminal (eller kommandotolk på Windows) och lära sig lite om denna och lite av dess kommandon.

* [Introduction to the Mac OS X Command Line](http://blog.teamtreehouse.com/introduction-to-the-mac-os-x-command-line) OS X
* [Terminal Tutorial - Part I: Basic Commands and Concepts](https://www.youtube.com/watch?v=-Vl4rpZVA6I) (video) OS X
* [Windows Command Prompt in 15 Minutes](http://www.cs.princeton.edu/courses/archive/spr05/cos126/cmd-prompt.html) Windows
* [Windows Command Line Tutorial - 1 - Introduction to the Command Prompt](https://www.youtube.com/watch?v=MBBWVgE0ewk) (video) Windows
* [LinuxCommand.org: Learn the Linux command line. Write shell scripts.](http://linuxcommand.org/) Linux
* [Linux Terminal Tutorial Episode 1: Back to Basics](https://www.youtube.com/watch?v=2FiQSLdnBqA) (video) Linux

Du kan nu pröva att öppna din terminal och skriva in någonting i stil med `python --version` så ser du vilken Pythonversion du har. Du rekommenderas att använda Python 3.x men det fungerar givetvis med Python 2.7.x också - det finns olikheter men dessa löser du ganska enkelt när du stöter på dessa genom en mindre googling eller dylikt.

Om du vill få möjlighet att testa Python räcker det med att du skriver in `python` i er terminal så kommer du få fram något som kallas för en Pythontolk - här kan du skriva saker som `1 + 1` och se resultaten direkt (men givetvis mer avancerade saker också).

För att komma igång med det sista steget så är det dags att skapa en Pythonfil. Spara denna som `test.py` i en valfri mapp med följande innehåll:

``` py
# A variable (where we store data)
name = "Sherlock Holmes"
print(name)
```

Notera att om du använder du av Pythonversion 2.7.x så måste du ändra "print" till `print name` (dvs. utan parenteser)
{: .info}

Nu ska du öppna din terminal och gå till den plats (mapp) där du sparat er Pythonfil - detta görs oftast med kommandot `cd` (change-directory). Skriv därefter `python test.py` och se vad du får för resultat. Om allt gått som de ska bör du nu ha kommit igång med arbetsprocessen för Python. Hurra!
