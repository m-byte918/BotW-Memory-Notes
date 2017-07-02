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
