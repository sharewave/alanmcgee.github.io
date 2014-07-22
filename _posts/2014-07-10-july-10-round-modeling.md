---
layout: post
title: "Round Modeling"
date: 2014-07-10
author: robert
category: startup-math
excerpt: "This week we released a round modeling tool so you can see the effect that taking on a new round of funding will have on your existing shareholders. To make it as usable as possible our interface hides many of the low level calculations &ndash; we're trying to make it easy for you &ndash; but we thought we'd explain the mathematics behind the scenes in case you wanted to run the calculation yourself."
---

We've recently implemented several modeling tools on Sharewave. The Convertible Note Calculator has been [available for some time](https://sharewave.com/features/convertible-notes) (though we've recently enhanced it for our users with interest calculations built in). This week we released a round modeling tool so you can see the effect that taking on a new round of funding will have on your existing shareholders. To make it as usable as possible our interface hides many of the low level calculations &ndash; we're trying to make it easy for you &ndash; but we thought we'd explain the mathematics behind the scenes in case you wanted to run the calculation yourself.

We take only three inputs (plus your existing cap table!). The pre-money valuation of the company, the incoming investment and an optional post-money option pool. From these we can calculate everyone’s dilution and percentage ownership once the money comes in.

The model works in two stages:

1. We work out the effective pre-money (Eff-Pre) valuation of the company. This is most likely lower than the top line pre-money valuation given to you in your term sheet. Here we must broach the Option Pool Shuffle (there's no better explanation of this [than Venture Hack's](http://venturehacks.com/articles/option-pool-shuffle)) and the impact of any convertible note instruments.
1. We use this Eff-Pre to calculate how many shares are bought, created and converted.

Note that whilst new options and notes are treated as part of the investment round, they are almost always (as we do here) factored in pre-money so they dilute existing shareholders not the incoming investors.

<div class="example-block">
    <p>Throughout I’ll lay out the raw algebra but also follow through with an example, nestled in these blue boxes.</p>
    <p>We’ll use a company with just three securities:</p>

    <ul>
        <li><span>Common</span> An Equity Series with 90,000 shares issued</li>
        <li><span>Options</span> An options series with 10,000 authorized but only 5,000 issued</li>
        <li><span>Debt A</span> A Debt series with $100,000 invested at a 20% discount.</li>
    </ul>

    <p>This company is doing a Series A of $1,000,000 at a pre-money valuation of $4,000,000. The incoming investors are requesting a 10% post-money option pool.</p>
    <img src="{{ site.url }}/images/initial-round.png">
</div>

<h2 style="text-align: left">Note Impact</h2>

The value of the notes is fairly straightforward to calculate:

If there is no valuation cap, use the note's flat discount. Otherwise, the discount on the note is the larger of:

![Effective Discount]({{ site.url }}/images/effective-discount.png)

This gives the note the following value:

![Adjusted Note Amount]({{ site.url }}/images/adjusted-note-amount.png)

This value is taken away from the Eff-Pre, and has to be repeated for each note (though if they're all on the same terms you can calculate them all at once).

<div class="example-block">
    <p>We have one $100,000 note at a 20% discount. There’s no valuation cap so we take that discount as is and divide 100,000 by 0.8 giving us a reduction in pre-money valuation of $125,000.</p>
</div>
<h2 style="text-align: left">Post-money Option Pool Impact</h2>

Next we have to handle the option pool shuffle. The incoming investors want a post-money option pool of a specific percent (PostOPP). You already have an existing option pool, some of which is still unissued. This means you can roll your existing unissued options into the new pool.

First we calculate what percentage option pool size we need to have pre-money (PreOPP) to get the correct PostOPP:

![PreOPP]({{ site.url }}/images/PreOPP1.png)

Then factor in the existing unissued options, to reveal the percentage of options we have to create:

![Created Options]({{ site.url }}/images/created-options.png)

Which then lowers the Eff-Pre:

![Eff-pre reduced by]({{ site.url }}/images/Eff-pre.png)

You can simplify this hugely if you have no existing unissued options, but that’s not often the case in practice.

<div class="example-block">
    <p>We already have 5% unissued options so we only have to boost this up to 10%. Using the first equation, it’s 10% after dilution so pre-money we have to increase it to 12.5% (our PreOPP). The increase to this amount lowers the Eff-Pre by $322,368.421.</p>
</div>

<h2 style="text-align: left">Calculating Price-per-Share</h2>

We now have our Eff-Pre which also gives us a share price for our incoming investors (and note holders):

![Price per share]({{ site.url }}/images/PPS.png)

<div class="example-block">
    <p>The Eff-pre is then $4,000,000 - ($125,000 + $322,368.421) which comes out at $3,552,631.578 giving us a Price per share of $35.526</p>
</div>

<h2 style="text-align: left">Calculating Ownership Percentage</h2>

With our final price per share calculated we now have everything we need to calculate the new ownership.

<h2 style="text-align: left">Note Conversion</h2>
First the notes convert. We use the same effective discount calculated above for each note (the larger of the discount vs valuation cap discount)

![Note Discount Share Price]({{ site.url }}/images/note-discount.png)

![Note Units]({{ site.url }}/images/note-units.png)

<div class="example-block">
    <p>The $100,000 note converts to 3,518.518 shares at a discounted price of $28.421.</p>
    <img src="{{ site.url }}/images/note-round.png">
</div>

<h2 style="text-align: left">Option Pool Increase</h2>

Creating the new option pool shares is essentially the same mathematics as the option pool impact above, only using shares rather than percentages.

![PreOPP2]({{ site.url }}/images/PreOPP2.png)

![Options Created]({{ site.url }}/images/Options-created.png)

<div class="example-block">
    <p>The options created bring the unissued options up from 5,000 to 14,074.074</p>
    <img src="{{ site.url }}/images/option-round.png">
</div>

<h2 style="text-align: left">New Series Shares</h2>

Finally we generate the number of shares that the investor gets for their money:

![New Series Percent]({{ site.url }}/images/new-series-percent.png)

![New Series Shares]({{ site.url }}/images/new-series-shares.png)

<div class="example-block">
    <p>The New Series holders get 28,148.148 shares for their $1,000,000 investment and 20% of the company.</p>
    <img src="{{ site.url }}/images/final-round.png">
</div>

<h2 style="text-align: left">Conclusion</h2>

You can check that all the above worked by multiplying the New Series Shares by our earlier calculated Price Per Share. If that sum doesn't equal the Investment Amount&hellip; something's gone wrong!

If you've got this far &ndash; bravo! It's confusing, not well understood mathematics, but it is of course massively important. I hope at this stage I've given you enough such that you could do it all yourself. Alternatively, [sign up for Sharewave](https://sharewave.com) and we'll do it all for you!