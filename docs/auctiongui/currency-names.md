# Changing currency names

Every economy has a default prefix and suffix for its currency. These can be always overwritten in `config.yml`. The
used keys are the same as used in `economyTypes` section.

You can set only prefix or suffix, it's not mandatory to set both.

If you want to disable the default prefix/suffix set the value to an empty string.

Examples:

```yaml
currencies:
  prefixes:
    VAULT: ""
    TOKEN_ENCHANT: "Tokens: "
  suffixes:
    VAULT: " USD"
    TOKEN_ENCHANT: ""
```

```yaml
currencies:
  suffixes:
    PLAYER_POINTS: " puntos"
```