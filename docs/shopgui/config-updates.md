# Config updates

Some of new releases come with new configuration options, that must be added manually.

## 1.113.0
### Buy Full Inventory
```yaml
amountSelectionGUI:
  (...)
  buttons:
    (...)
    # "Buy Full Inventory" button
    buyFullInventory:
      item:
        material: CHEST
        quantity: 1
        name: "&a&lBuy Full Inventory"
        lore:
          - "&7Purchase %stacks% stacks"
          - "&7for %price%"
      states:
        inventoryFull:
          material: CHEST
          quantity: 1
          name: "&a&lBuy Full Inventory"
          lore:
            - "&cYour inventory is already full."
      slot: 40
```
