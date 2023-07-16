# Hidden Configuration Options

There are some hidden configuration options that can resolve some potential issues with our plugins on some setups, along with provide additional behavior to the plugin, that may be potentially dangerous.

## Number Formatting
We provide several options which allow you to change the way numbers are formatted in messages sent to players. These have been shown below:

### Decimal Separation
This setting can be used to change the character used for separating decimals in figures which may not be integers. This is useful for other languages, who may use different characters for decimal separation. (E.g: Spain uses the comma to separate decimals.)

This can be changed by inserting the following setting in the `config.yml`:
```yaml
numberFormat:
  # The default value for this is "."
  decimalSeparator: '.'
```

### Grouping Separation
This setting can be used to change the character used for separating groups of numbers for larger numbers. (E.g: 1,000,000) This is useful for other languages, who may use different characters for grouping separation. (E.g: Spain uses the decimal point to separate such groups.)

This can be changed by inserting the following setting in the `config.yml`:
```yaml
numberFormat:
  # The default value for this is ","
  groupingSeparator: ','
```

### Maximum Integer Digits
This setting allows you to specify the maximum number of digits shown for integer numbers. This can help display larger amounts of currency, in cases where the economy may be more inflated. 

TThis can be changed by inserting the following setting in the `config.yml`:
```yaml
numberFormat:
  # The default value for this is "32"
  maximumIntegerDigits: 32
```

### Minimum Integer Digits
This setting allows you to specify the minimum number of digits shown for integer numbers. This can help display smaller amounts of currency, in cases where the economy may be more deflationary.

This can be changed by inserting the following setting in the `config.yml`:
```yaml
numberFormat:
  # The default value for this is "1"
  minimumIntegerDigits: 1
```
### Maximum Fraction Digits
This setting allows you to specify the maximum number of decimal places shown for fractional numbers. This can help display currency amounts more precisely.

This can be changed by inserting the following setting in the `config.yml`:
```yaml
numberFormat:
  # The default value for this is "8"
  maximumFractionDigits: 8
```

### Minimum Fraction Digits
This setting allows you to specify the minimum number of decimal places shown for fractional numbers. This can help display currency amounts less accurately, should the need arise. 

This can be changed by inserting the following setting in the `config.yml`:
```yaml
numberFormat:
  # The default value for this is "1"
  minimumFractionDigits: 1
```

### Hide Fraction
This setting will allow you to specify whether you would like the ending decimal digits to be removed when not applicable. This will allow for messages to be displayed as $100, instead of $100.00.

This can be changed by inserting the following setting in the `config.yml`:
```yaml
numberFormat:
  # The default value for this is "true".
  hideFraction: true
```

### Short-Scale Number Formatting
We also provide several options which allow you to change the way numbers are displayed to users in messages sent to players. Using the [short-scale number system](https://en.wikipedia.org/wiki/Long_and_short_scales#:~:text=In%20the%20short%20scale%2C%20a,illion%20equals%20103n%2B3), you are able to shorten numbers such as `1,000,000` to `1 Million`, formatting numbers in an easier-to-read format for your players. The advantages of this become more evident when your economies reach larger numbers, such as in the Quintillions. Settings involving such features have been shown below:

#### Enable Short-Scale Formatting
By default, short-scale formatting is disabled within messages. You can enable it by inserting the following into your `config.yml`:
```yaml
numberFormat:
  shortScale:
    enableShortScaleNumbering: true
```

<p class="error"><b>WARNING:</b> If you are concerned about performance, enabling this setting will repeatedly perform division by powers of 10. This can get intensive on lower-end systems. Please take this into account if you are currently experiencing performance issues.</p>

#### Short Scale Limit
This setting will allow you to specify the numerical limit from where you would like short-scale formatting to apply within messages. In most cases, there is little need to convert smaller numbers to short-scale numbers, and as such, you can set the limit to higher numbers to only convert larger numbers to short-scale notation.

This can be done by inserting the following setting into your `config.yml`:
```yaml
numberFormat:
  shortScale:
    shortScaleLimit: 1000
```

#### Short Scale Decimal Limit
For numbers such as `1,123,456`, converting this to short-scale notation will form `1.123456 Million`. This can be quite long when working with larger numbers. As such, you can truncate the numbers using the following setting, truncating these numbers to a specified number of decimal places.

This can be done by inserting the following setting into your `config.yml`:
```yaml
numberFormat:
  shortScale:
    shortHandDecimalLimit: 6
```

#### Short Scale Number Limit
For numbers that get extremely large (this would be beyond the Decillions), you can truncate the figure to a specified amount of digits, ensuring the number does not get exceedingly large.

It is also worth noting that it is very rare that this setting will actually apply. There are few to no servers that scale their economies to the decillions. 

This can be done by inserting the following setting into your `config.yml`:
```yaml
numberFormat:
  shortScale:
    shortHandNumberLimit: 32
```

#### Short Scale Notation
You may wish to choose to display the format of short-scale numbers alternatively. If this is the case, you can make use of the following settings in your `lang.yml`:
```yaml
MSG:
  NUMBERFORMAT:
    SHORTSCALE:
      THOUSAND: ' Thousand'
      MILLION: ' Million'
      BILLION: ' Billion'
      TRILLION: ' Trillion'
      QUADRILLION: ' Quadrillion'
      QUINTILLION: ' Quintillion'
      SEXTILLION: ' Sextillion'
      SEPTILLION: ' Septillion'
      OCTILLION: ' Octillion'
      NONILLION: ' Nonillion'
      DECILLION: ' Decillion'
```

With the above configuration, `1,000,000` would be displayed as `1 Million`.