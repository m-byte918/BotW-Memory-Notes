# Pointer notes for Breath of the Wild

#### This file contains information about certain Pointers and where they lead to.

## _Object Structure_ (v1.2.0, USA)
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
