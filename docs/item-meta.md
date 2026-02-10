# Item Meta

Some of our plugins require manual adding item stacks with certain meta data. This tutorial will help you add the
desired meta to items.

Useful links:

* [Materials list](materials)
* [Enchantments list](enchantments)
* [Item flags list](item-flags)
* [Firework effects list](firework-effects)
* [Leather dye colors list](leather-dye-colors)
* [Potion types list (1.9+ only)](potion-types)
* [Potion Calculator by Graham Edgecombe (1.7-1.8 only)](https://minecraft-ids.grahamedgecombe.com/potion-calculator)
* [Goat horns list](music-instruments)
* [Armor Trim Materials and Patterns list](armor-trims)

## Basic meta

The most important and the only required part is the material name. It has to be a valid material name or numeric
ID. [Full list of materials](materials)

```yaml
item:
  material: BREAD
```

Now you can add the amount of the item.

```yaml
  amount: 32
```

You can also add the damage value. Damage value is the part after the colon in data values, for instance 35:1 is Orange
Wool where 1 is the damage value. It can be used to define more specific type of item (wood type, wool color, potion
type etc).

```yaml
  damage: 0
```

Result:

```yaml
item:
  material: BREAD
  amount: 32
  damage: 0
```

## Name & lore

Sometimes when you want to customize an item, you may want to change name and lore of the item. Both names and lores
support color codes.

You can change the name by simply adding name to the item section:

```yaml
  name: "&aPowerful Blade"
```

It's easy to edit the lore too, each line of lore has to be a new line in the config starting with the hyphen.

```yaml
  lore:
    - "&31st line"
    - "&22nd line"
```

Result:

```yaml
item:
  material: DIAMOND_SWORD
  amount: 1
  damage: 0
  name: "&aPowerful Blade"
  lore:
    - "&31st line"
    - "&22nd line"
```

## Item flags

You can set item flags on items. Each flag needs to be put in separate line. [Full list of item flags](item-flags)

Example of item with hidden attributes:

```yaml
item:
  material: DIAMOND_SWORD
  amount: 1
  damage: 0
  name: "&aPowerful Blade"
  lore:
    - "&31st line"
    - "&22nd line"
  flags:
    - HIDE_ATTRIBUTES
```

## Unbreakable items

You can add the "Unbreakable" tag to an item. If can be combined with `HIDE_ATTRIBUTES` item flag described above to
make the item glow.

Example of a pickaxe with "Unbreakable" tag:

```yaml
item:
  material: DIAMOND_PICKAXE
  amount: 1
  unbreakable: true
```

## Enchantments

You can also add enchantments to items. Each enchantment has to be put in separate line in format NAME:
LEVEL. [Full list of enchantments](enchantments)

For example, let's add Sharpness IV and Looting I to the sword from the previous example:

```yaml
  enchantments:
    - SHARPNESS:4
    - LOOTING:1
```

Result:

```yaml
item:
  material: DIAMOND_SWORD
  amount: 1
  damage: 0
  name: "&aPowerful Blade"
  lore:
    - "&31st line"
    - "&22nd line"
  enchantments:
    - SHARPNESS:4
    - LOOTING:1
```

## Glow

You can add glow effect to any item using the `glow` option.

Example:

```yaml
item:
  material: STONE
  quantity: 64
  glow: true
```

## Tipped Arrows

You can add potion effects to tipped arrows same way as to potions (explained below in the potions section).

Example:

```yaml
item:
  material: TIPPED_ARROW
  quantity: 16
  potion:
    type: SPEED
```

## Potions

### 1.7-1.8

Adding potions is a bit different than in other plugins. You don't have to specify all parameters like type, effect and
tier, you need only the damage value.

It's recommended to use
the [Potion Calculator by Graham Edgecombe](https://minecraft-ids.grahamedgecombe.com/potion-calculator). All you have
to do is select desired parameters and write down the metadata value. Then you have to create a new item with material
POTION and damage value same as the metadata value. Damage value of Splash Potion of Regeneration II is 16417, so that's
what we will put in the damage value.

Example:

```yaml
item:
  material: POTION
  amount: 1
  damage: 16417
```

### 1.9-1.20.1

Since 1.9 damage values don't work any more. You have to set the potion parameters using particular settings.

First off, you have to choose the type of the potion by using appropriate material, POTION, LINGERING_POTION or
SPLASH_POTION. Then you can adjust the potion parameters using following settings (only type is required).

[List of all 1.9+ potion types](potion-types)

Example:

```yaml
item:
  material: SPLASH_POTION
  quantity: 16
  potion:
    type: SPEED
    level: 1
    extended: true
    color: BLUE
```

### 1.20.2+

In 1.20.2 there were separate potion types introduced in place of extended and level fields.

Example:

```yaml
item:
  material: POTION
  quantity: 1
  potion:
    type: STRONG_STRENGTH
```

## Spawn Eggs

### 1.7-1.8

In 1.7-1.8 setting spawn egg type as simple as setting a correct damage value (eg. 50 is Creeper, 51 is Skeleton etc).

Example:

```yaml
item:
  material: MONSTER_EGG
  quantity: 1
  damage: 1
```

### 1.9-1.12

Since 1.9 damage values don't work any more. You have to set the mob name using a separate parameter.

**"mob" has to be a valid entity name.** [List of all entity types](entity-types)

<p class="warn"><b>Note:</b>  Entity type names changed in 1.11!</p>

You can also set more specific type using the "mobType" setting (eg. to set
the [horse type](http://minecraft.gamepedia.com/Horse#Data_values)).

Example (Creeper Spawn Egg):

```yaml
item:
  material: MONSTER_EGG
  quantity: 1
  mob: Creeper
```

Example (Zombie Horse Spawn Egg):

```yaml
item:
  material: MONSTER_EGG
  quantity: 1
  mob: EntityHorse
  mobType: 4
```

### 1.13+

Since 1.13, there were created separate material names for each spawn egg what made creating them much more simple. You
need only the material name which can be found [here](item-ids#mob-spawning-eggs).

Example (Creeper Spawn Egg):

```yaml
item:
  material: CREEPER_SPAWN_EGG
  quantity: 1
```

## Player heads

### 1.7-1.12

To add a player head you have to use the SKULL_ITEM material, set the damage value to 3 and set the skull owner.

Example:

```yaml
item:
  material: SKULL_ITEM
  quantity: 1
  damage: 3
  skullOwner: jeb_
```

### 1.13+

To add a player head you have to use the new PLAYER_HEAD material and set the skull owner.

Example:

```yaml
item:
  material: PLAYER_HEAD
  quantity: 1
  skullOwner: jeb_
```

## Base64 heads
You can find Base64 heads on [Minecraft-Heads](https://minecraft-heads.com/). <br>
Simply find a head you like, and use the "value" property at the bottom of the head's page as the skin value in the item's config. 

### 1.7-1.12

To add a custom base64 head you need to use the SKULL_ITEM material as well. The base64 skin can be passed in a skin
entry.

Example:

```yaml
item:
  material: SKULL_ITEM
  quantity: 1
  damage: 3
  skin: eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvYjI4NDM1ZDc5MWEwMThmY2E3OTI2ODU0Zjc3ZWNkN2RmMmQxZGYwYjFjMWM3ZjlhNjM4YjhhOTMxZGI5NWEifX19
```

### 1.13+

To add a custom base64 head you need to use the PLAYER_HEAD material as well. The base64 skin can be passed in a skin
entry.

Example:

```yaml
item:
  material: PLAYER_HEAD
  quantity: 1
  skin: eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvYjI4NDM1ZDc5MWEwMThmY2E3OTI2ODU0Zjc3ZWNkN2RmMmQxZGYwYjFjMWM3ZjlhNjM4YjhhOTMxZGI5NWEifX19
```

## Custom item models

**Note: This only works on Spigot versions 1.14 or newer when the custom model support was added.**

To set custom item model number you need to use the "model" entry.

Example:

```yaml
item:
  material: LEATHER_HELMET
  quantity: 1
  model: 123
```

## Banners

You can change the banner's color by setting the color name and add as many patterns as you wish.

[Pattern types list](pattern-types)

[Colors list](dye-colors)

### 1.7 - 1.12

Example:

```yaml
item:
  material: BANNER
  quantity: 1
  color: BLACK
  patterns:
    1:
      type: STRIPE_BOTTOM
      color: WHITE
    2:
      type: STRIPE_MIDDLE
      color: WHITE
    3:
      type: STRIPE_TOP
      color: WHITE
```

### 1.13+

Since 1.13 you need to use specific [material name](materials) containing the color, without specifying it explicitly.

Example:

```yaml
item:
  material: BLACK_BANNER
  quantity: 1
  patterns:
    1:
      type: STRIPE_BOTTOM
      color: WHITE
    2:
      type: STRIPE_MIDDLE
      color: WHITE
    3:
      type: STRIPE_TOP
      color: WHITE
```

## Shields

[Pattern types list](pattern-types)

[Colors list](dye-colors)

Example:

```yaml
item:
  material: SHIELD
  quantity: 1
  color: ORANGE
  patterns:
    1:
      type: STRIPE_BOTTOM
      color: WHITE
    2:
      type: STRIPE_TOP
      color: WHITE
```

## NBT tags

<p class="error"><b>WARNING:</b> If you're using ShopGUI+, we recommend using our <a href="#/shopgui/shops-items-setup?id=custom-items">Item Providers</a> where possible instead. Please reach out to our Discord support if you need any help whatsoever with NBT: <a href="https://discord.brcdev.net/">https://discord.brcdev.net/</a></p>

<p class="warn"><b>Note:</b> The <i>compareMeta</i> option must be enabled for an item to use the NBT option!</p>

Adding NBT tags to items is as simple as adding `nbt` section and tags inside.

Each tag (except `ARRAY`s and `COMPOUND` types) must contain `type`, `key` and `value`. Array tags require `type`, `key` and `values`. Compound tags require `type`, `key` and `children` instead. Compounds can be nested
recursively.

Since 1.13, you can easily view item NBT data by holding the item ingame and running `/data get entity <player> SelectedItem`.

More info on the NBT format itself can be found [here](https://minecraft.gamepedia.com/NBT_format).

### NBT tag types

* BYTE
* SHORT
* INT
* LONG
* FLOAT
* DOUBLE
* STRING
* BYTE_ARRAY
* COMPOUND_ARRAY (LIST of COMPOUNDs)
* DOUBLE_ARRAY (LIST of DOUBLEs)
* FLOAT_ARRAY (LIST of FLOATs)
* INT_ARRAY
* LONG_ARRAY
* STRING_ARRAY (LIST of STRINGs)
* UUID_ARRAY (LIST of UUIDs)
* COMPOUND

### NBT tag Configuration

Below shows how each of the NBT tag types are configured and what their resultant NBT looks like:

#### Byte
Byte is a boolean with two possible values, 1 or 0, and the following YAML produces: `{ BYTE_EXAMPLE: 1b }`

```yaml
nbt:
  1:
    type: BYTE
    key: BYTE_EXAMPLE
    value: 1
```

#### Short
Short is a 16-bit signed integer ranging from -32,768 to 32,767 and the following YAML produces: `{ SHORT_EXAMPLE: 100s }`

```yaml
nbt:
  1:
    type: SHORT
    key: SHORT_EXAMPLE
    value: 100
```

#### Int
Int is a 32-bit signed integer ranging from -2,147,483,648 and 2,147,483,647 and the following YAML produces: `{ INT_EXAMPLE: 2026 }`

```yaml
nbt:
  1:
    type: INT
    key: INT_EXAMPLE
    value: 2026
```

#### Long
Long is a 64-bit signed integer ranging from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 and the following YAML produces: `{ LONG_EXAMPLE: 19072005L }`

```yaml
nbt:
  1:
    type: LONG
    key: LONG_EXAMPLE
    value: 19072005
```

#### Float
Float is a 32-bit single-precision floating-point number ranging from -3.4E+38 to +3.4E+38 and the following YAML produces: `{ FLOAT_EXAMPLE: 1430262000f }`

```yaml
nbt:
  1:
    type: FLOAT
    key: FLOAT_EXAMPLE
    value: 1430262000
```

#### Double
Double is a 64-bit double-precision floating-point number ranging from -1.7E+308 to +1.7E+308 and the following YAML produces: `{ DOUBLE_EXAMPLE: 6515.0d }`

```yaml
nbt:
  1:
    type: DOUBLE
    key: DOUBLE_EXAMPLE
    value: 6515.0
```

#### String
String is text and the following YAML produces: `{ STRING_EXAMPLE: "This is an example string" }`

```yaml
nbt:
  1:
    type: STRING
    key: STRING_EXAMPLE
    value: "This is an example string"
```

#### Byte Array
Byte Array is a list of Bytes and the following YAML produces: `{ BYTE_ARRAY_EXAMPLE: [B; 1B, 0B] }` 

```yaml
nbt:
  1:
    type: BYTE_ARRAY
    key: "BYTE_ARRAY_EXAMPLE"
    values:
      - 1
      - 0
```

#### Compound Array
Compound Array is a list of Compounds and the following YAML produces: `{ COMPOUND_ARRAY_EXAMPLE: [{ CHILD_STRING_EXAMPLE: "Compound inside Compound Array" }] }`

```yaml
nbt:
  1:
    type: COMPOUND_ARRAY
    key: COMPOUND_ARRAY_EXAMPLE
    children:
      1:
        type: COMPOUND
        key: ""
        children:
          1:
            type: STRING
            key: "CHILD_STRING_EXAMPLE"
            value: "Compound inside Compound Array"
```

#### Double Array (LIST of DOUBLEs)
Double Array is a list of Doubles and the following YAML produces: `{ DOUBLE_ARRAY_EXAMPLE: [1.0d, 2.0d] }`

```yaml
nbt:
  1:
    type: DOUBLE_ARRAY
    key: "DOUBLE_ARRAY_EXAMPLE"
    values:
      - 1.0
      - 2.0
```

#### Float Array (LIST of FLOATs)
Float Array is a list of Floats and the following YAML produces: `{ FLOAT_ARRAY_EXAMPLE: [1.0f, 2.0f] }`

```yaml
nbt:
  1:
    type: FLOAT_ARRAY
    key: "FLOAT_ARRAY_EXAMPLE"
    values:
      - 1.0
      - 2.0
```

#### Int Array
Int Array is a list of Ints and the following YAML produces: `{ INT_ARRAY_EXAMPLE: [I; 1, 2] }`

```yaml
nbt:
  1:
    type: INT_ARRAY
    key: "INT_ARRAY_EXAMPLE"
    values:
      - 1
      - 2
```

#### Long Array
Long Array is a list of Longs and the following YAML produces: `{ LONG_ARRAY_EXAMPLE: [1L, 2L] }`

```yaml
nbt:
  1:
    type: LONG_ARRAY
    key: "LONG_ARRAY_EXAMPLE"
    values:
      - 1
      - 2
```

#### String Array (LIST of STRINGs)
String Array is a list of Strings and the following YAML produces: `{ STRING_ARRAY_EXAMPLE: ["Text1", "Text2"] }`

```yaml
nbt:
  1:
    type: STRING_ARRAY
    key: "STRING_ARRAY_EXAMPLE"
    values:
      - "Text1"
      - "Text2"
```

#### UUID Array (LIST of UUIDs)
UUID Array is a list of UUIDs and the following YAML produces: `{ UUID_ARRAY_EXAMPLE: [[I; -129209735, 172901862, -2123148138, 422810289]] }`

```yaml
nbt:
  1:
    type: UUID_ARRAY
    key: "UUID_ARRAY_EXAMPLE"
    values:
      - "f84c6a79-0a4e-45e6-8173-5496193392b1"
```

#### Compound
Compound is a collection of NBT tags and the following YAML produces: `{ COMPOUND_EXAMPLE: { STRING_EXAMPLE: "String inside compound", CHILD_COMPOUND_EXAMPLE: { CHILD_BYTE_EXAMPLE: 1b } } }` 

```yaml
nbt:
  1:
    type: COMPOUND
    key: "COMPOUND_EXAMPLE"
    children:
      1:
        type: STRING
        key: "STRING_EXAMPLE"
        value: "String inside compound"
      2:
        type: COMPOUND
        key: "CHILD_COMPOUND_EXAMPLE"
        children:
          1:
            type: BYTE
            key: "CHILD_BYTE_EXAMPLE"
            value: 1
```

### Specific Examples

#### Ominious Banner

<!-- tabs:start -->

## ** 1.20.4 and below **
```yaml
item:
  material: WHITE_BANNER
  quantity: 1
  patterns:
    1:
      type: RHOMBUS_MIDDLE
      color: CYAN
    2:
      type: STRIPE_BOTTOM
      color: LIGHT_GRAY
    3:
      type: STRIPE_CENTER
      color: GRAY
    4:
      type: BORDER
      color: LIGHT_GRAY
    5:
      type: STRIPE_MIDDLE
      color: BLACK
    6:
      type: HALF_HORIZONTAL
      color: LIGHT_GRAY
    7:
      type: CIRCLE_MIDDLE
      color: LIGHT_GRAY
    8:
      type: BORDER
      color: BLACK
  nbt:
    0:
      type: INT
      key: "HideFlags"
      value: 32
    1:
      type: COMPOUND
      key: "display"
      children:
        1: 
          type: STRING
          key: "Name"
          value: '{"translate":"block.minecraft.ominous_banner","color":"gold"}'
```

## ** 1.20.5 - 1.21.1 **
```yaml
item:
  material: WHITE_BANNER
  quantity: 1
  patterns:
    1:
      type: RHOMBUS
      color: CYAN
    2:
      type: STRIPE_BOTTOM
      color: LIGHT_GRAY
    3:
      type: STRIPE_CENTER
      color: GRAY
    4:
      type: BORDER
      color: LIGHT_GRAY
    5:
      type: STRIPE_MIDDLE
      color: BLACK
    6:
      type: HALF_HORIZONTAL
      color: LIGHT_GRAY
    7:
      type: CIRCLE
      color: LIGHT_GRAY
    8:
      type: BORDER
      color: BLACK
  nbt:
    1:
      type: STRING
      key: "minecraft:item_name"
      value: '{"color":"gold","translate":"block.minecraft.ominous_banner"}'
    2:
      type: COMPOUND
      key: "minecraft:hide_additional_tooltip"
      children: {}
```

## ** 1.21.2 - 1.21.4 **
```yaml
item:
  material: WHITE_BANNER
  quantity: 1
  patterns:
    1:
      type: RHOMBUS
      color: CYAN
    2:
      type: STRIPE_BOTTOM
      color: LIGHT_GRAY
    3:
      type: STRIPE_CENTER
      color: GRAY
    4:
      type: BORDER
      color: LIGHT_GRAY
    5:
      type: STRIPE_MIDDLE
      color: BLACK
    6:
      type: HALF_HORIZONTAL
      color: LIGHT_GRAY
    7:
      type: CIRCLE
      color: LIGHT_GRAY
    8:
      type: BORDER
      color: BLACK
  nbt:
    1:
      type: STRING
      key: "minecraft:rarity"
      value: "uncommon"
    2:
      type: STRING
      key: "minecraft:item_name"
      value: '{"translate":"block.minecraft.ominous_banner"}'
    3:
      type: COMPOUND
      key: "minecraft:hide_additional_tooltip"
      children: {}
```

## ** 1.21.5+ **
```yaml
item:
  material: WHITE_BANNER
  quantity: 1
  patterns:
    1:
      type: RHOMBUS
      color: CYAN
    2:
      type: STRIPE_BOTTOM
      color: LIGHT_GRAY
    3:
      type: STRIPE_CENTER
      color: GRAY
    4:
      type: BORDER
      color: LIGHT_GRAY
    5:
      type: STRIPE_MIDDLE
      color: BLACK
    6:
      type: HALF_HORIZONTAL
      color: LIGHT_GRAY
    7:
      type: CIRCLE
      color: LIGHT_GRAY
    8:
      type: BORDER
      color: BLACK
  nbt:
    1:
      type: COMPOUND
      key: "minecraft:item_name"
      children:
        1:
          type: STRING
          key: "translate"
          value: "block.minecraft.ominous_banner"
    2:
      type: COMPOUND
      key: "minecraft:tooltip_display"
      children:
        1:
          type: STRING_ARRAY
          key: "hidden_components"
          values:
            - "minecraft:banner_patterns"
    3:
      type: STRING
      key: "minecraft:rarity"
      value: "uncommon"
```

<!-- tabs:end -->

#### Suspicious Stew
The following configuration was tested on 1.21.4:

```yaml
item:
  material: SUSPICIOUS_STEW
  quantity: 1
  nbt:
    1: 
      type: COMPOUND_ARRAY
      key: "minecraft:suspicious_stew_effects"
      values: 
        1: 
          type: COMPOUND
          key: ""
          children:
            1: 
              type: STRING
              key: "id"
              value: "minecraft:blindness"
            2:
              type: INT
              key: "duration"
              value: 220
```

#### Poke Balls (Pixelmon)
We don't officially support modded (Forge, Fabric, Arclight, Magma, etc) servers however here is an example of how Pokeballs are configured for 1.16.5.

Gold & Silver (GS) Ball:
```yaml
item:
  material: PIXELMON_POKE_BALL
  quantity: 1
  nbt:
    1:
      type: STRING
      key: "PokeBallID"
      value: "gs_ball"
```

## Leather armor color

To add a dyed leather armor you can define the color either as a [RGB color](leather-dye-colors) or one
of [Colors](colors).

Example (regular color):

```yaml
item:
  material: LEATHER_HELMET
  quantity: 1
  color: TEAL
```

Example (RGB color):

```yaml
item:
  material: LEATHER_HELMET
  quantity: 1
  color: 127,255,0
```

## Fireworks

To add a new firework you have to choose the FIREWORK material and define firework power and effects. You can set the
power by adding fireworkPower entry with number from 1 to 4 which will be the result power.

```yaml
item:
  material: FIREWORK
  amount: 32
  damage: 0
  fireworkPower: 4
```

Now you have to add effects. Here's the list of available effect types and colors:

Let's add two different effects, one burst type and second one star. You can add multiple colors (at least 1 required)
and fade colors (optional) to each of effects. [Full list of firework effects](firework-effects)

```yaml
item:
  material: FIREWORK
  amount: 32
  damage: 0
  fireworkPower: 4
  fireworkEffects:
    1:
      type: BURST
      colors:
       - MAGENTA
       - LIME
       - BROWN
      fadeColors:
       - BLUE
    2:
      type: STAR
      colors:
       - RED
```

You can also add two additional effects - flicker and trail by adding one or both of following lines:

```yaml
      flicker: true
      trail: true
```

Final result:

```yaml
item:
  material: FIREWORK
  amount: 32
  damage: 0
  fireworkPower: 4
  fireworkEffects:
    1:
      type: BURST
      colors:
       - MAGENTA
       - LIME
       - BROWN
      fadeColors:
       - BLUE
      flicker: true
    2:
      type: STAR
      colors:
       - RED
      flicker: true
      trail: true
```

## Firework stars

<p class="warn"><b>Note:</b> Remember to use valid material name corresponding to your Minecraft version (<i
>FIREWORK_STAR</i> or <i>FIREWORK_CHARGE</i>).</p>

Example (regular Firework Star):

```yaml
item:
  material: FIREWORK_STAR
  amount: 1
```

Example (Firework Star with color):

```yaml
item:
  material: FIREWORK_STAR
  amount: 1
  fireworkColor: RED
```

Example (Firework Star with color and fade color):

```yaml
item:
  material: FIREWORK_STAR
  amount: 1
  fireworkColor: RED
  fireworkFadeColor: PURPLE
```


## Goat horns

Example (Goat Horn Dream):

```yaml
item:
  material: GOAT_HORN
  quantity: 1
  musicInstrument: DREAM_GOAT_HORN
```

## Armor trims

Example (Lapis Wayfinder trim):
```yaml
item:
  material: LEATHER_CHESTPLATE
  quantity: 1
  armorTrim: 
    material: "LAPIS"
    pattern: "WAYFINDER"
```
