# Soft3D engine archaeology

- Engine written in C++, at least some builds include RTTI

## File formats overview

|  | File extension | Platform(s) | Notes & open questions |
|--|----------------|-------------|------------------------|
|✔️|S3DTEX|GA330|images/textures, well-understood
|❌|S3DSTY||
|❌|SAI||probably 3D model animations
|✔️|SAU|A320|AMI ADPCM audio, well-understood
|🔧|SBN|GA330|<p>font (glyphs) + text data (32-bit encoding), mostly understood</p><ul><li>Why is the header length not always the same?</li><li>How to calculate glyph indexes across SBNs?</li></ul>
|🔧|SBN|Win32|font (glyphs) + text data (7-bit encoding), mostly understood
|🔧|SBP|GA330|<p>maps, using [binary space partitioning](https://en.wikipedia.org/wiki/Binary_space_partitioning)</p><ul><li>How to interpret all the chunks?</li><li>Which geometry is used by the game?</li><li>How are textures referenced?</li><li>How are UV coordinates encoded?</li><li>How are lightmaps applied?</li></ul>
|❌|SDT||various _data tables_ without a common format?
|❌|SPL||
|🔧|SOJ||<p>3D objects, partially understood</p><ul><li>How are textures mapped?</li><li>How are UV coordinates encoded?</li><li>Skinning? Animations?</li></ul>
|🔧|SST|GA330|“simple script”, partially understood, but overall structure uncertain
|✔️|STX|GA330|images/textures, well-understood
|✔️|WAR|Win32|AMI ADPCM audio, well-understood

_Let us know if you have had success parsing files from platforms not listed in the table!_

## Some links

### 7 Days

- [Table of known versions of the game](http://web.archive.org/web/20200710065823/https://vitawiki.xyz/doku.php?id=7ds:versions)
- http://legendsworld.net/adventure/game/2455
- http://www.legendsworld.net/phpBB3/viewtopic.php?f=5&t=9745
- https://imgur.com/a/3IMWR7r
- https://sourceforge.net/projects/spkextractor/

### Misc

- [Domestic "Silent Hill" IMGA award-winning mobile game-"7 Nights", can not afford the award](http://web.archive.org/web/20200709200829/http://www.1b2g.com/newsyx/1246.html) (story of the demise of Dingoo Games, in Chinese)

## Games known to use the engine

- 7 Days: Salvation
- [天地道 aka Hellstriker II](https://www.google.com/search?q=天地道+dingoo&tbm=isch) (ships on GA330)
- 斗地主 (ships on GA330)

## Platforms

- Symbian S60
- Dingoo A320
- Gemei A330
- Win32
