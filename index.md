---
layout: default
title: Donchian Quest Research
description: Trend following in crypto.
---

# What is trend following?

Trend following is an investment strategy that aims to capitalize on the directional movement, or trends, in financial markets. Followers of this strategy believe that assets tend to move in persistent directions over time. 

> Trend followers typically buy or sell assets based on the direction of the prevailing trend, attempting to ride the trend for as long as possible to maximize profits. 

Trend following is characterized by its systematic and disciplined approach, with practitioners aiming to minimize losses during periods of market volatility while capturing gains during trend movements.

This approach involves using technical analysis tools to identify and confirm trends: moving averages, different types of price channels, Bollinger bands, Supertrend and so on. 

Different researches say that they all give approximately the same results if you choose approximately the same settings.

Therefore, any of these tools can be used.


# Black Box Trend Following

Idea of this strategy was proposed in article "Black Box Trend Following - Lifting the Veil". Authors: Nigol Koulajian and Paul Czkwianianc. The authors of this paper are principals of Quest Partners LLC, trading company manages $2.3 billion in assets.

I coded this as a script in Tradingview:

[Tradingview](https://www.tradingview.com/script/YPQwKNF8-Donchian-Quest-Research/).

* * *

![Script on Tradingview](/images/BTCUSD.png)

* * *

# How to use it

You can use it for your trading as you wish - on any exchange, spot or perpetual futures. My referral link for Hyperliquid exchange:

[app.hyperliquid.xyz/join/SERGEYEN](app.hyperliquid.xyz/join/SERGEYEN).

You can invest your money in my Hyperliquid vault - if you clearly understand theory of trend following in next chapters:

[Vault Donchian Quest Research](https://app.hyperliquid.xyz/vaults/0x54094fd5077de413017b5e83da0b587043b55144).

# Script description

Strategy uses two channels. One channel - for opening trades. Second channel - for closing. Channel is similar to Donchian channel, but uses Close prices (not High/Low). 
* * *
Strategy waits for beginning of trend - when price breakout of channel. Default length of both channels = 50 candles.

Conditions of trading:

* Open Long: If last Close = max Close for 50 closes.
* Close Long: If last Close = min Close for 50 closes.
* Open Short: If last Close = min Close for 50 closes.
* Close Short: If last Close = max Close for 50 closes.
* * *

Color of lines:

- black - channel for opening trade.
- red - channel for closing trade.
- yellow - entry price.
- fuchsia - stoploss and breakeven.
- vertical green - go Long.
- vertical red - go Short.
- vertical gray - close in end, don't trade anymore.


* * *

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)
![Branching](/images/BTCUSD.png)



### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
