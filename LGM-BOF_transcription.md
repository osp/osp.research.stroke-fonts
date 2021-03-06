## STROKE FONTS Birds Of a Feather discussion transcription
### LGM Toronto 2015, Friday 1 May 2015 - 12:20 → 14:00

With :
- Amelia Bellamy-Royds <amelia.bellamy.royds@gmail.com>
- Chris Lilley <chris@w3.org>
- Lasse Fister <lasse@graphicore.de>
- Simon Budig <simon@budig.de>
- Colm O'Neill <mail@colm.be>
- Gijs de Heij <gijs@de-heij.com>
- Pierre Huyghebaert <pierre@speculoos.com>
- Ludivine Loiseau <ludi.loiseau@gmail.com>

---

`00:01:12`

_Pierre H_: So yesterday, during the talk, we did a small tour, but it's not the full range. We ommitted for example Pierre Marchand's fork of Scribus that removes the code that closes paths, for which case true type fonts can become strokes, but it's quite clunky. It only works on Pierre's old computer so it doesn't seem to be the way to go.

*General talk until 12:26 and kerfuffle while Lasse shows his experiments around the Bauhaus logo.*

---

`15:24:`

*First description of CPS Cascading Properties Sheet until `19:58`*

---

`19:58 till 22:07`

*State of standards; SVG fonts, etc, Hershey, Metafont*

---

*`22:07` CPS questions, always rendering, responsiveness to environments?*

*_Chris_ describes what is accepted into Opentype, SVG glyphs inside Opentype fonts until `23:55`*

---

20 -> 25
_Simon:_
There isn't really a standarized stroke based file-format? SVG fonts?

_Chris:_
SVG-fonts allowed it in theory but the problem was the strokeswidths were not in the right coordinate-system. You had to have very small stroke width so when it came down to the space where the actual glyphs were drawn you would get consistent result. And SVG-fonts have completely gone away now.

_Amelia:_
There's MetaFonts which are used in LaTEX, but there's not, any computers that I know of that will live-render them, there are special processes that convert them to bitmap for their print-layout.

_Chris:_
Strokefonts are used on (pen-)plotters and their used in Printed Circuit Board (PCB) manufacturing.

_Simon:_
But you can't exchange the fonts; they are all propietary. PCB-design is actually what made me interested in this kind of stuff. Because I have a stroke-font and I want to release it or actually use it...

_Chris:_
But there is no format for you to...

_Simon:_
I have a patent / (pattern ?) dictionary right now.

_Gijs:_
I like the idea of live-rendering as the font becomes an object that can also respond to it's environment. Is that something that would be possible?

_Chris:_
It's where the comment 'lets not call this a font' helps.  You know about SVG and OpenType? Their idea of having SVG-glyphs inside an OpenType font. In TrueType you had quadratic bezier-curves, in OpenType thay also added cubic bezier's like in Postscript Type 1 fonts, so that were the two types but you could only have the one or the other. But since the've added a bunch of other types of outlines, including SVG. The SVG type supports multiple colors, it can bring in colors from the environment,  it can be animated. And all the people who where doing like HarfBuzz said you can't have animated glyphs: a glyph is rendered once as a bitmap at a certain size and then it's cached; their entire architecture depends on it not being animated. Then I pointed out Google also added something to OpenType which has PNG in it for colored bitmap fonts, and there's animated PNG which actually looks the same so people could put those in so those would be animated and their head just exploded. You're not allowed to that ever for fonts.

_Amelia:_
But the problem is there is such a strong user use because of emoticons and icons. On iOS-devices they are currently - I think - still implemented as SVG-fonts. Everywhere else they are implemented as little PNG-images the browser just dumps in.

_Chris:_
Actually Apple have their own format, which is totally undocumented, but used bitmap images they had all the different sizes that you would want in 1-pixel increments for a range of sizes. And three or four sizes reverse-engineered them and started producing their own, but being Apple they did not standardize it, because then they had to standardize it.

_Pierre:_
Yes, it's true, if we don't call it a font we gain a lot of freedom, but still we need some connection to the typography stack.

_Gijs:_
That's where an idea like Polyfills are interesting. If the technology is missing you just implement you just implement it yourself.

`25:51`

`26:00`
*Apple's custom font format example for iOS by Chris and Amelia
What will be needed for printers? Amelia's concern for backwards compatibility.*
*Usage on the web, loading speeds, font loading API by the W3C*

`31:37`
![](http://ospublish.constantvzw.org/images/LGM-Toronto-workshops/IMG_5281)
*CPS demo by Lasse: Explanations, workflow, importing, anchor points pairs, skeleton generating process*

`49:04`
_Amelia:_
But is there talk of making a font metrics API?

_Chris:_
Oh yeah, the font metrics API will be part of the Houdini initiative, and I'm one of the editors, so yes, you will be able to, on a piece of web page that is styled by CSS, you'll be able to say, this particular run of text, that is in the document what font does it use actually, not the font stack that you would get but which one does it actually use? for the first character and having got that what's it's ascender, it's baseline, and all that sort of stuff. what it's typographic ascent and all that stuff.

_Amelia:_
Oooh!

_Chris:_
So that you can then write polyfills to do things like drop caps or whatever or basically things that line up with other stuff, and this has to join up with the cap height of that line and all that stuff. Which you can't do currently.

_Amelia:_
Which right now, is like a black box, and it's a black box with many broken parts, and many different broken parts on different browsers and aaaaaaah!

_Chris:_
that's why it's called Houdini, because the mission statement is removing some of the magic from this stuff.

_Gijs:_
and is this something that is supported? by the browsers?

_Amelia:_
not yet

_Chris:_
no

_Gijs:_
no but if you speak about the process, is there a willingness?

_Amelia:_
oh oh, *emotionnal* support?

_Pierre:_
haha, that's important.

_Chris:_The first meeting of this group was in February this year (2015) in Sidney. That was when it started. And all the browser people were there, and other people, mostly from the CSS working group, but also from the technical architecture working group and people got handed out, assigned to write documents and whatever and there was some discussion, so it's at a very early stage, there isn't even a editor draft yet, but it's comming. This will be useful.

_Gijs:_ And it's not something that will be killed by Google two months after?

_Chris:_ [...] I understand the concern. No, the browsers are quite interested in this because it means that they don't have to do stuff, instead they give the tools to other people though Javascript and that seems to be the way to move things. They don't really want to add new features they want to add the toolkit for others to add their own features.

_Amelia:_ There are lots of things like turning all the HTML widgets into web components that you can style. I just went through by writing my book on SVG text layout and besides the fact that the browsers so incompletely and inconsistently implement the things we do have, for controlling baseline alignment and what not, the constant annoying thing is when you set the height of the text you don't know how much of that height is above or below the baseline and there is no way to find out. And when you're trying to arrange that text just right along a picture it's...

_Chris:_ yeah that would solve that problem...

`52:39 Ink ML`
How this could be of use for stroke fonts / inspiration at least.
 
`58:50 Back to CPS demo`
_Gijs :_ what's the added value of the CPS?
_Lasse :_ You can specify very global transformations for your font, like the width factor for example (+showing on screen)
_Amelia :_ So, the power is that you can assign that classes to all the points and shapes you have this structured language you can use on your selectors
_Lasse :_ yes cascading style sheet idea [...] + we can define interpolations

`01:02:00`
*Simon speaks a layout system showed the day before (?)*
*He shows some of his experiments on fonts and PCP (?) design 
straight lines and circular segments* 
*unhappy of the default fonts in PCP systems*
→
- he built a small font editor - a python application
- does the drawing with Cairo
- proof of concept thing
- can't yet compose text blocs

*there is an eagle script (?) in PCB where you can run scripts
Simon uses a python script witch process existing fonts 
look curves have survived* 
PCP niches

_Simon:_ these are actually the interesting point - the niches
PCB, pen plotters
CNC 
_Lasse:_ the constrains of the technology force them to continue using strokes fonts

`01:15:08`
_Amelia :_ You're not going to get operating systems on board that would make engraving tools easier. But on the other hand if you could find a mainstream general application font format that you can say all these little niches groups that are currently using stroke fonts. There is this potential that every fonts in the world might eventually be coded in a stroke font
especially for artistic engravers. Somebody that could potentially get on board and say. So in that sens if you can connect all the existing niches that could be a little bit of extra mass to but to get the mainstreams I think the biggest argument - to have one file that could generate that could be more efficient.
    
`01:17:00`
_Pierre H :_ Pierre M uses OpenType.js http://nodebox.github.io/opentype.js/

`1:18:05`
_Amelia :_ Yes. There is this strong demand on web for having text that all stretches to fit a certain width and those sort of artistic text layout.
You have to them with javascript right now.
There is no way to get the font metrics directly except from loading the font file from you javascript and decoding the opentype yourself.

`01:19:00`
*Pierre H and Lasse speaking about the next step of Metapolator.
- importing UFO on the way*

`01:21:15`
_Chris :_ There has been discussion about stroke fonts inside the W3c group. There is possible interest. 
Google font team, Monotype, Adobe - so a collection of different interests.

`01:22:22`
_Gijs :_ Is there a way we can contribute then. 
_Chris :_ One way to do that is to build a W3C group. So you have a mailing list, a wiki and you can produce a report eventually saying look this is the technology and it's ready for standard. You get a set of tools and a place.

_Pierre_ mentions the residency in October 2015.

_Chris :_ I think it needs much more discussions and prototypes.

*Questions / links with Open type format*

_Chris :_ How we used to get things standardized.
(Woff : Web Open Font Format)
Describing the steps.

_Simon :_ Is there ways for Open Type font currently to accept flow parameters, like numbers that would change the appearance of the font?
Because that would be something that would be need for stroke fonts. 

_Amelia :_ There is already a color palette for svg fonts.
 
_Lasse :_ That used to be called CSS variables

`01:29:00`
_Chris :_ svg already have stroke dashes 

_Amelia :_ The question is how much would you encode in the font 
and how much would you allow the rendrer to apply default parameters

---

→ SVG Fonts
`01:32:50`

_Pierre H :_ How was it used how was it problematic?

_Amelia :_ The basic svg fonts there were some control because you could inherit styles. You could create a stroke font and then change the stroke weight. But then things were messy, you couldn't adjust the base line.

_Pierre H :_ 2 sides: the side of the drawing / the side of the usage 

_Simon :_ I think (for) stroke font to be useful you need rendering parameters

_Gijs :_ Then where does this information come from ?

_Amelia :_ (missing transcription)

_Simon :_ And how would it be used out of the web context ? For example in Gimp ?

_Amelia :_ You' ll need a font processing tool

`01:36:25`
_Simon :_ Or some API - like Freetype to pass parameters inside.
You also want to be able to render the stuff with Freetype

_Lasse :_ from stroke font to ttf; but then will be back to multiple master fonts problems 

_Amelia :_ in the short term if can have a uility that could generate a TruType font from a stroke fonts 

_Simon :_ But if we thinking to add stroke fonts to Open Type. Then telling the people ok we have those Open type font...


→ cartography
1:19:45

Pierre H : link to cartograpy - GIS is heavely fonded - because every government has interests in it.


→ (Simon) amateurs of the FabLab movement 

→ Conclusion

_Amelia :_ First step is to come with use cases. What gap is this filling ?
 
`01:46:00`
Founding questions


