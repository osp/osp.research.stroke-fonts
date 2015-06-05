This document is a work-on progress list on current various stroke fonts attempts.

The sources are :
- an presentation at LGM 2015 at Toronto (http://pad.stdin.fr/r/stroke-fonts.md)
- a transcript of a BOF at the same LGM (http://libregraphicsmeeting.org/2015/programme/##gijs-de-heij-stroke-fonts-—-open-call-for-a-standard?)
- the fontlog of the Belgica-Belgika font project (http://ospublish.constantvzw.org/foundry/belgica-belgika/)
- and lots of online sources like (https://en.wikipedia.org/wiki/Computer_font#Stroke-based_fonts)

The following list is more or less sorted chronologically.

Any writing and lettering
-------------------------
(To translate to English) Avant l’apparition de la typographie vers 1450 en Occident, l’expérience de l’écriture était en contraste une pratique extrêmement variée (entre la caroline rapide des scribes et la capitale gravée dans le marbre des romains) et unifiée autour du trait et de son ductus. Le poinçon qui a commencé à dessiner des caractères par leur bord (leur extérieur) dans des matières dures destinées à produire en série des lettres en plomb a introduit une manière indirecte de comprendre la lettre. Et ainsi, depuis plus de cinq siècles, la typographie a été industriellement tenue séparée de l’écriture. Depuis la genèse de la typographie digitale, cette séparation a organiquement été maintenue, en partie par la révérence de la loge des typographes se sentant dépositaires d’une très longue tradition, en partie par souci de commodité par les grands éditeurs logiciels par ailleurs aux prises avec l’effroyable chantier de la gestion encore non entièrement résolue des très nombreux systèmes d’écritures existant dans le monde.

Din
---
DIN schriften at the Institute itself in 2008, some versions are redrawn from 1932 plates as fonts with a modularity by blocks, grid based. The centerline version is still to investigate.
(To translate to English) Un des premiers mouvements de reconstruction de l’Allemagne industrielle après la première guerre mondiale est de mettre en place un institut de normalisation, le Deutsches Institut für Normung (DIN). Et lorsqu’il s’agit, au milieu des années vingt de décrire un système d’écriture standardisé, c’est par le trait et sur une grille que les ingénieurs allemands tentent de rassembler d’une manière cohérente l’ethos de chaque lettre. Pour ces outilleurs, l’épaisseur du tracé est défini par l’outil qui trace, le trait par son centre, la typographie des bords produite est donc un artefact local, perpétuant ainsi trois millénaires d’écriture humaine. Ce standard se plie donc à toutes sortes de variations en fonction des besoins, plus ou moins décrites dans les planches du standard, et reste largement à déduire au cas par cas par le bon sens de ses utilisateurs.
(http://ospublish.constantvzw.org/foundry/osp-din/)

Hershey
-------
Another more broad approach use the public domain Hershey typefaces as python script to simulate pseudo-fonts functions.
(To translate to English) Dans les années soixante, lorsqu’il semble que les machines à commande numériques commencent à être introduites au US Naval Weapons Laboratory, le DR. Hershey met en place une série d’instructions permettant la gravure de lettres simple pour le marquage industriel et les premiers affichages digitaux à base de vecteurs. Loin du contexte typographique, ce jeu d’instruction circule librement sans licence trop restrictive, et est progressivement implémentée dans nombre d’applications industrielles civiles. Un nombre incalculable de plaques nominatives d’ascenseur sont ainsi gravée avec des lettres dessinées par l’armée américaine.
(https://en.wikipedia.org/wiki/Hershey_font)

Metafont
--------
(To translate to English) À la fin des années septante, le mathématicien Donald Knuth est mécontent du traitement typographique réservé à l’édition de ses équations et décide de mettre en place un système de composition entier, TeX, pour publier ses ouvrages “The Art of Computer Programming” encore en écriture à l’heure actuelle. Confiant de pouvoir construire numériquement l’antédiluvien lien entre typographie et mathématiques, Knuth décrit de manière algorithmique le format Metafont destiné à être utilisé dans TeX. Et c’est principalement par le ductus central que Metafont trace ses lettres et signes. N’utilisant que du code sans support visuel direct, le format est craint ou boudé pendant longtemps par les typographes. Le monde scientifique et lui seul utilise depuis le système TeX avec majoritairement les seules fontes proposées par son créateur, et cela sans souci particulier…
(https://en.wikipedia.org/wiki/Metafont)

Postscript Type 3
-----------------
(To translate to English) À la fin des années quatre-vingt, Adobe, après avoir mis en place le standard typographique appelé Type 1 et encore à la base des standards actuels, s’aventure à introduire le Type 3. Ce format permet de stocker dans chaque glyphe (espace visuel décrivant une lettre dans une fonte) n’importe quel type d’objet. Y compris donc des traits simples ouverts ou non plutôt qu’un contour strictement fermé. Ce qui permet à certains typographes d’introduire des polices construites selon un principe de dessin vectoriel se rapprochant de l’écriture. Mais l’ouverture du format, autorisant l’inclusion de tout type d’objet, a tendance à saturer la mémoire encore très restreinte des unités de traitement des imprimantes de l’époque. Et une réputation d’insécurité fait rapidement retirer les Type 3 de la circulation par Adobe, qui ne veut prendre aucun risque de fiabilité des solutions proposées par elle au moment même où Apple et Microsoft l’attaquent avec le format Truetype concurrent du Type 1.
(https://en.wikipedia.org/wiki/PostScript_fonts#Type_3)

Stylized stroke fonts and Saffron (Asian interest in stroke fonts)
------------------------------------------------------------------
Saffron, a framework for representing, rendering, and animating Type (adopted by Adobe Flash, Amazon Kindle and been licensed by Monotype)
Outline-based Asian fonts often require 5 to 15 MB of storage, which is problematic for memory-constrained devices such as cell phones. In contrast, uniform-width stroke-based fonts (USFs) require significantly less storage — for example, the GB2312 character set can be represented compactly with only 250 KB. However, since each stroke has a uniform width, USFs lack the expressiveness and the cultural acceptance of their outline-based counterparts. Saffron supports an improved representation for stroke-based fonts called Stylized Stroke Fonts (SSFs) which provide the expressiveness of traditional outline-based fonts and the small memory footprint of USFs.
Automatic grid fitting system aligns strong vertical and horizontal edges of glyphs to the pixel grid or to the sub-pixel grid.
Character simplification - Chinese, Japanese, and Korean characters often contain many strokes which are difficult to render distinctly at small sizes. Simply aligning horizontal and vertical strokes to the pixel grid (e.g., by rounding each stroke to the nearest grid point) is not sufficient to produce a clear image. Saffron's MAZ grid fitting system performs character simplification (as needed) to ensure that each character remains clear and legible, even at small sizes.
Sub-pixel rendering - The program supports sub-pixel rendering to optimize image quality for LCD displays. Although RGB vertical striped arrays are common, Saffron can also render to alternative pixel patterns such as RGB delta arrays, which are often used on digital camera LCDs. In addition, prototype implementations of Saffron are optimized for Clairvoyante's PenTile patterns. During sub-pixel rendering, the program reduces color fringing artifacts that would otherwise be visible and at small sizes.
Continuous stroke modulation - Saffron exploits the inherent properties of distance fields to provide continuous stroke modulation (CSM), the continuous modulation of both stroke weight and edge sharpness. This allows users to tune the appearance of text to suit individual preference. For example, sharper, softer, thinner, and thicker versions of the same typeface can be rendered by using different CSM parameters.
(http://www.ronaldperry.org/)
(https://en.wikipedia.org/wiki/Saffron_Type_System)
(http://www.ronaldperry.org/SaffronWebPage/index.html)
(http://www.dynalab.com/Products/DigiType.aspx)

SVG fonts
---------
Extract from the transcript (20:00 -> 25:51)
Simon: There isn't really a standarized stroke based file-format? SVG fonts?

Chris: SVG-fonts allowed it in theory but the problem was the strokeswidths were not in the right coordinate-system. You had to have very small stroke width so when it came down to the space where the actual glyphs were drawn you would get consistent result. And SVG-fonts have completely gone away now.

Amelia: There's MetaFonts which are used in LaTEX, but there's not, any computers that I know of that will live-render them, there are special processes that convert them to bitmap for their print-layout.

Chris: Strokefonts are used on (pen-)plotters and their used in Printed Circuit Board (PCB) manufacturing.

Simon: But you can't exchange the fonts; they are all propietary. PCB-design is actually what made me interested in this kind of stuff. Because I have a stroke-font and I want to release it or actually use it...

Chris: But there is no format for you to...

Simon: I have a patent / (pattern ?) dictionary right now.

Gijs: I like the idea of live-rendering as the font becomes an object that can also respond to it's environment. Is that something that would be possible?

Chris: It's where the comment 'lets not call this a font' helps.  You know about SVG and OpenType? Their idea of having SVG-glyphs inside an OpenType font. In TrueType you had quadratic bezier-curves, in OpenType thay also added cubic bezier's like in Postscript Type 1 fonts, so that were the two types but you could only have the one or the other. But since the've added a bunch of other types of outlines, including SVG. The SVG type supports multiple colors, it can bring in colors from the environment,  it can be animated. And all the people who where doing like HarfBuzz said you can't have animated glyphs: a glyph is rendered once as a bitmap at a certain size and then it's cached; their entire architecture depends on it not being animated. Then I pointed out Google also added something to OpenType which has PNG in it for colored bitmap fonts, and there's animated PNG which actually looks the same so people could put those in so those would be animated and their head just exploded. You're not allowed to that ever for fonts.

Amelia: But the problem is there is such a strong user use because of emoticons and icons. On iOS-devices they are currently - I think - still implemented as SVG-fonts. Everywhere else they are implemented as little PNG-images the browser just dumps in.

Chris: Actually Apple have their own format, which is totally undocumented, but used bitmap images they had all the different sizes that you would want in 1-pixel increments for a range of sizes. And three or four sizes reverse-engineered them and started producing their own, but being Apple they did not standardize it, because then they had to standardize it.

Pierre: Yes, it's true, if we don't call it a font we gain a lot of freedom, but still we need some connection to the typography stack.

Gijs: That's where an idea like Polyfills are interesting. If the technology is missing you just implement you just implement it yourself.

(http://fr.wikipedia.org/wiki/SVG_Font)

"Classical" typographic hack
----------------------------
Doubling of the path, back and forth. Description needed here.

Scribus and other OSP hacks
------------
Page layout software could print manipulated Truetype fonts with open contours, and a hack prevent the automatic closing operation. 
(To translate to English) Hacking – En mélangeant sans hiérarchie précise ces quatre expériences, le collectif OSP (Open Souce Publishing) suit un sentier de traverse pour ramener cette question des ‘stroke fonts’ régulièrement au milieu de la table. Ainsi un alphabet double est tracé par éléments modulaires dans un logiciel de dessin, à distance des pratiques typographiques. Les lettres y prennent chacune deux formes différentes pour appuyer leur rapport avec l’écriture où l’aspect de chaque lettre peut est adapté en fonction de l’influence visuelle de ses voisines. Un visuel en spirale et récursif expérimente avec un autre type de déformation que ces formes produisent. Ailleurs, un hack modifie la fermeture automatique des fontes considérées par le logiciel de mise en page Scribus comme une erreur mais volontairement introduites pour produire des fontes au trait. Plus loin, le trait est utilisé à l’essence de sa non-épaisseur pour produire la lame sinueuse des poinçons qui frappent les lettres ORS sur des plaques de laiton. Ou encore ces projets de couverture d’ouvrages à paraître où le trait est démultiplié par l’épaisseur sur des lettres superposées. Le trait encore est interrompu par un algorithme pour permettre la création automatique de monogrammes pour un média social en préparation. Le trait toujours, lors de son apparition, gelé temporairement par efficacité pour une fonte à utiliser selon les standards par un tiers en Italie.
Retour au Belgika – Le propriétaire le demande, il faut un grand Belgika sur le toit de cette baraque, pour marquer le lieu. L’ingénieur trace les sept lettres sur une feuille et les dimensionne. Quelqu’un, ou peut-être étaient-ils deux, peint avec un certain soin chaque lettre. Un empattement est ajouté au G pour lui donner une sorte d’équilibre. La graisse de la barre centrale du B hésite et l’interlettrage est un peu trop mécanique mais le résultat ne manque pas d’élégance. Quand une carte postale immortalise l’alignement des vélos sous cet auvent d’Elisabethville quelques temps après, le contraste des lettres, même en angle, est bien marqué.
Comment plier ces sommes d’expériences pour les amener vers des formes à superposer.

Metapolator
-----------
Description needed here.

Lasse's Bauhaus logo experiment
-------------------------------
Description needed here.

Mondialisation
--------------
M17N - Description needed here.

Harfbuzz
--------
Not a font system, but need some introspection.
(https://github.com/behdad/harfbuzz)

HZ
--
"In the fall of 1992, URW has completed computer programs for manufacturers ofsetting and composition equipment. These programs are outstanding in the field of micro-typography. To express his delight over the results, Hermann Zapf, the inventor, has called them “nonplusultra” in advanced typography. At the beginning, he and URW wanted to renovate in the age of computers that what Johannes Gutenberg had achieved five hundred years ago: namely, a justified setting of text with equal inter-word spacing and optical straight aligned margins. Our hz-program has achieved this and even more, namely its application saves 3-5% of paper. Therefore, the hz-program does environmental protection by typographic means."
(http://cahiers.gutenberg.eu.org/fitem?id=CG_1997___27_34_0)
(http://cajun.cs.nott.ac.uk/compsci/epo/papers/volume6/issue3/zapf.pdf)
(http://www.typografi.org/justering/gut_hz/karow.pdf)

InkML
-----
(https://en.wikipedia.org/wiki/InkML)
(http://www.w3.org/2002/mmi/ink)

GML
---
(http://www.graffitimarkuplanguage.com/)
