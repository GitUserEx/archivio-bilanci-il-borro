# Archivio dei bilanci di sostenibilità — Il Borro S.r.l. – Società Agricola

Pagina web in HTML e CSS per la divulgazione delle attività di sostenibilità di
un'impresa del settore primario e per il download dei suoi bilanci di
sostenibilità dal 2020 al 2025.

**Sito pubblicato:** [https://gituserex.github.io/archivio-bilanci-il-borro/](https://gituserex.github.io/archivio-bilanci-il-borro/)

\---

## Contesto

Elaborato realizzato a fini didattici nell'ambito di un project work
universitario.

|||
|-|-|
|Corso di Studio|Informatica per le Aziende Digitali (L-31)|
|Tema|n. 3 — Tecnologia web per la sostenibilità d'impresa|
|Traccia|n. 17 — Sviluppo di una pagina web per il download dei report di sostenibilità di un'impresa del settore primario|
|Autore|*Federico Amato*|

La pagina **non è un sito ufficiale de Il Borro S.r.l.** e non è in alcun modo
collegata all'impresa, che non ne è a conoscenza e non l'ha autorizzata.

## Cosa fa la pagina

La traccia richiede due funzioni distinte, che la struttura del documento tiene
separate.

**Comunicare** le attività di sostenibilità dell'impresa. Le prime tre
sezioni presentano la ripartizione della superficie della tenuta in scala, sei
ambiti di attività (agricoltura biologica, energia, clima, acqua, economia
circolare, persone) e un confronto quantitativo fra gli esercizi 2024 e 2025.

**Consentire il download** dei report. La quarta sezione è un archivio delle sei
edizioni pubblicate, ciascuna con una scheda che riporta esercizio, data di
creazione del file, numero di società comprese nel perimetro di rendicontazione,
numero di pagine e peso, oltre al collegamento di scaricamento.

Chiude una nota metodologica che dichiara lo standard applicato, il livello di
conformità, l'assenza di verifica esterna e la presenza di dati riesposti.

## Struttura del repository

```
index.html      markup della pagina, commentato
style.css       foglio di stile, commentato
report/         i sei bilanci di sostenibilità in PDF
```

## Scelte tecniche

**Solo HTML e CSS**, come richiesto dalla traccia. L'interattività è ottenuta
con elementi nativi: `<details>` per le schede espandibili dell'archivio,
collegamenti interni per la navigazione.

**Nessuna dipendenza esterna**, essuna libreria, nessun font remoto, nessuna
immagine bitmap. La pagina è composta da due soli file più i PDF che
distribuisce: funziona offline una volta caricata e non invia richieste a terze
parti.

**I PDF sono ospitati nel repository**, l'attributo `download` viene ignorato
dai browser sugli indirizzi che puntano a un dominio diverso da quello della
pagina.

**Dati nel markup, non nel foglio di stile.** Le parcelle del grafico della
tenuta portano l'attributo `style="--ha: N"` con gli ettari reali, e il CSS ne
ricava la larghezza con `flex-grow`. Le celle della tabella di confronto portano
`style="--q: N"` con il valore in percentuale del massimo di riga, da cui il CSS
disegna la barra come sfondo. Aggiornare un dato significa cambiare un numero
nel markup.

**Accessibilità: s**truttura semantica con elementi di riferimento, gerarchia
dei titoli senza salti di livello, tabelle con `scope` sulle intestazioni di
riga e di colonna, navigazione completa da tastiera con indicatore di focus
visibile, rispetto della preferenza di sistema per il movimento ridotto. I
rapporti di contrasto fra testo e sfondo sono stati calcolati secondo le
norme WCAG 2.2: 11,8:1 per il testo principale, 6,6:1 per il testo secondario, 
5,8:1 per i collegamenti, da 5,4:1 a 8,7:1 per le etichette del grafico della tenuta.

**Foglio di stampa:** La versione a schermo ha fondo scuro, che su carta
produrrebbe pagine completamente inchiostrate. La media query `print`
ridichiara le variabili di colore in bianco e nero, invertendo l'intera pagina
senza riscrivere alcuna regola.

## Fonti

I contenuti della pagina sono tratti dai Bilanci di Sostenibilità 2020-2025
pubblicati da Il Borro S.r.l. – Società Agricola, gli stessi documenti resi
scaricabili dall'archivio. I valori numerici provengono dalle sezioni
«Indicatori di performance» delle singole edizioni.

## Proprietà dei documenti

I sei PDF contenuti nella cartella `report/` sono pubblicati da Il Borro S.r.l.
– Società Agricola e ne restano di proprietà. Sono qui riprodotti a fini
esclusivamente didattici e di studio, senza alcuna finalità commerciale.
Il codice della pagina è opera dell'autore.

