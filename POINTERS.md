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
|[43856C88] + 0x72C  |If Object is a shield |FFFFFFFF = Not a shield
|[43856C88] + 0x364  |IsStasis'd            |* 1040 = True, 1000 = False
|[43856C88] + 0x48F  |IsStasis'd x2         |* X01X = Being Targeted, X0XC = Froze, X0X4 = Free
|[43856C88] + 0x540  |Object Health         |Number of HP is in Decimal

_*_ 1040 = 00001040 (16-bit value).

_*_ X's are bits that may vary depending on the object.

## _Link's data_ (v1.2.0, USA)
| Pointer Notation |Address it points to|          Notes
|------------------|--------------------|------------------------
|[439D89A4] + 0x140|Link's Coordinates  |Relative to map. Order: YZX
|[42274980] + 0x388|Link's Health       |Number of HP is in Decimal
|[43AD1E30] + 0x770|Link's Damage       |3F800000 = Normal Damage

## _Gear_ (All Versions, USA)
**Drop your weapon then pick it back up after editing bonuses or it might softlock your game.
Will not work on every weapon since not all weapons allow bonuses.**

|                 Pointer Notation               |   Address it points to    |          Notes
|------------------------------------------------|---------------------------|-------------------------
|[[[[101C1D40] + 0x2580] + 0xBDC] + 0x40] + 0x980|Equipped Bow Durability    |Durability Number is in Decimal
|[[[[101C1D40] + 0x2580] + 0xBDC] + 0x40] + 0x990|Equipped Bow Size          |Order: YZX, 3F800000 = Normal
|[[[[101C1D40] + 0x2580] + 0xBDC] + 0x40] + 0xAE0|Equipped Bow Bonus         |*800000XX = Bonus
|[[[[101C1D40] + 0x2580] + 0xBDC] + 0x40] + 0xAE4|Equipped Bow Bonus Value   |Value is in Decimal
|[[[[101C1D40] + 0x2580] + 0xB80] + 0x40] + 0x980|Equipped Shield Durability |Durability Number is in Decimal
|[[[[101C1D40] + 0x2580] + 0xB80] + 0x40] + 0x990|Equipped Shield Size       |Order: YZX, 3F800000 = Normal
|[[[[101C1D40] + 0x2580] + 0xB80] + 0x40] + 0xAE0|Equipped Shield Bonus      |*800000XX = Bonus
|[[[[101C1D40] + 0x2580] + 0xB80] + 0x40] + 0xAE4|Equipped Shield Bonus Value|Value is in Decimal
|[[[[101C1D40] + 0x2580] + 0xB24] + 0x40] + 0x980|Equipped Weapon Durability |Durability Number is in Decimal
|[[[[101C1D40] + 0x2580] + 0xB24] + 0x40] + 0x990|Equipped Weapon Size       |Order: YZX, 3F800000 = Normal
|[[[[101C1D40] + 0x2580] + 0xB24] + 0x40] + 0xAE0|Equipped Weapon Bonus      |*800000XX = Bonus
|[[[[101C1D40] + 0x2580] + 0xB24] + 0x40] + 0xAE4|Equipped Weapon Bonus Value|Value is in Decimal

*XX = Bonus value. See [here](https://github.com/Megabyte918/BotW-Cheat-Codes/blob/master/All%20Versions/Equipped%20Weapon%20Bonus%20Modifier) for more information on bonus values.

## _Timers_ (v1.2.0, USA)
| Pointer Notation |Address it points to     |          Notes
|------------------|-------------------------|------------------------
|[43AD2220] + 0x488|Master Sword Charge Timer|40200000 = Power Restored
|[43AD2220] + 0x470|Urbosa's Fury Timer      |Float value
|[43AD2220] + 0x458|Revali's Gale Timer      |Float value
|[43AD2220] + 0x464|Daruk's Protection Timer |Float value
|[43AD2220] + 0x47C|Mipha's Grace Timer      |Float value

## _Miscellaneous_ (v1.2.0, USA)
| Pointer Notation                 |Address it points to      |          Notes
|----------------------------------|--------------------------|------------------------
|[42452678] + 0x2B64               |Master Sword Glow         |00000000 = Not glowing, 00000001 = Glowing
|[10903D74] + 0x50                 |Wolf Link's Health        |Number of HP is in Decimal
|[[3FAB6B1C] + 0xFFFFCA38] + 0x2DD8|Amount of horse whips     |Value decrements by 00010000 per whip
