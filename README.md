# Övning: Intro till GitHub Actions

Den här övningen syftar till att ge dig en grundläggande förståelse för hur GitHub Actions fungerar. Du kommer att arbeta med olika steg och koncept som är centrala i en pipeline: `workflow`, `trigger`, `job`, `steps`, `uses`, `run` m.m.

Målet är inte att skapa en perfekt pipeline utan att **utforska**, **felsöka** och **förstå**.

---

## Förberedelse

1. Gör fork på detta repo
2. Gör git clone på ditt forkade repo
3. Gör övningarna i/till ditt forkade repo

---

## Delövning 1: Förstå strukturen

**Syfte:** förstå de olika delarna och strukturen i ett workflow

Uppdatera [.github/workflows/1-minimal.yml](./.github/workflows/1-minimal.yml) så att denna pipeline:

-	Triggas manuellt
-	Innehåller ett jobb som kör på en GitHub-hostad runner
-	Har två steg:
    1. Ett kommando som visar att pipelinen startat
    1. Ett kommando som visar vilken version av Python som finns tillgänglig

Läs dokumentationen för att ta reda på hur du ska göra!

Länkar:
- [GitHub Actions - Overview](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions)
- [GitHub Runners](https://docs.github.com/en/actions/using-github-hosted-runners/using-github-hosted-runners/about-github-hosted-runners)

---

## Delövning 2: Lägga till `uses` och styra exekvering

**Syfte:** förstå `uses`, `jobs` och exekveringsordning

Uppdatera [.github/workflows/2-uses.yml](./.github/workflows/2-uses.yml) så att denna pipeline:

1. Hämtar ut repots filer
2. Listar repots filer
3. Se till att det andra jobbet körs efter det första (sekventiellt)
4. Hur kan du få det andra jobbet att köra parallellt med det första?
    - Hur ser du exekveringsordningen visuellt i GitHub UI?

Länkar:
- [Återanvändbara actions](https://github.com/marketplace?verification=verified_creator&type=actions)
- [Jobb och deras exekvering](https://docs.github.com/en/actions/writing-workflows/choosing-what-your-workflow-does/using-jobs-in-a-workflow)

---

## Delövning 3: Lägga till artifacts

**Syfte:** förstå hur artefakter från steg, såsom loggar / testresultat / byggresultat, lagras och hanteras

Uppdatera [.github/workflows/3-artifact.yml](./.github/workflows/3-artifact.yml) så att denna pipeline:

1. Skapar en fil `log.txt` med valfritt innehåll  
2. Laddar upp denna fil som en artifact  
3. Efter körningen: hämta filen i GitHub UI och öppna den – vad innehåller den?

Länkar:
- [Storing and sharing data from a workflow](https://docs.github.com/en/actions/writing-workflows/choosing-what-your-workflow-does/storing-and-sharing-data-from-a-workflow)

---

## Delövning 4: Experimentera med triggers

Uppdatera [.github/workflows/4-triggers.yml](./.github/workflows/4-triggers.yml) så att denna pipeline:

**Syfte:** förstå `triggers` och vad som startar pipelinen

1. Triggas av en ny commit
    - Gör en commit och se vad som händer
1. Ändra så att den triggas av en pull request
    - Skapa en PR och se vad som händer

Länkar:
- [Events that trigger workflows](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows)

---

## Tips

- Du kan se resultatet av varje körning under fliken **Actions** i ditt repo
- Klicka på ett jobb för att se detaljer, loggar etc
- Testa att göra fel med flit! Det är så man lär sig mest
