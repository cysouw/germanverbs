# Introduction

## Derivational morphology by exhaustive listing

The goal of this paper is to list and analyse all German verbs

list: there is a concrete list than can be discussed, changed, amendet
analyse: morphological structure, not all different meanings of all forms
all: practically, whatever listed in Wiktionary and DWDS
German: practically, however Wiktionary and DWDS interpret this. My impression is: still actively used in the last ± 100 years. Note that dictionaries tend to have a 'long memory'
verb: PNT-inflection possible

selection of words:

- some verbs only in infinitiv or partizip (e.g "gefrustet, verpönt"). Ideally, words should be used with person/number inflection
- some word in very restricted usage (loanwords, specific occupations, too regional, too old "veraltet", very specific meanings). This criterium is not very consistenly applied, and I have included words freely. Only extreme cases removed
- orthographic alternants and voiced/unvoiced plosives with the same meaning are removed. also differences in palatalised /s/ vs. /sch/ are removed when identical meaning
- words listed in DWDS, but without any explanantion
- not included NUMERAL bases except "ein(s)", e.g. achteln, verdreifachen, because they can be made with any numeral

Verbs consist of: PREVERBIAL - STEM - PNT ending
STEM consist of: ROOT -s/ig/el/er, 

All frequencies reported here are approximate numbers. In practice, the details about the analysis of individual examples is changing constantly, so the exact number of examples of a specific phenomenon is variable. However, the approximate numbers are not expected to change substantially. To reflect this reality, all frequencies are rounded to the nearest multiple of 5 and all percentages are round to the nearest whole number. 

## Method

data-download from DWDS
data-download from Wiktionary

Etymologie from Pfeifer (through DWDS), Wiktionary and etymologiebank.nl

Sijs, Nicoline van der (samensteller) (2010), Etymologiebank, op https://etymologiebank.nl/

# Inflection

- person/number/tempus
- infinitive > Nomen ("das Betteln")
- participle I > Adjective ("bettelnd") > Nomen ("der Bettelnde")
- participle II ("gebettelt"), only some as adjective
- participle II > Nomen ("das Gebettele")

- Ablaut series
- Nomen agentis always possible?

# Prefixes

[TODO: summary of prefixes]

## Fixed prefixes {#prefix:fixed}

Some verb stems only occur with a fixed prefix, i.e. these verbs cannot occur without a prefix. In total there are 685 such examples (20% of all verb stems), which come in various different guises. The major division is between transparant and fossilised fixed-prefix verbs. Transparent fixed-prefix verbs have a stem that exist elsewhere in the German language, while fossilised fixed-prefix verbs have a stem that does not (anymore) exist outside of the prefixed combination. The frequencies of the different kinds of fixed-prefix verbs are summarised in [@tbl:fixed-prefix] and will be discussed in more detail in subsequent sections.

| Fixed-prefix verbs | Frequency
| ------ | :-:
| Transparent, with noun stem | 390 (12%)
| Transparent, with adjective stem | 195 (6%)^[`SELECT * WHERE like(a.VERB, "%- %") && a.ADJEKTIV != " "`]
| Transparent, with other stem | 15 (<1%)^[`SELECT * WHERE like(a.VERB, "%- %") && a.WEITERE != " "`]
| Transparently related to other verb | 20 (<1%)^[`SELECT * WHERE like(a.VERB, "%- %") && (a.NOMEN == " " || like(a.NOMEN, "% -ung %") || like(a.NOMEN, "% Ge- %") || like(a.NOMEN, "% (%")) && a.ADJEKTIV == " " && a.WEITERE == " "`]
| Fossilised, including a fossilised prefix-noun | 15 (<1%)^[`SELECT * WHERE like(a.STAMM, "%- %") && !like(a.VERB, "%- %") && a.NOMEN != " " && !like(a.NOMEN, "% -ung %") && !like(a.NOMEN, "% (%") && !like(a.NOMEN, "% Ge- %")`]
| Fossilised, without a fossilised prefix-noun | 50 (2%)^[`SELECT * WHERE like(a.STAMM, "%- %") && (a.NOMEN == " " || like(a.NOMEN, "% -ung %") || like(a.NOMEN, "% (%") || like(a.NOMEN, "% Ge- %")) && a.ADJEKTIV == " " && a.WEITERE == " "`]
| **Total** | **685** (20%)

Table: Frequencies of different kinds of fixed-prefix structure {#tbl:fixed-prefix}

### Transparent fixed-prefix verbs {#prefix:transparent}

The largest group of fixed-prefix verbs transparently include a stem that exists elsewhere in the German language (620 examples, 18%).^[`SELECT * WHERE like(a.VERB, "%- %")`] Most frequently (390 examples, 12%), these transparent prefix-verbs are based on noun roots.^[`SELECT * WHERE like(a.VERB, "%- %") && a.NOMEN != " " && !like(a.NOMEN, "% -ung %") && !like(a.NOMEN, "% Ge- %") && !like(a.NOMEN, "% (%")`] For example, a noun like *Feind* 'enemy' can be used as a verb with various prefixes, like *anfeinden* 'treat hostile', *befeinden* 'be hostile' or *verfeinden* 'be enemies'. In contrast, a verb \**feinden* without any prefix does not exist.

verb-related:

- *bluff-en > ver-blüff-en*
- *eumel-n > be-ömmel-n*
- *fledder-n > zer-fleder-n*
- *kau-en > wieder-käu-en*
- *rumpel-n > ent-rümpel-n*
- *sauf-en > er-säuf-en*
- *sühn-en > ver-söhn-en*
- *schlaf-en > ein-schläf-er-n*
- *walt-en > be-wält-ig-en*
- *latsch-en > be-latsch-er-n*
- *wieg-en > ab-wieg-el-n*
- *schaff-en > be-schäff-tig-en*
- *hump-el-n > be-hum-s-en*
- *lech-z-en > ver-lech-en*
- *rütt-el-n > zer-rütt-en*
- *watsch-el-n > ab-watsch-en*
- *tüder-en > be-tüter-n*

### Fossilised fixed-prefix verbs {#prefix:fossilised}

fossilised verb roots (50 examples)^[SELECT * WHERE like(a.STAMM, "%- %") && (a.NOMEN == " " || like(a.NOMEN, "% -ung %") || like(a.NOMEN, "% (%") || like(a.NOMEN, "% Ge- %")) && a.ADJEKTIV == " " && a.WEITERE == " ".]

- *ahm* > *nach-ahm-en*
- *bar* > *ge-bar-en*
- *bas* > *ver-bas-el-n*
- *behr* > *ent-behr-en, ge-bär-en*
- *bräm* > *ver-bräm-en*
- *damm* > *ver-damm-en* (≠ *der Damm*)
- *dau* > *ver-dau-en*
- *depper* > *zer-depper-n*
- *drieß* > *ver-drieß-en*
- *dutz* > *ver-dutz-en*
- *gess* > *ver-gess-en*
- *geud* > *ver-geud-en*
- *gösch* > *be-gösch-en*
- *götz* > *er-götz-en* (≠ *der Götze*)
- *grätz* > *ver-grätz-en*
- *hag* > *be-hag-en*
- *hell* > *be-hell-ig-en* (≠ *hell*)
- *hör* > *ge-hör-en*
- *kies* > *er-kies-en* (≠ *das Kies*)
- *knock* > *aus-knock-en*
- *knus* > *ver-knus-en*
- *laub* > *er-laub-en* (≠ *das Laub*)
- *lier* > *ver-lier-en*
- *ling* > *ge-ling-en*
- *lock* > *froh-lock-en*
- *mahl* > *ver-mähl-en* (≠ mahlen)
- *merz* > *aus-merz-en*
- *nader* > *ver-nader-n*
- *nes* > *ge-nes-en*
- *nieß* > *ge-nieß-en* (≠ *niesen*)
- *raum* > *an-be-raum-en* (≠ *der Raum*)
- *sack* > *ver-sack-en* (≠ *der Sack*)
- *scheh* > *ge-scheh-en*
- *scher* > *be-scher-en* (≠ *die Schere*)
- *schwicht* > *be-schwicht-ig-en*
- *spell* > *zer-spell-en*
- *spill* > *ver-spill-en*
- *spratz* > *zer-spratz-en*
- *stalt* > *ver-un-stalt-en*
- *statt* > *ge-statt-en*
- *teidig* > *ver-teidig-en*
- *tick* > *ver-tick-en, ver-tick-er-n* (≠ ticken)
- *törn* > *an-törn-en* (≠ *der Törn*)
- *tupp* > *be-tupp-en*
- *wöhn* > *ge-wöhn-en, ent-wöhn-en, ver-wöhn-en* (≠ *wohnen*)
- *zicht* > *ver-zicht-en, be-zicht-ig-en*

fossilised nouns (15)^[SELECT * WHERE like(a.STAMM, "%- %") && !like(a.VERB, "%- %") && a.NOMEN != " " && !like(a.NOMEN, "% -ung %") && !like(a.NOMEN, "% (%") && !like(a.NOMEN, "% Ge- %").]

- *bär* > *Ge-bär-de* > *gebärde-n*
- *bühr* > *Ge-bühr* > *gebühr-en*
- *deih* > *Ge-deih* > *gedeih-en*
- *fahr* > *Ge-fahr* > *gefähr-d-en* (≠ *fahren*)
- *fehl* > *Be-fehl* > *befehl-en, befehl-ig-en* (≠ *fehlen*)
- *gehr* > *Be-gehr* > *begehr-en*
- *ginn* > *Be-ginn* > *beginn-en*
- *mein* > *Ge-mein-de* > *ein-gemeinde-n* (≠ *meinen*)
- *nunft* > *Ver-nunft* > *vernünft-el-n*
- *sell* > *Ge-sell-e* > *geselle-n*
- *spenst* > *Ge-spenst* > *Gespenst-er-n*
- *stalt* > *Ge-stalt* > *gestalt-en*
- *wicht* > *Ge-wicht* > *gewicht-en*
- *winn* > *Ge-winn* > *gewinn-en*

similar, but with transparent root

die Lust > Ge-lüst > gelüst-en
schaff-en > Ge-schäf-t > geschäft-en
das Wetter > Ge-witter > gewitter-n

Fossilised adjective>verb

- *sund* > *ge-sund* > *gesund-en*

### Multiple fixed-affix verbs {#prefix:multiple}

Of special interest are three exceptional examples that appear to have a double fixed-prefix structure. These prefixes cannot be used individually, only in these exact combinations.

- *ein-ver-leib-en* (~ *der Leib*)
- *ver-un-stalt-en* (~ *die Ge-stalt*)
- *an-be-raum-en* (~ mhd. *ramen* ≠ *der Raum*)

Slightly more frequent, but still highly exceptional, are verbs that have both a fixed-prefix and a fixed-suffix. There are 50 examples of such circumfixed verbs.

Circumfixed verbs | Frequency
- | -
Noun-based | 35^[SELECT * WHERE like(a.VERB, "%- % -% -%") && a.NOMEN != " ".]
Adjective-based | 10^[SELECT * WHERE like(a.VERB, "%- % -% -%") && a.ADJEKTIV != " ".]
Fossilised Stem | 5^[SELECT * WHERE like(a.STAMM, "%- % -%") && a.NOMEN == " " && a.ADJEKTIV == " " && a.WEITERE == " ".]

Most frequently

- Fixed-prefix nouns with suffix *-r*^[SELECT * WHERE like(a.VERB, "%- % -%r %") && a.NOMEN != " " ORDER BY a.STAMM.]
  - *Asche* > *ab/ein-äsche-r-n*
  - *Hede* > *ver-hedde-r-n*
  - *Knoch-en* > *ver-knöch-er-n*
  - *Scheiße* > *ver-scheiße-r-n*
  - *Stein* > *ver-stein-er-n*
  - *Weihrauch* > *be-weihräuch-er-n*
- Fixed-prefix nouns with suffix *-l*^[SELECT * WHERE like(a.VERB, "%- % -%l %") && a.NOMEN != " " ORDER BY a.STAMM.]
  - *Ast* > *ver-äst-el-n*
  - *Band* > *an-band-el-n*
  - *Heim* > *an-heim-el-n*
  - *Kast-en* > *ein-kast-el-n*
  - *Krag-en* > *ab-krag-el-n*
  - *Schande* > *ver-schande-l-n*
- Fixed-prefix nouns with suffix *-s*^[SELECT * WHERE like(a.VERB, "%- % -s %") && a.NOMEN != " " ORDER BY a.STAMM.]
  - *Heim* > *ein-heim-s-en*
  - *Kork* > *ver-kork-s-en*
  - *Name* > *be-nam-s-en*
- Fixed-prefix nouns with suffix *-ig*^[SELECT * WHERE like(a.VERB, "%- % -ig %") && a.NOMEN != " " ORDER BY a.STAMM.]
  - *Absicht* > *be-absicht-ig-en*
  - *Augenschein* > *be-augenschein-ig-en*
  - *Eid* > *be/ver-eid-ig-en*
  - *Erde* > *be-erd-ig-en*
  - *Fried-en** > *be-fried-ig-en*
  - *Gewalt* > *ver-gewalt-ig-en*
  - *Glaube* > *be-glaub-ig-en*
  - *Gnade* > *be-gnad-ig-en*
  - *Hand* > *aus/be/ein-händ-ig-en*
  - *Herz* > *be-herz-ig-en*
  - *Kost* > *be/ver-köst-ig-en*
  - *Lob* > *be-lob-ig-en*
  - *Nachricht* > *be-nachricht-ig-en*
  - *Recht* > *be-recht-ig-en*
  - *Rücksicht* > *be-rücksicht-ig-en*
  - *Schein* > *be-schein-ig-en*
  - *Seite* > *be-seit-ig-en*
  - *Sicht* > *be-sicht-ig-en*
  - *Teil* > *be-teil-ig-en*
  - *Vollmacht* > *be-vollmächt-ig-en*
  - *Vorrecht* > *be-vorrecht-ig-en*

Adjectives

- *fest* > *be/ver-fest-ig-en*
- *gerade* > *be-grad-ig-en*
- *grob* > *an-grob-s-en*
- *gut* > *be-güt-ig-en*
- *lahm* > *be-lämm-er-n*
- *nieder* > *er-niedr-ig-en*
- *gering* > *ver-ring-er-n*
- *sanft* > *be-sänft-ig-en*
- *schön* > *be-schön-ig-en*
- *gewiss* > *ver-gewiss-er-n*
- *zart* > *ver-zärt-el-n*

fossilised stems

- *ver-bas-el-n*
- *be-hell-ig-en*
- *be-schwicht-ig-en*
- *ver-tick-er-n*
- *be-zicht-ig-en*

# Stems

## Stem types

Stems: total 3355

Mostly monosyllabic, or with unstressed second syllable -e/-el/-er/-ig/-lich. Very few more complex stems: 90 morphologically complex and 95 (6%)

recent loans from english: 187 (6%)

Verbs: 1075 (32%)^[SELECT * WHERE (a.NOMEN == " " || like(a.NOMEN, "% -ung %") || like(a.NOMEN, "% (%") || like(a.NOMEN, "% Ge- %")) && a.ADJEKTIV == " " && a.WEITERE == " ".]
Nouns: 1850 (55%)^[SELECT * WHERE a.NOMEN != " " && !like(a.NOMEN, "% -ung %") && !like(a.NOMEN, "% Ge- %") && !like(a.NOMEN, "% (%").]
Adjektiv: 375 (11%)^[SELECT * WHERE a.ADJEKTIV != " ".]
Weitere: 65 (2%)^[SELECT * WHERE a.WEITERE != " ".]

Note: 10 Nomen+Adjektiv^[SELECT * WHERE a.NOMEN != " " && a.ADJEKTIV != " ".]

Roots: 2765, very few homonymic roots (43)^[REGEX: 1.+\n.+2]

±1075 verb stems^[SELECT * WHERE (a.NOMEN == " " || like(a.NOMEN, "% -ung %") || like(a.NOMEN, "% (%") || like(a.NOMEN, "% Ge- %")) && a.ADJEKTIV == " " && a.WEITERE == " ".]

&& a.BEDEUTUNG == "Körperbewegung" (120)
&& a.BEDEUTUNG == "Stimmgeräusch" (127)
&& a.BEDEUTUNG == "Tiergeräusch" (37)
&& a.BEDEUTUNG == "Dinggeräusch" (54)
&& like(a.BEDEUTUNG, "%geräusch") (218)

1850 noun stems^[SELECT * WHERE a.NOMEN != " " && !like(a.NOMEN, "% -ung %") && !like(a.NOMEN, "% Ge- %") && !like(a.NOMEN, "% (%").]

semantics: most can be easily categorised, but a few are currently unclear

- Resultative (750)^[&& (a.BEDEUTUNG == "Resultat" || a.BEDEUTUNG == "Resultat/Instrument" || a.BEDEUTUNG == "Resultat>Diminutiv" || a.BEDEUTUNG == "Resultat>Plural").]
- Instrumental (430)^[&& (a.BEDEUTUNG == "Instrument" || a.BEDEUTUNG == "Resultat/Instrument" || a.BEDEUTUNG == "Instrument>Diminutiv" || a.BEDEUTUNG == "Instrument>Plural").]
- Similative/Animate (190)^[&& like(a.BEDEUTUNG,"%Lebewesen%").]
- Similative/Inanimate (135)^[&& (a.BEDEUTUNG == "Analogon" || a.BEDEUTUNG == "Analogon>Plural").]
- Meronym (140)^[ && a.BEDEUTUNG == "Meronym".]
- Locative (100)^[ && a.BEDEUTUNG == "Ort".]
- Experience (40)^[ && a.BEDEUTUNG == "Empfindung".]
- Consumption (20)^[ && a.BEDEUTUNG == "Verzehr".]
- Unclear (50)^[&& a.BEDEUTUNG == "???".]

## Vowel change

Kausativ:

- i <-> e/ä (top-to-bottom and back)
- ü <-> ö/o
- i -> äu/eu (Licht/leuchten, triefen/Träufeln)
- ee -> ei (Schnee/schneien)

Ablaut:

ie/i/e/ä/au -> a/o/u (front-to-back)
ei -> i/ie (monophtonghize)
schwören -> schwur
helfen -> Hilfe
treten -> Tritt

Verbs with Umlaut/Ablaut/Kausativ without l/r/s (27)^[SELECT * WHERE (like(a.STAMM, "%(%") || like(a.VERB, "%(%")) && !like(a.STAMM, "%-%") && !like(a.VERB, "% -% -%") && (a.NOMEN == " " || like(a.NOMEN, "% -ung %") || like(a.NOMEN, "%(%") || like(a.NOMEN, "% Ge- %")) && a.ADJEKTIV == " " && a.WEITERE == " ".]

- *blaff-en* > *bläff-en*
- *bluff-en* > *ver-blüff-en*
- *dring-en* > *dräng-en*
- *fall-en* > *fäll-en*
- *kau-en* > *wieder-käu-en*
- *lieg-en* > *leg-en*
- *lupf-en* > *lüpf-en*
- *makel-n* > *mäkel-n*
- *nahr-en* > *nähr-en*
- *quak-en* > *quäck-en*
- *rumpel-n* > *ent-rümpel-n*
- *sauf-en* > *er-säuf-en*
- *saug-en* > *säug-en*
- *schlurf-en* > *schlürf-en*
- *schwing-en* > *schwenk-en*
- *sitz-en* > *setz-en*
- *ab-speck-en* > *spick-en*
- *spring-en* > *spreng-en*
- *suhl-en* > *siel-en*
- *sühn-en* > *ver-söhn-en*
- *sumpf-en* > *sümpf-en*
- *tatsch-en* > *tätsch-en*
- *tausch-en* > *täusch-en*
- *wall-en* > *wäll-en*
- *wetter-n* > *witter-n*
- *zuck-en* > *zück-en*
- *zwick-en* > *zwack-en*

65 nouns both with and without umlaut

- *das Aas* > *aas-en/äs-en* (A-I)
- *der Argwohn* > *argwohn-en/argwöhn-en* (E-E)
- *der Ast* > *ast-en/äst-en* (A-R)
- *der Balg* > *balg-en/aus-bälg-en* (A-R)
- *der Baum* > *baum-en/bäum-en* (O-A)
- *der Bock* > *bock-en/böck-el-n* (L-L)
- *der Dampf* > *dampf-en/dämpf-en* (R-I)
- *der Druck* > *druck-en/drück-en* (R-I)
- *der Dunst* > *dunst-en/dünst-en* (R-I)
- *der Durst* > *durst-en/dürst-en* (E-E)
- *der Fall* > *fall-en/fäll-en* (R-R)
- *die Flamme* > *flamm-en/ab-flämm-en* (R-I)
- *der Floh* > *ent-floh-en/flöh-en* (K-K)
- *die Fron* > *fron-en/frön-en* (R-A)
- *der Fuß* > *fuß-en/füß-el-n* (D-I/K)
- *das Futter* > *futter-n/fütter-n* (I-I)
- *die Galle* > *galle-n/ver-gälle-n* (K-A)
- *das Gold* > *ver-gold-en/ver-güld-en* (D-D)
- *der Gurt* > *gurt-en/gürt-en* (I-I)
- *der Hang* > *hang-el-n/häng-en* (???)
- *der Kampf* > *kamp-el-n/kämpf-en* (R-R)
- *die Kante* > *kante-n/kente-r-n* (O-O)
- *der Kast-en* > *ein-kast-el-n/käst-el-n* (O-D)
- *der Kopf* > *ver-kopf-en/köpf-en* (K-I/K)
- *die Kraft* > *ver-kraft-en/ent-kräft-en* (???)
- *die Krone* > *über-krone-n/kröne-n* (I-I)
- *die Kunde* > *be-kunde-n/künde-n* (R-R)
- *der Laut* > *laut-en/läut-en* (???)
- *der Lohn* > *lohn-en/löhn-en* (R-I)
- *das Malz* > *malz-en/mälz-en* (R-R)
- *der Mangel* > *mangel-n/be-mängel-n* (R-R)
- *der Mantel* > *um-mantel-n/be-mäntel-n* (I-A)
- *der Mund* > *mund-en/münd-en* (K-O)
- *die Nacht* > *nacht-en/nächt-ig-en* (???)
- *der Nutz-en* > *nutz-en/nütz-en* (R-R)
- *der Papp* > *papp-en/päpp-el-n* (V-V)
- *die Platte* > *ab-platte-n/plätte-l-n* (D-D)
- *die Probe* > *probe-n/pröbe-l-n* (R-I)
- *das Rad* > *rad-el-n/räd-el-n* (I-I)
- *der Rand* > *um-rand-en/ränd-el-n* (R-D)
- *der Rauch* > *rauch-en/räuch-er-n* (R-I)
- *der Ruck* > *ruck-en/rück-en* (A-I)
- *der Schad-en* > *schad-en/schäd-ig-en* (R-R)
- *die Schale* > *ver-schale-n/schäle-n* (D-D)
- *die Schande* > *ver-schande-l-n/schände-n* (R-R)
- *der Schatz* > *schatz-en/schätz-en* (R-A)
- *der Schlamm* > *ver-schlamm-en/schlämm-en* (D-D)
- *der Schlupf* > *schlupf-en/schlüpf-en* (O-O)
- *der Schnaps* > *schnaps-en/schnäps-el-n* (R-V)
- *der Schopp-en* > *schopp-en/schöpp-el-n* (I-V)
- *die Schnauze* > *schnauze-n/schnäuze-n* (A-K)
- *die Schranke* > *be-schranke-n/ein-schränke-n* (D-D)
- *der Schwatz* > *schwatz-en/schwätz-en* (R-R)
- *der Span* > *zer-span-en/spän-en* (R-I)
- *die Spur* > *spur-en/spür-en* (A-I)
- *der Staub* > *staub-en/stäub-en* (R-R)
- *der Strom* > *ver-strom-en/ström-en* (R-A)
- *die Tafel* > *tafel-n/ver-täfel-n* (O-I)
- *der Ton* > *ver-ton-en/tön-en* (R-R)
- *der Tratsch* > *tratsch-en/ver-trätsch-en* (R-R)
- *die Walze* > *walze-n/wälze-n* (I-A)
- *das Wasser* > *wasser-n/wässer-n* (O-D)
- *die Zahl* > *zahl-en/zähl-en* (R-I)
- *der Zahn* > *zahn-en/zähn-en* (R-I)

## Morphologically complex stems

very few complex stems (90 = 3%):

- compound noun > verb (20)
- affixed noun > verb (40)
- compound noun > adjective > verb (10)
- affixed adjective > verb (20)

Noun root compounds (20)^[SELECT * WHERE like(a.WURZEL, "%-%") && a.NOMEN != " ".]

- *Ant-wort* > *antwort-en*
- *Arg-wohn* > *argwöhn-en*
- *Aug-apfel* > *be-augapfel-n*
- *Augen-schein* > * *be-augenschein-ig-en*
- *Früh-stück* > *frühstück-en*
- *Fuhr-werk* > *fuhrwerk-en*
- *Fuß-ball* > *fußball-er-n*
- *Gack-ei* > *ver-gackei-er-n*
- *Hack-stück* > *ver-hackstück-en*
- *Hoch-deutsch* > *ver-hochdeutsch-en*
- *Irr-licht* > *irrlicht-er-n*
- *Kauder-welsch* > *kauderwelsch-en*
- *Ob-acht* > *be-obacht-en*
- *Rat-schlag* > *be-ratschlag-en*
- *Schau-spiel* > *schauspiel-er-n*
- *Schlag-wort* > *ver-schlagwort-en*
- *Schwein-igel* > *schweinigel-n*
- *Voll-macht* > *be-vollmächt-ig-en*
- *Weih-nacht* > *weihnacht-en*
- *Weih-rauch* > *be-weihräuch-er-n*

Suffixed non-l/r/z/ig/lich (10)^[SELECT * ORDER BY a.STAMM WHERE a.NOMEN != " " &&  !like(a.NOMEN, "% -ung %") && !like(a.NOMEN, "% (%") && !like(a.NOMEN, "% Ge- %") && like(a.STAMM, "% -%") && !like(a.STAMM, "% -lich %") && !like(a.STAMM, "% -ig %") && !like(a.STAMM, "% -%l %") && !like(a.STAMM, "% -%r %") && !like(a.STAMM, "% -s %") && !like(a.STAMM, "% -z %") && !like(a.STAMM, "% -sch %") && !like(a.STAMM, "% -e %") && !like(a.STAMM, "% -de %").]

- *Alter-tum* > *altertüm-el-n*
- *Deutsch-tum* > *deutschtüm-el-n*
- *Faul-enz* > *faulenz-en*
- *Ge-mein-schaft* > *ver-gemeinschaft-en*
- *Ge-sell-schaft* > *ver-gesellschaft-en*
- *Kund-schaft* > *aus-kundschaft-en*
- *Wahr-heit* > *be-wahrheit-en*
- *Wirt-schaft* > *wirtschaft-en*

Prefixed (30)^[SELECT * ORDER BY a.STAMM WHERE a.NOMEN != " " && !like(a.NOMEN, "% -ung %") && !like(a.NOMEN, "% (%") && !like(a.NOMEN, "% Ge- %") && like(a.STAMM, "%- %") && like(a.VERB, "%- %").]

- *Ab-schied* > *ver-abschied-en*
- *Ab-sicht* > *be-absicht-ig-en*
- *An-lag-e* > *ver-anlage-n*
- *An-spruch* > *be-anspruch-en*
- *An-stalt* > *ver-anstalt-en*
- *An-stand* > *be-anstand-en*
- *Auf-lag-e* > *be-auflage-n*
- *Auf-trag* > *be-auftrag-en*
- *Aus-gabe* > *ver-ausgabe-n*
- *Aus-kunft* > *be-auskunft-en*
- *Be-amt-e* > *ver-beamte-n
- *Bei-stand* > *ver-beiständ-en*
- *Ein-druck* > *be-eindruck-en*
- *Ein-nahm-e* > *ver-einnahme-n*
- *Ein-spruch* > *be-einspruch-en*
- *Für-Wort* > *be-fürwort-en*
- *Ge-walt* > *ver-gewalt-ig-en*
- *Mit-leid* > *be-mitleid-en*
- *Nach-richt* > *be-nachricht-ig-en*
- *Rück-sicht* > *be-rücksicht-ig-en*
- *Un-glimpf* > *ver-unglimpf-en*
- *Un-glück* > *ver-unglück-en*
- *Ur-kunde* > *be-urkunde-n*
- *Ur-laub* > *be-urlaub-en*
- *Ur-sache* > *ver-ursache-n*
- *Ur-teil* > *ver-urteil-en*
- *Vor-mund* > *be-vormund-en*
- *Vor-rat* > *be-vorrat-en*
- *Vor-recht* > *be-vorrecht-en*
- *Vor-schuss* > *be-vorschuss-en*
- *Vor-teil* > *be-vorteil-en*
- *Vor-zug* > *be-vorzug-en*
- *Zu-schuss* > *be-zuschuss-en*

Noun compounds > Adjective > Verb (10)^[SELECT * WHERE like(a.WURZEL, "%-%") && a.ADJEKTIV != " ".]

- *Ein-heit* > *einheit-lich > *ver-einheitlich-en*
- *Gegen-stand* > *gegenständ-lich* > *ver-gegenständlich-en*
- *Gegen-wart* > *gegenwärtig* > *ver-gegenwärtig-en*
- *Nach-lass* > *nachläss-ig* > *ver-nachlässig-en*
- *Nach-teil* > *nachteil-ig* > *be-nachteilig-en*
- *Sinn-bild* > *sinnbild-lich* > *ver-sinnbildlich-en*
- *Ver-dacht* > *verdächt-ig* > *verdächtig-en*
- *Ver-stand* > *verständ-ig* > *verständig-en*
- *Viel-falt* > *vielfält-ig* > *ver-vielfältig-en*

complex adjective > verb (20)^[SELECT * ORDER BY a.STAMM WHERE a.ADJEKTIV != " " && (like(a.STAMM, "%- %") || (like(a.STAMM, "% -%") && !like(a.STAMM, "% -lich %") && !like(a.STAMM, "% -ig %") && !like(a.STAMM, "% -%l %") && !like(a.STAMM, "% -%r %") && !like(a.STAMM, "% -e%"))).]

- *all-ge-mein-er* > *ver-allgemeiner-n*
- *an-schau-lich* > *ver-anschaulich-en*
- *ein-fach* > *ver-einfach-en*
- *ein-sam* > *ver-einsam-en*
- *ein-seit-ig* > *ver-einseitig-en*
- *ein-trächt-ig* > *be-einträchtig-en*
- *ge-nehm* > *genehm-ig-en*
- *ge-wiss* > *ver-gewiss-er-n*
- *ge-wärt-ig* > *gewärtig-en*
- *harm-los* > *ver-harmlos-en*
- *lang-sam* > *ver-langsam-en*
- *leb-end-ig* > *ver-lebendig-en*
- *selbst-ständ-ig* > *ver-selbstständig-en*
- *un-echt* > *ver-unecht-en*
- *un-sicher* > *ver-unsicher-n*
- *un-treu* > *ver-untreu=en*
- *ver-ein-bar* > *vereinbar-en*
- *ver-laut-bar* > *verlautbar-en*
- *viel-fach* > *ver-vielfach-en*
- *voll-komm-en* > ver-vollkommn-en*
- *voll-ständ-ig* > *ver-vollständig-en*
- *wahr-los* > *ver-wahrlos-en*

Adjective compound:

- *schlimm-besser* > *ver-schlimmbesser-n*

## Multisyllable simplex stems

very few multisyllable stems, almost all loans (95, 3%)

verbs: 25
nouns: 65
adjectives/others: 5

Multisyllable verb otherwise very unusual (24), typically loans (3 syllable stems: benedeien, klabastern, maledeien, revoluzzen)

- *benedei-en* (< lat. *benedicere*)
- *debugg-en* (< en. *to debug*)
- *dolmetsch-en* (< turk. *dilmaç*)
- *follow-en* (< en. *to follow*)
- *kastei-en* (< lat. *castigare*)
- *kidnapp-en* (< en. *to kidnap*)
- *klabaster-n* (< it. *calpestare*)
- *kredenz-en* (< it. *credenza*)
- *maledei-en* (< lat. *maledicere*)
- *manage-n* (< en. *to manage*)
- *marach-en* (< hebr. *meragem*)
- *perform-en* (< en. *to perform*)
- *piesack-en* (< nd. *Pesek*)
- *promot-en* (< en. *to promote*)
- *rament-en* (< fr. *regiment*)
- *rasaun-en* (< fr. *razonar*)
- *reboot-en* (< en. *to reboot*)
- *recycel-n* (< en. *to recycle*)
- *revoluzz-en* (< lat. *revolutio*)
- *schamfil-en* (< lat. *calefare*)
- *stibitz-en*
- *strabanz-en* (< it. *stravagante*)
- *ver-teidig-en* (< mhd. *tagedingen*)
- *werkstell-ig-en* (< mhd. *ze werce stellen*)

Multisyllable nouns (65), note reduction, e.g. Atem>atmen, *Leumund* > *verleumden*

- *Abenteuer* > *abenteuer-n* (< fr. *aventure*)
- *Arbeit* > *arbeit-en* 
- *Baldower* > *baldower-n* (< hebr. *ba‛al-dāwār*)
- *Ballast* > *ballast-en*
- *Batik* > *batik-en* (< nl. < maleis.)
- *Berserker* > *berserker-n* (< nord. *ber-serkr*)
- *Binokel* > *binokel-n* (< it. *bin oculi*)
- *Computer* > *computer-n* (< en.)
- *Container* > *container-n* (< en.)
- *Design* > *design-en* (< en.)
- *Download* > *download-en* (< en.)
- *Echo* > *echo-en* (< gr. *ēchṓ*)
- *Einfluss* > *be-einfluss-en* (< lat. *influentia*)
- *Elend* > *ver-elend-en* 
- *Email* > *email-en* (< en.)
- *Fittich* > *be-fittig-en* 
- *Franzose* > *französe-l-n* 
- *Heimat* > *be-heimat-en* 
- *Heirat* > *heirat-en* 
- *Herberge* > *be-herberge-n* 
- *Inhalt* > *be-inhalt-en* 
- *Inliner* > *inliner-n* (< en.)
- *Interview* > *interview-en* (< en.)
- *Kalauer* > *kalauer-n* (< fr. *calembour*)
- *Kapitel* > *ab-kapitel-n* (< lat. *capitulum*)
- *Kapriole* > *kapriole-n* (< it. *capriola*)
- *Karbatsche* > *karbatsche-n* (< turk. *kırbaç*)
- *Karriol* > *karriol-en* (< fr. *carriole*)
- *Katheter* > *katheter-n* (< gr. *kathetḗr*)
- *Kiebitz* > *kiebitz-en* 
- *Konditor* > *konditer-n* (< lat. *condītor*)
- *Kontakt* > *kontakt-en* (< lat. *contactus*)
- *Konterfei* > *konterfei-en* (< fr. *contrefait*)
- *Krakeel* > *krakeel-en* (fr. *querelle*)
- *Kredenz* > *kredenz-en* (< it. *credenza*) 
- *Leumund* > *be-leumund-en* 
- *Mäander* > *mäander-n* (< gr. *maíandros*)
- *Maloche* > *maloche-n* (< jidd. *maloche*)
- *Maniküre* > *maniküre-n* (< fr. *manicure*)
- *Menetekel* > *menetekel-n* (< aram. *mene teqel*)
- *Messing* > *ver-messing-en* 
- *Monitor* > *monitor-en* (< en.)
- *Orakel* > *orakel-n* (< lat. *oraculum*)
- *Palaver* > *palaver-n* (< span. *palabra*) 
- *Pediküre* > *pediküre-n* (< fr. *pédicure*)
- *Picknick* > *picknick-en* (< en. < fr. *piquer*)
- *Podcast* > *podcast-en* (< en.)
- *Pogo* > *pog-en* (< en.)
- *Posaune* > *posaune-n* (< lat. *būcina*)
- *Predig-t* > *predig-en* (< lat. *praedicāre*)
- *Prophetie* > *prophezei-en* (< gr. *prophḗtēs*)
- *Retweet* > *retweet-en* (< en.)
- *Review* > *review-en* (< en.)
- *Rigole* > *rigole-n* (< fr. *rigole*)
- *Rumor* > *rumor-en* (< lat. *rūmor*)
- *Scharmützel* > *scharmützel-n* (< fr. *escarmuche*)
- *Scharwenzel* > *scharwenzel-n* (< tsch. *červenc*)
- *Spektakel* > *spektakel-n* (< lat. *spectāculum*)
- *Tobak* > *ver-tobak-en* (< fr.)
- *Trompete* > *trompete-n* (< fr. *trompette*)
- *Update* > *update-n* (< en.)
- *Upgrade* > *upgrade-n* (< en.)
- *Upload* > *upload-en* (< en.)
- *Urass* > *urass-en* 
- *Zickzack* > *zickzack-en* (< fr. *zigzag*)

Adjective/Other:

- *(Johann) Ballhorn* > *ver-ballhorn-en*
- *(Henry) Bessemer* > *bessemer-n*
- *bequem* > *bequem-en*
- *bereit* > *bereit-en*
- *empor* > *empör-en*
- *genug* > *genüg-en*

## Noun roots

direction of derivation is variable

Nominalisations:

- das VERB-en works always
- die PREVERB-STEM-ung works always
- das Ge-STEM-e works always

all other patterns are interesting

- Ge-STEM without -e (and with changed sound, ie. Umlaut, Ablaut)
- VERB-en with die/der
- STEM-ung without preverb

- ending in -e/-en are included as "identical"
- but note etymology "Samen" < sa + men, but verbstem is "sa"
- but note the extra "n" in wappn-en/Wappen and zeichn-en/Zeichen

1260 completely identical (38% of all 3355 stems, 68% of all 1850 noun-based stems)^[SELECT * WHERE !like(a.VERB, "%- %") && !like(a.VERB, "% -% -%") && !like(a.VERB, "%(U)%") && a.NOMEN != " " && !like(a.NOMEN, "% Ge- %") && !like(a.NOMEN, "% -ung %") &&!like(a.NOMEN, "% (%").]

590 with differences: Three different variants (and all possible combinations occur, maybe a very slight preference for markings to co-occur, but statistical significance difficult to evaluate. Effects are really small. strongest effect: Suffix+Umlaut phi = 0.23 (freq: 44, 82, 133, 1592)):

- with Prefix (390/1850)^[SELECT * WHERE a.NOMEN != " " && !like(a.NOMEN, "%Ge- %") && !like(a.NOMEN, "% -ung%")  && !like(a.NOMEN, "%(%") && like(a.VERB, "%- %").]
- with Suffix (125/1850)^[SELECT * WHERE a.NOMEN != " " && !like(a.NOMEN, "%Ge- %") && !like(a.NOMEN, "% -ung%")  && !like(a.NOMEN, "%(%") && like(a.VERB, "% -% -%").]
- with Umlaut (180/1850)^[SELECT * WHERE a.NOMEN != " " && !like(a.NOMEN, "%Ge- %") && !like(a.NOMEN, "% -ung%")  && !like(a.NOMEN, "%(%") && like(a.VERB, "%(U)%").]

additionally 160 Derived nouns (ge-, -ung, ablaut):^[SELECT * WHERE (like(a.NOMEN, "% -ung %") || like(a.NOMEN, "% Ge- %") || like(a.NOMEN, "%(A)%")).]

## Adjective roots


219 out of about 300 monomorphemic adjectives: most are verbal roots (73%)!!! 

gering ~ verringern
keck ~ erquicken
doppelt ~ verdoppeln
freuen ~ froh

also some with -ieren

brüsk ~ brüskieren
egal ~ egalisieren
extrem ~ extremisieren
fad ~ fadisieren
komplett ~ komplettieren
rar ~ rarefizieren
stolz ~ stolzieren
total ~ totalisieren

remaining about 70 native monomorphemic adjectives that cannot be used as the root for a verb:

barsch, besondere, blank, brav, bunt, direkt, doof, einzig, enorm, ernst, erst, feig, feist, fesch, flink, flott, forsch, genau, geschwind, heikel, heiser, herb, hinter, jäh, kaputt, kess, keusch, klamm, krass, krude, lasch, lau, lässig, lecker, leise, letzt, lila, link, nächste, nackt, nett, orange, prüde, rank, rosa, rüde, sacht, schal, schick, schief, schlau, schnöde, schroff, schwül, seicht, selten, steil, stur, tapfer, träge, ungefähr, untere, vage, viel, wacker, weh, weise, wirsch, zäh

creative innovations with prefixes:

verschroffen
erblanken
verdoofen
verensten

- Der Sound wird bleiben und politische Auseinandersetzungen weiter verschroffen. https://www.main-echo.de/region/franken-bayern/eine-katastrophe-die-wahlergebnisse-der-teils-rechtsextremistischen-afd-art-8050452
- Alle anderen, so Waffen tragen, gelten als Störer des gräflichen Turnierfriedens, sofern sie ihre Waffen erblanken und dem Wappen Reichsforsts oder des Hauses Luring nicht Achtung zollen. https://garetien.de/index.php/Geschichten:Moderne_Zeiten_-_Turnierfriede
- Wir verdoofen sie auch noch ein bißchen, denn Bildungsinvestitionen werfen nicht schnell genug was ab. https://taz.de/Wuetend-werden-reicht-nicht/!1436062/
- Sich verernsten und still werden. https://benjamingerono.de/2023/03/29/dem-augenblicke-nicht-entfliehen-eine-gruendonnerstags-meditation/
- das bier ist schon verherbt. Deutsches Wörterbuch von Jacob und Wilhelm Grimm. Lfg. 3 (1889), Bd. XII,I (1956), Sp. 562, Z. 27. https://www.dwds.de/wb/dwb/verherben

# Suffixes

double?

- blink-en > blin-z-en > blin-z-el-n
- dreh-en > drechseln > drechslern

Consonant change? Old form retained with suffix

kamp-el-n > kämpf-en
schnupp-er-n > schnupf-en
schrump-el-n > schrumpf-en
stemp-el-n > stampf-en
stup-s-en > stupf-en
drech-sel-n > dreh-en
puck-er-n > poch-en
rap-sch-en > raff-en

360 transparant examples out of 3350 verb stems (~ 11%)

±180 verbs with suffix l/r/s.^[SELECT * WHERE like(a.VERB, "% -% -%") && (a.NOMEN == " " || like(a.NOMEN, "% -ung %") || like(a.NOMEN, "%(%") || like(a.NOMEN, "% Ge- %")) && a.ADJEKTIV == " " && a.WEITERE == " " ORDER BY a.BEDEUTUNG.]

## *l* (180)

[@kana2017] [@audring2021]

Germanic instrumental "l" [@kroonen2017]

diminutive -l- discussed in Weidhaas & Schmid [-@weidhaas2015] "iterative", "small pieces", "low intensity" ("playfull-tentative", "child-related")

Pfeifer [@pfeiffer1993] "Iterativbildung", "deminuierendes Iterativum", "Intensivbildung" "Gerätenamen" -ila, Gerätebezeichnungen germ. -ila-


Among the 3350 stems investigated, 

- 560 *eln*-verbs

there are about 235 stems in which a suffix *‑l* can be separated from the root. These will be discussed in this section. 

(212 + 21 unclear + 278 unanalysable + 45 other)

**Diminutive** (60+25)

- Action > Low intensity (33 + 9 unanalysable)
- Action > Multiple small steps (15)
- Action > Back and forth (7 + 16 unanalysable)
- Action > Repetition (5)

**Instrumental** (74+90)

- Instrument > Use (40)
- Instrument > Diminutive > Use (12 + 84 unanalysable)
- Process > Instrument > Use (22+6)

**Resultative** (23+70)

- Result > Produce (8)
- Result > Diminutive > Produce (16 + 68 unanalysable)
- Process > Result > Produce (7+2)

**Similative** (37+28)

- Animate > Be like (12)
- Property > Be like (10)
- Property > Animate > Be like (2)
- Animate > Diminutive > Be like (2 + 12 unanalysable)
- Process > Animate > Be like (2)
- Inanimate > Do like (9 + 16 unanalysable)

**Causative** (10+7)

- Noise > Cause to be (6)
- Property > Cause to be (4 + 7 unanalysable)

(21 unclear)
(26 noise production human)
(6 noise production inanimate)
(58 unanalysable)
(13 other)

Examples of no relation between verbs (32)

- atzen "Vogelbrut füttern" ≠ atzeln "stehlen"
- äußern "aussprechen" ≠ äußerln "Hund auslassen"
- (Bast) ent-basten "Bast entfernen" ≠ basteln "Arbeiten herstellen"
- baumen "auf einen Baum klettern" ≠ baumeln "schaukeln"
- aus-beinen "Knochen lösen" ≠ beineln "trippeln"
- bocken "nicht gehorchen" ≠ böckeln "stinken"
- über-borden "über das Maß hinausgehen" ≠ bördeln "Metallverarbeitung"
- ver-buschen "überwuchert werden" ≠ büscheln "zu einem Büschel zusammenfassen"
- enden "zu Ende gehen" ≠ endeln "Ende eines Gewebes einfassen"
- fischen "Fisch fangen" ≠ fischeln "nach Fisch riechen"
- frommen "nützen" ≠ frömmeln "sich fromm darstellen"
- fußen "stützen" ≠ füßeln "mit den Füßen unter dem Tisch Berührung suchen"
- giften "ärgern, schimpfen" ≠ gifteln "Gift einsetzen"
- gründen "Grundlage schaffen" ≠ gründeln "auf dem Grund von Gewässern nach Nahrung suchen"
- hacken "zerkleinern" ≠ hackeln "schuften, streiten"
- haken "festhängen" ≠ häckeln "Handarbeiten"
- ab-karten "verabreden" ≠ karteln "Karten spielen"
- köpfen "Kopf abschlagen ≠ köpfeln "mit dem Kopf etwas machen"
- ab-kragen "Stein abschrägen" ≠ ab-krageln "Hals umdrehen"
- lichten "weniger dicht werden" ≠ lichteln "Kerzen anzünden"
- (Papp) pappen "kleben" ≠ päppeln "gut ernähren"
- (Probe) proben "Aufführung üben" ≠ pröbeln "ohne Erfolg Versuche durchführen"
- (Ramme) rammen "in den Boden treiben, zusammenstoßen" > rammeln "heftig rütteln"
- (Ring) ringen "kämpfen ≠ ringeln "ein Ringel formen"
- sausen "schnell bewegen" ≠ säuseln "leise tönend" ^[sausen has older meaning "rauschen", both go back to "Saus"="ausgelassene Fröhlichkeit".]
- schänden "entehren" ≠ ver-schandeln "verunstalten"
- schnippen "Finger schnalzen" ≠ schnippeln "kleine Schnitte machen" ^[Schallwort "schnippschnapp".]
- schwänzen "Aufgabe nicht erfüllen" ≠ schwänzeln "mit dem Schwanz wedeln"
- spitzen "mit einer Spitze versehen" ≠ spitzeln "aushorchen"
- stocken "zu Stillstand kommen" ≠ stöckeln "in Stöckelschuhen gehen"
- tuschen "mit Tusche malen" ≠ tuscheln "heimlich sprechen"
- ab-watschen "ohrfeigen" ≠ watscheln "schwanken"

### Verb root > *l*-verb stem (95)

low intensity > multiple small steps > vibration > repetition
low intensity > lovingly

Action > Low intensity:^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == "Diminutiv".]

- *äug-en* > *äug-el-n* ("heimlich blicken")
- *brat-en* > *brät-el-n* ("auf schwachem Feuer leicht braten")
- *brumm-en* > *brumm-el-n/brümm-el-n* ("leise brummen")
- *deut-en* > *deut-el-n* ("spitzfindig, kleinlich deuten")
- en. *to drip* (tröpfen) > *dripp-el-n* ("leicht regnen")
- *fach-en* ("Feuer anblasen") > *fäch-el-n* ("sanft wehen")
- *frost-en* > *fröst-el-n* ("leicht frieren")
- en. *grab* ("greifen") > *grabb-el-n* ("suchend wühlen")
- *gräm-en* > *gräm-el-n* ("missmutig sein")
- *hatsch-en* ("mühsam gehen") > *hätsch-el-n* ("streicheln")
- *hust-en* > *hüst-el-n* ("leicht husten")
- *kämpf-en* > *kamp-el-n* ("raufen, bolzen")
- *kipp-en* > *kipp-el-n* ("Gefahr laufen umzukippen")
- *koch-en* > *köch-el-n* ("leicht kochen")
- *er-krank-en* > *kränk-el-n* ("ständig leicht krank sein")
- *kraus-en* > *kräus-el-n* ("zart wellen")
- *kusch-en* ("still liegen") > *kusch-el-n* ("sich anschmiegen")
- *lach-en* > *läch-el-n* ("ein wenig und lautlos lachen")
- *lieb-en* > *lieb-el-n* ("flüchtig lieben, flirten")
- *quack-en* ("Froschgeräusche machen") > *quack-el-n* ("schwatzen")
- ahd. *rīs-an* ("fallen") > *ries-el-n* ("sacht rinnen")
- ie. \**reuk* ("brüllen") > *röch-el-n* ("schnarchend atmen")
- *ruck-en* > *ruck-el-n* ("leichte Rucke machen")
- *sauf-en* > *süff-el-n* ("genüsslich trinken")
- *saus-en* ("rauschen") > *säus-el-n* ("leise tönend")
- ndl. *smek-en* ("flehen") > *schmeich-el-n* ("zärtlich sein, liebkosen")
- ndl. *snuiv-en* ("schnauben") > *schnüff-el-n*
- *schreib-en* > *skribb-el-n ("kritzeln")
- *spott-en* > *spött-el-n* ("leich, harmlos spotten")
- *streich-en* > *streich-el-n* ("liebkosend streichen")
- *tatsch-en* ("plump anfassen") > *tätsch-el-n* ("liebkosend streicheln")
- *trott-en* > *trott-el-n* ("langsam gehen")
- *werk-en* > *werk-el-n* ("gemütlich werken")
- mhd. *winsen* > *wins-el-n ("weinen")
- *zisch-en* > *zisch-el-n* ("zischend flüstern")
- *zuck-en* > *zuck-el-n/zock-el-n* ("langsam fortbewegen")
- *zünd-en* > *zünd-el-n* ("mit Feuer leichtsinnig umgehen")

Action > Multiple small steps^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == "KleineSchritte".]

- *ein-brock-en* > *bröck-el-n* ("in kleine Stücke zerfallen")
- *falt-en* > *fält-el-n* ("in kleine, eng aufeinanderfolgende Falten falten")
- *häng-en* > *hang-el-n* ("durch abwechselndes Weitergreifen beider Hände fortbewegen")
- *häuf-en* ("zu einem Haufen formen") > *häuf-el-n* ("zu kleinen Haufen aufschichten")
- *hopp-en* ("hüpfen") > *hopp-el-n* ("kleine Sprünge machen")
- *kremp-en* ("Hutrand nach oben biegen") > *kremp-el-n* ("mehrmals umschlagen")
- *schnipp-en* > *schnipp-el-n* ("viele kleine Schnitte machen")
- *schnitz-en* > *schnitz-el-n/schnetzeln* ("in kleine Stücke schneiden")
- *stech-en* > *stich-el-n* ("mit kleinen Stichen sticken")
- *tanz-en* > *tänz-el-n* ("mit kurzen, beschwingten, tänzerischen Schritten bewegen")
- *tapp-en* ("unsicher im Dunkel bewegen") > *tapp-el-n* ("mit kleinen, schnellen Schritten laufen")
- *tipp-en* ("leicht berühren") > *tipp-el-n* ("mit kleinen Schritten gehen")
- *trapp-en* > *trapp-el-n* ("mit leichten, kurzen, schnellen Schritten laufen")
- *trief-en* ("nass sein") > *träuf-el-n* ("tröpfen")
- en. *trip* ("stolpern") > *tripp-el-n* ("mit kleine Schritte laufen")
- *tropf-en* > *tröpf-el-n* ("in einzelnen Tropfen herabfallen")

Action > Back and forth^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == "Hinundher".]

- *juck-en* ("reizend schmerzen") > *juck-el-n* ("unruhig hin und her rutschen")
- *ramm-en* > *ramm-el-n* ("heftig rütteln")
- *reib-en* > *ribb-el-n* ("aufrauhen")
- *reib-en* > *rubb-el-n* ("kräftig reiben")
- *zer-rütt-en* ("zerstören") > *rütt-el-n* ("schnell hin und her bewegen")
- mhd. *slīt-en* > *schlitt-el-n* ("gleiten")
- *schütt-en* ("herausfließen lassen") > *schütt-el-n* ("ruckartig hin und her bewegen")
- *schwapp-en* ("verschütten") > *schwabb-el-n/schwapp-el-n* ("zitternd hin und her bewegen")
- mhd. *wab-en* ("bewegen") > *wabb-el-n*
- *watsch-en* > *watsch-el-n* ("schwanken")
- mhd. *wag-en* ("bewegen") > *wack-el-n* ("anhaltend hin und her bewegen")
- *wrigg-en* > *wrigg-el-n* ("ein Boot bewegen durch hin und her rudern")

Action > Repetition^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == "Wiederholung".]

- *bett-en* > *bett-el-n* ("mehrmals beten")
- *blinz-en* > *blinz-el-n* ("mehmals blinzen")
- *dräng-en* > *dräng-el-n* ("unablässig drängen")
- *funk-en* > *funk-el-n* ("Lichtstrahlen von wechselnder Helligkeit aussenden")
- *wind-en* > *wend-el-n*
- *werf-en* > *worf-el-n* ("Getreide werfen zum Spreu trennen")

Other^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == " " && a.NOMEN == " " && a.ADJEKTIV == " '.]

- nd. *bas-en* ("Unsinn reden") > *ver-bas-el-n* ("vergessen")
- mhd. *best-en* ("schnüren, binden") > *bast-el-n*
- mhd. *geng-en* ("gehen lassen") > *gäng-el-n* ("bevormunden")
- *grumm-en* > *grumm-el-n* ("dröhnen")
- *hack-en* > *hack-el-n* ("hart arbeiten")
- *hak-en* > *hak-el-n* ("hängen bleiben, festsitzen")
- nd. *hump-en* > *hump-el-n* ("hinken")
- *husch-en* ("schnell und leise bewegen") > *husch-el-n* ("einhüllen, oberflächlich arbeiten")
- *karte-n* > *karte-l-n* ("mit Karten spielen")
- *kett-en* > *kette-l-n* ("in Handarbeit Maschen verbinden")
- *misch-en* > *misch-el-n* ("durcheinander bringen")
- *mumm-en* > *mümm-el-n* ("kauen")
- *mumm-en* > *mumm-el-n* ("undeutlich sprechen")
- *mumme-n* > *mumme-l-n* ("einhüllen")
- *reib-en* > *reb-el-n* ("pflücken")
- *schnack-en* ("plaudern") > *schnack-el-n* ("schnalzen")
- mhd. *schurg-en* ("stoßen") > *schurig-el-n* ("schikanieren")
- *serb-en* > *serb-el-n* ("kränkeln, welken")
- *tramp-en* > *tramp-el-n* ("stampfen")
- *be-weg-en* > *ab-wieg-el-n* ("beschwichtigen")
- *wurst-en* > *wurst-el-n/würst-el-n* ("im alten Trott arbeiten")
- mhd. *zwirb-en* > *zwirb-el-n* ("wirbeln")

*-sel*^[SELECT * WHERE (like(a.VERB, "% -sel %") || like(a.VERB, "% -zel %")) && a.NOMEN == " ".]

- *brat-en* > *brut-zel-n*
- *brenn-en* > *bren-zel-n*
- *dreh-en* > *drech-sel-n*
- *snack-en* > *schnack-sel-n*

### Noun root > *l*-verb stem (66)

Instrument > Use:^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == "Instrument".]

- *Bein* > *bein-el-n* ("mit kleinen, schnellen Schritten laufen")
- *Bürste* > *bürst-el-n* ("mit einer Bürste bearbeiten")
- *Fad-en* > *fäd-el-n* ("mit einem Faden ziehen")
- *Fuß* > *füß-el-n* ("mit den Füßen unter dem Tisch Berührung suchen")
- *Gift* > *gift-el-n* ("Gift einsetzen")
- *Kopf* > *köpf-el-n* ("mit dem Kopf etwas tun (Ball weg, in Wasser springen)")
- *Hacke* > *hacke-l-n* ("mit der Hacke den Boden lockern")
- *Kraxe* > *kraxe-l-n* ("mit Kraxe (Anstrengung) klettern")
- *Nase* > *näse-l-n* ("mit der Nase sprechen")
- *Platte* > *platte-l-n* ("mit der Schuhplatte tanzen")
- *Probe* > *pröbe-l-n* ("Versuche durchführen, ohne Erfolg")
- *Rad* > *rad-el-n* ("mit dem Rad fahren")
- *Rad* > *räd-el-n* ("mit einem Rad arbeiten beim Kochen/Nähen")
- *Sand* > *sänd-el-n* ("mit Sand spielen")
- *Schwanz* > *schwänz-el-n* ("mit dem Schwanz wedeln")
- *Zange* > *zange-l-n* ("mit Werkzeug arbeiten")
- *Zunge* > *zünge-l-n* ("mit der Zunge schnell bewegen")

Result > Produce:^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == "Resultat".]

- *Ast* > *ver-äst-el-n* ("viele Äste ausbilden")
- *Ende* > *ende-l-n* ("Ende eines Gewebes bearbeiten")
- *Krise* > *krise-l-n* ("eine Krise passiert")
- *Kritik* > *kritt-el-n* ("Kritik üben")
- *Kunst* > *künst-el-n*
- *Licht* > *licht-el-n* ("Kerzen brennen lassen")
- *Schande* > *ver-schande-l-n* ("zur Schande machen")
- *Sport* > *sport-el-n*
- *Suff* > *süff-el-n*

Animate > Be like:^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == "Lebewesen".]

- *Ahne* > *ähne-l-n* ("gleich aussehen")
- *Bock* > *böck-el-n* ("einen durchdringenden Geruch haben; wie ein Bock riechen")
- *Fisch* > *fisch-el-n* ("wie Fisch riechen")
- *Franzose* > *französe-l-n* ("französisch nachahmen")
- *Grant* > *grant-el-n*
- *Krabbe* > *krabbe-l-n* ("kriechen, bewegen wie eine Krabbe")
- *Mensch* > *mensch-el-n* ("Mensch sein")
- *Pack* ("Gesindel") > *pack-el-n* ("heimlich verabreden")
- *Quappe* ("Fisch") > *quappe-l-n/quabbe-l-n* ("wabbelig hin und her bewegen")
- ahd. *Ram* ("Bock") > *ramme-l-n* ("heftig rütteln")
- *Range* ("Lebhaftes Kind") > *range-l-n* ("raufen")
- *Sachse* > *sächse-l-n* ("sächsisch reden")
- *Schlange* > *schlänge-l-n* ("wie ein Schlange fortbewegen")
- *Schwabe* > *schwäbe-l-n* ("schwäbisch reden")
- *Wild* > *wild-el-n*

Inanimate > Do like:^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == "Analogon".]

- *Altertum* > *altertüm-el-n* ("übertrieben archaisieren")
- *Baum* > *baum-el-n* ("schaukeln")
- *Deutschtum* > *deutschtüm-el-n* ("handeln mit aufdringlicher Betonung des Deutschtums")
- *Hanse* > *hänse-l-n* ("necken, wie bei Aufnahme in Hanse")
- *Heim* > *an-heim-el-n* ("wohlvertraut sein")
- *Herbst* > *herbst-el-n* ("herbstig sein")
- *Pfriem* ("Vorstecher") > *pfriem-el-n* ("mit den Finger herumstechen")
- lat. *tant-um* ("Kleinigkeit") > *tänd-el-n* ("Nichtiges tun")
- *Vernunft* > *vernünft-el-n* ("mit Vernunft argumentieren")
- *Witz* > *witz-el-n* ("mit Witz sprechen")

Ort^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == "Ort".]

- *Grund* > *gründ-el-n* ("auf dem Grund von Gewässern nach Nahrung suchen")
- *Kast-en* > *ein-kast-el-n ("einsperren")

Dingteil^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == "Meronym".]

- *Kast-en* > *käst-el-n* ("mit Rechtecken bemustern")
- *Krag-en* > *ab-krag-el-n* ("Hals umdrehen")
- *Platte* > *plätte-l-n* ("mit Platten belegen")
- *Quant* > *quant-el-n* ("in Quanten aufteilen")
- *Rand* > *ränd-el-n* ("mit einem Rand versehen")
- *Riefe* > *riefe-l-n* ("mit Riefen versehen")
- *Sand* > *sand-el-n* ("mit Sand bestreuen")
- *Strich* > *strich-el-n* ("mit kleine Striche versehen")
- *Stück* > *stück-el-n* ("aus kleinen Stücken zusammensetzen")

Nahrung^[SELECT * WHERE like(a.VERB, "% -%l %") && a.BEDEUTUNG == "Verzehr".]

- *Papp* > *päpp-el-n* ("mit Papp ernähren")
- *Schnaps* > *schnäps-el-n* ("Schnaps trinken")
- *Schoppen* > *schöpp-el-n* ("Schoppen trinken")

### Adjective root > *l*-verb stem (15)

examples^[SELECT * WHERE like(a.VERB, "% -%l %") && a.ADJEKTIV != " ".]

Property > Be like (intransitive):

- *blöd* > *blöd-el-n* ("Unsinn reden")
- *fremd* > *fremd-el-n* ("misstrauisch sein")
- *fromm* > *frömm-el-n* ("übertriebene Frömmigkeit zur Schau stellen")
- *gram* > *gräm-el-n* ("missmutig sein")
- *jidd-isch* > *jidd-el-n* ("jiddisch sprechen")
- *klug* > *klüg-el-n* ("scharf nachdenken")
- *muff* > *müff-el-n* ("muff sein")
- *schwach* > *schwäch-el-n* ("schwach sein")
- *stumm* > *stamm-el-n* ("stotternd sprechen")
- *wild* > *wild-el-n* ("wild gebärden")

Property > Cause to be (transitive):

- *äußer* > *äußer-l-n* ("Hund auslassen")
- *fies* > *fies-el-n* ("winzige Teile ablösen")
- *licht* > *licht-el-n* ("Kerzen anzünden")
- *zu-samm-en* > *samm-el-n* ("zusammen bringen")
- *zart* > *ver-zärt-el-n* ("weichlich erziehen")

### Onomatopoetic root > *l*-verb stem (4)

Animate Noise^[SELECT * WHERE like(a.VERB, "% -%r %") && a.BEDEUTUNG == "Tiergeräusch" && a.WEITERE != " ".]

- *gack* > *gack-el-n*
- *kak* > *kakel-n*

Human Noise^[SELECT * WHERE like(a.VERB, "% -%r %") && a.BEDEUTUNG == "Stimmgeräusch" && a.WEITERE != " ".]

- *jo* > *jodel-n*
- en. *tush* > *tusch-el-n* ("heimlich sprechen")

### Verb root > *l*-noun stem

Noun (with "l") is instrument to perform the action of the verb (without "l"), verb (with "l") describes doing something with the instrument (20)

Process > Instrument > Use:^[SELECT * WHERE like(a.STAMM, "% -el %") && like(a.BEDEUTUNG, "%Instrument").]

- *bieg-en* > *Büg-el* > *bügel-n*
- mhd. *teng-en* ("schlagen") > *Deng-el* > *dengel-n*
- *fass-en* > *Fess-el* > *fessel-n*
- *flieg-en* > *Flüg-el* > *flügel-n*
- *hant-ier-en* > *Hant-el* > *hantel-n*
- *heb-en* > *Heb-el* > *hebel-n*
- *henk-en* ("aufhängen") > *Henk-el* > *henkel-n* ("am Henkel tragen")
- ie. \**keup* ("biegen") > *Hob-el* > *hobel-n*
- *kling-en* > *Kling-el* > *klingel-n* 
- *klopp-en* > *Klöpp-el* > *klöppel-n*
- fr. *courbe* ("krumm") > *Kurb-el* > *kurbel-n*
- ie. \**lab* ("lecken") > *Löff-el* > *löffel-n*
- ahd. *meiʒ-an* ("schneiden") > *Meiß-el* > *meißel-n*
- *raffen* > *Raff-el* > *raffel-n*
- ahd. *rasp-en* ("kratzen") > *Rasp-el* > *raspel-n*
- *schaff-en* > *Scheff-el* > *scheffel-n*
- *schlag-en* > *Schläg-el* > *schlägel-n*
- *schließ-en* > *Schlüss-el* > *schlüssel-n*
- *schnaub-en* > *Schnab-el* > *schnäbel-n*
- *stampf-en* > *Stemp-el* > *stempel-n*
- *stech-en* > *Stach-el* > *stachel-n*
- en. *drum* > *Tromm-el* > *trommel-n*
- *werf-en* > *Würf-el* > *würfel-n*
- *zieh-en* > *Züg-el* > *zügel-n*

Dingteil^[SELECT * WHERE like(a.STAMM, "% -%l %") && a.BEDEUTUNG == "Meronym".]

- *deck-en* > *Deck-el* > *deckel-n*
- fries. *dubb-en* ("stoßen") > *Düb-el* > *dübel-n*
- *wind-en* ("drehen") > *Wind-el* > *windel-n*

Process > Result > Produce^[SELECT * WHERE like(a.STAMM, "% -el %") && a.BEDEUTUNG == "Resultat".]

- *henk-en* ("aufhängen") > *Henk-el* > *henkel-n* ("mit einem Henkel versehen")
- *knot-en* > *Knudd-el* > *knuddel-n*
- ie. \*sap ("schmecken") > *Sabb-el* > *sabbel-n*
- *scheid-en* > *Scheit-el* > *scheitel-n*
- *schrumpf-en* > *Schrump-el* ("Runzel") > *schrumpel-n*
- *schwind-en* ("vermindern") > *Schwind-el* > *schwindel-n*
- *spreng-en* > *Sprenk-el* > *sprenkel-n*
- ahd. *tūm-ōn* ("kreisen") > *Taum-el* > *taumel-n*
- mhd. *want-en* ("drehen") > *Wand-el* > *wandel-n*

Process > Animate > Be like:^[SELECT * WHERE like(a.STAMM, "% -el %") && a.BEDEUTUNG == "Lebewesen".]

- *atz-en* > *Atz-el* > *atzel-n* ^[atzen "Vogelbrut füttern" > die Atzel "Elster" > atzeln "stehlen".]
- nl. *kruip-en* ("kriechen") > *Krüppel* > *ver-krüppel-n*
- muff-en ("murren") > Muff-el > *muffel-n* ("mürrisch sprechen")
- *schling-en* > *Schling-el* ("Schelm, Umherschlingender") > *schlingel-n*
- *spitz-en* > *Spitz-el* ("Ohren-spitzender") > *spitzel-n*

Analogon^[SELECT * WHERE like(a.STAMM, "% -el %") && a.BEDEUTUNG == "Analogon".]

- *fecht-en* > *Fucht-el* > *fuchtel-n* ("wie mit einer Fuchtel bewegen")
- *kreis-en* > *Kreis-el* > *kreisel-n* ("wie ein Kreisel drehen")

Empfindung^[SELECT * WHERE like(a.STAMM, "% -el %") && a.BEDEUTUNG == "Empfindung".]

- *graus-en* > *Grus-el* > *grusel-n*
- *prick-en* > *Prick-el* > *prickel-n*
- *raff-en* > *Rapp-el* > *rappel-n*

(*-sel*)

Process > Instrument > Use^[SELECT * WHERE like(a.STAMM, "% -sel %") && a.BEDEUTUNG == "Instrument".]

- ie. \**ag* ("(Arme) schwingen") > *Ach-sel* > *achsel-n*
- *funk-en* > *Fun-zel* > *funzel-n*
- ie. \**kap* ("fassen") > *Hasp-el* > haspel-n
- *rat-en* > *Rät-sel* > *rätsel-n*
- *stopp-en* > *Stöp-sel* > *stöpsel-n*

Process > Result > Produce^[SELECT * WHERE like(a.STAMM, "% -sel %") && a.BEDEUTUNG == "Resultat".]

- *hack-en* > *Häck-sel* > *häcksel-n*
- *schnipp-en* > *Schnip-sel* > *schnipsel-n*
- *weich-en* > *Wech-sel* > *wechsel-n*

### Noun root > *l*-noun stem

Instrument > Diminutive > Use:^[SELECT * WHERE like(a.STAMM, "% -%l %") && a.BEDEUTUNG == "Instrument>Diminutiv".]

- en. *bud* ("Knospe") > *Beut-el* > *beutel-n*
- *Bord* > *Börd-el* > *bördel-n* ^[Bord "Reling des Schiff" > Bördel "gebogener Metallring" > bördeln "Metallverarbeitung".]
- germ. \**gaiza* ("Speer") > *Geiße-l* > *geißel-n*
- *Hak-en* > *Häk-el* > *häkel-n* 
- nl. *keg* ("Keil") > *Keg-el* > *kegel-n*
- germ. \**knab* ("Stock") > *Kneb-el* > *knebel-n*
- *Knoch-en* > *Knöch-el* > *über-knöchel-n*
- *Nabe* > *Nabe-l* > *ab-nabel-n*
- *Nock* ("Hügel") > *Nuck-el* > *nuckel-n*
- *Spat-en* > *Spacht-el* > *spachtel-n*
- *Stock* > *Stöck-el(Schuh)* > *stöckel-n*

Result > Diminutive > Produce:^[SELECT * WHERE like(a.STAMM, "% -%l %") && a.BEDEUTUNG == "Resultat>Diminutiv".]

- *Band* > Bänd-el > *an-bändel-n*
- *Breze* > *Brezel* > *auf-brezel-n*
- ahd. *Brod* ("Brühe") > *Brod-el* > *brodel-n*
- *Bros-ame* > *Brös-el* > *brösel-n*
- *Bund* > *Bünd-el* > *bündel-n*
- *Busch* > *Büsch-el* > *büschel-n*
- *Buss > *Buss-el* > *bussel-n*
- *Fase(r)* > *Fusse-l* > *fussel-n*
- *Graupe* > *Graupe-l* > *graupel-n*
- *Kies* > *Kies-el* > *ver-kiesel-n*
- nl. *kring* ("Kreis") > *Kring-el* > *kringel-n*
- *Krume* > *Krüme-l* > *krümel-n*
- *Kuch-en* > *Küch-el* > *küchel-n*
- mhd. *Murk* ("Brocken") > *Murkel* ("kleiner Kerl") > *murkeln* ("krümeln")
- *Ring* > *Ring-el* > *ringel-n*
- mhd. *scharmutz* > *Scharmütz-el* > *scharmützel-n*
- ahd. *Wurz* ("Wurzel") > *Wurz-el* > *wurzel-n*
- en. *tip* ("Spitze") > *Zipf-el* > *zipfel-n*
- *Zotte* > *Zotte-l* > *zottel-n*

Animate > Diminutive > Be like:^[SELECT * WHERE like(a.STAMM, "% -%l %") && a.BEDEUTUNG == "Lebewesen>Diminutiv".]

- *Dachs* > *Dack-el* > *dackel-n*
- ie. \**trozd* ("Singvogel") > *Dross-el* > *drossel-n*
- nl. *vark-en* ("Schwein") > *Ferk-el* > *ferkel-n*
- *Wicht* > *Wicht-el* > *wichtel-n*

Meronym

- *Sack* > Säck-el > *ein-säckel-n*

### Adjective root > *l*-noun stem

Property > Animate > Be like^[SELECT * WHERE like(a.STAMM, "% -%l %") && a.BEDEUTUNG == "Eigenschaft>Lebewesen".]

- fnhd. *lumm* ("schlaff") > *Lümm-el* > *lümmel-n*
- *spitz* > *Spitz-el* > *spitzel-n*

### Onomatopoetic root > *l*-noun stem

Noise > Cause to be:^[SELECT * WHERE like(a.STAMM, "% -%l %") && a.BEDEUTUNG == "Dinggeräusch".]

- *bim* > Bimm-el > *bimmel-n*
- *rum* > *Rumm-el* > *rummel-n*

### Verb root ending in *l*

Body movement/Back and forth^[SELECT * WHERE like(a.WURZEL, "%el %") && a.BEDEUTUNG == "Körperbewegung".]

- *bammel-n*
- *drömmel-n*
- *dümpel-n*
- *gaukel-n*
- *hampel-n*
- *hibbel-n*
- *purzel-n*
- *rempel-n*
- *scherbel-n*
- *schuckel-n*
- *schunkel-n*
- *strampel-n*
- *strauchel-n*
- *trödel-n*
- *trudel-n*
- *tummel-n*
- *wibbel-n*
- *wimmel-n*
- *wusel-n*
- *wuzel-n*
- *zappel-n*

Noise production (human)^[SELECT * WHERE like(a.WURZEL, "%el %") && a.BEDEUTUNG == "Stimmgeräusch".]

- *babbel-n*
- *brabbel-n*
- *bruddel-n*
- *dremmel-n*
- *düssel-n*
- *fasel-n*
- *fistel-n*
- *frotzel-n*
- *gibbel-n*
- *giggel-n*
- *hechel-n*
- *heuchel-n*
- *kabbel-n*
- *keppel-n*
- *knödel-n*
- *lispel-n*
- *mäkel-n*
- *mauschel-n*
- *munkel-n*
- *murmel-n*
- *nörgel-n*
- *nuschel-n*
- *be-ömmel-n*
- *plänkel-n*
- *quassel-n*
- *quengel-n*
- *schwafel-n*
- *schwurbel-n*
- *wispel-n*

Noise production (inanimate)^[SELECT * WHERE like(a.WURZEL, "%el %") && a.BEDEUTUNG == "Dinggeräusch".]

- *dudel-n*
- *nuddel-n*
- *prassel-n*
- *raschel-n*
- *rumpel-n*
- *schrammel-n*

Other^[SELECT * WHERE (like(a.WURZEL, "%el %") || like(a.WURZEL, "%le %")) && a.NOMEN == " " && a.ADJEKTIV == " " && a.WEITERE == " " && a.BEDEUTUNG == " ".]

- *bitzel-n* ("stechend kitzeln")
- *bossel-n* ("basteln")
- *brägel-n* ("brutzeln")
- *buddel-n* ("graben")
- *büffel-n* ("lernen")
- (engl. *cancel* >) *cancel-n*
- *daddel-n* ("spielen")
- *dammel-n* ("trödeln")
- *dibbel-n* ("säen")
- (engl. *dribble* >) *dribbel-n*
- *drösel-n* ("aufknoten")
- *drusel-n* ("schlummern")
- *fissel-n* ("regnen")
- *frickel-n* ("basteln")
- *friemel-n* ("basteln")
- *fuddel-n* ("pfuschen")
- *fuschel-n* ("pfuschen")
- *gammel-n* ("faulen")
- (engl. *google* >) "googel-n* ("suchen")
- *griesel-n* ("erschauern")
- *grübel-n* ("nachdenken")
- (engl. *handle* >) *händel-n*
- *hudel-n* ("pfuschen")
- *kampel-n* ("raufen")
- *kaupel-n* ("handeln")
- *kiefel-n* ("kauen")
- *knaupel-n* ("Fingernägel nagen")
- *knibbel-n* ("kratzen")
- *kokel-n* ("zündeln")
- *kribbel-n* ("jucken")
- *krickel-n* ("kritzeln")
- (lat. *conucla* >) *kungel-n* ("geheim eintscheiden")
- (fr. *couple* >) *kuppel-n* ("verbinden")
- *makel-n* ("vermitteln")
- *meuchel-n* ("ermorden")
- *mogel-n* ("schwindeln")
- (engl. *nibble* >) *nibbel-n*
- *niesel-n* ("regnen")
- *pichel-n* ("trinken")
- *piesel-n* ("urin ausscheiden")
- *pinkel-n* ("urin ausscheiden")
- *präpel-n* ("essen")
- *prudel-n* ("pfuschen")
- *pudel-n* ("daneben kegeln")
- *pussel-n* ("arbeiten")
- *rackel-n* ("laut des Rackelhuhn")
- (engl. *recycle* >) *recycel-n*
- *rödel-n* ("hart arbeiten")
- *schibbel-n* ("rollen")
- *schmunzel-n* ("lächeln")
- *schmurgel-n* ("brutzeln")
- *schniegel-n* ("frisieren")
- *schummel-n* ("mogeln")
- *siedel-n* ("niederlassen")
- *strubbel-n* ("strubbelig machen")
- *tingel-n* ("auftreten")
- *tüftel-n* ("lösen versuchen")
- *zuzel-n* ("saugen")

### Noun root ending in *l*

Instrument > Use^[SELECT * WHERE like(a.WURZEL, "%el %") && like(a.STAMM, "%el %") && a.BEDEUTUNG == "Instrument".]

- (lat. *ampulla* >) *Ampel* > *be-ampel-n*
- *Angel* > *angel-n*
- (ital. *bin oculi* >) *Binokel* > *binokel-n* ("Kartenspiel mit doppeltem Blatt")
- *Boßel* > *boßel-n*
- (germ. \**þihsl* >) *Deichsel* > *deichsel-n*
- (*Rudolf Diesel* >) *Diesel* > *diesel-n
- (fr. *falbala* >) *Falbel* > *fälbel-n*
- *Feudel* > *feudel-n*
- *Fiedel* > *fiedel-n*
- (lat. *gabalus* >) *Gabel* > *gabel-n*
- (ital. *gondola* >) *Gondel* > *gondel-n*
- (lat. *gurgulio* >) *Gurgel* > *gurgel-n*
- *Hechel* > *hechel-n* ("mit der Hechel bearbeiten")
- (lat. *capulum* >) *Kabel* > *kabel-n* ("telegrafieren")
- (lat. *capsula* >) *Kapsel* > *kapsel-n*
- (lat. *catillus* >) *Kessel* > *ein-kessel-n*
- *Knobel* > *knobel-n*
- *Knüppel* > *knüppel-n*
- *Knüttel* > *knüttel-n*
- (lat. *cupella* >) *Kübel* > *kübel-n* ("viel trinken")
- (lat. *cuminum* >) *Kümmel* > *kümmel-n*
- (engl. *label* >) *Label* > *label-n*
- (lat. *mantellus* >) *Mantel* > *um-mantel-n*
- *Marmel* > *marmel-n*
- (lat. *margila* >) *Mergel* > *mergel-n*
- (lat. *modulus* >) *Modell* > *um-model-n*
- (lat. *mortarium*) > *Mörtel* > *mörtel-n*
- *Murmel* > *murmel-n*
- (germ. \**nagla* >) *Nagel* > *nagel-n*
- *Nestel* > *nestel-n*
- *Odel* > *odel-n*
- (lat. *organa*) > *Orgel* > *orgel-n*
- *Paddel* > *paddel-n*
- (fr. *passe-poil* >) *Paspel* > *paspel-n*
- (lat. *peniculus* >) *Pinsel* > *pinsel-n*
- *Prügel* ("Stock") > *prügel-n*
- *Rassel* > *rassel-n*
- *Riegel* > *riegel-n*
- *Riffel* ("Kamm*) > *riffel-n*
- *Rodel* > *rodel-n*
- *Säbel* > *säbel-n*
- *Schaufel* > *schaufel-n*
- *Schaukel* > *schaukel-n*
- *Schindel* > *schindel-n*
- *Schmirgel* > *schmirgel-n*
- *Schnabel* > *schnäbel-n*
- *Schnorchel* > *schnorchel-n*
- *Schwefel* > *schwefel-n*
- *Segel* > *segel-n*
- (lat. *secula* >) *Sichel* > *sichel-n*
- *Spiegel* > *spiegel-n*
- *Spiel* > *spiel-en*
- (germ. \**stapula* >) *Staffel* > *staffel-n*
- *Striegel* > *striegel-n*
- *Tafel* > *ver/aus-täfel-n*
- *Takel* > *takel-n*
- *Töggel* > *töggel-n*
- *Treidel* > *treidel-n*
- *Trödel* > *trödel-n* (Trödel verkaufen)
- (lat. *circulum* >) *Zirkel* > *zirkel-n*

Result > Produce^[SELECT * WHERE like(a.WURZEL, "%el %") && like(a.STAMM, "%el %") && a.BEDEUTUNG == "Resultat".]

- *Adel* > *adel-n*
- *Apfel* > *äpfel-n* ("Pferdeäpfel fallen lassen")
- (lat. *buccula* >) *Buckel* > *buckel-n*
- *Bummel* > *bummel-n*
- *Dachtel* > *dachtel-n*
Doppel
- *Dünkel* > *dünkel-n*
- *Dusel* > *dusel-n*
- (lat. *fabula* >) *Fabel* > *fabel-n*
- *Frevel* > *frevel-n* ("Frevel begehen")
- (ie. \**kaghlo* >) *Hagel* > *hagel-n*
- *Handel* > *handel-n*
- (lat. *jubilare* >) *Jubel* > *jubel-n*
- *Kitzel* > *kitzel-n*
- *Knäuel* > *knäuel-n*
- *Knorpel* > *ver-knorpel-n*
- (fr. *couple* >) *Koppel* > *koppel-n*
- *Krakeel* > *krakeel-en*
- *Krakel* > *krakel-n*
- *Kritzel* > *kritzel-n*
- *Krumpel* > *krumpel-n*
- *Mangel* > *be-mängel-n* ("Mangel beanstanden")
- *Mangel* > *mangel-n* ("Mangel haben")
- (jidd. *masol* >) *Massel* > *ver-massel-n*
- (aram. *menē teqēl* >) *Menetekel* > *menetekel-n*
- *Mittel* > *mittel-n*
- (germ. \**nebula* >) *Nebel* > *nebel-n*
- (lat. *pāgella* >) *Pegel* > *ein-pegel-n*
- *Popel* > *popel-n*
- (lat. *regula* >) *Regel* > *regel-n*
- *Rippel* > *rippel-n*
- *Rüffel* > *rüffel-n*
- *Runzel* > *runzel-n*
- *Schimmel* > *schimmel-n*
- *Schmuddel* > *schmuddel-n*
- *Schmuggel* > *schmuggel-n*
- *Schnörkel* > *ver-schnörkel-n*
- *Schwirbel* > *schwirbel-n*
- *Speichel* > *speichel-n*
- *Spektakel* > *spektakel-n*
- (germ. \**stapula* >) *Stapel* > *stapel-n*
- (lat. *stipula* >) *Stoppel* > *stoppel-n*
- *Stummel* > *ver-stümmel-n*
- *Tadel* > *tadel-n*
- *Titel* > *titel-n*
- (lat. *torcula* >) *Torkel* > *torkel-n*
- *Wickel* > *wickel-n*
- *Winkel* > *an-winkel-n*
- *Wirbel* > *wirbel-n*
- (lat. *cedula* >) *Zettel* > *ver-zettel-n*
- *Zwiesel* > *zwiesel-n*

Animate > Be like:^[SELECT * WHERE like(a.WURZEL, "%el %") && like(a.STAMM, "%el %") && a.BEDEUTUNG == "Lebewesen".]

- *Eumel* ("sympathischer Mensch" )> *eumel-n* ("feiern, liebkosen")
- (fr. *double* >) *Double* > *doubel-n*
- (lat. *flagellum* >) *Flegel* > *flegel-n*
- *Fummel* > *fummel-n*
- *Igel* > *ein-igel-n*
- *Klüngel* > *klüngel-n*
- (lat. *oraculum* >) *Orakel* > *orakel-n*
- (fr. *peuple* >) *Pöbel* > *pöbel-n*
- *Pummel* > *an-pummel-n*
- *Räkel* > *räkel-n*
- *Rudel* > *rudel-n*
- (tsch. *červenc* >) *Scharwenzel* > *scharwenzel-n*
- *Schussel* > *schussel-n*
- *Schweinigel* > *schweinigel-n*
- *Schwiemel* > *schwiemel-n*
- (gr. *diábolos* >) *Teufel* > *ver-teufel-n*
- *Tölpel* > *tölpel-n*
- (lat. *turtur* >) *Turtel(taube)* > *turtel-n*
- (germ. \**fugla* >) *Vogel* > *vögel-n*
- *Wiesel* > *wiesel-n*

Inanimate > Do like^[SELECT * WHERE like(a.WURZEL, "%el %") && like(a.STAMM, "%el %") && a.BEDEUTUNG == "Analogon".]

- *Apfel* > *ver-äppel-n* ("täuschen")
- *Augapfel* > *be-augapfel-n*
- *Fackel* > *fackel-n* ("brennen, zögern")
- (lat. *gabalus* >) *Gabel* > *gabel-n* ("verzweigen")
- *Himmel* > *an-himmel-n*
- (lat. *cancella* >) *Kanzel* > *ab-kanzel-n*
- (lat. *capitulum* >) *Kapitel* > *ab-kapitel-n*
- *Kugel* > *kugel-n*
- (lat. *mantellus* >) *Mantel* > *be-mäntel-n* ("verharmlosen")
- (lat. *mobilis* >) *Möbel* > *ver-möbel-n* ("verprügeln")
- (lat. *pendulus* >) *Pendel* > *pendel-n*
- (engl. *pixel* >) *Pixel* > *ver-pixel-n*
- *Rubel* > *rubel-n*
- (lat. *aestivalia* >) *Stiefel* > *stiefel-n*
- *Strudel* > *strudel-n*
- *Tunnel* > *tunnel-n*
- (germ. \**waþila* >) *Wedel* > *wedel-n*
- (lat. *cepula* >) *Zwiebel* > *zwiebel-n*

Nahrung^[SELECT * WHERE like(a.WURZEL, "%el %") && like(a.STAMM, "%el %") && a.BEDEUTUNG == "Verzehr".]

- *Achel* ("Getreide") > *achel-n* ("essen")
- *Nudel* > *nudel-n*

Empfindung^[SELECT * WHERE like(a.WURZEL, "%el %") && like(a.STAMM, "%el %") && a.BEDEUTUNG == "Empfindung".]

- *Ekel* > *ekel-n*
- *Zweifel* > *zweifel-n*

Ort^[SELECT * WHERE like(a.WURZEL, "%el %") && like(a.STAMM, "%el %") && a.BEDEUTUNG == "Ort".]

- *Gipfel* > *gipfel-n*
- *Schachtel* > *schachtel-n*
- *Sprudel* ("Quelle") > *sprudel-n*
- *Sudel* ("Morast") > *sudel-n*
- *Tafel* > *tafel-n*
- *Wuschel* > *wuschel-n* (Haare wuscheln)
- (lat. *cingula* >) *Zingel* > *um-zingel-n*

Dingteil^[SELECT * WHERE like(a.WURZEL, "%el %") && like(a.STAMM, "%el %") && a.BEDEUTUNG == "Meronym".]

- (lat. *caculus* >) *Kachel* > *kachel-n*
- *Nadel* > *nadel-n*
- *Nickel* > *ver-nickel-n*
- *Pökel* > *pökel-n*
- *Sattel* > *sattel-n*
- *Siegel* > *siegel-n*
- *Sockel* > *auf-sockel-n*
- *Trüffel* > *trüffel-n*
- *Wimpel* > *be-wimpel-n*
- (lat. *cedula* >) *Zettel* > *zettel-n*

### Adjective root ending in *l*

Property > Cause to be^[SELECT * WHERE like(a.WURZEL, "%el %") && a.ADJEKTIV != " ".]

- *dunkel* > *ver-dunkel-n*
- *edel* > *ver-edel-n*
- *einzel-n* > *ver-einzel-n*
- *eitel* > *ver-eitel-n*
- (fr. *simple* >) *simpel* > *ver-simpel-n*
- *übel* > *ver-übel-n*

### Other roots ending in *l*

Fractional numerals

- *sechs* > *sechs-tel* > *sechstel-n*

Name^[SELECT * WHERE like(a.WURZEL, "%el %") && a.BEDEUTUNG == "Name".]

- *(Gregor) Mendel* > *mendel-n*
- *(Angela) Merkel* > *merkel-n*
- *(Rudolf) Diesel* > *ver-diesel-n*

## *r* (79)

In the complete list of 3350 verbstems there are about 435 verbs that end in *-ern*. Of those verbs, 175 can be transparently analysed as having some kind of German-language morpheme *r*. These verbs will be the main topic of this chapter. The analysis of the *r* in the remaining 260 verbs is either unclear or it has an "outside" origin.

limited productivity, but also interesting would be what associations users have, e.g. between highly similar words like *erneuen/erneurn, versteinen/versteinern*.

I report here on the corpus of available examples that users could (intuitively) use to build such (if any) intuitions.

Two aspects: what is the relation between *r*-noun with its root? What is the relation between the *r*-noun and the derived *r*-verb.

first question: Regular range of using *r* to form a noun [@fleischer2012: 201-207].

for second question: particularly interesting are *r*-nouns that are not synchronically analysable [@fleischer2012: 201-207: 434-437]

(437 = 177 analysable + 4 unclear + 256 unanalysable)

**Causative** (67+37)

- Process > Cause to be (13)
- Object > Cause to become (8)
- Object > Cause to have (8 + 12 unanalysable)
- Property > Cause to be (6 + 25 unanalysable)
- Property > More > Cause to be (25)
- Noise > Cause to be (7)

**Iterative** (32+54)

- Movement > Repetition (5)
- Movement > Back and forth (6 + 18 unanalysable)
- Light production > Vibration (7)
- Noise production (inanimate) > Repetition (5 + 17 unanalysable)
- Noise production (animate) > Intensity (5 + 14 unanalysable)
- Consumption > Glee (4 + 5 unanalysable)

(29 unanalysable)
(32 other)

**Instrumental** (23+38)

- Process > Instrument > Use (18)
- Instrument > Plural > Use (5)
- Instrument > Use (38 unanalysable)

**Resultative** (13+31)

- Process > Result > Produce (8)
- Result > Plural > Produce (5)
- Result > Produce (31 unanalysable)

**Similative** (42+35)

- Animate > Plural > Be like (7 + 21 unanalysable)
- Process > Animate > Be like (12)
- Result > Producer/Custodian > Be like (8)
- Instrument > User > Be like (6)
- Location > Inhabitant > Be like (4)
- Object > Similar human > Be like (2)
- Inanimate > Plural > Do like (3 + 5 unanalysable)
- Emotion > Perceive (9 unanalysable)


many already have "r" before Germanic, many left over. Many nouns wiht "r" that probably are old.

There is just a rather limited literature about the suffix *r*. Fleischer & Barz [-@fleischer2012: 430-431] describe the suffix *r* as "iterative (without diminutive component)" or "causative" when used with verb bases, also noting that the suffix appears to be a plural marker with some noun-based derivations. Eisenberg [-@eisenberg1992: 97-98] uses the terms "iterative",  "pejorative" and "causative" to describe the meaning of *-r*. The Duden grammar says that it has mostly a "diminutive-iterative" meaning ["meist eine diminutiv-iterativ Bedeutung", @duden2009: 708]. The concepts iterative and causative indeed appear usefull, but need to be made more precise. However, I cannot find any clear evidence of pejorative or diminutive functions for *r*. 

[@lujan2010; @rainer2015] on agent/instrument similarity, no mention of result

There are approximately 80 examples of verbs ending in *-ern* that are based on a noun stem with a clear morpheme *-er*. These examples can be subdivided into the following classes.

- Verbs with a ~~plural~~ noun as stem,
  - derived from a noun root: N +*er* > N~plural~ > V \
    e.g. *Blatt* > *Blätter* > *blättern* \
    20 examples: Instrumental (5), Similative (10), Resultative (5)
- Verbs with an ~~agent~~ noun as stem,
  - derived from a noun root: N +*er* > N~agent~ > V \
    e.g. *Garten* > *Gärtner* > *gärtnern* (19 examples)
  - derived from a verb root: V +*er* > N~agent~ > V \
    e.g. *dienen* > *Diener* > *dienern* (10 examples)
- Verbs with an ~~instrument~~ noun as stem,
  - derived from a noun root: N +*er* > N~instr.~ > V \
    e.g. *Stand* > *Ständer* > *aufständern* (3 examples)
  - derived from a verb root: V +*er* > N~instr.~ > V \
    e.g. *blinken* > *Blinker* > *blinkern* (19 examples)
- Verbs with a ~~result~~ noun as stem,
  - derived from a verb root: V +*er* > N~result~ > V \
    e.g. *mausen* > *Mauser* > *mausern* (6 examples)

Various stems of the *-ern*-verbs are agent nouns. The *r* in these verbs arises because the suffix *-er* is used to derive this agent noun, either from another noun root or from a verb root. The semantics of the noun-to-agent-noun derivation is variable: the agent is somebody that either does something "with" or "in" the noun stem.

Adjectives, about 35 examples

most with preverbs (70%), typically *ver-*

Adjectives with [aou] always with umlaut, except alt/altern, schlack/schlackern, latsch/belatschen, sauer/versauern

- Verbs with a ~~comparative adjective as stem~~, which is derived from an adjective root by adding the suffix *-er* (A>A+*er*>V), e.g. *neu* > *neuer* > *erneuern* (25 examples)
- Verbs with an ~~adjective as stem~~, which already ends in *er* (A>V), e.g. *bitter* > *verbittern* (22 examples)
- Verbs with an ~~adjective as root~~ by adding a suffix *-er* (A>V+*er*), e.g. *gewiss* > *vergewissern* (6 examples)

Iterative "r": (33)

  V   +r >  V  glucken      > gluckern

Causative/Result "r": (24)

  V +r > V steigen       > steigern
V/N +r > V Rauch/rauchen > räuchern
  N +r > V Knochen       > ver-knöchern

Adjective/Causative (32)

  A +r > V   alt           > altern
  A +r > A/V mild          > milder/mildern
A/V +r > A/V nah/nahen     > näher/nähern

No opposition (separate parallel origins from Noun)

- (Bild) bilden ≠ be-bildern
- (Blatt) ab-blatten ≠ blättern
- (Forst) auf-forsten (Forst erneuern) ≠ be-förstern (vom Förster betreuen lassen)
- (Geist) be-geisten (Mit Geist füllen) > be-geistern (in erhöhte Stimmung versetzen)
- (Kalb) kalben (ein Kalb bekommen) ≠ kälbern (sich albern benehmen)
- (to kick) kicken (fußball spielen) ≠ kickern (Tischfußball spielen)
- (Knick?) knicken ("umbiegen") ≠ knickern (geizig sein) < Knicker ("Geizhals")
- (latsch=lasch) latschen ≠ belatschern (überreden)
- nähen ≠ nähern (~ nahen)
- (Scheiße) scheißen ("Darm entleeren") ≠ ver-scheißern (zum Narren halten)
- (Schilf) verschilfen ("vollwachsen mit Schilf") ≠ schilfern ("sich schuppen") < schilfer (nl. "Schuppe")
- (Stein) ent-steinen (Stein entfernen) ≠ ver-steinern ("zu Stein werden")
- (Volk) um-volken (Volk ändern) ≠ be-völkern (besiedeln)
- (wild/Wild) er-wilden (wild werden) > wildern (unberechtigt Wild fangen)


### Verb root > *r*-verb stem (45)

Movement > Repetition/Back and forth:^[SELECT * WHERE like(a.VERB, "% -%r %") && like(a.BEDEUTUNG, "%bewegung").]

- mnd. *bōn-en* > *bohn-er-n* ("putzen")
- *poch-en* > *puck-er-n* ("pulsieren")
- *schling-en* ("herumwickeln") > *schling-er-n* ("hin und her schwanken")
- mhd. *slīten* ("gleiten") > *schlitt-er-n/schlidd-er-n* ("hin- und herrutschen")
- *schnapp-en* ("greifen") > *schnapp-er-n* ("zittern")
- *schnupf-en* ("Nase putzen") > *schnupp-er-n* ("Luft durch die Nase einziehen")
- *schütt-en* ("hineingießen") > *schütt-er-n* ("beben")
- *schwapp-en* ("überlaufen") > *schwabb-er-n/schwapp-er-n* ("hin- und herbewegen")
- mhd. *want-en* ("drehen") > *wand-er-n* ("umherlaufen")

Light production > Vibration:^[SELECT * WHERE like(a.VERB, "% -%r %") && a.BEDEUTUNG == "Lichteffekt".]

- *blink-en* > *blink-er-n* > *Blinker*
- *flack-en* > *flack-er-n* ("unruhig brennen")
- mhd. *flimm-en* ("brennen") > *flimm-er-n* ("unruhig glänzen") > *Flimmer*
- *glimm-en* ("schwach glühen") > *glimm-er-n* ("funkeln") > *Glimmer*
- mhd. *glitz-en* ("glänzen") > *glitz-er-n* ("funkelnd glänzen") > *Glitzer*
- md. *schem-en* ("blinken, funkeln") > *schimm-er-n* ("schwach leuchten") > *Schimmer*
- mhd. *wab-en* ("bewegen") > *wab-er-n* ("flackern")

Noise production (inanimate) > Repetition:^[SELECT * WHERE like(a.VERB, "% -%r %") && a.BEDEUTUNG == "Dinggeräusch" && a.WEITERE == " ".]

- *klack-en* > *klack-er-n* ("wiederholt klacken")
- *klapp-en* > *klapp-er-n* ("mehmals klappen")
- *klick-en* > *klick-er-n* ("mehmals klicken")
- *platsch-en* > *plätsch-er-n* ("Wassergeräusch")

Noise production (human) > Intensity:^[SELECT * WHERE like(a.VERB, "% -%r %") && a.BEDEUTUNG == "Stimmgeräusch" && a.ADJEKTIV == " " && a.WEITERE == " ".]

- nl. *mopp-en* > *mopp-er-n* ("nörgeln")
- *muck-en* > *muck-er-n* ("murren")
- *rament-en* > *rament-er-n* ("rumoren")
- *schall-en* > *schall-er-n* ("laut singen")
- *schnaub-en* > *schnob-er-n* ("Atem einziehen")

Consumption (human) > Intensity:^[SELECT * WHERE like(a.VERB, "% -%r %") && a.BEDEUTUNG == "Verzehr".]

- *knapp-en* > *knabb-er-n* ("etwas Hartes essen")
- mnd. *lāp-en* ("lecken, schlürfen") > *läpp-er-n* ("großen Appetit haben")
- *rauch-en* > *rauch-er-n* ("Lust auf rauchen haben")
- *schlapp-en* > *schlabb-er-n*
- *schleck-en* ("lecken") > *schleck-er-n* ("Süßes genießen")
- *schlemm-en* > *schlemm-er-n* ("viel essen")

Others:^[SELECT * WHERE like(a.VERB, "% -%r %") && a.ADJEKTIV == " " && a.BEDEUTUNG == " ".]

Causative? typically with change of vowel (umlaut, or shortening), except <ei>, which is merger, e.g. ahd long [ī] and [ai]. Other No umlaut with /a/, except platschen > plätschern, trällern

*lächern* 'something makes me laugh'
*läppern* 'have a sudden craving > it's mounting up'

es lächert mich
es läppert mich nach Schokolade

- *hack-en* ("zerteilen") > *hack-er-n* ("gerinnen der Milch")
- *kleck-en* > *kleck-er-n* ("Kleckse machen")
- *lach-en* > *läch-er-n* ("Lachreiz empfinden")
- mnd. *plūs-en* ("rupfen") > *plus-t-er-n* ("Fell aufrichten")
- mhd. *rūsp-en* ("aufstoßen") > *räusp-er-n* ("sich durch Hüsteln die Kehle reinigen")
- *schiel-en* ("schief schauen, blinzeln") > *schill-er-n* ("glänzen")
- *ein-schlaf-en* > *ein-schläf-er-n*
- *schlamp-en* ("lose hängen") > *schlamp-er-n* ("nachläßig sein")
- *steig-en* > *steig-er-n*
- *strull-en* > *strull-er-n* ("pinkeln")
- *ver-tick-en* > *ver-tick-er-n* ("verkaufen")
- ahd. *walagôn* ("rollen") > *wälg-er-n* ("Teig ausrollen")
- mhd. *zog-en* ("gehen, zerren") > *zög-er-n* ("hinnausschieben")
- mhd. *zwink-en* > *zwink-er-n*

### Noun root > *r*-verb stem (15)

Listed here are verbs ending in *ern* that have a noun as root for which *r* does not appear to be a noun suffix. The verb is apparently derived directly by adding a suffix *-r* to the noun stem. The stem with *-r* is not a possible derived noun. The application of Umlaut is variable.

Semantically, these verbs mean "cause to become/have noun", e.g. *folgern* 'to conclude' is derived from *Folge* 'result' by meaning something like 'do something to have the result'.

Instrument:^[SELECT * WHERE like(a.VERB, "% -%r %") && a.BEDEUTUNG == "Instrument".]

- *Dreck* > *dreck-er-n*
- *Rauch* > *räuch-er-n*
- *Scheiße* > *ver-scheiße-r-n*
- *Weihrauch* > *be-weihräuch-er-n*
- *Wien* > *wien-er-n* ("putzen mit Wiener Kalk")

Result:^[SELECT * WHERE like(a.VERB, "% -%r %") && a.BEDEUTUNG == "Resultat".]

- *Asche* > *ein-äsche-r-n*
- *Folge* > *folge-r-n* ("Schlussfolgerung ziegen")
- *Hede* ("Abfall von Flachs) > *ver-hedde-r-n* ("sich verfangen")
- nd. *Jacht* ("Jagd") > *jacht-er-n* ("umherrennen")
- *Kante* > *kente-r-n* ("sich auf die Kante legen")
- *Knochen* > *ver-knöch-er-n*
- *Meute* > *meute-r-n*
- ahd. *skeliva* ("Schuppe") > *schilf-er-n* ("sich schuppen")
- *Stein* > *ver-stein-er-n*
- *Wild* > *wild-er-n* ("unberechtigt Wild fangen")

A few of these nouns also exist as the root of a verb without any additional *er*. It is unclear whether there is any consistent semantic difference between these verbs listed below (derived from noun roots without *r*) and the verbs listed above (derived from noun roots with *r*). Many seem to be almost synonymous (e.g. *umranden* means the same as *umrändern*).

- *Asche* > *ent-asche-n*
- *Dreck* > *ver-dreck-en*
- *Folge* > *folge-n*
- *Rauch* > *rauch-en*
- *Scheiße* > *be-scheiß-en*
- *Stein* > *ent-stein-en* 

### Adjective root > *r*-verb stem (8)

Listed here are verbs ending in *ern* that have an adjective as root for which *er* does not appear to be a comparative suffix. The verb is apparently derived directly by adding a suffix *-r*. The verb stem with *-r* is not a comparative adjective. 

Semantically, these verbs have a clear causative/resultative meaning, but the derivation from the adjective root is not as transparent as with the comparative adjectives discussed previously.^[SELECT * WHERE like(a.VERB, "% -%r %") && a.ADJEKTIV != " ".]

Property > Be like (intransitive): 

- *gewiss* > *ver-gewiss-er-n*
- *schlack* ("schlaff") > *schlack-er-n* ("zittern")
- *stumm* > *stamm-er-n*
- *voll* > *völl-er-n*

Property > Cause to be (transitive):

- *ge-ring* > *ver-ring-er-n*
- *lahm* > *be-lämm-er-n*
- *latsch* ("schlaff") > *be-latsch-er-n* ("überreden")

### Onomatopoetic root > *r*-verb stem (11)

Inanimate Noise > Cause to be:^[SELECT * WHERE like(a.VERB, "% -%r %") && a.BEDEUTUNG == "Dinggeräusch" && a.WEITERE != " ".]

- *bumm-er-n*
- *gluck-er-n*
- *tuck-er-n*

Animate Noise > Cause to be^[SELECT * WHERE like(a.VERB, "% -%r %") && a.BEDEUTUNG == "Tiergeräusch" && a.WEITERE != " ".]

- *belf-er-n*
- *gack-er-n*
- *keck-er-n*
- *schnatt-er-n*
- *wieh-er-n*
- *zwitsch-er-n*

Human Noise^[SELECT * WHERE like(a.VERB, "% -%r %") && a.BEDEUTUNG == "Stimmgeräusch" && a.WEITERE != " ".]

- *meck-er-n*
- *träll-er-n* (< "tralalala")

### Verb root > *r*-noun stem

Listed here are verbs ending in *ern* that have a noun stem, which in turn is derived from a verb root with the suffix *-r*. In the process of deriving nouns from verb by adding *-r*, some nouns with a [aou] vowel get an additional *Umlaut*, but others do not. Further, there are two nouns that are based on the *Ablaut* stem of the verb, namely *stehen>Stand>Ständer* and *schießen>Schuss>Schusser*

Semantically, the *ern*-verbs have three different relations to the noun stem and its verb root, which show a remarkable similarity to the relations discussed in the previous [Section ???].

First, some verbs have an ~~instrumental~~ relation. These *ern*-verb mean "using the [*er*-noun stem], which is an instrument to do [verb root]", e.g. *rollern* 'ride a scooter' means to use a *Roller* 'scooter', which is an instrument used for *rollen* 'to roll'.

The second group of verbs have an ~~similative/human~~ relation. These *ern*-verbs mean "being (similar to) the [*er*-noun stem], which is a person characterised by doing [verb root]", e.g. *dienern* 'to bow and scrape' means to behave similar to a *Diener* 'servant', which is a person that is characterised by *dienen* 'to serve'.

Finally, the third group of verbs has a ~~resultative~~ relation. These *ern*-verbs mean "producing [*er*-noun stem] which is the product of [verb root]", e.g. *splittern* 'to splinter' is a process that produces *Splitter* 'splinter', which is the result of *splitten* 'to split'.

Purely synchronically, the derivation from the underlying noun root to the *er*-noun stem is transparent only in about half of the examples listed below. For all other verbs some comparative and/or diachronical interpretation is necessary. 

Process > Instrument > Use:^[SELECT * WHERE like(a.STAMM, "% -%r %") && a.BEDEUTUNG == "Instrument".]

- *bind-en* > *Bind-er* > *binder-n*
- *bol-n* (mhd. "werfen, schleudern") > *Böll-er* > *böller-n*
- *fach-en* > *Fäch-er* > *fächer-n*
- \**fado-jan* (germ. "nähren") > *Futt-er* > *futter-n*
- \**fado-jan* (germ. "nähren") > *Futt-er* > *fütter-n*
- *flip* (engl. ")
- *grub* (engl. "graben") > *Grubb-er* ("Landwirtschaftsgerät")> *grubber-n*
- *halt-en* > *Halt-er* > *halter-n* ("befestigen")
- *halt-en* > *Hält-er* ("Behälter") > *hälter-n* ("Fische halten")
- *heb-en* > *Heb-er* > *ab-heber-n*
- *kap-en* (nl. "Seeräuberei treiben") > *Kaper* > *kaper-n*
- *catch* (engl. "fangen") > *Kesch-er* ("Netz")> *kescher-n*
- *kill* (engl. "töten") > *Tinten-kill-er* > *killer-n*
- *klemm-en* > *Klamm-er* *klammer-n*
- *prang-en* (mnd. "drücken") > *Prang-er* ("Schandpfahl") > *an-pranger-n*
- *puff-en* > *Puff-er* ("Zugabfederung") > *ab-puffer-n*
- *reut-en* ("roden") > *Reut-er* ("Gerüst zum Trocknen") > *reuter-n*
- *roll-en* > *Roll-er* > *roller-n*
- *schieß-en* > *Schuss-er* ("Murmel") > *schusser-n* ("murmeln")
- *schmök-en* ("rauchen") > *Schmök-er* ("Buch") > *schmöker-n* ("viel lesen")
- *schrubb-en* > *Schrubb-er* > *schrubber-n*
- *schütt-en* > *Schott-er* > *schotter-n*
- *steh-en* > *Ständ-er* > *auf-ständer-n*
- *stink-en* > *Stänk-er* *stänker-n*
- *staub-en* > *Stöb-er* > *stöber-n*
- *stech-en* > *Stoch-er* > *stocher-n*
- *tack* (engl. "heften) > *Tack-er* > *tacker-n*

Process > Result > Produce:^[SELECT * WHERE like(a.STAMM, "% -%r %") && a.BEDEUTUNG == "Resultat".]

- mhd. *dun-en* ("dröhnen") > *Donn-er* > *donner-n*
- bair. *gaif-en* ("Mund verziehen") > *Geif-er* ("Speichel") > *geifer-n*
- *kling-en* > *Klink-er* ("klingender Stein") > *ver-klinker-n*
- *maus-en* ("federwechseln") > *Maus-er* > *mauser-n*
- ie. \**sap* ("schmecken") > *Sabb-er* > *sabber-n* ("Speichel fließen lassen")
- ie. \**skē̌ip* ("schneiden") > *Schief-er* > *schiefer-n*
- fnhd. *schlenk-en* > *Schlenk-er* > *schlenker-n*
- mnd. *splitt-en* ("spalten) > *Splitt-er* > *splitter-n*
- nl. *trill-en* ("zittern") > *Trill-er* > *triller-n*

Process > Agent > Be like:^[SELECT * WHERE like(a.STAMM, "% -%r %") && a.BEDEUTUNG == "Lebewesen".]

- *bau-en* > *Bau-er* > *ver-bauer-n*^[The etymological origin of the word *Bauer* is slightly more complex than suggested here, but eventually the roots of *bauen* and *Bauer* are cognate.]
- *dien-en* > *Dien-er* > *diener-n*
- *drechsel-n* > *Drechsl-er* > *drechsler-n*
- rotw. *jun-en* ("falschspielen") > *Gaun-er* > *gauner-n*
- *gönn-en* > *Gönn-er* > *be-gönner-n*
- arab. *calfata* > *Kalfat-er* > *kalfater-n*
- mhd. *knūʒ* ("vermessen, waghalsig") > *Knaus-er* > *knauser-n*
- mnd. *rāk-en* ("graben") > *Rack-er* > *racker-n*
- *rauben* > *Räub-er* > *räuber-n*
- mnl. *rīd-en* ("reiten") > *Ritt-er* > *ritter-n*
- *schlagen* > *Schläg-er* > *schläger-n*
- *schneid-en* > *Schneid-er* > *schneider-n*

### Noun root > *r*-noun stem

Human:

Listed here are verbs ending in *ern* that are based on a noun stem, which in turn is based on a noun root with a suffix *-r*. Additionally, all noun roots with the vowels [a/o/u] regularly obtain an Umlaut for the derived noun, the exceptions being *Fußball>Fußballer* and *Schloss>Schlosser*. Slight variations of the suffix are attested with *Klempner*, which is derived with the suffix *-ner* [@eisenberg1992: 106-107;@fleischer2012: 208-209], and *Tischler*, which is derived with the suffix *-ler* [see @eisenberg1992: 103-106;@fleischer2012: 207-208]. Yet another variant is found with *Schuh>Schuster*, which appears to be derived with the suffix *-ster*.

Semantically, the noun stems ending in *-r* are humans that have various relations to their noun root. Most relations are agentive, namely being ~~producer~~, ~~custodian~~ or ~~user~~ of the noun root. A few remaining examples are less agentive, namely being ~~inhabitant~~ of the noun root or simply being ~~similar~~ to the noun root. 

In a second step, the verb ending in *ern* is derived from this human noun stem. The meaning of these verbs is simply 'to be that human'. There does not seem to be any extra semantic derivation in this second step. Note that the prefixed verbs (e.g. *verspießern, einbürgern, verstädern*) slightly change this meaning to 'to become that human'.

Instrument > Agent (User) > Be like:^[SELECT * WHERE like(a.STAMM, "% -%r %") && a.BEDEUTUNG == "Instrument>Lebewesen".]

- *Fußball* > *Fußball-er* > *fußballer-n*
- *calamus* (lat. "Schreibrohr") > *Klamüs-er* (nd. "Grübler") > *klamüser-n* ("studieren")
- *Klampe* (mnd. "Klammer") > *Klemp-ner* > *klempner-n*
- *Reede* ("Ankerplatz") > *Reede-r* ("Schiffsbesitzer") > *be-reeder-n*
- *Schiff* > *Schipp-er* (nd. "Kapitän") > *schipper-n*
- *Spieß* > *Spieß-er*^[The relation of *Spießer* 'burgeous' to *Spieß* 'spike' is complicated, but seems to hold through an intermediate *Spießbürger*, which might have originally been citizens that earned their right to citizenship through military service, i.e. by handling the spike [@harm2021;@harm2021a].] > *ver-spießer-n*

Result > Agent (Producer/Custodian) > Be like:^[SELECT * WHERE like(a.STAMM, "% -%r %") && a.BEDEUTUNG == "Resultat>Lebewesen".]

- *Forst* > *Först-er* > *beförster-n*
- *Garten* > *Gärtn-er* > *gärtner-n*
- *Schauspiel* > *Schauspiel-er* > *schauspieler-n*
- *Schloss* > *Schloss-er* > *schlosser-n*
- *Schrein* > *Schrein-er* > *schreiner-n*
- *Schuh* > *Schu-ster* > *schuster-n*
- *Tisch* > *Tisch-ler* > *tischler-n*
- *Topf* > *Töpf-er* > *töpfer-n*

Location > Agent (Inhabitant) > Be like:^[SELECT * WHERE like(a.STAMM, "% -%r %") && a.BEDEUTUNG == " Ort>Lebewesen ".]

- *Berlin* > *Berlin-er* > *berliner-n*
- *Burg* > *Bürg-er* > *ein-bürger-n*
- *Holland* > *Holländ-er* > *holländer-n*
- *Stadt* > *Städt-er* > *ver-städter-n*

Object > Agent (Similar human) > Be like:^[SELECT * WHERE like(a.STAMM, "% -%r %") && a.BEDEUTUNG == "Analogon>Lebewesen".]

- *Stumpf* > *Stümp-er* ("Krüppel, Nichtskönner") > *stümper-n*
- *Strom* > *Strom-er* ("Landstreicher") > *stromer-n*

Plural:

Listed here are verbs ending in *ern* that appear to be based on a plural noun ending in *-r*. These nouns are the regular plurals of the root nouns. To mark the plural, almost all examples below add a suffix *-er* to the noun root with an additional Umlaut for the roots with an [a/o/u] vowel. Only the plural *Bruder>Brüder* is derived from a singular that already ends in *er*. Also note that the plural forms *Ort>Örter* and *Scheit>Scheiter* are substandart.

Note that all the nouns ending in *-r* from the previous section have an unmarked plural, i.e. the singular and plural is identical. That means that those *er*-nouns also could be analysed as being plural. Or reversed, the *er* suffix for the nouns in this section just look like plurals, but are actually something different.

Semantically, the verbs in this section show a range of relations to their noun stems, namely ~~instrumental~~ ("to do something with the noun"), ~~similative~~ ("to act in the manner of the noun") and ~~resultative~~ ("to do something that produces the noun").

Crucially, there is nothing in the meaning of the verbs that suggest any plural semantics, although the verbs are morphologically based on plural nouns. Instead, the range of semantic functions is highly reminiscent of the verbs in the next [Section ???] and of the verbs derived from nouns with the suffix *-el* (see Section ???). These parallels strengthen the impression that the verbs in this section semantically do not use a plural noun as stem, but repurpose the already existing plural in *-er* as the basis for deriving the verb.

Instrument > Plural > Use:^[SELECT * WHERE like(a.STAMM, "% -%r %") && a.BEDEUTUNG == "Instrument>Plural".]

- *Band* > *Bänd-er* > *bänder-n*
- *Bild* > *Bild-er* > *be-bilder-n*
- *Blatt* > *Blätt-er* > *blätter-n*
- *Rad* > *Räd-er* > *räder-n* ("hinrichten")
- *Schild* > *Schild-er* > *be-schilder-n*

Result > Plural > Produce:^[SELECT * WHERE like(a.STAMM, "% -%r %") && a.BEDEUTUNG == "Resultat>Plural".]

- *Glied* > *Glied-er* > *glieder-n*
- *Loch* > *Löch-er* > *löcher-n* ("dauernd fragen", "Löcher in den Bauch fragen")
- *Ort* > *Ört-er* > *er-örter-n*
- *Rand* > *Ränd-er* > *ränder-n*
- *Scheit* ("gespaltenes Holzstück") > *Scheit-er* > *scheiter-n* ("erfolglos sein", "in Scheitern zerfallen")
- *Trumm* ("großer Brocken") > *Trümm-er* > *zer-trümmer-n*

Animate > Plural > Be like:^[SELECT * WHERE like(a.STAMM, "% -%r %") && a.BEDEUTUNG == "Lebewesen>Plural".]

- *Bruder* > *Brüder* > *ver-brüder-n*
- *Geist* > *Geist-er* > *geister-n*
- *Gespenst* > *Gespenst-er* > *gespenster-n*
- *Gott* > *Gött-er* > *ver-götter-n*
- *Kalb* > *Kälb-er* > *kälber-n* ("sich albern benehmen")
- *Rind* > *Rind-er* > *rinder-n* ("brünstig sein")
- *Volk* > *Völk-er* > *be-völker-n*

Inanimate > Plural > Do like:^[SELECT * WHERE like(a.STAMM, "% -%r %") && a.BEDEUTUNG == "Analogon>Plural".]

- *Brett* > *Brett-er* > *bretter-n* ("schnell fahren", "Skifahren")
- *Ei* > *Ei-er* > *eier-n*
- *Gackei* > *Gackei-er* > *ver-gackeier-n*
- *Irrlicht* > *Irrlicht-er* > *irrlichter-n*

### Adjective root > *r*-adjective stem

Listed here are verbs ending in *ern* that have a comparative adjective as stem, which in turn is derived from an adjective root with the comparative suffix *-er*. There are two comparative adjectives that do not have a transparent root, namely *besser* 'better' and ahd. *furdir* 'further. Root vowels [a/o/u] get an *Umlaut*, except for *altern* 'to become old' (the comparative of *alt* 'old' has an *Umlaut*, viz. *älter* 'older).

Semantically, these verbs are clearly causative/resultative, i.e. these verbs mean "to cause an object to become [adjective]", e.g. *mildern* 'to reduce' means *milder machen* 'make mild'. Note that the verbs *altern* 'to become old' and *bessern* 'to become better' seem to be mostly used in an anticausative meaning.

Property > More > Cause to be:^[SELECT * WHERE like(a.STAMM, "% -%r %") && !like(a.STAMM, "% -bar ") && a.ADJEKTIV != " ".]

- *allgemein* > *allgemein-er* > *ver-allgemeiner-n*
- *arg* > *ärg-er* > *ärger-n*
- *besser* > *besser-n*
- *böse* > *böse-r* > *ver-böser-n*
- *breit* > *breit-er* > *ver-breiter-n*
- *eng* > *eng-er* > *ver-enger-n*
- *fein* > *fein-er* > *ver-feiner-n*
- *fort* > ahd. *furdir* ("weiter") > *förder-n*
- *grob* > *gröb-er* > *ver-gröber-n*
- *groß* > *größ-er* > *ver-größer-n*
- *klein* > *klein-er* > *ver-kleiner-n*
- *lang* > *läng-er* > *ver-länger-n*
- *leicht* > *leicht-er* > *er-leichter-n*
- *lind* > *lind-er* > *linder-n*
- *mild* > *mild-er* > *milder-n*
- *nah* > *näh-er* > *näher-n*
- *neu* > *neu-er* > *er-neuer-n*
- *reich* > *reich-er* > *be-reicher-n*
- *schlecht* > *schlecht-er* > *ver-schlechter-n*
- *schlimm*> *schlimm-er* > *ver-schlimmer-n*
- *schmal* > *schmäl-er* > *schmäler-n*
- *schnell* > *schnell-er* > *ver-schneller-n*
- *schön* > *schön-er* > *ver-schöner-n*
- *weit* > *weit-er* > *er-weiter-n*

A few of these adjectives also exist as the root of a verb without any additional *er*. Note that some of these verbs still get an *Umlaut* with root vowels [a/o/u], viz *längen, schmälen*, while others do not, viz. *veralten, verargen*. The "anti-Umlaut" with *erbosen* is exceptional. It is unclear whether there is any consistent semantic difference between these verbs listed below (derived from adjective roots without *er*) and the verbs listed above (derived from comparative adjectives with *er*).

- *arg* > *ver-arg-en*
- *böse* > *er-bose-n*
- *breit* > *breit-en*
- *eng* > *ver-eng-en*
- *fein* > *fein-en*
- *lang* > *läng-en*
- *nah* > *nah-en*
- *neu* > *er-neu-en*
- *schmal* > *schmäl-en*
- *schnell* > *schnell-en*
- *schön* > *ver-schön-en*
- *weit* > *weit-en*

### Verb root ending in *r*

Movement of the body back and forth:^[SELECT * WHERE like(a.WURZEL, "%er ") && a.BEDEUTUNG == "Körperbewegung".]

- *bebber-n*
- *bibber-n*
- *bubber-n*
- *flatter-n*
- *holper-n*
- *klabaster-n* (< it. *calpestare*)
- *pimper-n*
- *plinker-n* ("blinzeln")
- *schlender-n*
- *schlotter-n* ("zittern")
- *schubber-n* ("reiben")
- *schudder-n* ("frösteln")
- *stolper-n*
- *taper-n*
- *tatter-n* ("zittern")
- *zitter-n*

Noise production (human):^[SELECT * WHERE like(a.WURZEL, "%er ") && a.BEDEUTUNG == "Stimmgeräusch".]

- *dibber-n* ("leise sprechen")
- *flüster-n*
- *kicher-n*
- *knoter-n* ("nörgeln")
- *laber-n*
- *pisper-n*
- *plapper-n*
- *plauder-n*
- *stotter-n*
- *suder-n*
- *wimmer-n*
- *wisper-n*
- *zeter-n*

Noise production (inanimate):^[SELECT * WHERE like(a.WURZEL, "%er ") && a.BEDEUTUNG == "Dinggeräusch".]

- *baller-n*
- *boller-n*
- *buller-n*
- *klimper-n*
- *knatter-n*
- *knister-n*
- *knusper-n*
- *polter-n*
- *pumper-n*
- *ratter-n*
- *schepper-n*
- *schmetter-n*
- *scholler-n*
- *wummer-n*

Others:^[SELECT * WHERE like(a.STAMM, "%er ") && !like(a.STAMM, "%ier ") && (a.NOMEN == " " || like(a.NOMEN, "% -ung ")) && a.ADJEKTIV == " " && a.WEITERE == " " && a.BEDEUTUNG == " ".]

- (engl. *boulder* >) *boulder-n*
- *dalber-n* ("herum albern")
- (ahd. *demar* >) *dämmer-n*
- *zer-depper-n* ("zerschlagen")
- (lat. *intrare* >) *enter-n*
- *flader-n* ("stehlen")
- *zer-fledder-n* ("Leichen plündern")
- *zer-fleder-n* ("abnützen")
- *flunker-n* ("schwindeln")
- *haper-n* ("fehlen")
- *iller-n* ("spähen")
- *kauer-n* ("knien")
- *kletter-n* ("hochsteigen")
- *klitter-n* ("zusammenfügen")
- *labber-n* ("lose hängen")
- (lat. *liber* > fr. *livrer* >) *liefer-n*
- *loder-n* ("stark brennen")
- *lunger-n* ("lauern")
- *micker-n* ("kränkeln")
- *ver-nader-n* ("verraten")
- *pladder-n* ("regnen")
- *pläster-n* ("regnen")
- *plemper-n* ("trödeln")
- *puller-n* ("pinkeln")
- (engl. *render* >) *render-n*
- *scheuer-n* ("reiben")
- *schluder-n* ("nachlässig arbeiten")
- *schummer-n* ("dämmern")
- *sicker-n* ("langsam durchfließen")
- (engl. *simmer* >) *simmer-n* ("köcheln")
- *be-tüter-n* ("umsorgen")
- (germ. \**waigar-ōn* >) *weiger-n*
- (germ. \**wedra* >) *witter-n*
- *zauder-n* ("zögern")

### Noun root ending in *r*

Listed here are verbs ending in *ern* that have an noun as stem, which itself already has a second syllable *er* (with a non-transparent or currently unclear origin).

Many examples can be clearly shown to have an *r* that originates from outside of the German verbal morphology, either as a loanword that already has an *r* or as a reconstructed form for proto-Germanic (or even proto-Indo-European) that already has an *r*.

These functions are partly connected by established paths of grammaticalisation [@kuteva2019: 241-242, 281-282, 400-401], see [@next]. The relation between instrument and result appear obvious, but does not seem to be documented in the literature on grammaticalisation.

::: ex
Instrument > Manner > Similative
:::

Instrument > Use:^[SELECT * WHERE like(a.WURZEL, "%r ") && a.BEDEUTUNG == "Instrument".]

- *Bagger* > *bagger-n*
- (engl. *booster* >) *Booster* > *booster-n*
- (lat. *bicarius* >) *Becher* > *becher-n*
- (engl. *charter* >) *Charter* > *charter-n*
- (engl. *computer* >) *Computer* > *computer-n*
- (lat. *filtrum* >) *Filter* > *filter-n*
- (ie. \**penku̯ro* >) *Finger* > *finger-n*
- (engl. *flipper* >) *Flipper* > *flipper-n*
- (germ. \**hamara* >) *Hammer* > *hämmer-n*
- *Heuer* > *an-heuer-n*
- (engl. *inliner* >) *Inliner* > *inliner-n*
- (gr. *kathetḗr* >) *Katheter* > *katheter-n*
- (lat. *calcatura* >) *Kelter* > *kelter-n*
- (engl. *kicker* >) *Kicker* > *kicker-n*
- (mhd. *klīster* >) *Kleister* > *kleister-n*
- (germ. \**kwerþraz* >) *Köder* > *köder-n*
- (engl. *laser* >) *Laser* > *laser-n*
- (germ. \**leþra* >) *Leder* > *leder-n*
- (germ. \**hrīdrā* >) *Reiter* ("Sieb") > *durch-reiter-n*
- (germ. \**rōþr* >) *Ruder* > *ruder-n*
- *Schleuder* > *schleuder-n*
- (engl. *shredder* >) *Schredder* > *schredder-n*
- (germ. \**skuldrō* >) *Schulter* > *schulter-n*
- (germ. \**steurija* >) *Steuer* > *steuer-n*
- (engl. *taser* >) *Taser* > *taser-n*
- (lat. *traiectorium* >) *Trichter* > *trichter-n*
- (engl. *trigger* >) *Trigger* > *trigger-n*
- (germ. \**teudr* >) *Tüder* > *tüder-n*
- (germ. \**taubra* >) *Zauber* > *zauber-n*
- (arab. *ṣifr* >) *Ziffer* > *ent-ziffer-n*
- (germ. \**timbra* ("bauholz") >) *Zimmer* > *zimmer-n*

Nahrung:

- (lat. *vespera* >) *Vesper* > *vesper-n*

Meronym

- (germ. \**feþrō* >) *Fieder* > *be-fieder-n*

Ingredient > Cause to have:^[SELECT * WHERE like(a.WURZEL, "%r ") && a.BEDEUTUNG == "Meronym".]

- (ie. \**ēter* >) *Ader* > *äder-n*
- *Halfter* > *halfter-n*
- *Gitter* > *um-gitter-n*
- (fr. *cofre* >) *Koffer* > *aus-koffer-n*
- (lat. *cuprum* >) *Kupfer* > *ab-kupfer-n*
- (germ. \**masara* >) *Maser* > *maser-n*
- (lat. *numerus* >) *Nummer* > *be-nummer-n*
- (lat. *piper* >) *Pfeffer* > *pfeffer-n*
- (lat. *plastrum* >) *Pflaster* > *pflaster-n*
- (germ. \**bulhstra* >) *Polster* > *polster-n*
- (fr. *poudre* >) *Puder* > *puder-n*
- *Schleier* > *ver-schleier-n*
- (germ. \**silubara* >) *Silber* > *ver-silber-n*
- (germ. \**watr* >) *Wasser* > *wässer-n*
- (ital. *zucchero* >) *Zucker* > *zucker-n*

Result > Produce:^[SELECT * WHERE like(a.WURZEL, "%r ") && a.BEDEUTUNG == "Resultat".]

- (fr. *aventure* >) *Abenteuer* > *abenteuer-n*
- (ie. \**altro* >) *Alter* > *alter-n*
- (gr. *bū́s-tȳrós* >) *Butter* > *butter-n*
- (engl. *cluster* >) *Cluster* > *cluster-n*
- (engl. *cover* >) *Cover* > *cover-n*
- (lat. *durus* >) *Dauer* > *dauer-n*
- (germ. \**aitra* >) *Eiter* > *eiter-n*
- (*Essigäther* >) *Ester* > *ver-ester-n*
- *Faser* > *faser-n*
- (lat. *feria* >) *Feier* > *feier-n*
- (gr. *pȳ́r* >) *Feuer* > *feuer-n*
- (lat. *poletrus* >) *Folter* > *folter-n*
- (engl. *gender* >) *Gender* > *gender-n*
- (fr. *glacier* >) *Gletscher* > *ver-gletscher-n*
- (ahd. *jāmar* >) *Jammer* > *jammer-n*
- *Knitter* > *knitter-n*
- (gr. *kholéra* >) *Koller* > *koller-n*
- (lat. *contra* > en. *counter* >) *Konter* > *konter-n*
- (lat. *corpus* >) *Körper* > *ver-körper-n*
- (gr. *maíandros* >) *Mäander* > *mäander-n*
- (gr. *mártyr* >) *Marter* > *marter-n*
- (lat. *murus* >) *Mauer* > *mauer-n*
- (germ. \**muþraz* >) *Moder* > *moder-n*
- (lat. *offerre* >) *Opfer* > *opfer-n*
- (fr. *ordre* >) *Order* > *order-n*
- (span. *palabra* >) *Palaver* > *palaver-n*
- *Polder* > *ein-polder-n*
- (engl. *power* >) *Power* > *aus-power-n*
- (lat. *pulvis/pulveris* >) *Pulver* > *pulver-n*
- *Qualster* ("Schleim") > *qualster-n*
- (lat. *rāster* >) *Raster* > *raster-n*
- (hebr. *sāḥar* >) *Schacher* ("kleinhandel") > *schacher-n*
- *Schmadder* > *schmadder-n* ("schneien")
- *Schlummer* > *schlummer-n*
- *Schober* > *schober-n*
- (germ. \**sendra* >) *Sinter* > *sinter-n*
- (engl. *spoiler* >) *Spoiler* > *spoiler-n*
- (germ. \**wedra* >) *Wetter* > *wetter-n*
- (germ. \**wentru* >) *Winter* > *über-winter-n*
- (germ. \**wōkra* >) *Wucher* > *wucher-n*

Location > Use:^[SELECT * WHERE like(a.WURZEL, "%r ") && a.BEDEUTUNG == "Ort".]

- (lat. *ager*) > *Acker* > *acker-n*
- (engl. *bunker* >) *Bunker* > *bunker-n*
- (engl. *container* >) *Container* > *container-n*
- *Gatter* > *er-gatter-n* ("Über ein Gatter empfangen")
- (lat. *cellarium* >) *Keller* > *keller-n*
- (lat. *carcer* >) *Kerker* > *ein-kerker-n*
- (germ. \**legra* >) *Lager* > *lager-n*
- *Lauer* ("Hinterhalt") > *lauer-n*
- (lat. *spicarium* >) *Speicher* > *speicher-n*
- (ie. \**āpero* >) *Ufer* > *aus-ufer-n*
- (germ. \**watr* >) *Wasser* > *wasser-n*

Animate > Be like:^[SELECT * WHERE like(a.STAMM, "%r ") && !like(a.STAMM, "% -%r ") && a.BEDEUTUNG == "Lebewesen".]

- (hebr. *ba‛al-dāwār* >) *Baldower* > *baldower-n*
- (nord. *ber-serkr* >) *Berserker* > *berserker-n*
- (lat. *doctor* >) *Doktor* > *doktor-n*
- (germ. \**gira* >) *Geier* > *geier-n*
- (urruss. \**choměstrъ* >) *Hamster* > *hamster-n*
- *Höker* ("Kleinhändler") > *höker-n* 
- *Imker* > *imker-n*
- (*Junge Frau* >) *Jungfer* > *ent-jungfer-n*
- (lat. *cellenarius* >) *Kellner* > *kellner-n*
- (gr. *katharós* >) *Ketzer* > *ketzer-n*
- *Knicker* > *knicker-n* ("sparsam sein")
- (lat. *condītor* >) *Konditor* > *konditer-n*
- *Luder* > *luder-n*
- (lat. *maior* >) *Meier* > *ab-meier-n*
- (lat. *magister* >) *Meister* > *meister-n*
- *Mutter* > *be-mutter-n*
- (engl. *partner* >) *Partner* > *ver-partner-n*
- (lat. *peregrinus* >) *Pilger* > *pilger-n*
- *Pracher* > *pracher-n*
- *Reiher* > *reiher-n* ("kotzen wie ein Reiher")
- *Schäker* > *schäker-n*
- *Schwager* > *ver-schwäger-n*
- (engl. *sponsor* >) *Sponsor* > *sponser-n*
- (lat. *tigris* >) *Tiger* > *tiger-n*
- (gr. *pátrōs* >) *Vetter* > *an-vetter-n*

Inanimate > Do like:^[SELECT * WHERE like(a.WURZEL, "%r ") && a.BEDEUTUNG == "Analogon".]

- *Blubber* > *blubber-n*
- (germ. \**feþrō* >) *Feder* > *feder-n* ("bewegen wie eine Feder")
- *Flitter* > *flitter-n*
- (engl. *canter* >) *Kanter* > *kanter-n*
- *Klunker* > *klunker-n* ("hängen wie große Klunker")
- *Kuller* > *kuller-n* ("rollen wie ein Kuller")
- (gr. *lýra* >) *Leier* > *leier-n* ("drehen wie an einer Leier")
- (engl. *monitor* >) *Monitor* > *monitor- en*
- (engl. *poker* >) *Poker* > *poker-n*

Emotion > Perceive:^[SELECT * WHERE like(a.WURZEL, "%r ") && a.BEDEUTUNG == "Empfindung".]

- *Eifer* > *eifer-n*
- (lat. *febris* >) *Fieber* > *fieber-n*
- *Hader* > *hader-n*
- (germ. \**hungru* >) *Hunger* > *hunger-n*
- (fr. *combres* "Hindernis") > *Kummer* > *kümmer-n*
- *Schauder* > *schauder-n*
- (germ. \**skūra* >) *Schauer* > *schauer-n*
- *Trauer* > *trauer-n*
- (germ. \**wundra* >) *Wunder* > *wunder-n*

### Adjective root ending in *r*

Listed here are verbs ending in *ern* that have an adjective as stem, which itself already has a second syllable *er* (with a non-transparent structure in contemporary German). Some of them even end in *ern*, namely *nüchtern* and sondern*. The comparative form would have another *er*, e.g. *bitterer*, which is not attested in the derived verbs. Application of *Umlaut* is variable.

The meaning of the verbs is clearly causative/resultative, i.e. these verbs mean "to cause an object to become [adjective]", e.g. *säubern* 'to clean' means 'to cause something to become clean'.

Property > (Cause) to be:^[SELECT * WHERE like(a.WURZEL, "%er ") && !like(a.STAMM, "%-%") && a.ADJEKTIV != " ".]

- *alber-n* > *alber-n*
- *ander* > *änder-n*
- *aper* > *aper-n*
- *äußer* > *äußer-n*
- *bieder* > *an-bieder-n*
- *bitter* > *ver-bitter-n*
- *düster* > *ver-düster-n*
- *finster* > *ver-finster-n
- *hager* > *hager-n*
- *heiter* > *auf-heiter-n*
- *inner* > *er-inner-n*
- *lauter* > *läuter-n*
- *locker* > *locker-n*
- mhd. *loter* ("leichtsinnig") > *lotter-n* ("liederlich leben")
- *mager* > *ab-mager-n*
- *minder* > *minder-n*
- *munter* > *er-munter-n*
- *nüchter-n* > *er-nüchter-n*
- *ober* > *er-ober-n*
- *sauber* > *säuber-n*
- *sauer* > *säuer-n*
- *sauer* > *ver-sauer-n*
- *schicker* ("betrunken") > *schicker-n*
- *schüchter-n* > *ein-schüchter-n*
- *schwanger* > *schwänger-n*
- *sicher* > *sicher-n*
- *be-sonder* > *ab-sonder-n*
- *teuer* > *über-teuer-n*
- *vorder* > *forder-n*

### Other roots ending in *r*

Other stems:^[SELECT * WHERE like(a.WURZEL, "%er ") && a.WEITERE != " ".]

- *wider* > *er-wider-n*
- *zum Acker* > *zacker-n*
- *hinter* > *hinder-n*

Name:^[SELECT * WHERE like(a.WURZEL, "%er %") && a.BEDEUTUNG == "Name".]

- *(Henry) Bessemer* > *bessemer-n*
- *Kärcher* > *kärcher-n*
- *(Hans) Moser* > *moser-n* ("schimpfen")
- *(Gerd) Müller* > *müller-n* ("viele Tore schießen")
- *(Walter) Riester* > *riester-n*
- *Tinder* > *tinder-n*
- *Twitter* > *twitter-n*

## *s* (56)

Many "non-words" made into verb by using *s*: onomatopoetic roots, pronouns

Noun-suffix *s* [@fleischer2012: 220]

analysed here are *s* after consonant. Some cases of *z* or *sch*, but most of those do not seem to be analyzable, so they have not been included here (e.g. blinzen < blinkezzen)

all stems end in [pk]

no <ts> stems, because written as <z>,<tz>, or <tsch>. There does not seem to be a suffix in those cases.

### Verb root > *s*-verb stem (36)

note some [mn]+[pkg]+[s]->[mn]+[z]

Geräusch:^[SELECT * WHERE (like(a.VERB, "% -s %") || like(a.VERB, "% -z %") || like(a.VERB, "% -sch %")) && a.NOMEN == " " && a.ADJEKTIV == " " && a.WEITERE == " " && like(a.BEDEUTUNG, "%geräusch").]

- *fiep-en* > *fiep-s-en*
- fnhd. *grunn-en* > *grun-z-en*
- *hick-en* > *hick-s-en*
- *japp-en* > *jap-s-en*
- *klack-en* > *klack-s-en*
- *knarr-en* > *knar-z-en*
- nl. *knipp-en* > *knip-s-en*
- mhd. *knirr-en* > *knir-sch-en*
- *krach-en* > *kräch-z-en*
- *mau-en* > *mau-z-en/maun-z-en*
- *piep-en* > *piep-s-en*
- *quieck-en* > *quieck-s-en*
- *raun-en* > *raun-z-en*
- mhd. *schluch-en* > *schluch-z-en*
- mhd. *schnall-en* > *schnal-z-en*
- *summ-en* > *sum-s-en*

Action > High intensity/Derogatory:^[SELECT * WHERE (like(a.VERB, "% -s %") || like(a.VERB, "% -z %") || like(a.VERB, "% -sch %")) && a.NOMEN == " " && a.ADJEKTIV == " " && a.WEITERE == " "&& a.BEDEUTUNG == " ".]

- *druck-en* > *druck-s-en* ("nicht reden wollen")
- *giek-en* > *giek-s-en* ("stechen")
- *gleit-en* > *glit-sch-en* ("gleiten")
- en. *grab* ("greifen") > *grab-sch-en* ("gierig greifen")
- *grien-en* > *grin-s-en* ("breit lächeln")
- mhd. *lech-en* ("austrocknen") > *lech-z-en* ("gierig verlangen")
- *muck-en* > *muck-sch-en* ("schlechte Laune zeigen")
- *raff-en* > *rap-sch-en* ("hastig ergreifen")
- *schnapp-en* > *schnap-s-en* ("Karten spielen")
- *stak-en* > *stak-s-en* ("steif und ungelenk laufen")
- *tapp-en* > *tap-s-en* ("plump und schwerfällig gehen, unsicher gehen")
- *trapp-en* > *trap-s-en* ("schwer auftreten")

Loss of consonant after nasal:^[SELECT * WHERE (like(a.VERB, "% -s %") || like(a.VERB, "% -z %") || like(a.VERB, "% -sch %")) && (like(a.WURZEL, "%n_ ") || like(a.WURZEL, "%m_ ")) && a.NOMEN == " " && a.ADJEKTIV == " " && a.WEITERE == " "&& a.BEDEUTUNG == " ".]

- *blink-en* > *blin-z-en* ("blinzeln")
- nd. *hump-en* ("hinken") > *be-hum-s-en* ("betrügen")
- *klump-en* > *glum-s-en* ("klumpig werden")
- *prang-en* > *pran-z-en* ("prahlen")
- mhd. *rang-en* ("bewegen") > *ran-z-en* ("heftig bewegen, sich paaren")
- *schlenk-en* ("schleudern") > *schlen-z-en* ("Ball gezielt weiterleiten")
- *schwank-en* > *schwänz-en* ("versäumen")
- *spreng-en* ("feucht machen") > *spren-z-en* ("regnen")

### Noun root > *s*-verb stem (10)

Heim/Kork maybe folketymology?

Object > Cause to be/have:^[SELECT * WHERE (like(a.VERB, "% -s %") || like(a.VERB, "% -z %") || like(a.VERB, "% -sch %")) && a.NOMEN != " ".]

- *Heim* > *ein-heim-s-en*
- *Herr* > *herr-sch-en*
- *Hund* > *hun-z-en*
- *Kork* > *ver-kork-s-en*
- *Name* > *be-nam-s-en*
- *Trick* > *trick-s-en*

Pronoun > Cause to be:^[SELECT * WHERE (like(a.VERB, "% -s %") || like(a.VERB, "% -z %") || like(a.VERB, "% -sch %")) && a.WEITERE != " " && like(a.BEDEUTUNG, "%geräusch").]

- *du* > *du-z-en*
- *er* > *er-z-en*
- *ihr* > *ihr-z-en*
- *sie* > *sie-z-en*

### Adjective root > *s*-verb stem (3)

examples^[SELECT * WHERE (like(a.VERB, "% -s %") || like(a.VERB, "% -z %") || like(a.VERB, "% -sch %")) && a.ADJEKTIV != " ".]

- *feil* > *feil-sch-en*
- *grob* > *an-grob-s-en*
- *knapp* > *knap-s-en*

### Onomatopoetic root > *s*-verb stem (7)

Onomatopeotic:^[SELECT * WHERE (like(a.VERB, "% -s %") || like(a.VERB, "% -z %") || like(a.VERB, "% -sch %")) && a.WEITERE != " " && like(a.BEDEUTUNG, "%geräusch").]

- *ach* > *äch-z-en*
- *bum* > *bum-s-en*
- *gick* > *gick-s-en*
- *gluck* > *gluck-s-en*
- *jauch* > *jauch-z-en* ("juchhei")
- *juch* > *juch-z-en*
- *rum* > *rum-s-en*

### Verb root > *s*-noun stem

Action > Result > Perform^[SELECT * WHERE (like(a.STAMM, "% -s %") || like(a.STAMM, "% -z %") || like(a.STAMM, "% -sch %")) && !like(a.VERB, "% -el %") && a.NOMEN != " " && !like(a.KOGNATE, " ~%").]

- germ. \**blīkan* ("glänzen") > *Blit-z* > *blitz-en*
- mhd. *schmack-en* > *Schmat-z* > *schmatz-en*

- *falt-en* > *Fal-z* > *falz-en*
- *hopp-en* > *Hop-s* > *hops-en*
- *klapp-en* > *Klap-s* > *klaps-en*
- *kleck-en* > *Kleck-s* > *klecks-en*
- *knack-en* > *Knack-s* > *knacks-en*
- *knick-en* > *Knick-s* > *knicks-en*
- *kok-en* > *Kok-s* > *koks-en*
- *mopp-ern* > *Mop-s* > *mops-en*
- *muck-en* > *Muck-s* > *mucks-en*
- *murk-en* > *Murk-s* > *murks-en*
- *pik-en* > *Pik-s* > *Piks-en*
- nd. *plump-en* > *Plump-s* > *plumps-en*
- *pup-en* > *Pup-s* > *pups-en*
- *scher-en* > *Scher-z* > *scherz-en
- *schieb-en* > *Schub-s* > *schubs-en*
- *schnapp-en* > *Schnap-s* > *schnaps-en*
- *schnipp-en* > *Schnip-s* > *schnips-en*
- *schwipp-en* > *Schwip-s* > *be-schwips-en*
- *stupf-en* > *Stup-s* > *stups-en*

### Noun root > *s*-noun stem

examples^[SELECT * WHERE (like(a.STAMM, "% -s %") || like(a.STAMM, "% -z %") || like(a.STAMM, "% -sch %")) && !like(a.VERB, "% -el %") && a.NOMEN != " " && like(a.KOGNATE, " ~%").]

- *Kobold* > *Kobol-z* > *Kobolz-en* ("Purzelbaume schlagen")
- *Brunn-en* > *Brun-z* > *brunz -en* ("pinkeln")

### Adjective root > *s*-noun stem

- *faul-end* > *Faulen-z* > *faulenz-en*

### Verb root ending in *s*

Only after consonant without t.^[SELECT * WHERE (like(a.WURZEL, "%s %") || like(a.WURZEL, "%z %") || like(a.WURZEL, "%sch %")) && a.NOMEN == " " && a.ADJEKTIV == " " && a.WEITERE == " ".]

- (lat. *merx* >) *aus-merz-en* ("beseitigen")
- *benz-en* ("bitten")
- *flachs-en* ("lustigen Unsinn reden")
- (lat. *poscere* > ) *forsch-en*
- *lunz-en* ("schauen")
- *pansch-en* ("im Wasser wühlen")
- *plansch-en* ("im Wasser wühlen")
- *plins-en* ("weinen")
- (pol. *kurzyk* > ) *quarz-en* ("rauchen")
- *schnurps-en* ("abbeißen")
- (mhd. *siuften* >) *seufzen*
- (ital. *stravagante* > ) *strabanz-en* ("umherstreifen")
- *strenz-en* ("stehlen")
- *trenz-en* ("Tiergeräusch")
- (germ. \**wahsjan* >) *wachs-en* ("größer werden")

### Noun root ending in *s*

Only consonant+s^[SELECT * WHERE (like(a.WURZEL, "%s %") || like(a.WURZEL, "%z %") || like(a.WURZEL, "%sch %")) && a.NOMEN != " ".]

remove regex: ^\| \S*[aeiouäöütsz](s|z|sch) .+\n

- *Arsch* > *ver-arsch-en* 
- *Balz* > *balz-en* 
- (lat. *pūmex/pūmicis* >) *Bims* > *bims-en* ("mit Bimsstein glätten")  
- *Bolz-en* > *bolz-en* 
- (germ. \**þahsu* >) *Dachs* > *dachs-en* ("fest schlafen wie ein Dachs")
- *Filz* > *filz-en* 
- *Flansch* > *flansch-en* 
- *Fuchs* > *ein-fuchs-en* 
- (germ. \**fertan* >) *Furz* > *furz-en*
- (gr. *gýpsos* >) *Gips* > *gips-en*
- *Glanz* > *glänz-en* 
- *Gunks* > *gunks-en* ("mit dem Arm stoßen")
- (germ. \**halsa* >) *Hals* > *hals-en* ("umarmen")
- *Harsch* > *harsch-en* "vereisen" 
- *Harz* > *harz-en*
- (germ. \**hertan* >) *Herz* > *herz-en*
- (germ. \**hulta* >) *Holz* > *holz-en*
- *Kauderwelsch* > *kauderwelsch-en* 
- *Kranz* > *um/be-kränz-en* 
- *Krebs* > *krebs-en*
- (ital. *credenza* >) *Kredenz* > *kredenz-en*
- (germ. \**len-tī̌na* >) *Lenz* > *lenz-en*
- *Luchs* > *luchs-en* 
- (germ. \**malta* >) *Malz* > *malz-en*
- *Mansch* > *mansch-en*
- *Mensch* > *ent-mensch-en* 
- (lat. *pellīcium* >) *Pelz* > *pelz-en*
- *Pirsch* > *pirsch-en* 
- (lat. *pulsus* >) *Puls* > *puls-en*
- *Ramsch* > *ver-ramsch-en* 
- *Rülps* > *rülps-en* 
- *Runks* > *runks-en*
- (germ. \**salta* >) *Salz* > *salz-en*
- (germ. \**smulta* >) *Schmalz* > *schmalz-en*
- (germ. \**smulta* >) *Schmelz* > *schmelz-en*
- (germ. \**smertan* >) *Schmerz* > *schmerz-en*
- *Schurz* > *schürz-en*
- (germ. \**sturtjan* >) *Sturz* > *stürz-en*
- *Tanz* > *tanz-en* 
- (germ. \**wahsa* >) *Wachs* > *wachs-en* ("Bienenwachs")
- (germ. \**waltō* >) *Walz* > *walz-en*
- (fr. *wambuis* >) *Wams* ("Ritterjacke") > *wams-en* ("prügeln")
- *Wunsch* > *wünsch-en* 
- (lat. *cēnsus* >) *Zins* > *ver-zins-en*

### Adjective root ending in *s*

only with consonant, without t.^[SELECT * WHERE (like(a.WURZEL, "%s %") || like(a.WURZEL, "%z %") || like(a.WURZEL, "%sch %")) && a.ADJEKTIV != " ".]

- (lat. falsus >) falsch > fälschen
- ganz > ergänzen
- (glupisch >) glupsch > glupschen
- (höfisch >) hübsch > aufhübschen
- latsch > latschen
- morsch > vermorschen
- (germ. \*swarta >) schwarz > schärzen

### Other roots ending in *s*

Proper names:^[SELECT * WHERE (like(a.WURZEL, "%s %") || like(a.WURZEL, "%z %") || like(a.WURZEL, "%sch %")) && a.WEITERE != " " && a.BEDEUTUNG == "Name".]

Franz > verfranzen ("sich verfliegen")
Peter Hartz > hartzen
SMS > simsen

## *ig* (46)

96 examples

Semanitically unclear, cf. enden/endigen, kreuzen/kreuzigen, schaden/schädigen, begnaden/begnadigen

### Noun root > *ig*-verb stem (35)

Without prefixes:^[SELECT * WHERE like(a.VERB, "% -ig %") && !like(a.VERB, "%- %") && a.NOMEN != " " ORDER BY a.STAMM.]

- *Angst* > *ängst-ig-en*
- *Band* > *bänd-ig-en*
- *Befehl* > *befehl-ig-en*
- *Bod-en* > *bod-ig-en*
- *Ende* > *end-ig-en*
- *Huld* > *huld-ig-en*
- *Kreuz* > *kreuz-ig-en*
- *Kunde* > *künd-ig-en*
- *Nacht* > *nächt-ig-en*
- *Pein* > *pein-ig-en*
- *Schad-en> *schäd-ig-en*
- *Stein* > *stein-ig-en*
- *Würde* > *würd-ig-en*

With prefixes:^[SELECT * WHERE like(a.VERB, "% -ig %") && like(a.VERB, "%- %") && a.NOMEN != " " ORDER BY a.STAMM.]

- *Absicht* > *be-absicht-ig-en*
- *Augenschein* > *be-augenschein-ig-en*
- *Eid* > *ver-eid-ig-en*
- *Erde* > *be-erd-ig-en*
- *Fried-en* > *be-fried-ig-en*
- *Gewalt* > *ver-gewalt-ig-en*
- *Glaube* > *be-glaub-ig-en*
- *Gnade* > *be-gnad-ig-en*
- *Hand* > *aus-händ-ig-en*
- *Herz* > *be-herz-ig-en*
- *Kost* > *ver-köst-ig-en*
- *Lob* > *be-lob-ig-en*
- *Nachricht* > *be-nachricht-ig-en*
- *Recht* > *be-recht-ig-en*
- *Rücksicht* > *be-rücksicht-ig-en*
- *Schein* > *be-schein-ig-en*
- *Seite* > *be-seit-ig-en*
- *Sicht* > *be-sicht-ig-en*
- *Teil* > *be-teil-ig-en*
- *Vollmacht* > *be-vollmächt-ig-en*
- *Vorrecht* > *be-vorrecht-ig-en*

### Adjective root > *ig*-verb stem (11)

Without prefix^[SELECT * WHERE like(a.VERB, "% -ig %") && !like(a.VERB, "%- %") && a.ADJEKTIV != " " ORDER BY a.STAMM.]

- *genehm* > *genehm-ig-en*
- *rein* > *rein-ig-en*
- *satt* > *sätt-ig-en*

With prefix^[SELECT * WHERE like(a.VERB, "% -ig %") && like(a.VERB, "%- %") && a.ADJEKTIV != " " ORDER BY a.STAMM.]

- *fest* > *be-fest-ig-en*
- *gerade* > *be-grad-ig-en*
- *gut* > *be-güt-ig-en* (≠ gütig)
- *nieder* > *er-niedr-ig-en* (≠ niedrig)
- *sanft* > *be-sänft-ig-en*
- *schön* > *be-schön-ig-en*

fossilised examples^[SELECT * WHERE like(a.STAMM, "% -ig %") && like(a.STAMM, "%- %") && a.ADJEKTIV == " ".]

- germ. \**halla* ("schwach") > *be-hell-ig-en*
- mhd. *swifte* > *be-schwicht-ig-en*

### Noun root > *ig*-adjective stem

examples^[SELECT * WHERE like(a.STAMM, "% -ig %") && !like(a.STAMM, "%- %") && !like(a.KOGNATE, " ~%") && a.ADJEKTIV != " ".]

- *Demut* > *demüt-ig* > *demütig-en*
- *Fleiß* > *fleiß-ig* > *be-fleißig-en*
- *Flucht* > *flücht-ig > *ver-flüchtig-en*
- *Fluss* > *flüss-ig* > *ver-flüssig-en*
- *Gegenwart* > *gegenwärt-ig* > *ver-gegenwärtig-en*
- *Geist* > *geist-ig* * *ver-geistig-en*
- *Gunst* > *günst-ig* > *ver-günstig-en*
- *Heil* > *heil-ig* > *heilig-en*
- *Kraft* > *kräft-ig* > *kräftig-en*
- *Kunde* > *kund-ig* > *er-kundig-en*
- *Last* > *läst-ig* > *be-lästig-en*
- *Leid* > *leid-ig* > *be-leidig-en*
- *Lust* > *lust-ig* > *be-lustig-en*
- *Macht* > *mächt-ig* > *be-mächtig-en*
- *Maß* > *mäß-ig* > *mäßig-en*
- *Mund* > *münd-ig* > *ent-mündig-en*
- *Muße* *müß-ig* > *be-müßig-en*
- *Mut* > *mut-ig* > *er-mutig-en*
- *Nachteil* > *nachteil-ig* > *be-nachteilig-en*
- *Not* > *nöt-ig* > *nötig-en*
- *Ruhe* > *ruh-ig* > *be-ruhig-en*
- *Schuld* > *schuld-ig* > *be-schuldig-en*
- *Sünde* > *sünd-ig* > *sündig-en*
- *Tat* > *tät-ig* > *tätig-en*
- *Verdacht* > *verdächt-ig* > *verdächtig-en*
- *Verstand* > *verständ-ig* > *verständig-en
- *Vielfalt* > *vielfält-ig* > *ver-vielfältig-en*
- *Wille* > *will-ig* > *willig-en*
- *Zeit* *zeit-ig* > *zeitig-en*
- *Zucht* > *zücht-ig* > *züchtig-en*

Komplex^[SELECT * WHERE like(a.STAMM, "% -ig %") && like(a.STAMM, "%- %") && !like(a.KOGNATE, " ~%") && a.ADJEKTIV != " ".]

- *Seite* > *ein-seit-ig* > *ver-einseitig-en*
- *Stand* > *selbst-ständ-ig* > *ver-selbstständig-en*
- *Stand* > *voll-ständ-ig* > *ver-vollständig-en*

### Verb root > *ig*-adjective stem

examples^[SELECT * WHERE like(a.STAMM, "% -ig %") && like(a.KOGNATE, " ~%") && a.ADJEKTIV != " ".]

- *ein-en* > *ein-ig* > *einig-en*
- *leb-en* > *leb-end-ig* > *ver-lebendig-en*
- *nachlass-en* > *nachläss-ig* > *ver-nachlässig-en*
- *richt-en* > *richt-ig* > *be-richtig-en*
- *trag-en* > *ein-trächt-ig* > *be-einträchtig-en*
- *wart-en* > *ge-wärt-ig* > *gewärtig-en*

grammaticalised examples^[SELECT * WHERE like(a.STAMM, "% -ig %") && like(a.VERB, "%- %") && like(a.KOGNATE, " ~%") && a.ADJEKTIV == " ".]

- ahd. *bizīh-an* ("beschuldigen") > ahd. *bizih-tīg* ("beschuldigend") > *bezichtig-en*
- *schaff-en* > mhd. *schef-tic* ("tätig") > *be-schäftig-en*
- *walt-en* > mhd. *walt-ec* ("mächtig") > *be-wältig-en*
- mhd. *ze werce stellen* > nhd. *werkstell-ig* > *be-werkstellig-en*

### Adjective root ending in *ig*

examples^[SELECT * WHERE like(a.WURZEL, "%ig %") && a.NOMEN == " " && a.ADJEKTIV != " " ORDER BY a.STAMM.]

- *billig* > *billig-en*
- *ewig* > *ver-ewig-en*
- *fertig* > *fertig-en*
- *fähig* > *be-fähig-en*
- *ledig* > *er-ledig-en*
- *schleunig* > *be-schleunig-en*
- *selig* > *be-selig-en*
- *stetig* > *be-stätig-en*
- *stetig* > *ver-stetig-en*
- *tüchtig* > *er-tüchtig-en*
- *übrig* > *er-übrig-en*

## *lich*

38 examples, all existing adjectives

### Noun root > *lich*-adjective stem

examples^[SELECT * WHERE like(a.STAMM, "% -lich %") && !like(a.KOGNATE, " ~%").]

- *Bild* > *bild-lich* > *ver-bildlich-en*
- *Bürger* > *bürger-lich* > *ver-bürgerlich-en*
- *Christ* > *christ-lich* > *ent-christlich-en*
- *Ding* > *ding-lich* > *ver-dinglich-en*
- *Ehe* > *ehe-lich* > *ehelich-en*
- *Einheit* > *einheit-lich* > *ver-einheitlich-en*
- *Gegenstand* > *gegenständ-lich* > *ver-gegenständlich-en*
- *Gott* > *gött-lich* > *ver-göttlich-en*
- *Hass* > *häss-lich* > *ver-hässlich-en*
- *Haus* > *häus-lich* > *ver-häuslich-en*
- *Heim* > *heim-lich* > *ver-heimlich-en*
- *Herr* > *herr-lich* > *ver-herrlich-en*
- *Körper* > *körper-lich* > *ent-körperlich-en*
- *Leib* > *leib-lich* > *ver-leiblich-en*
- *Mann* > *männ-lich* > *ver-männlich-en*
- *Mensch* > *mensch-lich* > *ent-menschlich-en*
- ahd. *niot* ("Verlangen") > *nied-lich* > *ver-niedlich-en*
- *Person* > *persön-lich* > *ent-persönlich-en*
- *Recht* > *recht-lich* > *ver-rechtlich-en*
- *Sache* > *sach-lich* > *ver-sachlich-en*
- *Schrift* > *schrift-lich* > *ver-schriftlich-en*
- *Sinn* > *sinn-lich* > *ver-sinnlich-en*
- *Sinnbild* > *sinnbild-lich* > *ver-sinnbildlich-en*
- *Sitte* > *sitt-lich* > *ent-sittlich-en*
- *Sprache* > *sprach-lich* > *ver-sprachlich-en*
- *Staat* > *staat-lich* > *ver-staatlich-en*
- *Stoff* > *stoff-lich* > *ver-stofflich-en*
- *Weib* > *weib-lich* > *ver-weiblich-en*
- *Welt* > *welt-lich* > *ver-weltlich-en*
- *West-en* > *west-lich* > *ver-westlich-en*

### Verb root > *lich*-adjective stem

examples^[SELECT * WHERE like(a.STAMM, "% -lich %") && like(a.KOGNATE, " ~%").]

- *anschau-en* > *anschau-lich* > *ver-anschaulich-en*
- *deut-en* > *deut-lich* > *ver-deutlich-en*
- *mög-en* > *mög-lich* > *er-möglich-en*
- *wirk-en* > *wirk-lich* > *ver-wirklich-en*

### Adjective root > *lich*-adjective stem

examples^[SELECT * WHERE like(a.STAMM, "% -lich %") && like(a.KOGNATE, " ~ ADJ%").]

- *äußer* > *äußer-lich* > *ver-äußerlich-en*
- *inner* > *inner-lich* > *ver-innerlich-en*
- *offen* > *öffen-t-lich* > *ver-öffentlich-en*
- *weich* > *weich-lich* > *ver-weichlich-en*
