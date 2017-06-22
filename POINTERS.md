# Pointer notes for Breath of the Wild

#### This file contains information about certain Pointers and where they lead to.

## _Object Structure_ (v1.2.0, USA)
All of these stem from the address "43856C88", which is what you are pointing at with the stasis or magnesis rune. 
Pointers will only "point" to the correct address/value if you have the rune's crosshairs on a valid object. Otherwise
it will point to a value that is "invalid"

Object structure also includes structure for enemies.

|  Pointer Notation| Address it points to |          Notes
|------------------|----------------------|-------------------------
|[43856C88] + 0x0  |Start of object's data|Object's name is in UTF8
|[43856C88] + 0x50 |Stasis ID             |ID stored when stasis'd, FFFFFFFF = no object stasis'd
|[43856C88] + 0x274|Object's size X,Y,Z.  |None
|[43856C88] + 0x204|Spoofed X coordinate  |None
|[43856C88] + 0x214|Spoofed Y coordinate  |None
|[43856C88] + 0x224|Spoofed Z coordinate  |None
|[43856C88] + 0x794|Awareness of Link     |FFFFFFFF/00000000 = Doesn't see Link
|[43856C88] + 0x71C|If Object is a weapon |FFFFFFFF = Not a weapon
|[43856C88] + 0x72C|If Object is a shield |FFFFFFFF = Not a shield
|[43856C88] + 0x364|IsStasis'd            |00001040 = True, 00001000 = False
|[43856C88] + 0x48F|IsStasis'd x2         |*X01X = Being Targeted, X0XC = Froze, X0X4 = Free
|[43856C88] + 0x540|Object Health         |Number of HP is in Decimal

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

*XX = Bonus value. See [here](https://github.com/Megabyte918/BotW-Cheat-Codes/blob/master/All%20Versions/Equipped%20Gear%20Bonus%20Modifier) for more information on bonus values.

## _[Weapon](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/1%20Handed%20Weapons) Slots_ (v1.2.0, USA)
Information about weapons within the slots of the "Weapons" section of Link's inventory.

| Pointer Notation  |Address it points to      |          Notes
|-------------------|--------------------------|------------------------
|[43CBAD5C] + 0xE384|Name of Weapon in 1st Slot|See Below
|[43CBAD5C] + 0xE374|Slot 1 Equipped State     |See Below. 00010000 = Unequipped, 01010000 = Equipped

Subtract 0x220 from the previous slot's offset to get the offset for the next slot's pointer.
See the "Material Slots" Example below for more clarification.

## _[Bow & Arrow](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Bows%20%26%20Arrows) Slots_ (v1.2.0, USA)
Information about bows & arrows within the slots of the "Bows & Arrows" section of Link's inventory.

| Pointer Notation  |Address it points to       |          Notes
|-------------------|---------------------------|------------------------
|[43CBAD5C] + 0xB904|Name of Bow in 1st Slot    |See Below
|[43CBAD5C] + 0xB8F4|Slot 1 Bow Equipped State  |See Below. 00010000 = Unequipped, 01010000 = Equipped
|[43CBAD5C] + 0xA1A4|Name of Arrow in 1st Slot  |See Below
|[43CBAD5C] + 0xA194|Slot 1 Arrow Equipped State|See Below. 00010000 = Unequipped, 01010000 = Equipped

Subtract 0x220 from the previous slot's offset to get the offset for the next slot's pointer.
See the "Material Slots" Example below for more clarification.

## _[Shield](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Shields) Slots_ (v1.2.0, USA)
Information about shields within the slots of the "Shields" section of Link's inventory.

| Pointer Notation  |Address it points to      |          Notes
|-------------------|--------------------------|------------------------
|[43CBAD5C] + 0x94E6|Name of Sheild in 1st Slot|See Below
|[43CBAD5C] + 0x94D6|Slot 1 Equipped State     |See Below. 00010000 = Unequipped, 01010000 = Equipped

Subtract 0x220 from the previous slot's offset to get the offset for the next slot's pointer.
See the "Material Slots" Example below for more clarification.
If you are looking for the 2nd shield slot, you must subtract 0x1760 (weird). 3rd, 4th, and so on you
must subtract 0x220 as normal.

## _[Armor](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Armor) Slots_ (v1.2.0, USA)
Information about armor within the slots of the "Armor" section of Link's inventory.

| Pointer Notation  |Address it points to     |          Notes
|-------------------|-------------------------|------------------------
|[43CBAD5C] + 0x7B64|Name of Armor in 1st Slot|See Below
|[43CBAD5C] + 0x7B54|Slot 1 Equipped State    |See Below. 00010000 = Unequipped, 01010000 = Equipped

Subtract 0x220 from the previous slot's offset to get the offset for the next slot's pointer.
See the "Material Slots" Example below for more clarification.

## _[Material](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Items%20(Materials)) Slots_ (v1.2.0, USA)
Information about items within the slots of the "Material" section of Link's inventory.

| Pointer Notation|Address it points to        |          Notes
|-----------------|----------------------------|------------------------
|[43CBAD5C] + 0x10|Quantity of item in 1st Slot|See Below
|[43CBAD5C] + 0x24|Name of item in 1st Slot    |See Below

Subtract 0x220 from the previous slot's offset to get the offset for the next slot's pointer. 

**Example, finding the pointers for the 2nd slot:**

Quantity: 0x10 - 0x220 = -0x210. The pointer would be [43CBAD5C] - 0x210.

Name: 0x24 - 0x220 = -0x1FC. The pointer would be [43CBAD5C] - 0x1FC.

**Example 2, finding the pointers for the 3rd slot:**

Quantity: -0x220 - 0x220 = -0x430. The pointer would be [43CBAD5C] - 0x430. And so on.

Name: -0x1FC - 0x220 = -0x41C. The pointer would be [43CBAD5C] - 0x41C. And so on.

## _[Food](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Food%20Items) Slots_ (v1.2.0, USA)
Information about food items within the slots of the "Food" section of Link's inventory.

| Pointer Notation   |Address it points to        |          Notes
|--------------------|----------------------------|------------------------
|[43CBAD5C] - 0x1609C|Name of food in 1st Slot    |Offset= -0x1609C, See Below

Subtract 0x220 from the previous slot's offset to get the offset for the next slot's pointer.
See the "Material Slots" Example above for more clarification.

## _[Key Item](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Key%20Items) Slots_ (v1.2.0, USA)
Information about key items within the slots of the "Key Items" section of Link's inventory.

| Pointer Notation   |Address it points to        |          Notes
|--------------------|----------------------------|------------------------
|[43CBAD5C] - 0x18B1C|Name of Key Item in 1st Slot|Offset= -0x18B1C, See Below

Subtract 0x220 from the previous slot's offset to get the offset for the next slot's pointer.
See the "Material Slots" Example above for more clarification.

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
