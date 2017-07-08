# Address notes for Breath of the Wild
#### This file contains information about certain Addresses and what they do.

## _Runes_ (v1.2.0, USA)
|Address |  What the value is  |   Notes
|--------|---------------------|----------
|401343E4|Amiibo availability  |00000000 = No amiibo used today

## _Link's data_ (v1.2.0, USA)
|Address |  What the value is     |   Notes
|--------|------------------------|----------
|439D8738|Link's Gravity          |3F800000 = 1x Gravity (Normal)
|439D8724|Link's Speed            |3F800000 = 1x Speed (Normal)
|424527A4|Current Stamina         |Float value
|43A77EA8|Link's Stealth          |00000000 = Completely silent

## _Link's data_ (v1.3.0, USA)
|Address |  What the value is     |   Notes
|--------|------------------------|----------
|4228B0CC|Current Stamina         |Float value

## _Weather & Skybox_ (v1.2.0, USA)
|Address |    What the value is    |   Notes
|--------|-------------------------|----------
|407CE158|Lightning strike Interval|Normal delay is about 00000080
|3FF8E72B|If Blood moon is tonight |00000000 = False, 00000001 = True
|407CDDA8|Clouds                   |00000000 = Off, 3F800000 = On
|407CDE1C|Current Weather          |None

## _Savegame data_ (v1.2.0, USA)
|Address |  What the value is     |   Notes
|--------|------------------------|----------
|40123BA4|Current Rupees          |Rupee number is in decimal
|401242E4|Current Mon             |Mon number is in decimal
|424527A0|Overall Heart Containers|Float value, **4** = 1 conatiner, **120** = 30 containers
|424527A8|Overall Stamina         |Float value, regular max stamina value is 3000
|401244E4|Weapon Inventory Slots  |Slot number is in Decimal
|4012A404|Bow Inventory Slots     |Slot number is in Decimal
|4012A424|Shield Inventory Slots  |Slot number is in Decimal

## _Savegame data_ (v1.3.0, USA)
|Address |  What the value is     |   Notes
|--------|------------------------|----------
|4228B0C8|Overall Heart Containers|Float value, **4** = 1 conatiner, **120** = 30 containers
|4228B0D0|Overall Stamina         |Float value, regular max stamina value is 3000

## _Visual Effects_ (v1.3.0, USA)
|Address |  What the value is    |   Notes
|--------|-----------------------|------------
|405FC458|Red-ness of the game   |Float Value
|405FC45C|Green-ness of the game |Float Value
|405FC460|Blue-ness of the game  |Float Value
|405FC458|Red Haze value         |Float Value
|405FC45C|Green Haze value       |Float Value
|405FC460|Blue Haze value        |Float Value
|405FC474|Sky brightness         |Float Value
|405FC494|Brightness of the sun  |Float Value
|405FC4D4|Fog amount?            |Float Value
|406458D4|Glow amount/brightness?|Float Value
|40645898|General brightness?    |Float Value
|40645078|Red-ness of the Sky    |Float Value
|4064507C|Green-ness of the Sky  |Float Value
|40645080|Blue-ness of the Sky   |Float Value
|40645094|Sky brightness 2       |Float Value

## _Visual Effects_ (v1.1.1, USA)
|Address |  What the value is            |   Notes
|--------|-------------------------------|------------
|407F5988|Red-ness of the game           |Float Value
|407F598C|Green-ness of the game         |Float Value
|407F5990|Blue-ness of the game          |Float Value
|407F59A4|Red Haze-ish value             |Float Value
|407F59A8|Green Haze value               |Float Value
|407F59AC|Blue Haze value                |Float Value
|407C1AC8|Red air thing?                 |Float Value
|407C1728|Green fog                      |Float Value
|407C179C|Red fog                        |Float Value
|407C1818|Blue fog                       |Float Value
|407C090C|All colours Glow Radius        |Float Value
|407C0908|Blue Glow Radius               |Float Value
|407C0904|Green Glow Radius              |Float Value
|407C0900|Red Glow Radius                |Float Value
|407C0970|All Glow Brightness            |Float Value
|407C0968|Green Glow Brightness          |Float Value
|407C096C|Blue Glow Brightness           |Float Value
|407C0964|Red Glow Brightness            |Float Value
|407F61C4|Overall In game Brightness     |Float Value
|408D4008|Icons stretch amount upright   |Float Value
|408D4014|Icons stretch amount down-left |Float Value
|408D4018|Icons stretch amount down-right|Float Value
|408D401C|Icon Skew?                     |Float Value
|407B5C70|The suns distance away from you|Float Value
