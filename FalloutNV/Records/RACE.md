---
layout: falloutnvrec
title: fopdoc
---
RACE
====

Race

## Format

Count | Subrecord | Name | Type | Info
------|-------|------|------|-----
+ | EDID | Editor ID | cstring |
 | FULL | Name | cstring |
+ | DESC | Description | cstring |
-* | [XNAM](Subrecords/XNAM (FACT, RACE).md) | Relation | struct |
+ | DATA | | struct |
 | ONAM | Older | formid | FormID of a [RACE](RACE.md) record.
 | YNAM | Younger | formid | FormID of a [RACE](RACE.md) record.
+ | NAM2 | Unkonwin Marker | null |
+ | VTCK | Voices | struct |
+ | DNAM | Default Hair Styles | struct |
+ | CNAM | Default Hair Colors | struct |
+ | PNAM | FaceGen - Main Clamp | float32 |
+ | UNAM | FaceGen - Face Clamp | float32 |
+ | ATTR | Unknown | ?? |
+ | NAM0 | Head Data Marker | null |
+ | MNAM | Male Head Data Marker | null |
+* | | Male Head Part | collection | See below for details.
+ | FNAM | Female Head Data Marker | null |
+* | | Female Head Part | collection | See below for details.
+ | NAM1 | Body Data Marker | null |
+ | MNAM | Male Body Data Marker | null |
+* | | Male Body Part | collection | See below for details.
+ | FNAM | Female Body Data Marker | null |
+* | | Female Body Part | collection | See below for details.
+ | HNAM | Hairs | formid[] | Array of [HAIR](HAIR.md) record FormIDs.
+ | ENAM | Eyes | formid[] | Array of [EYES](EYES.md) record FormIDs.
+ | MNAM | Male FaceGen Data Marker | null |
+ | FGGS | Male FaceGen Geometry-Symmetric | uint8[] |
+ | FGGA | Male FaceGen Geometry-Asymmetric | uint8[] |
+ | FGTS | Male FaceGen Texture-Symmetric | uint8[] |
+ | SNAM | ?? | ?? |
+ | FNAM | Female FaceGen Data Marker | null |
+ | FGGS | Female FaceGen Geometry-Symmetric | uint8[] |
+ | FGGA | Female FaceGen Geometry-Asymmetric | uint8[] |
+ | FGTS | Female FaceGen Texture-Symmetric | uint8[] |
+ | SNAM | ?? | ?? |


### DATA

Name | Type | Info
-----|------|-----
Skill Boost 1 | struct |
Skill Boost 2 | struct |
Skill Boost 3 | struct |
Skill Boost 4 | struct |
Skill Boost 5 | struct |
Skill Boost 6 | struct |
Skill Boost 7 | struct |
Unused | byte[2] |
Male Height | float32 |
Female Height | float32 |
Male Weight | float32 |
Female Weight | float32 |
Flags | uint32 | See below for values.


#### Skill Boost

Name | Type | Info
-----|------|-----
[Skill](Values/Actor Values.md) | int8 |
Boost | int8 |

#### Flag Values

Value | Meaning
------|--------
0x00000001 | Playable
0x00000002 | ??
0x00000004 | Child

### VTCK

Name | Type | Info
-----|------|-----
Male Voice | formid | FormID of a [VTYP](VTYP.md) record.
Female Voice | formid | FormID of a [VTYP](VTYP.md) record.

### DNAM

Name | Type | Info
-----|------|-----
Male Default Hair Style | formid | FormID of a [HAIR](HAIR.md) record, or null.
Female Default Hair Style | formid | FormID of a [HAIR](HAIR.md) record, or null.

### CNAM

Name | Type | Info
-----|------|-----
Male Default Hair Color | uint8 | Enum - see below for values.
Female Default Hair Color | uint8 | Enum - see below for values.

#### Default Hair Color Values

Value | Meaning
------|--------
0 | Bleached
1 | Brown
2 | Chocolate
3 | Platinum
4 | Cornsilk
5 | Suede
6 | Pecan
7 | Auburn
8 | Ginger
9 | Honey
10 | Gold
11 | Rosewood
12 | Black
13 | Chestnut
14 | Steel
15 | Champagne

### Male Head Part / Female Head Part

Count | Subrecord | Name | Type | Info
------|-------|------|------|-----
 | INDX | Index | uint32 | See below for values.
+ | | [Model Data](Subrecords/Model.md) | collection |
 | ICON | Large icon filename | cstring |
 | MICO | Small icon filename | cstring |

#### Head Part Index Values

Value | Meaning
------|--------
0 | Head
1 | Ears
2 | Mouth
3 | Teeth Lower
4 | Teeth Upper
5 | Tongue
6 | Left Eye
7 | Right Eye

### Male Body Part / Female Body Part

Count | Subrecord | Name | Type | Info
------|-------|------|------|-----
 | INDX | Index | uint32 | See below for values.
 | ICON | Large icon filename | cstring |
 | MICO | Small icon filename | cstring |
+ | | [Model Data](Subrecords/Model.md) | collection |

#### Body Part Index Values

Value | Meaning
------|--------
0 | Upper Body
1 | Left Hand
2 | Right Hand
3 | Upper Body Texture
