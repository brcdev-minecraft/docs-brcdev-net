# Hidden Configuration Options

There are some hidden configuration options that can resolve some potential issues with Christmas+ on some setups, along with provide additional behavior to the plugin, that may be potentially dangerous.

## Click Cooldown
Using the `clickCooldown` option can change the time allowed between clicks in the GUI in milliseconds.

 **WARNING:** This setting is dangerous. This is used to prevent duplication bugs, and is set to 250ms to prevent this. Removing this cooldown can harm changes of duplication. 

 To make use of this option, insert the following anywhere in the [`config.yml`](https://pastebin.com/sYUf6mNk):
 ```yaml
 gui:
   # The default value for this is "250".
   clickCooldown: 250
```
Any decimal number can be inserted into this value, as long as it lies within the bounds of $-2^{63}$ and $2^{63}-1$

## Snow Display Interval
Using the `displayTaskInterval` option can change the time allowed between snow particles spawning for Santa in ticks. Removing this cooldown can harm performance.

**WARNING:** This setting is dangerous. This is used to influence the amount of particles spawning within your server for Santa. Removing this cooldown can negatively affect performance.

To make use of this option, insert the following anywhere in the [`config.yml`](https://pastebin.com/sYUf6mNk):
```yaml
snow:
  # The default value for this is "2".
  displayTaskInterval: 2
```
Any integer can be inserted into this value, as long as it lies within the bounds of $-2^{63}$ and $2^{63}-1$