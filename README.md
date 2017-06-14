# Memory notes for Breath of the Wild (v1.2.0, USA)

#### This file contains information about the memory Breath of the Wild uses.
---

I've only included the addresses/pointers that I know of at the moment.

If you know of any more that aren't on this list or if I got something wrong, feel free to edit it.
_**Anyone can edit this file**_, just make sure whatever you add has something to do with the list below!

Includes:

* [Address Information, what they do, etc](#addresses---runes-v120-usa)
* [Pointer locations, where they lead to, etc](#pointers---object-structure-v120-usa)
* [Memory dump of every address (for creating pointers)](#full-botw-memory-dump-v120-usa)

## Pointers - _Object Structure_ (v1.2.0, USA)
All of these stem from the address "43856C88", which is what you are pointing at with the stasis or magnesis rune. 
Pointers will only "point" to the correct address/value if you have the rune's crosshairs on a valid object. Otherwise
it will point to a value that is "invalid"

Object structure also includes structure for enemies.

|  Pointer Notation  | Address it points to |          Notes
|--------------------|----------------------|-------------------------
|[43856C88] + 0x0    |Start of object's data|Object's name is in UTF8
|[43856C88] + 0x50   |Stasis ID             |ID stored when stasis'd, FFFFFFFF = no object stasis'd
|[43856C88] + 0x274  |Object's size X,Y,Z.  |None
|[43856C88] + 0x204  |Spoofed X coordinate  |None
|[43856C88] + 0x214  |Spoofed Y coordinate  |None
|[43856C88] + 0x224  |Spoofed Z coordinate  |None
|[43856C88] + 0x794  |Awareness of Link     |FFFFFFFF/00000000 = Doesn't see Link
|[43856C88] + 0x71C  |If Object is a weapon |FFFFFFFF = Not a weapon
|[43856C88] + 0x72C  |If Object is a sheild |FFFFFFFF = Not a sheild
|[43856C88] + 0x364  |IsStasis'd            |* 1040 = True, 1000 = False
|[43856C88] + 0x48F  |IsStasis'd x2         |* X01X = Being Targeted, X0XC = Froze, X0X4 = Free
|[43856C88] + 0x540  |Object Health         |Number of HP is in Decimal

_*_ 1040 = 00001040 (16-bit value).

_*_ X's are bits that may vary depending on the object.

## Addresses - _Runes_ (v1.2.0, USA)
These addresses apply to the stasis and magnesis runes. Need to add other runes later.

|Address |  What the value is  |   Notes
|--------|---------------------|----------
|43856C88|Crosshair Target's ID|00000000 = No object within crosshairs
|43856B58|Crosshair Position X |None
|43856B5C|Crosshair Position Y |None
|43856B54|Crosshair Position Z |None

## Addresses - _Link's data_ (v1.2.0, USA)
|Address |  What the value is  |   Notes
|--------|---------------------|----------
|4398F294|Link's Current Health|Number of HP is in Decimal 
|439D8738|Link's Gravity       |3F800000 = 1x Gravity (Normal)
|439D8724|Link's Speed         |3F800000 = 1x Speed (Normal)
|11BC5B40|Link's Position X    |Coordinate on Map
|11BC5B48|Link's Position Y    |Coordinate on Map
|11BC5B44|Link's Position Z    |Coordinate on Map

## Full BotW Memory Dump (v1.2.0, USA)
From Addresses 0C900000 to 4C8A0000. Can be used to create pointers from any starting address without creating new dumps every time.
I recommend using BullyWiiPlaza's [Universal Pointer Searcher](https://github.com/BullyWiiPlaza/Universal-Pointer-Searcher) to create pointers using this dump.

[Here is a link to the .bin download (Google Drive)](https://drive.google.com/file/d/0B_zcN8fQAOWxdUhxR25lTnlqZUU/)
