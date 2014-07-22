---
layout: post
title: "Convertible Note Basics"
date: 2014-07-22
author: robert
category: startup-math
publish: false
excerpt: "Convertible notes have become extremely popular in the early stage startup space, but their simplicity can be deceptive."
---

Convertible notes have become extremely popular in the early stage startup space, but their simplicity can be deceptive. The low interest rate debt note with reasonable discount might look fantastic from the company’s perspective until it raises a Series A and finds the note holders getting an epic discount thanks to a low valuation cap. Conversely, the note holder doesn’t want to take a huge amount of risk on an early stage company and then see no real upside when that company’s valuation sky rockets.

Both sides have plenty of skin in this game but the only way all parties will leave happy is if everyone understands what all the terms mean, and what impact they will have over the lifetime of the note and through it’s conversion.

<h2 style="text-align: left">Convertible Notes</h2>

At the most basic level a convertible note really only has a few components:

1. The Investment Amount
2. A Discount
3. A Valuation Cap

There are many more potential terms, some of which I’ll briefly touch on at the end, but these three make up the core of how convertible notes work.

The investment amount is the cash invested into the business; it gives the investor no equity in the business &ndash; they still own zero percent.

The note converts when the conversion trigger is hit. This trigger will be defined in your convertible note agreement. In practice, it is almost always at the company’s next “qualified financing” &ndash; basically a new round of investment above a certain amount.

The conversion is where things get interesting.

<h2 style="text-align: left">Conversion Discount</h2>
If the incoming investors of the new series are paying $5/share and the note holders have a 20% discount, then the note holders will convert at $5 * (1 - 0.2) which is $4 a share. This is a guaranteed discount against the share price paid by the new investors, the perk of investing earlier and at greater risk.

However, lets say the note investors came in with $500K thinking the company is worth about $10M and one year later the new series investors are valuing the company at $90M. At a flat 20% discount the note holders convert the value of their investment giving them $625K's worth of equity. $625K out of 100M is a marginal percentage of the company, the note holders see very little benefit from the massive gains in company value.

Perhaps counter to what you might expect, the higher the company valuation, the lower the percentage ownership for existing note holders. This is brilliant for the founders who see the big bucks with virtually no dilution, but annoying and arguably unfair for your early investors. That’s rarely a good thing in the bigger picture.


![Without Valuation Cap]({{ site.url }}/images/note-without-cap.png)
<span class="image-caption">Percentage ownership decreases as pre-money valuation increases</span>

<h2 style="text-align: left">Valuation Caps</h2>
A valuation cap effectively puts a floor on the minimum percentage of the company that the note holders will own after conversion. This minimum is calculated as:

![Valuation Cap Percentage]({{ site.url }}/images/valuationcappercent.png)

You'll note that this calculation does not involve the pre-money valuation. With a valuation cap in place the note holders get a minimum fixed percentage of the company irrespective of the pre-money valuation. Of course, given a low pre-money the investors can still take the flat discount if it amounts to a larger share of the company.

<h2 style="text-align: left">With and Without Cap Examples</h2>
If the $500K note had no valuation cap and the company sells 10% of the company at a  $90M valuation then the note holder would get 0.625% of the resulting equity, valuing their stake at $625K (i.e. exactly the same percent, no matter if the company had been valued at $50M or $10M).

If, however, the $500K note had a $10M valuation cap and the company sells 10% of the company at this $90M valuation, then the note holders would get 4.5% of the company, valuing their stake at $4.5M. This effectively means they get to purchase equity at a discount of 88.8% relative to the incoming shareholders.

A very big difference!

![WithValuation Cap]({{ site.url }}/images/note-with-cap.png)
<span class="image-caption">Note converts to fixed percentage (the grey line shows the conversion without a cap)</span>

<h2 style="text-align: left">Negotiating Terms</h2>
There are no rights or wrongs here. In the above scenario the note holders did enormously well, but so did the founders. The incoming investors might grumble however, though because the dilution almost always comes out of the pre-money rather than the post-money: the investors still get their 10% for exactly the same amount they would have without the debt ever existing.

You can experiment with [our convertible note calculator](https://sharewave.com/features/convertible-notes) to see how the effective discount and resulting equity vary as you change the various parameters. The key takeaway is that any valuation cap should be a measure of what all parties think is the likely value of the company.
It’s a balancing act between you, your investors and your lawyer. Whether you have a valuation cap, and at what value, is something you’ll have to work out with your potential investors.

<h2 style="text-align: left">Other terms to watch out for</h2>
<br>
<b>Increasing Discounts:</b> Some notes are structured such that the discount increases over time. For example, the discount might increase by 3% each month up to a cap of say 25%.

<b>Debt:</b> If your convertible note is structured as debt, there’ll likely be an interest rate and a term. In most cases this interest is not payable over the lifetime of the note, and only comes into play at the point of conversion or at the end of the note's term. This simply means that the note amount used in the above calculations is the principal plus all the accrued interest at the time of conversion.

<b>Pro rata rights:</b> Pro rata rights give the note holder the option to maintain their ownership percentage by investing in future financing. How these affect a company’s ability to raise money in future rounds is a matter of some debate, but some investors will [require this](http://gothamgal.com/2012/06/pro-rata-rights/) and there is potentially upside for all involved. You’ve got to make a decision based on more than just maths.

<b>Liquidation Preferences:</b> A subject for another post but suffice it to say it’s worth realizing that most convertible notes convert into the new series on the same terms as that new security. This means they will pick up any liquidation preferences from the new security. This can be distressing for the founders in a liquidation scenario. Read more about this in [Mark Suster’s great post](http://www.bothsidesofthetable.com/2012/09/05/the-truth-about-convertible-debt-at-startups-and-the-hidden-terms-you-didnt-understand/).