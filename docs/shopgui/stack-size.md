# Controlling the stack size
There are several options which allow you to alter the purchased item's stack size.

## unstack 
When an item with this option is purchased, it's going to be unstacked to 1 item per stack. This allows you to sell unstacked blocks, armor etc.

With `unstack: true`:

![](https://i.imgur.com/lPuSy07.png)

With `unstack: false` or none set:

![](https://i.imgur.com/C4bM24E.png)

Example:
```yaml
    4:
      type: item
      item:
        material: DIAMOND_HELMET
        quantity: 1
      unstack: true
      buyPrice: 800
      sellPrice: 160
      slot: 13
```

## stacked 
When an item with this option is purchased, it's going to preserve the amount from the shop or the selection GUI. This allows you to sell stacked items which don't stack by default, such as potions.

With `stacked: true`:

![](https://i.imgur.com/Ej1bneT.png)

With ``stacked: false`` or none set:

![](https://i.imgur.com/J7RBH27.png)


Example:
```yaml
    1:
      type: item
      item:
        material: SPLASH_POTION
        quantity: 3
        potion:
          type: SPEED
          level: 1
          extended: true
      stacked: true
      buyPrice: 40
      sellPrice: 8
      slot: 10
```
