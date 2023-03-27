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

### 1.9+

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
You can get the find heads from sites such as [Minecraft-Heads](https://minecraft-heads.com//). 
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

<p class="warn"><b>Note:</b> The <i>compareMeta</i> option must be enabled for an item to use the NBT option!</p>

Adding NBT tags to items is as simple as adding `nbt` section and tags inside. Each tag (except `STRING_ARRAY` and `COMPOUND` types) must
contain `type`, `key` and `value`. String array tags require `type`, `key` and `values`. Compound tags require `type`, `key` and `children` instead. Compounds can be nested
recursively.

More info on the NBT format itself can be found [here](https://minecraft.gamepedia.com/NBT_format).

### NBT tag types

* BYTE
* SHORT
* INT
* LONG
* FLOAT
* DOUBLE
* BYTE_ARRAY
* STRING
* STRING_ARRAY
* COMPOUND
* INT_ARRAY

Example (single string tag):

```yaml
item:
  material: BREAD
  amount: 32
  damage: 0
  nbt:
    1:
      type: STRING
      key: Hello
      value: World
```

Example (compound with a string array to add name and lore using NBT):

```yaml
item:
  material: BREAD
  amount: 32
  damage: 0
  nbt:
    1:
      type: COMPOUND
      key: display
      children:
        1:
          type: STRING
          key: Name
          value: "{\"bold\":true,\"italic\":false,\"color\":\"white\",\"text\":\"Magic Bread\"}"
        2:
          type: STRING_ARRAY
          key: Lore
          values:
            - "{\"italic\":false,\"color\":\"gray\",\"extra\":[{\"color\":\"white\",\"text\":\"High Value\"}],\"text\":\"This item can be sold for \"}"
            - "{\"italic\":false,\"color\":\"gray\",\"text\":\"on the server shop\"}"
```

Example (two tags - string and compound containing two doubles):

```yaml
item:
  material: BREAD
  amount: 32
  damage: 0
  nbt:
    1:
      type: STRING
      key: Hello
      value: World
    2:
      type: COMPOUND
      key: TestCompound
      children:
        1:
          type: DOUBLE
          key: ExampleKey1
          value: 123
        2:
          type: DOUBLE
          key: ExampleKey2
          value: 456
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
