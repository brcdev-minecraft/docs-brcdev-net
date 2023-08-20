# FAQ

## Changing Command Alias
You are not able to completely change the name of the command, but you can implement an alias, allowing you to use another command as if it was the /pshop command.

You are able to do this by adding the following to Spigot's built-in commands.yml:
```yaml
aliases:
  market:
  - pshop $1-
```

This file can be found in the root directory of your server. The above extract will allow players to make use of the /market command as if it was the /pshop command, while accounting for any arguments that may be passed through. 