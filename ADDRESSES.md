# Address notes for Breath of the Wild
#### This file contains information about certain Addresses and what they do.

## _Runes_ (v1.2.0, USA)
|Address |  What the value is  |   Notes
|--------|---------------------|----------
|43856C88|Crosshair Target's ID|00000000 = No object within crosshairs
|43856B50|Crosshair Coordinates|0, Z, X, Y. Applies to Stasis, Magnesis, and Camera
|43856CC8|Stasis State         |01000000 = On, 00000100 = Frozen, 01000100 = On+Frozen
|43856CD0|Stasis Cooldown Timer|None
|43856B3C|Magnesis State       |00000000 = Not Scanning, 01000000 = Scanning
|43F1EBF0|Cryonis State        |00000000 = Not Scanning, 01000000 = Scanning
|43859B24|# of Cryonis Blocks  |Increments by 00000001 per block
|43859BC8|Cryonis Cooldown Time|None 
|43856C44|Remote Bomb+ Cooldown|Square bomb only
|43856C5C|Remote Bomb+ Cooldown|Circular bomb only

## _Link's data_ (v1.2.0, USA)
|Address |  What the value is     |   Notes
|--------|------------------------|----------
|439D8738|Link's Gravity          |3F800000 = 1x Gravity (Normal)
|439D8724|Link's Speed            |3F800000 = 1x Speed (Normal)
|40123BA4|Current Rupees          |Rupee number is in decimal
|424527A0|Overall Heart Containers|Float value, **4** = 1 conatiner, **120** = 30 containers
|424527A4|Current Stamina         |Float value
|424527A8|Overall Stamina         |Float value

## _Weather & Skybox_ (v1.2.0, USA)
|Address |    What the value is    |   Notes
|--------|-------------------------|----------
|407CE158|Lightning strike Interval|Normal delay is about 00000080
|3FF8E72B|If Blood moon is tonight |00000000 = False, 00000001 = True
|407CDDA8|Clouds                   |00000000 = Off, 3F800000 = On
|407CDE1C|Current Weather          |None
