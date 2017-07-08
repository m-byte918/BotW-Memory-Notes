# Pointer notes for Breath of the Wild

#### This file contains information about certain Pointers and where they lead to.

## _Runes_ (All Versions, USA)
|  Pointer Notation             | Address it points to|          Notes
|-------------------------------|---------------------|----------------------
|[[0x101C1D40] + 0x2564] + 0x2FC|Crosshair Target's ID|00000000 = No object within crosshairs
|[[0x101C1D40] + 0x2564] + 0x1C4|Crosshair Coordinates|Order: 0, Y, Z, X. Applies to Stasis, Magnesis, and Camera (Float values)
|[[0x101C1D40] + 0x2564] + 0x33C|Stasis State         |01000000 = On, 00000100 = Frozen, 01000100 = On+Frozen
|[[0x101C1D40] + 0x2564] + 0x35C|Stored Stasis ID     |Stores object's Stasis ID for tangibility restoration
|[[0x101C1D40] + 0x2564] + 0x340|Stasis Cooldown Timer|Float value
|[[0x101C1D40] + 0x2564] + 0x344|Stasis Time Limit    |Float value
|[[0x101C1D40] + 0x2564] + 0x1B0|Magnesis State       |00000000 = Not Scanning, 01000000 = Scanning
|[[0x101C1D40] + 0x2564] + 0x1B4|Magnesis Target ID   |ID is unique for every object
|[[0x101C1D40] + 0x2564] + 0x857F30|Magnesis Availability|3F800000 = Can activate, 00000000 = Cannot activate
|[[0x101C1D40] + 0x2564] + 0x707234|Cryonis State     |00000000 = Not Scanning, 01000000 = Scanning
|[[0x101C1D40] + 0x2564] + 0x3558|# of Cryonis Blocks |Increments by 00000001 per block
|[[0x101C1D40] + 0x2564] + 0x35FC|Cryonis Cooldown Time|Float value
|[[0x101C1D40] + 0x2564] + 0x2D0|Remote Bomb+ Cooldown|Square bomb only
|[[0x101C1D40] + 0x2564] + 0x2B8|Remote Bomb+ Cooldown|Circular bomb only
|[[[[0x101C1D40] + 0x2540] + 0xFFFFF3FC] + 0xFFFFFF30] + 0x10884|Last Amiibo Use Date|Decimal value

## _Object Structure_ (All Versions, USA)
All of these stem from crosshair ID pointer (see above), which is what you are pointing at with the stasis or magnesis rune. 
Pointers will only "point" to the correct address/value if you have the rune's crosshairs on a valid object. Otherwise
it will point to a value that is "invalid"

Object structure also includes structure for enemies.

|  Pointer Notation                       | Address it points to|          Notes
|-----------------------------------------|---------------------|-------------------------
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x0  |Start of object's data|Object's name is in UTF8
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x50 |Stasis ID            |ID stored when stasis'd, FFFFFFFF = no object stasis'd
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x274|Object's size X,Y,Z. |Only applies to objects with health?
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x204|Spoofed X coordinate |None
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x214|Spoofed Y coordinate |None
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x224|Spoofed Z coordinate |None
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x848|Awareness of Link    |Applies to enemies only, FFFFFFFF = Doesn't see Link
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x71C|If Object is a weapon|FFFFFFFF = Not a weapon
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x72C|If Object is a shield|FFFFFFFF = Not a shield
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x364|IsStasis'd           |*104X = True, 100X = False
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x48F|IsStasis'd x2        |*7814 = Being Targeted, 780C = Frozen, 781C = Being Targeted + Frozen, 7804 = Free
|[[[0x101C1D40] + 0x2564] + 0x2FC] + 0x540|Object Health        |Number of HP is in Decimal

_*_ X's are bits that may vary depending on the object.

## _Link's data_ (v1.2.0, USA)
| Pointer Notation   |Address it points to|          Notes
|--------------------|--------------------|------------------------
|[0x439D89A4] + 0x140|Link's Coordinates  |Relative to map. Order: YZX
|[0x43AD1E30] + 0x770|Link's Damage       |3F800000 = Normal Damage

## _Link's data_ (All Versions, USA)
| Pointer Notation            |Address it points to|          Notes
|-----------------------------|--------------------|------------------------
|[[0x1001FC20] + 0x8D30] + 0x388|Link's Health       |Number of HP is in Decimal

## _Gear_ (All Versions, USA)
**Drop your weapon then pick it back up after editing bonuses or it might softlock your game.
Will not work on every weapon since not all weapons allow bonuses.**

|                 Pointer Notation               |   Address it points to    |          Notes
|------------------------------------------------|---------------------------|-------------------------
|[[[[0x101C1D40] + 0x2580] + 0xBDC] + 0x40] + 0x980|Equipped Bow Durability    |Durability Number is in Decimal
|[[[[0x101C1D40] + 0x2580] + 0xBDC] + 0x40] + 0x990|Equipped Bow Size          |Order: YZX, 3F800000 = Normal
|[[[[0x101C1D40] + 0x2580] + 0xBDC] + 0x40] + 0xAE0|Equipped Bow Bonus         |*800000XX = Bonus
|[[[[0x101C1D40] + 0x2580] + 0xBDC] + 0x40] + 0xAE4|Equipped Bow Bonus Value   |Value is in Decimal
|[[[[0x101C1D40] + 0x2580] + 0xB80] + 0x40] + 0x980|Equipped Shield Durability |Durability Number is in Decimal
|[[[[0x101C1D40] + 0x2580] + 0xB80] + 0x40] + 0x990|Equipped Shield Size       |Order: YZX, 3F800000 = Normal
|[[[[0x101C1D40] + 0x2580] + 0xB80] + 0x40] + 0xAE0|Equipped Shield Bonus      |*800000XX = Bonus
|[[[[0x101C1D40] + 0x2580] + 0xB80] + 0x40] + 0xAE4|Equipped Shield Bonus Value|Value is in Decimal
|[[[[0x101C1D40] + 0x2580] + 0xB24] + 0x40] + 0x980|Equipped Weapon Durability |Durability Number is in Decimal
|[[[[0x101C1D40] + 0x2580] + 0xB24] + 0x40] + 0x990|Equipped Weapon Size       |Order: YZX, 3F800000 = Normal
|[[[[0x101C1D40] + 0x2580] + 0xB24] + 0x40] + 0xAE0|Equipped Weapon Bonus      |*800000XX = Bonus
|[[[[0x101C1D40] + 0x2580] + 0xB24] + 0x40] + 0xAE4|Equipped Weapon Bonus Value|Value is in Decimal

*XX = Bonus value. See [here](https://github.com/Megabyte918/BotW-Cheat-Codes/blob/master/All%20Versions/Equipped%20Gear%20Bonus%20Modifier) for more information on bonus values.

## _[Weapon](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/1%20Handed%20Weapons) Slots_ (v1.3.0, USA)
Information about weapons within the slots of the "Weapons" section of Link's inventory.

| Pointer Notation            |Address it points to      |          Notes
|-----------------------------|--------------------------|------------------------
|[[0x1093E4C8] + 0x2CC] + 0x24|Name of Weapon in 1st Slot|See Below
|[[0x1093E4C8] + 0x2CC] + 0x14|Slot 1 Equipped State     |See Below. 00010000 = Unequipped, 01010000 = Equipped

Subtract 0x220 from the previous slot's last offset to get the offset for the next slot's pointer.
See the "Material Slots" Example below for more clarification.

## _[Bow & Arrow](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Bows%20%26%20Arrows) Slots_ (v1.3.0, USA)
Information about bows & arrows within the slots of the "Bows & Arrows" section of Link's inventory.

| Pointer Notation              |Address it points to       |          Notes
|-------------------------------|---------------------------|------------------------
|[[0x1093E4C8] + 0x2CC] - 0x2A5C|Name of Bow in 1st Slot    |See Below
|[[0x1093E4C8] + 0x2CC] - 0x2A6C|Slot 1 Bow Equipped State  |See Below. 00010000 = Unequipped, 01010000 = Equipped
|[[0x1093E4C8] + 0x2CC] - 0x41BC|Name of Arrow in 1st Slot  |See Below
|[[0x1093E4C8] + 0x2CC] - 0x41CC|Slot 1 Arrow Equipped State|See Below. 00010000 = Unequipped, 01010000 = Equipped

Add 0x220 to the previous slot's last offset to get the offset for the next slot's pointer.
See the "Material Slots" Example below for more clarification.

## _[Shield](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Shields) Slots_ (v1.3.0, USA)
Information about shields within the slots of the "Shields" section of Link's inventory.

| Pointer Notation              |Address it points to      |          Notes
|-------------------------------|--------------------------|------------------------
|[[0x1093E4C8] + 0x2CC] - 0x5B3C|Name of Sheild in 1st Slot|See Below
|[[0x1093E4C8] + 0x2CC] - 0x5B4C|Slot 1 Equipped State     |See Below. 00010000 = Unequipped, 01010000 = Equipped

Add 0x220 to the previous slot's last offset to get the offset for the next slot's pointer.
See the "Material Slots" Example below for more clarification.

## _[Armor](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Armor) Slots_ (v1.3.0, USA)
Information about armor within the slots of the "Armor" section of Link's inventory.

| Pointer Notation              |Address it points to     |          Notes
|-------------------------------|-------------------------|------------------------
|[[0x1093E4C8] + 0x2CC] - 0x67FC|Name of Armor in 1st Slot|See Below
|[[0x1093E4C8] + 0x2CC] - 0x6A1C|Slot 1 Equipped State    |See Below. 00010000 = Unequipped, 01010000 = Equipped

Add 0x220 to the previous slot's last offset to get the offset for the next slot's pointer.
See the "Material Slots" Example below for more clarification.

## _[Material](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Items%20(Materials)) Slots_ (v1.3.0, USA)
Information about items within the slots of the "Material" section of Link's inventory.

| Pointer Notation              |Address it points to        |          Notes
|-------------------------------|----------------------------|------------------------
|[[0x1093E4C8] + 0x2CC] - 0xE350|Quantity of item in 1st Slot|See Below, Decimal value
|[[0x1093E4C8] + 0x2CC] - 0xE33C|Name of item in 1st Slot    |See Below

Add 0x220 to the previous slot's last offset to get the offset for the next slot's pointer. 

**Example, finding the pointers for the 2nd slot:**

Quantity: 0xE350 + 0x220 = 0xE570. The pointer would be [[0x1093E4C8] + 0x2CC] - 0xE570.

Name: 0xE33C + 0x220 = 0xE55C. The pointer would be [[0x1093E4C8] + 0x2CC] - 0xE55C.

**Example 2, finding the pointers for the 3rd slot:**

Quantity: 0xE570 + 0x220 = 0xE790. The pointer would be [[0x1093E4C8] + 0x2CC] - 0xE790. And so on.

Name: 0xE55C + 0x220 = 0xE77C. The pointer would be [[0x1093E4C8] + 0x2CC] - 0xE77C. And so on.

## _[Food](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Food%20Items) Slots_ (v1.3.0, USA)
Information about food items within the slots of the "Food" section of Link's inventory.

| Pointer Notation               |Address it points to        |          Notes
|--------------------------------|----------------------------|------------------------
|[[0x1093E4C8] + 0x2CC] - 0x241DC|Name of food in 1st Slot    |See Below

Add 0x220 to the previous slot's last offset to get the offset for the next slot's pointer.
See the "Material Slots" Example above for more clarification.

## _[Key Item](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Key%20Items) Slots_ (v1.3.0, USA)
Information about key items within the slots of the "Key Items" section of Link's inventory.

| Pointer Notation               |Address it points to        |          Notes
|--------------------------------|----------------------------|------------------------
|[[0x1093E4C8] + 0x2CC] - 0x24C7C|Name of Key Item in 1st Slot|See Below

Add 0x220 to the previous slot's last offset to get the offset for the next slot's pointer.
See the "Material Slots" Example above for more clarification.

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
|[43CBAD5C] - 0x1609C|Name of food in 1st Slot    |See Below

Add 0x220 to the previous slot's offset to get the offset for the next slot's pointer.
See the "Material Slots" Example above for more clarification.

## _[Key Item](https://github.com/Megabyte918/BotW-Memory-Notes/blob/master/OBJECTS/Key%20Items) Slots_ (v1.2.0, USA)
Information about key items within the slots of the "Key Items" section of Link's inventory.

| Pointer Notation   |Address it points to        |          Notes
|--------------------|----------------------------|------------------------
|[43CBAD5C] - 0x18B1C|Name of Key Item in 1st Slot|See Below

Add 0x220 to the previous slot's offset to get the offset for the next slot's pointer.
See the "Material Slots" Example above for more clarification.

## _Timers_ (v1.2.0, USA)
| Pointer Notation   |Address it points to     |          Notes
|--------------------|-------------------------|------------------------
|[0x43AD2220] + 0x488|Master Sword Charge Timer|40200000 = Power Restored
|[0x43AD2220] + 0x470|Urbosa's Fury Timer      |Float value
|[0x43AD2220] + 0x458|Revali's Gale Timer      |Float value
|[0x43AD2220] + 0x464|Daruk's Protection Timer |Float value
|[0x43AD2220] + 0x47C|Mipha's Grace Timer      |Float value

## _Miscellaneous_ (v1.2.0, USA)
| Pointer Notation                   |Address it points to      |          Notes
|------------------------------------|--------------------------|------------------------
|[0x42452678] + 0x2B64               |Master Sword Glow         |00000000 = Not glowing, 00000001 = Glowing
|[0x10903D74] + 0x50                 |Wolf Link's Health        |Number of HP is in Decimal
|[[0x3FAB6B1C] + 0xFFFFCA38] + 0x2DD8|Amount of horse whips     |Value decrements by 00010000 per whip
|[0x407C3D2C] + 0x2E0                |Lightning Strike Coords   |General location, not exact
|[0x43AD1E30] - 0x10                 |Max Health                |Number of HP is in Decimal

## _Miscellaneous_ (All Versions, USA)
| Pointer Notation                                         |Address it points to                    |          Notes
|----------------------------------------------------------|----------------------------------------|------------------------
|[[[[[0x101C1D40] + 0x2580] + 0xB24] + 0x40] + 0x970] + 0xC|Equipped Elemental Weapon Charge        |Float value
|[[[[[0x101C1D40] + 0x2580] + 0xB24] + 0x40] + 0x970] + 0xC|Equipped Elemental Weapon Recharge Timer|Float value
