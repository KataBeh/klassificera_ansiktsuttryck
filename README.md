# Klassificering av ansiktsuttryck med neurala nätverk

## Introduktion
Individuell deep learning-uppgift där en CNN-modell byggs, tränas och utvärderas för att klassificera ansiktsuttryck från 48x48 gråskalebilder. Projektet innehåller dataförberedelse, modellträning, prediktioner, resultatanalys och reflektion.

## Dataset
Jag använder datasetet **FER-2013**, som laddades ner i zip version från läraren.

Datasetet innehåller gråskalebilder av olika ansiktsutryck där varje bild är:

- 48 x 48 pixlar
- 1 färgkanal
- tillhör en av 7 klasser

Bilderna är uppdelade i följande klasser:

- angry
- disgust
- fear
- happy
- neutral
- sad
- surprise

## I projektet görs följande steg:

- Förstå och undersöka datasetet
- Undersöka vilka klasser som finns
- Kontrollera antal bilder per klass
- Förbereda bilddata för modellträning
- Skapa ett balanserat subset med 400 bilder per klass
- Normalisera bilderna
- Anpassa bildformatet till CNN-modellen
- Bygga en baseline CNN-modell
- Träna baseline-modellen med validation data
- Testa förbättrade modellvarianter
- Jämföra modeller med validation accuracy
- Välja en final model
- Utvärdera final model på testdata
- Analysera resultat med accuracy, confusion matrix och accuracy per klass
- Testa modellen på egna bilder
- Reflektera kring resultat, begränsningar och förbättringar

## Modell

Jag använder CNN-modeller eftersom bilddata passar bra för convolutional neural networks. CNN-modeller kan lära sig mönster i bilder, till exempel kanter, former och strukturer.

I projektet testas tre modellvarianter:

### Baseline CNN

Den första modellen fungerar som en grundmodell. Den används för att få ett första resultat att jämföra med.

### Improved CNN

Den andra modellen är en mer avancerad modell med fler lager och dropout. Syftet var att undersöka om en mer komplex modell kunde ge bättre resultat.

### Model 3 CNN

Den tredje modellen använder bland annat BatchNormalization och mindre dropout. Denna modell presterade bäst på validation data och valdes därför som final model.

Modellerna använder:

- `Conv2D`
- `MaxPooling2D`
- `Flatten`
- `Dense`
- `Dropout`
- `BatchNormalization` i Model 3
- `softmax` som output
- `Adam` som optimizer
- `SparseCategoricalCrossentropy` som loss function
- `accuracy` som metric

## Analys och reflektion

I analysen diskuteras:

- hur bra modellen fungerar
- skillnaden mellan validation data och testdata
- tecken på overfitting eller underfitting
- varför vissa klasser är svårare än andra
- hur bildstorlek, gråskala och begränsad datamängd påverkar resultatet
- modellens begränsningar
- vad som hade kunnat förbättras vid fortsatt arbete

## Hur man kör projektet

### 1. Klona repositoryt

```bash
git clone https://github.com/KataBeh/klassificera_ansiktsuttryck.git

cd klassificera_ansiktsuttryck

python -m venv .venv
.venv\Scripts\activate

pip install -r requirements.txt

```

### Öppna filen
rapport.ipynb


Miljö: Python 3.13.7