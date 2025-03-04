![Version](https://img.shields.io/github/v/release/DCMLab/poulenc_mouvements_perpetuels?display_name=tag)
[![DOI](https://zenodo.org/badge/{{ zenodo_badge_id }}.svg)](https://doi.org/{{ concept_doi }})
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/poulenc_mouvements_perpetuels)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/poulenc_mouvements_perpetuels](https://github.com/DCMLab/poulenc_mouvements_perpetuels) and the corresponding
* documentation page [https://dcmlab.github.io/poulenc_mouvements_perpetuels](https://dcmlab.github.io/poulenc_mouvements_perpetuels)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/poulenc_mouvements_perpetuels/introduction).

# Francis Poulenc – Mouvements Perpetuels (A corpus of annotated scores)

This is an early work by the prodigy Poulenc, then 19 years old. The composer and his five colleagues in the Groupe des
Six had briefly come under the influence of Erik Satie, whose dry musical sarcasm appears to have been an influence on
this work: each of the three movements ends in a non sequitur musical punchline, and despite being titled 'Perpetual',
the entire set takes only about five minutes to perform. It is unclear whether this irony or the indisputable lyrical
beauty of the music has played a bigger part in making this set a fixture in the 20th-century piano repertoire. Though
largely diatonic, Poulenc's language is by no means retrograde, so adapting the annotation standard to this music is
both straightforward and illuminating, showing conventional harmonic triads behaving in distinctively modern ways.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/poulenc_mouvements_perpetuels/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [poulenc_mouvements_perpetuels.zip](https://github.com/DCMLab/poulenc_mouvements_perpetuels/releases/latest/download/poulenc_mouvements_perpetuels.zip)
  * [poulenc_mouvements_perpetuels.datapackage.json](https://github.com/DCMLab/poulenc_mouvements_perpetuels/releases/latest/download/poulenc_mouvements_perpetuels.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/poulenc_mouvements_perpetuels.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first movement, *Assez modéré* has the following files:

* `MS3/01_assez_modere.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/01_assez_modere.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/01_assez_modere.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/01_assez_modere.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/01_assez_modere.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/01_assez_modere.harmonies.tsv")
notes = ms3.load_tsv("notes/01_assez_modere.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/poulenc_mouvements_perpetuels/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/poulenc_mouvements_perpetuels/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Francis Poulenc – Mouvements Perpetuels (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/{{ concept_doi }}

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)


## Overview
|   file_name   |measures|labels|standard|annotators |reviewers|
|---------------|-------:|-----:|--------|-----------|---------|
|01_assez_modere|      24|    93|2.3.0   |Amelia Brey|DK       |
|02_tres_modere |      14|    58|2.3.0   |Amelia Brey|HB       |
|03_alerte      |      56|   127|2.3.0   |Amelia Brey|HB       |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
